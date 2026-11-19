# Tailwind + daisyUI Guidelines

- Before building a component from scratch with CSS, first see if something already exists within daisyUI. Avoid custom components when possible, especially for one-off needs.
- Use Tailwind utility classes and DaisyUI components directly in templates. Do NOT create custom class names or custom components.
- Element defaults (e.g. heading sizes) belong in `@layer base` in `tailwind/source.css`, using `@apply` with existing utilities.
- After changing classes in templates, rebuild the CSS with `python manage.py tailwind build` and commit `static/css/tailwind.css`.