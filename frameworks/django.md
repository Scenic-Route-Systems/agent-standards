# Django Guidelines

- When you need to create a reusable utility method, create it in helpers.py, rather than pollute the views with additional methods. Views having their own helper methods are acceptable only when it's highly specific to the view concept in general, like repeated context creation.
- When reviewing code, NEVER complain about a `UUIDField(default=uuid.uuid4)` computing the default UUID only once during a migration. We understand that issue and always mass randomize the records post-migration. Stop pointing it out.
- In templates, treat Django block tags (`{% if %}`, `{% for %}`, `{% block %}`, `{% partialdef %}`, `{% with %}`, etc.) as nesting levels, like HTML elements: indent their contents one level (2 spaces) and align the closing tag with the opening tag.
- NEVER run `makemigrations` or `migrate`. NEVER create migrations manually either -- solely focus on updating the models. I will handle all model migrations.
- NEVER run the Django application (`runserver`, gunicorn) or the test suite. I will handle all running and testing.