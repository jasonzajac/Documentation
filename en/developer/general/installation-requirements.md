# System Requirements and Installation

## Desktop SDK Requirements

- The Reveal SDK requires .NET version 4.6.2+ and Visual Studio 2015 or up.

## Web SDK .NET Requirements

- The Reveal Server SDK requires .NET Core 2.2+ server-side projects
targeting .NET framework 4.6.2+.

## Installing Desktop and Web .NET SDK

To get the Reveal SDK for both Web and Desktop .NET platforms, sign up [here](https://www.revealbi.io/#download-sdk).
Once ready, follow through the provided installer:

<img src="images/installScreen_desktop.png" alt="installScreen_desktop" class="responsive-img"/>

After a successful installation, you can browse the installed samples by clicking the *Open SDK Samples* link.

<img src="images/afterInstallScreen_desktop.png" alt="afterInstallScreen_desktop" class="responsive-img"/>

### Samples

In case you missed the samples link, you can find them in
“%public%\\Documents\\Infragistics\\Reveal\\SDK\\”.

In this location you will find a solution file (Reveal.Sdk.Samples.sln). This project combines all Web, WPF, and WinForms samples.

For Web you need to restore the node packages in order to run the samples with IIS and change the StartUp project. To restore, just right click the solution in the Solution Explorer and select Restore packages.


## Web SDK JAVA Requirements
- [Java SDK](https://www.oracle.com/java/technologies/javase-downloads.html) 11.0.10 and up recommended.
- [Maven](https://maven.apache.org/download.cgi) 3.6.3 and up recommended
 
## Installing JAVA SDK

Reveal Java SDK is distributed as a set of [Maven](https://maven.apache.org/what-is-maven.html) modules. To work with the SDK libraries, you need to add a reference to Reveal's Maven Repository and also a dependency in your Maven pom.xml file. For further details, please refer to [Setup and Configuration](~/en/developer/java-sdk/setup-configuration.md).

### Samples
The **UpMedia samples** illustrate how to use the JAVA SDK, you can get them from GitHub [here](https://github.com/RevealBi/sdk-samples-java).

For details about how to run the UpMedia samples, please follow this [link](~/en/developer/java-sdk/running-upmedia-samples.md).

