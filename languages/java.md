# Java Guidelines

- Always leverage the latest features of the Java version tied to the project, instead of being concerned with backward compatibility with older versions of the JDK and previous language levels.
- One exception: NEVER use the `var` keyword, despite it being a modern feature. Always define variables with a type.
- Utilize declarative programming whenever possible, not imperative. Ex: fluent style, method chaining, lambdas, Streams, etc.