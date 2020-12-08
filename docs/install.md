---
id: installation
title: Installation
---
When you're ready to get rolling, Lightrun sets up the backend server for you and issues an admin account. Thereafter, you can: 
- [Spin the server up and down](installation#spin-the-server-up-and-down)
- [Log in to Lightrun](installation#log-in-to-lightrun)
- [Deploy the application server-side agent](installation#deploy-the-application-server-side-agent)

## Spin the server up and down

You can run the backend server on any host using a docker-compose or other container orchestration tool such as Kubernetes, Docker Swarm or Rancher.  

1. By default, the backend is configured to run over port 8080. If this port is unavailable, change the port number from the docker-compose file.
2. Copy the two `yml` files that Lightrun provided at installation into an empty directory and execute the following:

``` {.bash}
cd {docker-compose-directory}
docker-compose up -d
```

## Log in to Lightrun

1. The backend installed by Lightrun defaults to port 8080 and requires HTTPS. Log in to your Lightrun instance with your admin credentials at <https://192.168.1.108:8080/>. 
   
   **Note:** Be sure to change the port number if you changed the configuration from your docker-compose file. 
   
   **Note:** SSL certificates can be applied to domains only. Therefore, the page loads with an HTTPS warning. 
2. Add an exception for this URL in order to bypass the certificate warning that loads. 
   The landing page loads with *customized* installation instructions for the agent, plugin and CLI.

## Deploy the agent

Once you've logged in to the backend server, the agent can be downloaded and deployed on your application servers.

Copy the following code *from the welcome page* which loads with the customized `server IP` and `port` values when you log in. 

``` {.bash}
wget --no-check-certificate https://server-ip:8080/content/files/agent.zip&host=server-ip&port=8080 -O agent.zip
mkdir agent
unzip agent.zip -d agent
```

**Tip:** Check out the content of the file `agent/agent.config`. It includes many options, including the backend server URL.

## Attach the Agent

Once you've deployed the agent to your application servers, you should add it to your application as follows: 

**Note:** Lightrun currently supports Java applications.

1. From the application server, navigate to the folder where your application resides. 
2. Copy the following code:
``` {.bash}
java -agentpath:/path/to/agent/lightrun_agent.so RestOfTheArgumentsHere
```
3. Replace the `agentpath` value with the path to the Lightrun agent where you downloaded it and replace `RestOfTheArgumentsHere` with the name of your application and then run the command. 

   OR

   Add the `JAVA_OPTS` environment variable to the server so that all Java processes launched on that server have an agent attached. Copy the following command from the server and replace the `agentpath` value with the path to the Lightrun agent where you downloaded it:

``` {.bash}
export JAVA_OPTS=-agentpath:/path/to/agent/lightrun_agent.so
```

Once an agent is up and running, you and your team can install the IntelliJ plugin.