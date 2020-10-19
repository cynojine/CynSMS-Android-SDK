# Getting started

This Api is meant for 3rd party integrations

## How to Build

The generated code uses a few Gradle dependencies e.g., Jackson, Volley,
and Apache HttpClient. The reference to these dependencies is already
added in the build.gradle file will be installed automatically. Therefore,
you will need internet access for a successful build.

* In order to open the client library in Android Studio click on ``` Open an Existing Android Project ```.

![Importing SDK into Android Studio - Step 1](https://apidocs.io/illustration/android?step=import1&workspaceFolder=CynSMS%20API&workspaceName=CynSMSAPI&projectName=CynSMSAPILib&rootNamespace=com.cynojine.sms)

* Browse to locate the folder containing the source code. Select the location of the CynSMSAPI gradle project and click ``` Ok ```.

![Importing SDK into Android Studio - Step 2](https://apidocs.io/illustration/android?step=import2&workspaceFolder=CynSMS%20API&workspaceName=CynSMSAPI&projectName=CynSMSAPILib&rootNamespace=com.cynojine.sms)

* Upon successful import, the project can be built by clicking on ``` Build > Make Project ``` or  pressing ``` Ctrl + F9 ```.

![Importing SDK into Android Studio - Step 3](https://apidocs.io/illustration/android?step=import3&workspaceFolder=CynSMS%20API&workspaceName=CynSMSAPI&projectName=CynSMSAPILib&rootNamespace=com.cynojine.sms)

## How to Use

The following section explains how to use the CynSMSAPI library in a new project.

### 1. Starting a new project 

For starting a new project, click on ``` Create New Android Studio Project ```.

![Add a new project in Android Studio - Step 1](https://apidocs.io/illustration/android?step=createNewProject0&workspaceFolder=CynSMS%20API&workspaceName=CynSMSAPI&projectName=CynSMSAPILib&rootNamespace=com.cynojine.sms)

Here, configure the new project by adding the name, domain and location of the sample application followed by clicking ``` Next ```.

![Create a new Android Studio Project - Step 2](https://apidocs.io/illustration/android?step=createNewProject1&workspaceFolder=CynSMS%20API&workspaceName=CynSMSAPI&projectName=CynSMSAPILib&rootNamespace=com.cynojine.sms)

Following this, select the `Phone and Tablet` option as shown in the illustration below and click `Next`.

![Create a new Android Studio Project - Step 3](https://apidocs.io/illustration/android?step=createNewProject2&workspaceFolder=CynSMS%20API&workspaceName=CynSMSAPI&projectName=CynSMSAPILib&rootNamespace=com.cynojine.sms)

In the following step, choose ``` Empty Activity ``` as the activity type and click ``` Next ```.

![Create a new Android Studio Project - Step 4](https://apidocs.io/illustration/android?step=createNewProject3&workspaceFolder=CynSMS%20API&workspaceName=CynSMSAPI&projectName=CynSMSAPILib&rootNamespace=com.cynojine.sms)

In this step, provide an ``` Activity Name ``` and ``` Layout Name ``` and click ``` Finish ```.  This would take you to the newly created project.

![Create a new Android Studio Project - Step 4](https://apidocs.io/illustration/android?step=createNewProject4&workspaceFolder=CynSMS%20API&workspaceName=CynSMSAPI&projectName=CynSMSAPILib&rootNamespace=com.cynojine.sms)

### 2. Add reference of the library project

In order to add a dependency to this sample application, click on the android button shown in the project explorer on the left side as shown in the picture. Click on ``` Project ``` in the drop down that emerges.  

![Adding dependency to the client library - Step 1](https://apidocs.io/illustration/android?step=testProject0&workspaceFolder=CynSMS%20API&workspaceName=CynSMSAPI&projectName=CynSMSAPILib&rootNamespace=com.cynojine.sms)

Right click the sample application in the project explorer and click on ``` New > Module ```  as shown in the picture.

![Adding dependency to the client library - Step 2](https://apidocs.io/illustration/android?step=testProject1&workspaceFolder=CynSMS%20API&workspaceName=CynSMSAPI&projectName=CynSMSAPILib&rootNamespace=com.cynojine.sms)

Choose ``` Import Gradle Project ``` and click ``` Next ```.

![Adding dependency to the client library - Step 3](https://apidocs.io/illustration/android?step=testProject2&workspaceFolder=CynSMS%20API&workspaceName=CynSMSAPI&projectName=CynSMSAPILib&rootNamespace=com.cynojine.sms)

Click on ``` Finish ``` which would take you back to the sample application with the refernced SDK. 

![Adding dependency to the client library - Step 4](https://apidocs.io/illustration/android?step=testProject3&workspaceFolder=CynSMS%20API&workspaceName=CynSMSAPI&projectName=CynSMSAPILib&rootNamespace=com.cynojine.sms)

In the following step first navigate to the ``` SampleApplication > settings.gradle ``` file and add the line
```include ':CynSMSAPILib'```

Then navigate to the ``` SampleApplication >  app > build.gradle ``` file and add the following line 
```implementation project(path: ':CynSMSAPILib')```
to the dependencies section as shown in the illustration below. Also add the following packagingOptions.

packagingOptions
    exclude 'META-INF/LICENSE'
    exclude 'META-INF/NOTICE'
    exclude 'META-INF/DEPENDENCIES'
}

![Adding dependency to the client library - Step 5](https://apidocs.io/illustration/android?step=testProject4&workspaceFolder=CynSMS%20API&workspaceName=CynSMSAPI&projectName=CynSMSAPILib&rootNamespace=com.cynojine.sms)

Finally, press ``` Sync Now ``` in the warning visible as shown in the picture below.

![Adding dependency to the client library - Step 6](https://apidocs.io/illustration/android?step=testProject5&workspaceFolder=CynSMS%20API&workspaceName=CynSMSAPI&projectName=CynSMSAPILib&rootNamespace=com.cynojine.sms)

### 3. Write sample code

Once the ``` SampleApplication ``` is created, a file named ``` SampleApplication > app > src > main > java > MainActivity ``` will be visible in the *Project Explorer* with an ``` onCreate ``` method. This is the entry point for the execution of the created project.
Here, you can add code to initialize the client library and instantiate a *Controller* class. Sample code to initialize the client library and using controller methods is given in the subsequent sections.

## How to Test

The generated code and the server can be tested using automatically generated test cases. 
JUnit is used as the testing framework and test runner.

In Android Studio, for running the tests do the following:

1. Right click on *SampleApplication > CynSMSAPILib > androidTest > java)* from the project explorer.
2. Select "Run All Tests" or use "Ctrl + Shift + F10" to run the Tests.

## Initialization

### 

API client can be initialized as following. The `appContext` being passed is the Android application [`Context`](https://developer.android.com/reference/android/content/Context.html).

```java

com.cynojine.sms.Configuration.initialize(appContext);
CynSMSAPIClient client = new CynSMSAPIClient();
```


# Class Reference

## <a name="list_of_controllers"></a>List of Controllers

* [APIController](#api_controller)

## <a name="api_controller"></a>![Class: ](https://apidocs.io/img/class.png "com.cynojine.sms.controllers.APIController") APIController

### Get singleton instance

The singleton instance of the ``` APIController ``` class can be accessed from the API Client.

```java
APIController client = client.getClient();
```

### <a name="create_send_sms_async"></a>![Method: ](https://apidocs.io/img/method.png "com.cynojine.sms.controllers.APIController.createSendSMSAsync") createSendSMSAsync

> TODO: Add a method description


```java
void createSendSMSAsync(
        final String apiKey,
        final String to,
        final String sms,
        final String from,
        final APICallBack<String> callBack)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| apiKey |  ``` Required ```  ``` DefaultValue ```  | set your API_KEY from http://sms.cynojine.com/sms-api/info (user panel) |
| to |  ``` Required ```  ``` DefaultValue ```  | the number we are sending to - Any phone number |
| sms |  ``` Required ```  | SMS Body |
| from |  ``` Required ```  | Change the from number below. It can be a valid phone number or a String |


#### Example Usage

```java
String apiKey = "xxxxxxxxxxxxx";
String to = "260986";
String sms = "sms";
String from = "from";
// Invoking the API call with sample inputs
client.createSendSMSAsync(apiKey, to, sms, from, new APICallBack<String>() {
    public void onSuccess(HttpContext context, String response) {
        // TODO success callback handler
    }
    public void onFailure(HttpContext context, Throwable error) {
        // TODO failure callback handler
    }
});

```


### <a name="get_balancecheck_async"></a>![Method: ](https://apidocs.io/img/method.png "com.cynojine.sms.controllers.APIController.getBALANCECHECKAsync") getBALANCECHECKAsync

> Checking SMS Balance


```java
void getBALANCECHECKAsync(
        final GetBALANCECHECKInput input,
        final Map<String, Object> queryParameters,
        final APICallBack<Object> callBack)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| apiKey |  ``` Required ```  | Get your account balance |
| response |  ``` Required ```  ``` DefaultValue ```  | Json Responce |
| queryParameters | ``` Optional ``` | Additional optional query parameters are supported by this method |


#### Example Usage

```java
GetBALANCECHECKInput collect = new GetBALANCECHECKInput();

String apiKey = "api_key";
collect.setApiKey(apiKey);

String response = "json";
collect.setResponse(response);

// key-value map for optional query parameters
Map<String, Object> queryParams = new LinkedHashMap<String, Object>();
// Invoking the API call with sample inputs
client.getBALANCECHECKAsync(collect, , queryParams, new APICallBack<void>() {
    public void onSuccess(HttpContext context, void response) {
        // TODO success callback handler
    }
    public void onFailure(HttpContext context, Throwable error) {
        // TODO failure callback handler
    }
}
);

```


[Back to List of Controllers](#list_of_controllers)



