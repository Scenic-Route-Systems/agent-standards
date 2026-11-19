# htmx + Alpine.js Guidelines

- Avoid custom `<script>` blocks and raw JS unless htmx and Alpine.js cannot do it.
- For client-only UI state (dropdowns, modals, tabs, toggles), use Alpine.js attributes in the template.