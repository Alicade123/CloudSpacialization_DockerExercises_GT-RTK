# Flask

The `gunicorn.py` file contains a few config settings. `accesslog = '-'` ensures
that things get logged to STDOUT.

View all of [gunicorn's documentation](https://gunicorn.org/).

If you're a seasoned Flask developer and you prefer uWSGI instead of gunicorn,
by all means use that instead. You know what to change!
