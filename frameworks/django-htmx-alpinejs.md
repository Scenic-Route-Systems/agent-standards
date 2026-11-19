# htmx + Alpine.js Guidelines

- For anything that talks to the server, ALWAYS use htmx, with views returning rendered HTML (prefer Django template partials, e.g. `inquiry_list.html#status_cell`), NOT JSON plus hand-written DOM updates.  