---
id: introduction
title: Lightrun Documentation Overview

---

Lightrun bridges the gap between development and production debugging by shifting debugging left in the process and by helping you witness real-time problems in real-time and real environments. 

Already from the development environment and through to and including the production environment you can inspect your code in *real* real-time - while the application is actually running, to catch bugs without having to sift for needles in a haystack. 

Identify the root cause of any real-time problem (logical bug,
performance issue, downtime, etc.) by installing the Lightrun agent on your servers and then configuring the client from your local environment to help you quickly:

- Reproduce the problem in a development or test environment
- Review the right runtime logs 
- View and analyze actual performance metrics

Lightrun architecture
--------

Lightrun is divided into these three parts:

- **Java Agent** - the JVMTI agent that runs alongside the application
  to dynamically insert commands.

- **Backend Server** -  the Lightrun server responsible for service
  management.

- **Client** - the IDE plugin and command line utility; you can use either to add, remove and modify actions

![Lightrun architecture](assets/diagram.png)

Limitations
----------

The compiler may miss some debugging information in order to reduce the binary size. For that reason, not all variables are visible for exploration.

We strongly **recommend** that you enhance this information. To do this, add the`-g` flag to the compilation command.

If the project uses Maven, add the following lines to the `pom.xml` file:

``` {.xml}
<compilerArgs>
    <arg>-g:source,lines</arg>
</compilerArgs>
```

This flag has no impact on compiler optimization, but only enhances the bytecode with additional debug information. As such, the performance of the app is not effected.
