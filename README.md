# mule-pi-historian-connector


The Anypoint Connector for PI Historian (PI Historian Connector) enables you to connect Mule flows to the PI system using the PI Web API.

For information about compatibility and fixed issues, see [Pi Historian Release Notes](http://example.com/).

All required request headers, error handling, and HTTPS connection configurations are built into the connector.

You can use Pi Historian Connector in Mule applications as an outbound connector with CRUD (create, retrieve, update, delete) operations on the following PI Controllers:

- AssetDatabase

  Create

- AssetServer

  List, Get

- Element

  Create, Update, Delete

- Stream

  Get Recorded, Get Plot, Get Value, Get End Value, Get Summary, Update Value, Update Values

You can configure the PI Historian Connector using basic authentication with credentials to connect to a PI Server instance and perform operations.

## Prerequisites

To use this connector, you must be familiar with:

- PI Server
- Mule runtime engine (Mule), including concepts, elements in a Mule flow, and global elements
- Anypoint Connectors
- Anypoint Studio

Before creating an app, you must:

- Have an Anypoint Platform account
- Have a PI Server to access the PI Server target resources
- Understand how to create a Mule app using Design Center or Anypoint Studio

## Setup

Add this dependency to your application pom.xml

```
<groupId>works.integration</groupId>
<artifactId>mule-pi-historian-connector</artifactId>
<version>1.0.0</version>
<classifier>mule-plugin</classifier>
```
## Server config
set the values of the following properties:

```
pi.server.username=
pi.server.password=
pi.server.host=
pi.server.port=
```

To use the connecter see reference: [PI Historian Connector Reference](http://example.com/)

For more information see: [PI Web API Reference](https://techsupport.osisoft.com/Documentation/PI-Web-API/help.html)
