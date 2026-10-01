# I Think Therefore I Blog

[Português (Brasil)](README.pt-BR.md) | **English**

A Django blog learning project based on the Code Institute student template. The reviewed source includes published-post lists, post details, approved comments and likes.

**Documentation reviewed:** 2026-10-01. The hostname in settings, https://iurjoh-blog.herokuapp.com/, returned HTTP 404 with Heroku's "No such app" page on this date. No active deployment there was confirmed.

## Idea and development record

The code organizes a blog through Django models, views and HTML templates. The previous README was the generic Gitpod template, not a project planning record. Original user research, design choices and successful test history are not invented here; git history records implementation changes.

## Architecture

```text
Browser -> blog URLs -> Django views -> models/database
                                   -> HTML templates
                                   -> comments and likes
```

`PostList` selects published posts in newest-first order, with six items per page. `PostDetail` shows approved comments and processes the comment form. `PostLike` toggles a user relation. The project configuration is in `codestar/`; settings use `DATABASE_URL` and an environment-provided `SECRET_KEY`.

`requirements.txt` records Django 3.2.16, Allauth 0.52, Cloudinary, Crispy Forms, Social Share, Summernote, Gunicorn and psycopg2. Versions are historical, not a fresh production recommendation.

## Local setup

Use an isolated environment and fictional data:

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

Configure a local `SECRET_KEY` and `DATABASE_URL` according to `codestar/settings.py`; the SQLite example is commented out. Do not use a production database or commit secrets.

```bash
python3 manage.py migrate
python3 manage.py runserver
```

These steps were not run in this update. Review dependency compatibility before reuse.

## Design, testing and security

Source review covered settings, views, routes, dependencies and the previous README. No tests, migrations or rendered app review were performed. `DEBUG` is enabled in the current source, and the comment/like views reviewed do not contain explicit login guards. Check server-side access rules, form validation, CSRF behavior, approved-comment filtering and dependencies before public reuse. A database file is versioned in the repository; review its contents privately before sharing or republishing, without assuming it contains only fictional data.

No fresh snapshot is embedded. Future dated screenshots with fictional content belong in `docs/assets/`.

## Credits and license

Code Institute template and course work, plus third-party dependencies. No root `LICENSE` was found in the review. Preserve their terms; this update does not apply MIT to third-party code or use template release notes as the author's project history.
