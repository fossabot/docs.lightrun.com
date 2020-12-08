---
id: server-setup
title: Start debugging with your team
---
Once you've deployed the agent on your application servers, it's time to kickstart debugging for your team. Have team members [install the plugin for IntelliJ or the CLI](#install-client), and follow these steps:
- [launch the backend](server-setup#launch-the-backend)
- [launch an agent](server-setup#launch-an-agent)
- [start debugging](server-setup#start-debugging)
## Launch the backend
From the relevant application servers run the following command:
`service lightrund start`
Alternatively, you can run the backend from a Docker file as follows:
`docker-compose up -d`.
## Launch an agent
Run an application instance with the agent attached. 
1. Copy the following command and replace `<install_dir>` with the installation directory. 
`java -agentpath:<install_dir>/agent/lightrun_agent.so java-app`\
2. Run the command. 
## Start debugging
So long as the application is running with the agent, you and your team can debug!
Use the [plugin](install-client.md) or [CLI](cli) to [add actions and debug](exceptions.md) the app. 