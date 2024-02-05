<h1>Spring Boot</h1>
<p>For this app, I followed this tutorial: https://youtu.be/yp_uleaOzV4?si=pimcOzQa9GEXgQvz </p>
<p>This tutorial creates a simple Spring Boot application with a Thymeleaf form that has a connection to a MySQL database. However, for simplicity purposes, I did not implement the /users page. I also made my application.properties file connect to a Azure database. The steps to create and add that database are below: </p>

<h1>Azure Database for MySQL</h1>
<p>To create the instance, go to Azure Database for MySQL in the Azure console. Click Create a resource. Set a name and generate a password for your instance. Make sure to save the password somewhere so you can use it later. You can keep the default settings for everything else.</p>
<p>After the instance creates, you need to create the database. Set a name (in my case, I put "users") and Create. </p>
<p>In your Spring Boot application.properties file, add your database's url, username, and password. The url should look similar to the following: </p>

```
spring.datasource.url=jdbc:mysql://<PUBLIC_IP>:3306/<DB_NAME>
```

<p>Now, when you run the application, it should automatically create a table in the database with the schema required. In this case, it creates a table called "user." </p>

<h2>MySQL Workbench</h2>
<p>You can use MySQL Workbench to query the database and make sure changes are going through. Set up the connection by adding your database's public IP address into the Hostname. Set the port to 3306 and put "root" for the username and enter your database password that you saved earlier. </p>
<p>Once you are in the database, run the following query: </p>

```
USE <DB_NAME>;
SELECT * FROM user;
```

<p>This should show everything that is in your table. When you run your application and input data, this is where it should be stored. You can keep running the SELECT query to check the table. </p>
