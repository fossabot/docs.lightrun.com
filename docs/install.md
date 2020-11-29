---
id: installation
title: Installation
---
Installation
==============================

Lightrun comprises these main components:

- Management Server
- Agent
- Client - CLI and Plugin

Once the backend is installed we can create a user account. We can then
login with this new account and follow the instructions to install the
agent, plugin and CLI.

::: {.tip}
The backend defaults to port 8080 and requires HTTPS so the URL should
look like <https://192.168.1.108:8080/>
:::

::: {.important}
We will receive an HTTPS warning in the browser and will need to add an
exception for this URL. SSL certificates can be applied to domains only
and will produce a warning for in-house servers!
:::

Management Server Deployment - Docker Compose
---------------------------------------------

Lightrun's management server works best in a container environment.
Running Lightrun is as easy as running a single command from the
terminal. We can run the backend server on any host using docker-compose
or other container orchestration tool such as Kubernetes, Docker Swarm
or Rancher etc.

The easiest way to deploy the server is to run the docker-compose file.
Copy the two `yml` files provided into an empty directory and execute:

``` {.bash}
cd {docker-compose-directory}
docker-compose up -d
```

In case port 8080 is already taken, we can change the port number in the
docker-compose file.

Agent Deployment
----------------

The agent can be downloaded from the backend server page once we login
to the backend.

In order to use the agent in an app, download and extract the zip in the
apps server.

::: {.important}
The following code is available in the backend welcome page and should
be copied from there as the `server-ip` and port value will be set
correctly
:::

``` {.bash}
wget --no-check-certificate https://server-ip:8080/content/files/agent.zip&host=server-ip&port=8080 -O agent.zip
mkdir agent
unzip agent.zip -d agent
```

::: {.tip}
Check out the content of the file `agent/agent.config`. It includes many
setting options including the backend server URL
:::

### Attaching the Agent

Now we add the agent to the java application by changing the command
line as such:

``` {.bash}
java -agentpath:/path/to/agent/lightrun_agent.so RestOfTheArgumentsHere
```

Alternatively we can add the `JAVA_OPTS` environment variable to the
server so all java processes launched in the server would have an agent
attached as such:

``` {.bash}
export JAVA_OPTS=-agentpath:/path/to/agent/lightrun_agent.so
```

Once an agent is running we can move to the IntelliJ plugin
installation.
The compiler may miss some debugging information in order to reduce the binary size. For that reason, not all variables are visible for exploration.

We strongly **recommend** that you enhance this information. To do this, add the`-g` flag to the compilation command.

If the project uses Maven, add the following lines to the `pom.xml` file:

``` {.xml}
<compilerArgs>
    <arg>-g:source,lines</arg>
</compilerArgs>
```

This flag has no impact on compiler optimization, but only enhances the bytecode with additional debug information. As such, the performance of the app is not effected.

Plugin Installation
-------------------

To install the plugin download the plugin zip from the Lightrun backend.

::: {.important}
Don't unzip the file!
:::

Open IntelliJ's preferences:

![IntelliJ Preferences Menu on Mac OS](img/intellij-preferences-mac.png)

Select the plugins section in the preferences menu:

![The plugins section](img/plugins-section.png)

Click the settings button on the right most point and select *Install
Plugin from Disk*:

![Install Plugin from Disk](img/install-plugin.png)

Then select the zip file for the plugin from the download folder.
