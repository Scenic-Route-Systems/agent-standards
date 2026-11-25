# django-tailwind-cli Guidelines

- You MAY run `python manage.py tailwind build` (or `tailwind watch`, or the SCSS equivalent) to compile and verify CSS. It only writes `static/css/*.css`.
- After changing classes in templates, rebuild the CSS with `python manage.py tailwind build` and commit `static/css/tailwind.css`.