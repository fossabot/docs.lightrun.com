---
id: introduction
title: Overview

---

Lightrun helps you and your team debug already from the development stages by helping you witness real-time problems in real-time and in real environments, already from the development environment and also from the production environment. 

Use Lightrun to: 
- Reproduce the problem in a development or test environment
- Review the right runtime logs 
- View and analyze actual performance metrics

To get up and running: 
- [Install](install.md) the agent on the relevant servers
- [Configure](install.md) your local environments

Lightrun architecture
--------

Lightrun comprises these parts:

- **Backend Server** -  the Lightrun server responsible for service
  management.

- **Java Agent** - the JVMTI agent that runs alongside the application on your servers,
    to dynamically insert commands.

- **Client** - the IDE plugin and command line utility; you can use either of them to add, remove and modify actions - whichever is part of your natural workflow

![Lightrun architecture](assets/diagram.png)