# Weather Rest Adapter
### This application is a rest adapater for SOAP based Weather service.

### Instructions to run the project:

### 1.	NODE
Clone the aforementioned repository using the following command.
  ```sh
$ git clone https://github.com/sachinarora92/weather-app-deloitte.git
```
Go to weatherExcerciseDockerFile folder and run npm install
Go to weatherExcerciseDockerFile folder and execute build the docker image and run it as a container or, simply run `node server.js` to start the Weather SOAP WS
Go to `http://localhost:8080/GlobalWeather?WSDL` and make sure it answers the WS spec
### 2.	MULE EE RUNTIME [4.3.3]
Go to https://www.mulesoft.com/lp/dl/studio and download Mule Anypoint Studio 7 and Mule 4
Unzip the downloaded file to create the folder
 
### 3.	MULE APPLICATION
Copy the JAR file `weather-adapter-rest.jar` into the app folder of the Mule Enterprise Standalone folder unzipped in the previous step	 
Be sure to have JRE or JDK 8 installed
Go to `/bin` Mule standalone subfolder and run mule.sh in Linux or mule.bat in Windows

The project code can also be imported into the Anypoint studio and can be executed.

### 4.  API Routes
Open postman or simply go to a browser and navigate to these URLs:
  ```sh
http://localhost:8081/api/countries  
http://localhost:8081/api/countries/Australia/cities 
http://localhost:8081/api/countries/Australia/cities/Melbourne/weather
```  


### 5.  CHALLENGES

•	The SOAP webservice at URL http://www.webservicex.com/globalweather.asmx?WSDL was unavailable. Used Docker image for the service.
•	Webservice provide with the docker image embedded the content in two CDATA elements (<![CDATA[ <![CDATA[ ]] ]]) which was wrong. Corrected the docker image. New docker sample is available in repo.
•	This is the first time I have used Mulesoft Anypoint for development. So some code or design decisions may be naive. The intent of this exercise is to learn a new technology like MuleSoft AnyPoint and to demonstrate an integration scenario using it. This code should not be used in production and should just be used as a reference.
•	Anypoint studio was not able to provide the support for dataweave expression checker. I had to run the application again and again to check the expression’s result.



### 6.  BACKLOG

•	Security aspects are not included or demonstrated.
•	Unit tests are added only for happy path scenarios.
•	Error handling is done at the generic level. No detailed description is available in the API response. For unavailable cities/countries, it just returns 400 BAD_REQUEST {“message”:”Bad request”}.
•	Cloudhub deployment is not supported.
•	Caching strategies are not incorporated in the API.


Note : For detailed design, architecture, challenges and issues, please refer to the developer documentation [Technical_Specification_DOC_Weather_APP_V1.docx].
