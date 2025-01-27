# MySQL

>[!NOTE] **Limitations in Web**. In the *Reveal Web* app, you can connect only to publicly accessible MySQL addresses. If your MySQL address is restricted for the general public (private or hosted in the company's intranet, for example), you can use *Reveal Desktop*, *iOS* or *Android* to connect to it. The device where you're running Reveal needs to have access to this MySQL address. This limitation does not apply to *Reveal Embedded*.

## Connecting to MySQL

To configure a MySQL server data source, you will need to enter the
following information:

<img src="images/enter-mySQL-server-details.png" alt="Enter MySQL Server Details dialog" class="responsive-img"/>

1.  **Default name** of the data source: Your data source name will be displayed in the list of accounts in the previous dialog. By default, Reveal names the data source *MySQL*. You can change it to your preference.


2. [**Server**](#how-to-find-server): the computer name or IP address
    assigned to the computer on which the server is running.

3.  **Port**: if applicable, the server port details. If no information
    is entered, Reveal will connect to the port in the hint text (3306)
    by default.

4.  **Credentials**: after selecting *Credentials*, you will be able to
    enter the credentials for your MySQL server or choose existing ones
    if applicable.

      - **Name**: the name for your data source account. It will be
        displayed in the list of accounts in the previous dialog.

      - *(Optional)* **Domain**: the name of the domain, if applicable.

      - **Username**: the user account for the MySQL server.

      - **Password**: the password to access the MySQL server.

    Once ready, select **Continue**.

<a name='how-to-find-server'></a>
## How to find your Server Information

You can find your server by following the steps below. Please note that
the commands should be executed on the server.

| WINDOWS                                                                                                         | LINUX                                                                                                         | MAC                                                                  |
| --------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| 1\. Open the File Explorer.                                                                                     | 1\. Open a Terminal.                                                                                          | 1\. Open System Preferences.                                         |
| 2\. Right Click on My Computer \> Properties.                                                                   | 2\. Type in **$hostname**                                                                                     | 2\. Navigate to the Sharing Section.                                 |
| Your Hostname will appear as "Computer Name" under the *Computer name, domain, and workgroups settings* section. | Your Hostname will appear along with your DNS domain name. Make sure you only include **Hostname** in Reveal. | Your Hostname will be listed under the "Computer Name" field on top. |

You can find your *IP address* by following the steps below. Please note
that the commands should be executed on the server.

| WINDOWS                              | LINUX                             | MAC                                                           |
| ------------------------------------ | --------------------------------- | ------------------------------------------------------------- |
| 1\. Open a Command Prompt.           | 1\. Open a Terminal.              | 1\. Launch your Network app.                                  |
| 2\. Type in **ipconfig**             | 2\. Type in **$ /bin/ifconfig**   | 2\. Select your connection.                                   |
| **IPv4 Address** is your IP address. | **Inet addr** is your IP address. | The **IP Address** field will have the necessary information. |

## Setting Up Your Data

With Reveal, you can retrieve MySQL data from entire tables. Still, you can also select a particular view that returns a subset of data from a table or a set of tables instead.

<img src="images/MySQL-views.png" alt="MySQL Views section" class="responsive-img"/>

In the sample above, the **invoices** view contains a modified version
of the data in the **Products** table in the MySQL server.

<img src="images/invoices-MySQL-view-sample.png" alt="Sample dashboard using MySQL invoices view data" class="responsive-img"/>

For more information on views and MySQL, visit [this documentation page](https://dev.mysql.com/doc/refman/8.0/en/views.html).
