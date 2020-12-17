# PI Historian Connector

The Anypoint Connector for PI Historian (PI Historian Connector) enables you to connect Mule flows to the PI system using the PI Web API.

For information about compatibility and fixed issues, see [Pi Historian Release Notes](http://example.com/).

All required request headers, error handling, and HTTPS connection configurations are built into the connector.

You can use Pi Historian Connector in Mule applications as an outbound connector with CRUD (create, retrieve, update, delete) operations on the following PI Controllers:

### AssetDatabase

- Create elements in the Asset database.

### AssetServer

- List Asset Servers
  		
- Get Asset Server by WebId

### Element

- Create an Element.
	
- Update an Element.
	
- Delete an Element.

### Stream

- Get Recorded
- Get Plot
- Get Value
- Get End Value
- Get Summary
- Update Value
- Update Values in bulk
  
### Subscribe Stream Channel

 - Subscribe a stream channel

You can configure the PI Historian Connector using basic authentication with credentials to connect to a PI Server instance and perform operations.

## Prerequisites

To use this connector, you must be familiar with:

- PI Server
- PI Web API 2016 or higher.
- Mule runtime engine (Mule), including concepts, elements in a Mule flow, and global elements
- Anypoint Connectors
- Anypoint Studio

Before creating an app, you must:

- Have an Anypoint Platform account.
- Have a PI Server to access the PI Web APIs.
- Have `basicAuth` enabled in the PI Web API server.
- Understand how to create a Mule App using Design Center or Anypoint Studio

## Setup

Add this dependency to your application pom.xml

```
<groupId>works.integration</groupId>
<artifactId>mule-pi-historian-connector</artifactId>
<version>1.0.0</version>
<classifier>mule-plugin</classifier>
```

## Configuration

|Parameter|Sample|Description|
|---|---|---|
|PIServer host| `localhost` | Pi Web API hostname. |
|PIServer port|`443`| Pi Web API port.|
|PIServer username|`piuser`|Pi Web API Username.|
|PIServer password|`password1`|Pi Web API Password.|


## Run test

* set the values of the following properties in `src/test/resources/server-config.properties` file:

```
pi.server.username=
pi.server.password=
pi.server.host=
pi.server.port=
		
```

* set the values of the following properties in `src/test/resources/test-data.properties` file:

```
stream.test.web.id= <WebID of a Point.>
element.test.web.id= <WebId of an element in the AssetDatabase.>
asset.test.web.id= <WebId of an Asset server.>
point.test.web.id= <WebId of Point.>
asset.database.web.id= <WebId of an Asset database.>
		
```

* To run the test cases, use `mvn clean integration-test`

## Deploying to Exchange
The Mule Pi Historian Connector can be deployed to an Exchange with following steps.

1. Update the connector pom.xml file
    * Change the `groupId` value to the Organization Id 
        
        
        ```
        		<modelVersion>4.0.0</modelVersion>
				<groupId>xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx</groupId>
				<artifactId>mule-pi-historian-connector</artifactId>
				<version>2.0.29</version>
				<packaging>mule-extension</packaging>
				<name>Pi Historian Connector</name>
				<description>A Mule extension that provides functionality to interact with OSISoft Pi Historian system.</description>

      	```
           
     
    * Update `distributionManagement` to point to the Exchange Repository (Uncomment these lines)
        
        ```
        <distributionManagement>
          <snapshotRepository>
            <id>exchange-repository</id>
            <name>Exchange Repository</name>
            <url>https://maven.anypoint.mulesoft.com/api/v1/organizations/${pom.groupId}/maven</url>
            <layout>default</layout>
          </snapshotRepository>
          <repository>
            <id>exchange-repository</id>
            <name>Exchange Repository</name>
            <url>https://maven.anypoint.mulesoft.com/api/v1/organizations/${pom.groupId}/maven</url>
            <layout>default</layout>
          </repository>
        </distributionManagement>
        ```
2. Configure your `~/.m2/settings.xml` file with your Exchange credentials

    ```
    <servers>
     <server>
       <id>exchange-repository</id>
       <username>USERNAME</username>
       <password>PASSWORD</password>
     </server>
    </servers>
    
    ```
3. Execute `mvn deploy` to publish to Exchange

### Demo

* [Streams Demo Application](https://github.com/IntegrationWorksAus/mule-pi-historian-connector/tree/main/demos/mule-pi-historian-connector-stream-operations-demo)
* [Subscribe Stream Demo Application](https://github.com/IntegrationWorksAus/mule-pi-historian-connector/tree/main/demos/mule-pi-historian-connector-subscribe-streams-demo)

To use the connecter see reference: [PI Historian Connector Reference](http://example.com/)

For more information see: [PI Web API Reference](https://techsupport.osisoft.com/Documentation/PI-Web-API/help.html)
