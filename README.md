# DCP-ECom-springboot-ProductCategory

### Project Title : DCP-ECom-ProductCategory

### Description : This service is a part of DCP-ECom project. It is used to create, update and delete product categories.

# Getting Started

These instructions will guide you to set project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

# Prerequisites

To develop, build and run the ProductCategory Microservice, you need
JDK 1.8
Install Mongodb
Link : https://www.mongodb.com/download-center#community
Installing
Starting Mongo Server : Go to Mongo Folder(mongodb-win32-x86_64-enterprise-windows-64-4.0.0)->Bin Folder(mongodb-win32-x86_64-enterprise-windows-64-4.0.0\bin)-> first run mongod.exe and then mongo.exe(here you can execute your querries).
In application.yml file of the project mention the Db details
Example :

# MongoDB

spring:
data:
mongodb:
database: productcategories
host: dcp-ecom-db
port: '27017'

# Running the tests :

1)Clone this project using following command :
git clone git@gitlab.com:capgemini-digital-cloud-platform/product-category.git
2)Make sure database is up and running before launching the Spring Boot code.
3)Use STS:  Run as Spring Boot App

How to import: Go to STS(IDE)->In STS go to file-> import->from drop-down menu select gradle->in Gradle select existing gradle project->Click on browse and go to the directory where you have extracted/cloned the project->select the extracted/cloned folder*->click next->Finish. Once you click on finish wait till the project is imported(progress of which you can see in the bottom right corner) It will take around 3-5 mins. Once it is done, Right Click on the project->Go to Run as->click on Spring boot app. In console (part of IDE) you will see "Started ProductCategoryApplication(service name) in 4.191 seconds (JVM running for 4.671) "(only if you have imported the code correctly). Once you see that message Go to Postman (Postman is a Google Chrome app for interacting with HTTP APIs. It presents you with a friendly GUI for constructing requests and reading responses) Download it for testing and hit the URLs one by one given below. ###
4)Use CMD(If failing to run through STS): run command java  –jar “name-Of-JAR-In-build/libs/.jar”

# To test data:
POST Mapping
End Point: localhost(or IPv4 address ): portNo/api/v1/productcategories/
Example: Create ProductCategory –Request
localhost:8080/api/v1/productcategories/
Sample Input:
{
  "productCategory": {
    "description": "description about this",
    "fields": {},
    "fromDate": "2019-07-26T07:38:14.058Z",
    "id": "string",
    "imageRef": "reference address if image",
    "name": "pizza",
    "parentId": "123",
    "throughDate": "2019-07-26T07:38:14.058Z",
    "type": "any"
  }
}
Output response:
{
  "correlationId": "02dfbf8f-49f6-4c4b-9f09-874b8d2a633d",
  "statusCode": 201,
  "statusReason": "Created",
  "success": true,
  "productCategoryId": "5d3aaf0e61661415346e1e60"
}

GET Data: GET Mapping
EndPoint:  localhost:localhost:8087/api/v1/productcategories/
Input: just hit endpoint
Output:
 {
  "correlationId": "650ce82e-8c07-4095-86d0-b7345766fd6c",
  "statusCode": 200,
  "statusReason": "OK",
  "success": true,
  "productCategories": [
    {
      "id": "5d3aafa261661415346e1e61",
      "parentId": "123",
      "type": "any",
      "fromDate": "2019-07-26T07:38:14.058+0000",
      "throughDate": "2019-07-26T07:38:14.058+0000",
      "name": "pizza",
      "description": "description about this",
      "imageRef": "reference address if image",
      "fields": {}
    }
  ]
}

# Built With:

Java Spring Boot

Gradle  - Dependency Management

Mongo Template - Through query to save date in mongodb database 

### Version:
0.1.0

### Author:
Aruna B H