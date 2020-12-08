---
id: install-client
title: Install the plugin
---

In order to use the plugin from your local environment, *ensure the admin for your Lightrun account has deployed the Lightrun agent* from the relevant application servers.

**Note:** Lightrun currently supports a plugin for IntelliJ, and is working on more. 

## Install the plugin

1. To install the plugin, log in to your Lightrun account from your local environment. 
    The Lightrun installation page loads. 
    
2. Scroll down to the Install the Plugin section. 

3. Click **Download plugin** and store the file in a memorable location.

4. Navigate to your IntelliJ instance. 

5. Open the IntelliJ preferences:
    ![IntelliJ Preferences Menu on Mac OS](../../img/intellij-preferences-mac.png)

6. Select the plugins section:
    ![The plugins section](../../img/plugins-section.png)

7. Click the settings cog from the top right and select *Install
    Plugin from Disk*:
    ![Install Plugin from Disk](../../img/install-plugin.png)

8. Select the zip file for the plugin from the folder where you stored it when you downloaded.

## Maximize debugging information

Maven and Gradle compile Java class files without specific instructions but  exclude certain debugging details in order to reduce the binary size. 

To ensure these details are included, add a flag to the compiler. This flag has no impact on compiler optimization or  performance, only enhancing the bytecode with additional debug information. 

### Maven

For Maven, add the following lines to the `pom.xml` file: 
``` {.xml}
<compilerArgs>
    <arg>-g:source,lines</arg>
</compilerArgs>
```

### Gradle

In the Gradle build file, ensure that the following properties are specified:
```
compileJava.options.debugOptions.debugLevel = "source,lines,vars"
compileTestJava.options.debugOptions.debugLevel = "source,lines,vars"
```
