## Diagnosis
The `postgres_health_check_failed` is caused by incorrect SQLAlchemy syntax where the current code fights with the SQLAlchemy standards because the SQL text `'SELECT 1'` is not wrapped with `sqlalchemy.text()`

## Scope
### Proposed Changes (In-Scope)
1. `api/routes/health.py` - The text `SELECT 1` will be wrapped with `sqlalchemy.text()`

### Out of Scope
* The redis_health_check_failed error. This issue is described in [issue #62](https://github.com/codepath/pathreview-ai301-fa26-s1/issues/62)

## Testing Instructions
*Steps largely copied from repro evidence*
1. Clone the copied repo in SSH with `git clone`.
    * `git clone git@github.com:RadEagle/pathreview-ai301-fa26-s1.git`
2. Open a terminal shell to your cloned repo
3. Checkout the fix branch with `git checkout fix/61-wrap-sql-in-sqlalchemy-text`
4. Follow the rest of the setup instructions as dictated by the README file
    ```bash
    # Configure environment (add your OPENROUTER_API_KEY to .env)
    cp .env.example .env
    
    # Start backing services — must be running before make setup
    docker compose up -d
    
    # Run first-time setup (installs deps, runs migrations, seeds DB, installs frontend)
    make setup
    
    # Start the application
    make run
    ```
5. In another terminal shell, call `GET /health` using a `curl` command. (Note that `localhost` is the same as `0.0.0.0` in this environment)
    * `curl http://localhost:8000/health`
6. See that there is no `postgres_health_check_failed` error, and that the JSON shows `"postgres": "healthy"`

## Risks
Fixing this issue alone will still get the call to `GET /health` to still return status code `503`, not `200`, because the redis error is unaccounted for. This is expected, since that issue is described in [issue #62](https://github.com/codepath/pathreview-ai301-fa26-s1/issues/62)

## Deviations
The changes actually required two lines, not one. One to import the `text()` function from `sqlalchemy` and another to wrap the SQL statement. Still, only `api/routes/health.py` was changed.
