# Tailwind Guidelines

- When making CSS updates, ALWAYS update Tailwind source files only, NEVER the raw/generated CSS files.
- Element defaults (e.g. heading sizes) belong in `@layer base` in `tailwind/source.css`, using `@apply` with existing utilities.