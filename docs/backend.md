---
id: server
title: Setting up the Lightrun Backend
---

Management Server {#_management_server}
=================
::: {.tip}
Server's logs can be found under `/tmp/lightrun-backend-server.log`.
Server Sign-up {#_server_sign_up}
--------------

Now that the backend server is running we need to create a user and
login. We need to navigate in the browser to the server.

::: {.note}
Notice that the URL is `https` and defaults to port `8080`. There should
be a self signed certificate warning from the browser! If you are having
issues accessing the server from your browser due to a certificate
blocking please follow the guidelines in the
`Troubleshooting certificates issues` section
:::

![Initial Web Page](../../img/backend-first-ui.png)

Under the account menu we can select register and create a new user
account.

![Register Menu](../../img/backend-logged-out-account-menu.png)

We can use any details as a verification email isn't sent at this time,
however values should be unique.

![Registration](../../img/backend-registration.png)

Once registered we can login immediately and should see this UI:

![Backend Post Login](../../img/backend-logged-in.png)

Notice this page is scrollable. It includes all of the important
instructions required for getting started.

Manager Role and Capabilities {#_manager_role_and_capabilities}
-----------------------------

::: {.note}
This section is only applicable for users with the manager role. You can
skip it if you don't have that role
:::

The backend server features several roles including: Manager, Set-Value
and User. A manager role has additional capabilities to manage
users/roles and more.

When logged in as a manager we have two additional menus in the top:
Manager and Entities. Entities provide information about the currently
connected agents, logs and tags. The manager menu provides three
options:

![Manager Menu](../../img/manager-menu.png)

User management lets us add a new user or delete/edit an existing user.

![User Management](../../img/manager-users.png)

One important feature is the ability to define the role for the created
user. It's crucial to provide the right roles to a user otherwise the
user won't be able to do anything!

![Create/Edit a User](../../img/manager-create-user.png)

In case of a server side error send logs provides an easy way to send
logs by email directly from the web UI.

![Send Logs](../../img/manager-send-logs.png)

The entities menu includes three editable entries, tags is one such
entry. The web UI lets us delete tags that are no longer used.

![Entities - Tags](../../img/manager-tags.png)

We can disable breakpoints insertion in files that might expose
sensitive data by configuring blacklist.\
Files and packages in blacklist section that don't appear in exception
section will be protected from breakpoints insertion.\
On agent startup the blacklist configuration is downloaded and applied
to future actions, which means patterns modifications here require agent
restart.\
All users can view the configured blacklist and exceptions. The manager
can also create and delete patterns.

![Config - Blacklist](../../img/blacklist-view.png)

![Create Blacklist Patterns](../../img/blacklist-add.png)


