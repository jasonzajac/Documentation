# Setup and Configuration

<a name='maven-dependency'></a>

## Prerequisites (Maven)

Reveal Java SDK is distributed as a set of [Maven](https://maven.apache.org/what-is-maven.html) modules. To work with the SDK libraries, you need to add a reference to Reveal's Maven Repository and also a dependency in your Maven pom.xml file.

Add the following repository:

```xml
<repositories>
  <repository>
    <id>reveal.public</id>
    <url>https://maven.revealbi.io/repository/public</url>
  </repository>	
</repositories>
```

And the following dependency:

```xml
<dependency>
  <groupId>com.infragistics.reveal.sdk</groupId>
  <artifactId>reveal-sdk</artifactId>
  <version>version_number</version>
</dependency>
```

Replace version_number with a number similar to **0.9.6**.

If you are not familiar with Maven, please refer to the following [link](https://maven.apache.org/guides/getting-started/maven-in-five-minutes.html).

> [!NOTE]
> If you work with an Oracle Database you need to add the driver to your application.

## Setup and Configuration (Generic Server)

To integrate Reveal with any existing application, you need to follow these generic steps:

1.  Add a dependency to the existing app implementation.
2.  Add a dependency to Reveal SDK.
3.  Initialize Reveal.
4.  Enable server-side export

If you are interested in configuring Tomcat or Spring, follow the links below:
- [Tomcat Server](setup-configuration-tomcat.md)
- [Spring Server](setup-configuration-spring.md)
- [Oracle Server](setup-configuration-oracle.md)

### Step 1 - Adding a dependency to the app implementation

Add a dependency to the existing application implementation, following the steps needed for the server of your preference.

### Step 2 - Adding a dependency to Reveal SDK

Add a dependency to *reveal-sdk* and specify your SDK version.

``` java
<dependency>
    <groupId>com.infragistics.reveal.sdk</groupId>
    <artifactId>reveal-sdk</artifactId>
    <version>version_number</version>
</dependency>
```

Replace version_number with a number similar to **1.0.1821**.

### Step 3 - Initializing Reveal

To initialize Reveal, you use **RevealEngineInitializer.initialize**.

It is possible to invoke the method without initial parameters:

``` java
RevealEngineInitializer.initialize();
```
But most of the times, you will be using parameters as shown in the example below:

``` java
RevealEngineInitializer.initialize(
    new InitializeParameterBuilder()
        .setAuthProvider(new RevealAuthenticationProvider())
        .setUserContextProvider(new RevealUserContextProvider())
        .setDashboardProvider(new RevealDashboardProvider())
        .setDataSourceProvider(new UpMediaDataSourceProvider())
        .setDataProvider(new UpMediaInMemoryDataProvider())
        .setMaxConcurrentImageRenderThreads(2)
        .setLicense("SERIAL_KEY_TO_BE_USED")
        .build());
```
Those parameters, are the **providers** used to customize Reveal, you’ll need to create your own providers when integrating Reveal into your application.

The available parameters passed to **RevealEngineInitializer.initialize** are:
- *setAuthProvider*. Here you should include a custom class that resolves authentication, implementing IRVAuthenticationProvider.
- *setUserContextProvider*. Custom class that provides information about the user, implementing IRVUserContextProvider.
- *setDashboardProvider*. Custom class that replaces or modifies a dashboard, implementing IRVDashboardProvider.
- *setDataSourceProvider*. Custom class that replaces or modifies a data source, implementing IRVDataSourceProvider.
- *setDataProvider*. Custom class that returns in-memory data for dashboards, implementing IRVDataProvider.
- *setLicense*. Here you can configure the SDK license, by including the Serial Key.

For further details about how implement your own Dashboard providers, please check our [UpMedia samples](https://github.com/RevealBi/sdk-samples-java) in GitHub.

### Step 4 - Enabling server-side export

The Java SDK uses some native components for exporting dashboards to different formats: Image, PDF, PPT and Excel.

If you are interested in exporting server-side to one or more of those formats, please refer to [Server-side Export Configuration](export-server-side.md)


## Setup and Configuration (Client)

To set up the Reveal Web Client SDK you need to:

1.  [**Check Dependencies**](#check-dependencies).

2.  [**Reference the Web Client SDK**](#reference-web-client-sdk).

3.  [**Instantiate the Web Client SDK**](#instantiate-web-client-sdk).


<a name='check-dependencies'></a>

### 1\. Checking Dependencies

The Reveal Web Client SDK has the following 3rd party references:

- [jQuery](https://jquery.com) 2.2 or greater
- [Day.js](https://day.js.org) 1.8.15 or greater
- [Quill RTE](https://quilljs.com/) 1.3.6 or greater
- [Marker Clusterer](https://developers.google.com/maps/documentation/javascript/examples/markerclusterer/markerclusterer.js) v3 or greater
- [Google Maps](https://maps.googleapis.com/maps/api/js?key=AIzaSyBpcuViSxzlScwOBZy5ln5iIvRl9TYn4y0&libraries=drawing,visualization) v3 or greater
- *(Optional)* [Spectrum](https://github.com/bgrins/spectrum) v 1.8.0 or newer - this is only needed if you enable the UI for the end user to set the background color for a particular visualization.
Check [canChangeVisualizationBackgroundColor](~/en/developer/web-sdk/using-the-client-sdk/showing-hiding-elements.html#canChangeVisualizationBackgroundColor)  


<a name='reference-web-client-sdk'></a>

### 2\. Referencing the Web Client SDK

Enabling **\$.ig.RevealView** component in a web page requires several scripts to be included. These
scripts will be provided as part of Reveal Web Client SDK.

```html
<script src="~/Reveal/infragistics.reveal.js"></script>
```

You need to download the JavaScript files for your version of the Java SDK. Find below a table with download links for all Java SDK versions. Links to each version's release notes are also provided in the table. 

|                                                                  **Download JS files for**                                                                   |                                 **Release notes**                                 |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------: |
| [JAVA SDK 1.0.7](https://maven.revealbi.io/repository/public/com/infragistics/reveal/sdk/reveal-sdk-distribution/1.0.7/reveal-sdk-distribution-1.0.7-js.zip) | [Version 1.0.7](~/en/developer/release-information/release-notes.html#java-sdk-1.0.7) |
| [JAVA SDK 1.0.6](https://maven.revealbi.io/repository/public/com/infragistics/reveal/sdk/reveal-sdk-distribution/1.0.6/reveal-sdk-distribution-1.0.6-js.zip) | [Version 1.0.6](~/en/developer/release-information/release-notes.html#java-sdk-1.0.6) |
| [JAVA SDK 1.0.5](https://maven.revealbi.io/repository/public/com/infragistics/reveal/sdk/reveal-sdk-distribution/1.0.5/reveal-sdk-distribution-1.0.5-js.zip) | [Version 1.0.5](~/en/developer/release-information/release-notes.html#java-sdk-1.0.5) |
| [JAVA SDK 1.0.4](https://maven.revealbi.io/repository/public/com/infragistics/reveal/sdk/reveal-sdk-distribution/1.0.4/reveal-sdk-distribution-1.0.4-js.zip) | [Version 1.0.4](~/en/developer/release-information/release-notes.html#java-sdk-1.0.4) |
| [JAVA SDK 1.0.3](https://maven.revealbi.io/repository/public/com/infragistics/reveal/sdk/reveal-sdk-distribution/1.0.3/reveal-sdk-distribution-1.0.3-js.zip) | [Version 1.0.3](~/en/developer/release-information/release-notes.html#java-sdk-1.0.3) |
| [JAVA SDK 1.0.0](https://maven.revealbi.io/repository/public/com/infragistics/reveal/sdk/reveal-sdk-distribution/1.0.0/reveal-sdk-distribution-1.0.0-js.zip) | [Version 1.0.0](~/en/developer/release-information/release-notes.html#java-sdk-1.0.0) |

> [!NOTE] **Referencing Reveal JS classes**
> You could reference the JS classes through **$.ig.** or **RevealApi.**.
> Through out the docs we're using "$.ig." prefix to reference classes.
> You could use the RevealApi prefix instead of the "$.ig." one, if you want.

<a name='instantiate-web-client-sdk'></a>

### 3\. Instantiating the Web Client SDK

Reveal’s Dashboard presentation is handled natively through the Web
Client SDK.

To get started follow these steps:

1.  Define a \<div /\> element with “id” and invoke the
    **\$.ig.RevealView** constructor.

    > [!NOTE] > **Hosting Client-Side and Server-Side Parts Separately**
    > If you want to host client-side and server-side parts on different servers, please read [here](~/en/developer/web-sdk/overview.html#host-client-server-separate) **before** you continue to next step.

2.  Call
    **\$.ig.RVDashboard.loadDashboard**
    providing the _dashboardId_ and success and error handlers.

3.  In the success handler instantiate the
    **\$.ig.RevealView** component
    by passing a selector for the DOM element
    where the dashboard should be rendered into. Finally
    you should use the retrieved dashboard and set it to the dashboard property of the
    **\$.ig.RevealView**

### Sample Code

```html
<!DOCTYPE html>
<html>
  <head>
    ⋮
    <script type="text/javascript">
      var dashboardId = "dashboardId";

      $.ig.RVDashboard.loadDashboard(
        dashboardId,
        function (dashboard) {
          var revealView = new $.ig.RevealView("#revealView");
          revealView.dashboard = dashboard;
        },
        function (error) {
          //Process any error that might occur here
        }
      );
    </script>
  </head>
  <body>
    <div id="revealView" style="height:500px;" />
  </body>
</html>
```
