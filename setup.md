### Creating a Workspace

Once logged into CodeReady Workspaces, you can now create your workspace based on the *Java 1.8 Stack*.

#### [TIP]

A **Stack** is a template for workspace configuration.
It includes the programming language and tools needed in your workspace to create applications.
Stacks make it possible to deploy identical workspaces for all users on demand.

`Select the stack called 'Java 1.8'` and then `click on 'CREATE & OPEN'`. 

![CodeReady Workspaces - Workspace]({% image_path codeready-create-workspace.png %})

#### [CAUTION]
*Make sure to select the stack called 'Java 1.8' otherwise, you will not be able to complete the lab!*

It takes a little while for the workspace to be ready. When it's ready, you will see a fully functional CodeReady Workspaces IDE running in your browser.

![CodeReady Workspaces - Workspace]({% image_path codeready-workspace.png %})

### Importing the lab project
Now you can import the project skeletons into your workspace.

In the Project Explorer pane, `click on 'Import Project...'` and enter the following:

  * Type: **GIT**
  * URL: **{{LABS_DOWNLOAD_URL}}**
  * Name: **labs**
  * Check **Skip the root folder of the archive**

image:{% image_path codeready-import.png %}[CodeReady Workspaces - Import Project,700]

`*Click on 'Import'*`. Make sure you choose the **Blank** project configuration since the zip file contains multiple 
project skeletons. `*Click on 'Save'*`

image:{% image_path codeready-import-save.png %}[CodeReady Workspaces - Import Project,500]

=== Converting your project skeletons
The projects are imported now into your workspace and is visible in the project explorer.

CodeReady Workspaces is a full featured IDE and provides language specific capabilities for various project types. In order to 
enable these capabilities, let's convert the imported project skeletons to Maven projects. 

In the Project Explorer, `*right-click on 'catalog-spring-boot'*` then, `*click on 'Convert to Project'*`.

image:{% image_path codeready-convert.png %}[CodeReady Workspaces - Convert to Project,500]

`*Choose 'JAVA > Maven'*` from the project configurations and then `*click on 'Save'*`

image:{% image_path codeready-maven.png %}[CodeReady Workspaces - Convert to Project,500]

[WARNING]
.Project Conversion
====
Repeat the above for **inventory-thorntail** and **gateway-vertx** projects.
====

[IMPORTANT]
.Terminal Window of CodeReady Workspaces
====
For the rest of these labs, anytime you need to run a command in a terminal, you can use the CodeReady Workspaces **Terminal** window.

image:{% image_path codeready-terminal.png %}[CodeReady Workspaces - Terminal, 700]
====

== Explore OpenShift with OpenShift CLI

In order to login, `*issue the following command*` and log in as `*{{OPENSHIFT_USER}}/{{OPENSHIFT_PASSWORD}}*`

[source,shell]
----
$ oc login {{OPENSHIFT_CONSOLE_URL}}
----

[TIP]
====
You may see the following output:

----
The server uses a certificate signed by an unknown authority.
You can bypass the certificate check, but any data you send to the server could be intercepted by others.
Use insecure connections? (y/n):
----

Enter in `*Y*` to use a potentially insecure connection.  The reason you received
this message is because we are using a self-signed certificate for this
workshop, but we did not provide you with the CA certificate that was generated
by OpenShift. In a real-world scenario, either OpenShift's certificate would be
signed by a standard CA (eg: Thawte, Verisign, StartSSL, etc.) or signed by a
corporate-standard CA that you already have installed on your system.
====

Congratulations, you are now authenticated to the OpenShift server.

{{OPENSHIFT_DOCS_BASE}}/architecture/core_concepts/projects_and_users.html#projects[Projects^] 
are a top level concept to help you organize your deployments. An
OpenShift project allows a community of users (or a user) to organize and manage
their content in isolation from other communities. Each project has its own
resources, policies (who can or cannot perform actions), and constraints (quotas
and limits on resources, etc). Projects act as a "wrapper" around all the
application services and endpoints you (or your teams) are using for your work.

[WARNING]
====

Make sure to use your dedicated project {{COOLSTORE_PROJECT}} by running the following command:

[source,shell]
----
$ oc project {{COOLSTORE_PROJECT}}
----

====

OpenShift ships with a web-based console that will allow users to
perform various tasks via a browser.  To get a feel for how the web console
works, open your browser and `*go to {{OPENSHIFT_CONSOLE_URL}}[OpenShift Web Console^]*`.

The first screen you will see is the authentication screen. Enter your username and password (`*{{OPENSHIFT_USER}}/{{OPENSHIFT_PASSWORD}}*`) and 
then log in. After you have authenticated to the web console, you will be presented with a
list of projects that your user has permission to work with. 

`*Click on '{{COOLSTORE_PROJECT}}'*` project to be taken to the project overview page
which will list all of the routes, services, deployments, and pods that you have
running as part of your project. There's nothing there now, but that's about to
change.

Now you are ready to get started with the labs!






## Setup the workspace

### Introduction to the lab environment

* Overview CodeReady Workspaces

### Introduction to devonfw and the reference app

* https://github.com/devonfw
* https://github.com/devonfw/my-thai-star

### Introduction to workshop assets

* https://github.com/redhat-capgemini-exchange
* https://github.com/redhat-capgemini-exchange/my-thai-star
* https://github.com/redhat-capgemini-exchange/my-thai-star-workshop
  
### Setup your own development workspace

1. Create a new workspace
- Add https://github.com/redhat-capgemini-exchange/my-thai-star

2. Add workshop assets
- Import project -> Git -> URL: https://github.com/redhat-capgemini-exchange/my-thai-star-workshop
- Project Configuration: blank
