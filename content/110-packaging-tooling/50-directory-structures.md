+++
+++

{{% section %}}
{{< slide id="dirStruct" >}}
## Directory Structures

---
#### Introduction
- Project structure plays a crucial role in software development.
- The standard Go project layout provides guidelines for organizing code, dependencies, and resources.
- Benefits: consistency, maintainability, and collaboration.

---
#### Overview of Standard Go Project Layout
- `/cmd:` Main applications for the project.
- `/internal:` Private application and library code.
- `/pkg:` Library code for external use.
- `/api:` OpenAPI/Swagger specs and protocol definition files.
- `/web:` Web application-specific components.
- `/configs:` Configuration file templates.
- `/init:` System init and process manager/supervisor configs.

{{% note %}}
**Core Components: /cmd**
- Contains main applications.
- Directory name should match the executable name.
- Keep the code minimal, import and invoke code from /internal and /pkg.


**Core Components: /internal**
- Private application and library code.
- Not intended for external use.
- Enforced by the Go compiler.
- Can have multiple internal directories at any level.


**Core Components: /pkg**
- Library code for external use.
- Other projects will import and use these libraries.
- Be cautious about what you put here.
- Consider using the internal directory for private packages.

**Core Components: /api**
- OpenAPI/Swagger specs and protocol definition files.
- Provides API documentation and schema.


**Core Components: /web**
- Web application-specific components.
- Includes static web assets, server-side templates, and SPAs.
{{% /note %}}


---
#### Overview of Standard Go Project Layout (continued)
- `/scripts:` Build, install, and analysis scripts.
- `/build:` Packaging and Continuous Integration.
- `/deployments:` Deployment configurations and templates.
- `/test:` Additional test apps and test data.

---
#### Overview of Standard Go Project Layout (continued)
- `/docs:` Design and user documents.
- `/tools:` Supporting tools for the project.
- `/examples:` Examples for applications and libraries.
- `/vendor:` Application dependencies that are copied into the project

[Back to Home](..)
{{% /section %}}
