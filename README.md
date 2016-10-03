# Getting Started
## How to Build

The generated code uses a few Maven dependencies e.g., Jackson, UniRest,
and Apache HttpClient. The reference to these dependencies is already
added in the pom.xml file will be installed automatically. Therefore,
you will need internet access for successful build.

* In order to open the client library in Eclipse click on ``` File -> Import ```.

![Importing SDK into Eclipse - Step 1](http://apidocs.io/illustration/java?step=import0&workspaceFolder=Uber%2FAPI-Java&workspaceName=UberAPI&projectName=UberAPILib&rootNamespace=com.uber.api)

* In the import dialog, select ``` Existing Java Project ``` and click ``` Next ```.

![Importing SDK into Eclipse - Step 2](http://apidocs.io/illustration/java?step=import1&workspaceFolder=Uber API-Java&workspaceName=UberAPI&projectName=UberAPILib&rootNamespace=com.uber.api)

* Browse to locate the folder containing the source code. Select the detected location of the project and click ``` Finish ```.

![Importing SDK into Eclipse - Step 3](http://apidocs.io/illustration/java?step=import2&workspaceFolder=Uber API-Java&workspaceName=UberAPI&projectName=UberAPILib&rootNamespace=com.uber.api)

* Upon successful import, the project will be automatically built by Eclipse after automatically resolving the dependencies.

![Importing SDK into Eclipse - Step 4](http://apidocs.io/illustration/java?step=import3&workspaceFolder=Uber API-Java&workspaceName=UberAPI&projectName=UberAPILib&rootNamespace=com.uber.api)

## How to Use

The following section explains how to use the UberAPI library in a new console project.     
    
#### 1. Starting a new project
For starting a new project, click the menu command ``` File > New > Project ```.

![Add a new project in Eclipse](http://apidocs.io/illustration/java?step=createNewProject0&workspaceFolder=Uber API-Java&workspaceName=UberAPI&projectName=UberAPILib&rootNamespace=com.uber.api)

Next, choose ``` Maven > Maven Project ```and click ``` Next ```.

![Create a new Maven Project - Step 1](http://apidocs.io/illustration/java?step=createNewProject1&workspaceFolder=Uber API-Java&workspaceName=UberAPI&projectName=UberAPILib&rootNamespace=com.uber.api)

Here, make sure to use the current workspace by choosing ``` Use default Workspace location	```, as shown in the picture below and click ``` Next ```.

![Create a new Maven Project - Step 2](http://apidocs.io/illustration/java?step=createNewProject2&workspaceFolder=Uber API-Java&workspaceName=UberAPI&projectName=UberAPILib&rootNamespace=com.uber.api)

Following this, select the *quick start* project type to create a simple project with an existing class and a ``` main ``` method. To do this, choose ``` maven-archetype-quickstart ``` item from the list and click ``` Next ```.

![Create a new Maven Project - Step 3](http://apidocs.io/illustration/java?step=createNewProject3&workspaceFolder=Uber API-Java&workspaceName=UberAPI&projectName=UberAPILib&rootNamespace=com.uber.api)

In the last step, provide a ``` Group Id ``` and ``` Artifact Id ``` as shown in the picture below and click ``` Finish ```.

![Create a new Maven Project - Step 4](http://apidocs.io/illustration/java?step=createNewProject4&workspaceFolder=Uber API-Java&workspaceName=UberAPI&projectName=UberAPILib&rootNamespace=com.uber.api)


#### 2. Add reference of the library project
The created Maven project manages its dependencies using its ``` pom.xml ``` file. In order to add a dependency on the *UberAPILib* client library, double click on the ``` pom.xml ``` file in the ``` Package Explorer ```. Opening the ``` pom.xml ``` file will render a graphical view on the cavas. Here, switch to the ``` Dependencies ``` tab and click the ``` Add ``` button as shown in the picture below.

![Adding dependency to the client library - Step 1](http://apidocs.io/illustration/java?step=testProject0&workspaceFolder=Uber API-Java&workspaceName=UberAPI&projectName=UberAPILib&rootNamespace=com.uber.api)

Clicking the ``` Add ``` button will open a dialog where you need to specify UberAPI in ``` Group Id ``` and UberAPILib in the ``` Artifact Id ``` fields. Once added click ``` OK ```. Save the ``` pom.xml ``` file.

![Adding dependency to the client library - Step 2](http://apidocs.io/illustration/java?step=testProject1&workspaceFolder=Uber API-Java&workspaceName=UberAPI&projectName=UberAPILib&rootNamespace=com.uber.api)

#### 3. Write sample code
Once the ``` SimpleConsoleApp ``` is created, a file named ``` App.java ``` will be visible in the *Package Explorer* with a ``` main ``` method. This is the entry point for the execution of the created project.
Here, you can add code to initialize the client library and instantiate a *Controller* class. Sample code to initialize the client library and using controller methods is given in the subsequent sections.

![Adding dependency to the client library - Step 2](http://apidocs.io/illustration/java?step=testProject2&workspaceFolder=Uber API-Java&workspaceName=UberAPI&projectName=UberAPILib&rootNamespace=com.uber.api)

## How to Test

The generated code and the server can be tested using automatically generated test cases. 
JUnit is used as the testing framework and test runner.

In Eclipse, for running the tests do the following:

1. Select the project *UberAPILib* from the package explorer.
2. Select "Run -> Run as -> JUnit Test" or use "Alt + Shift + X" followed by "T" to run the Tests.

## Initialization

#### Authentication and Initialization
In order to setup authentication and initialization of the API client, you need the following information.

| Parameter | Description |
|-----------|-------------|
| oAuthAccessToken | The OAuth 2.0 access token to be set before API calls |



API client can be initialized as following.

```java
// Initializing Object Mapper for Serialization and Deserialization purposes
public static ObjectMapper mapper = new ObjectMapper()
{
	private static final long serialVersionUID = -174113593500315394L;
	{
		configure(DeserializationFeature.FAIL_ON_UNKNOWN_PROPERTIES, false);
		setSerializationInclusion(JsonInclude.Include.NON_NULL);
	}
};

// Configuration parameters and credentials
String oAuthAccessToken = "oAuthAccessToken"; // The OAuth 2.0 access token to be set before API calls

UberAPIClient client = new UberAPIClient(oAuthAccessToken);
```

# Class Reference
## <a name="list_of_controllers"></a>List of Controllers

* [APIController](#api_controller)

## <a name="api_controller"></a>![Class: ](http://apidocs.io/img/class.png "com.uber.api.controllers.APIController") APIController

#### Get singleton instance
The singleton instance of the ``` APIController ``` class can be accessed from the API Client.
```java
APIController client = client.getClient();
```

### <a name="get_promotions_async"></a>![Method: ](http://apidocs.io/img/method.png "com.uber.api.controllers.APIController.getPromotionsAsync") getPromotionsAsync

> The Promotions endpoint returns information about the promotion that will be available to a new user based on their activity's location. These promotions do not apply for existing users.

```java
void getPromotionsAsync(
        final GetPromotionsInput input,
        final APICallBack<PromotionsResponse> callBack)
```

#### Parameters: 

| Parameter | Tags | Description |
|-----------|------|-------------|
| endLatitude |  ``` Required ```  | Latitude component of end location. |
| endLongitude |  ``` Required ```  | Longitude component of end location. |
| startLatitude |  ``` Required ```  | Latitude component of start location. |
| startLongitude |  ``` Required ```  | Longitude component of start location |



#### Example Usage:
```java
GetPromotionsInput collect = new GetPromotionsInput();

double endLatitude = 180.674409941153;
collect.setEndLatitude(endLatitude);

double endLongitude = 180.674409941153;
collect.setEndLongitude(endLongitude);

double startLatitude = 180.674409941153;
collect.setStartLatitude(startLatitude);

double startLongitude = 180.674409941153;
collect.setStartLongitude(startLongitude);

// Invoking the API call with sample inputs
client.getPromotionsAsync(collect, new APICallBack<PromotionsResponse>() {
    public void onSuccess(HttpContext context, PromotionsResponse response) {
        // TODO success callback handler
    }
    public void onFailure(HttpContext context, Throwable error) {
        // TODO failure callback handler
    }
}
);

```



#### Errors: 
| Error Code | Error Description |
|------------|-------------------|
| 400 | Malformed request. |
| 401 | Unauthorized the request requires user authentication (not logged in). |
| 403 | Forbidden. Also used for unauthorized requests such as improper OAuth 2.0 scopes or permissions issues. |
| 404 | Not found. |
| 406 | Unacceptable content type. Client sent an accepts header for a content type which does not exist on the server. Body includes a list of acceptable content types, such as ?Unacceptable content type. Request resource as: application/json. |
| 409 | A conflict needs to be resolved before the request can be made. |
| 422 | Invalid request. The request body is parse-able however with invalid content or there are issues with a rider's user account. |
| 429 | Too Many Requests. Rate limited |
| 500 | Internal Server Error. |
| 222 | bac |





### <a name="create_request_async"></a>![Method: ](http://apidocs.io/img/method.png "com.uber.api.controllers.APIController.createRequestAsync") createRequestAsync

> The Request endpoint allows a ride to be requested on behalf of an Uber user given their desired product, start, and end locations. Please review the Sandbox documentation on how to develop and test against these endpoints without making real-world Requests and being charged.

```java
void createRequestAsync(
        final RequestBody body,
        final APICallBack<Request> callBack)
```

#### Parameters: 

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |



#### Example Usage:
```java
try {
    RequestBody body = new RequestBody();
    // Invoking the API call with sample inputs
    client.createRequestAsync(body, new APICallBack<Request>() {
        public void onSuccess(HttpContext context, Request response) {
            // TODO success callback handler
        }
        public void onFailure(HttpContext context, Throwable error) {
            // TODO failure callback handler
        }
    });
} catch(JsonProcessingException e) {
    // TODO Auto-generated catch block
    e.printStackTrace();
}
```



#### Errors: 
| Error Code | Error Description |
|------------|-------------------|
| 400 | Malformed request |
| 401 | Unauthorized the request requires user authentication (not logged in). |
| 403 | Forbidden. Also used for unauthorized requests such as improper OAuth 2.0 scopes or permissions issues. |
| 404 | Not found |
| 406 | Unacceptable content type. Client sent an accepts header for a content type which does not exist on the server. Body includes a list of acceptable content types, such as ?Unacceptable content type. Request resource as: application/json |
| 409 | A conflict needs to be resolved before the request can be made. |
| 422 | Invalid request. The request body is parse-able however with invalid content or there are issues with a rider's user account. |
| 429 | Too Many Requests. Rate limited. |
| 500 | Internal Server Error. |





### <a name="delete_request_cancel_async"></a>![Method: ](http://apidocs.io/img/method.png "com.uber.api.controllers.APIController.deleteRequestCancelAsync") deleteRequestCancelAsync

> Cancel an ongoing Request on behalf of a rider.

```java
void deleteRequestCancelAsync(
        final String requestId,
        final APICallBack<Object> callBack)
```

#### Parameters: 

| Parameter | Tags | Description |
|-----------|------|-------------|
| requestId |  ``` Required ```  | Unique identifier representing a Request. |



#### Example Usage:
```java
String requestId = "request_id";
// Invoking the API call with sample inputs
client.deleteRequestCancelAsync(requestId, new APICallBack<void>() {
    public void onSuccess(HttpContext context, void response) {
        // TODO success callback handler
    }
    public void onFailure(HttpContext context, Throwable error) {
        // TODO failure callback handler
    }
});

```



#### Errors: 
| Error Code | Error Description |
|------------|-------------------|
| 400 | Malformed request. |
| 401 | Unauthorized the request requires user authentication (not logged in). |
| 403 | Forbidden. Also used for unauthorized requests such as improper OAuth 2.0 scopes or permissions issues. |
| 404 | Not found |
| 406 | Unacceptable content type. Client sent an accepts header for a content type which does not exist on the server. Body includes a list of acceptable content types, such as ?Unacceptable content type. Request resource as: application/json. |
| 409 | A conflict needs to be resolved before the request can be made |
| 422 | Invalid request. The request body is parse-able however with invalid content or there are issues with a rider's user account. |
| 429 | Too Many Requests. Rate limited. |
| 500 | Internal Server Error |





### <a name="get_request_map_async"></a>![Method: ](http://apidocs.io/img/method.png "com.uber.api.controllers.APIController.getRequestMapAsync") getRequestMapAsync

> Get a map with a visual representation of a Request.

```java
void getRequestMapAsync(
        final String requestId,
        final APICallBack<RequestMapResponse> callBack)
```

#### Parameters: 

| Parameter | Tags | Description |
|-----------|------|-------------|
| requestId |  ``` Required ```  | Unique identifier representing a Request. |



#### Example Usage:
```java
String requestId = "request_id";
// Invoking the API call with sample inputs
client.getRequestMapAsync(requestId, new APICallBack<RequestMapResponse>() {
    public void onSuccess(HttpContext context, RequestMapResponse response) {
        // TODO success callback handler
    }
    public void onFailure(HttpContext context, Throwable error) {
        // TODO failure callback handler
    }
});

```



#### Errors: 
| Error Code | Error Description |
|------------|-------------------|
| 400 | Malformed request. |
| 401 | Unauthorized the request requires user authentication (not logged in). |
| 403 | Forbidden. Also used for unauthorized requests such as improper OAuth 2.0 scopes or permissions issues |
| 404 | Not found |
| 406 | Unacceptable content type. Client sent an accepts header for a content type which does not exist on the server. Body includes a list of acceptable content types, such as ?Unacceptable content type. Request resource as: application/json. |
| 409 | A conflict needs to be resolved before the request can be made. |
| 422 | Invalid request. The request body is parse-able however with invalid content or there are issues with a rider's user account. |
| 429 | Too Many Requests. Rate limited. |
| 500 | Internal Server Error. |





### <a name="get_price_estimates_async"></a>![Method: ](http://apidocs.io/img/method.png "com.uber.api.controllers.APIController.getPriceEstimatesAsync") getPriceEstimatesAsync

> The Price Estimates endpoint returns an estimated price range for each product offered at a given location. The price estimate is provided as a formatted string with the full price range and the localized currency symbol.

```java
void getPriceEstimatesAsync(
        final GetPriceEstimatesInput input,
        final APICallBack<PriceEstimateCollection> callBack)
```

#### Parameters: 

| Parameter | Tags | Description |
|-----------|------|-------------|
| endLatitude |  ``` Required ```  | Latitude component of end location. |
| endLongitude |  ``` Required ```  | Longitude component of end location. |
| startLatitude |  ``` Required ```  | Latitude component of start location. |
| startLongitude |  ``` Required ```  | Longitude component of start location. |



#### Example Usage:
```java
GetPriceEstimatesInput collect = new GetPriceEstimatesInput();

double endLatitude = 180.674409941153;
collect.setEndLatitude(endLatitude);

double endLongitude = 180.674409941153;
collect.setEndLongitude(endLongitude);

double startLatitude = 180.674409941153;
collect.setStartLatitude(startLatitude);

double startLongitude = 180.674409941153;
collect.setStartLongitude(startLongitude);

// Invoking the API call with sample inputs
client.getPriceEstimatesAsync(collect, new APICallBack<PriceEstimateCollection>() {
    public void onSuccess(HttpContext context, PriceEstimateCollection response) {
        // TODO success callback handler
    }
    public void onFailure(HttpContext context, Throwable error) {
        // TODO failure callback handler
    }
}
);

```



#### Errors: 
| Error Code | Error Description |
|------------|-------------------|
| 400 | Malformed request. |
| 401 | Unauthorized the request requires user authentication (not logged in). |
| 403 | Forbidden. Also used for unauthorized requests such as improper OAuth 2.0 scopes or permissions issues. |
| 404 | Not found. |
| 406 | Unacceptable content type. Client sent an accepts header for a content type which does not exist on the server. Body includes a list of acceptable content types: ?Unacceptable content type. Request resource as: application/json, etc. |
| 422 | Invalid request. The request body is parse-able however with invalid content. |
| 429 | Too Many Requests. Rate limited. |
| 500 | Internal Server Error. |





### <a name="get_time_estimates_async"></a>![Method: ](http://apidocs.io/img/method.png "com.uber.api.controllers.APIController.getTimeEstimatesAsync") getTimeEstimatesAsync

> The Time Estimates endpoint returns ETAs for all products offered at a given location, with the responses expressed as integers in seconds. We recommend that this endpoint be called every minute to provide the most accurate, up-to-date ETAs.

```java
void getTimeEstimatesAsync(
        final GetTimeEstimatesInput input,
        final APICallBack<TimeEstimateCollection> callBack)
```

#### Parameters: 

| Parameter | Tags | Description |
|-----------|------|-------------|
| startLatitude |  ``` Required ```  | Latitude component of the start location |
| startLongitude |  ``` Required ```  | Longitude component of the start location |
| customerUuid |  ``` Optional ```  | The customer id interested in estimate |
| productId |  ``` Optional ```  | Id of the requested product |



#### Example Usage:
```java
GetTimeEstimatesInput collect = new GetTimeEstimatesInput();

double startLatitude = 180.674409941153;
collect.setStartLatitude(startLatitude);

double startLongitude = 180.674409941153;
collect.setStartLongitude(startLongitude);

String customerUuid = "customer_uuid";
collect.setCustomerUuid(customerUuid);

String productId = "product_id";
collect.setProductId(productId);

// Invoking the API call with sample inputs
client.getTimeEstimatesAsync(collect, new APICallBack<TimeEstimateCollection>() {
    public void onSuccess(HttpContext context, TimeEstimateCollection response) {
        // TODO success callback handler
    }
    public void onFailure(HttpContext context, Throwable error) {
        // TODO failure callback handler
    }
}
);

```



#### Errors: 
| Error Code | Error Description |
|------------|-------------------|
| 400 | Malformed request. |
| 401 | Unauthorized the request requires user authentication (not logged in). |
| 403 | Forbidden. Also used for unauthorized requests such as improper OAuth 2.0 scopes or permissions issues. |
| 404 | Not found. |
| 406 | Unacceptable content type. Client sent an accepts header for a content type which does not exist on the server. Body includes a list of acceptable content types: ?Unacceptable content type. Request resource as: application/json, etc. |
| 422 | Invalid request. The request body is parse-able however with invalid content. |
| 429 | Too Many Requests. Rate limited. |
| 500 | Internal Server Error. |





### <a name="get_user_activity_v11_async"></a>![Method: ](http://apidocs.io/img/method.png "com.uber.api.controllers.APIController.getUserActivityV11Async") getUserActivityV11Async

> The User Activity endpoint returns data about a user's lifetime activity with Uber. The response will include pickup locations and times, dropoff locations and times, the distance of past requests, and information about which products were requested.

```java
void getUserActivityV11Async(
        final GetUserActivityV11Input input,
        final APICallBack<UserActivity> callBack)
```

#### Parameters: 

| Parameter | Tags | Description |
|-----------|------|-------------|
| limit |  ``` Required ```  | Number of items to return for pagging |
| offset |  ``` Required ```  | Page offset for pagging |



#### Example Usage:
```java
GetUserActivityV11Input collect = new GetUserActivityV11Input();

int limit = 180;
collect.setLimit(limit);

int offset = 180;
collect.setOffset(offset);

// Invoking the API call with sample inputs
client.getUserActivityV11Async(collect, new APICallBack<UserActivity>() {
    public void onSuccess(HttpContext context, UserActivity response) {
        // TODO success callback handler
    }
    public void onFailure(HttpContext context, Throwable error) {
        // TODO failure callback handler
    }
}
);

```



#### Errors: 
| Error Code | Error Description |
|------------|-------------------|
| 400 | Malformed request. |
| 401 | Unauthorized the request requires user authentication (not logged in). |
| 403 | Forbidden. Also used for unauthorized requests such as improper OAuth 2.0 scopes or permissions issues. |
| 404 | Not found. |
| 406 | Unacceptable content type. Client sent an accepts header for a content type which does not exist on the server. Body includes a list of acceptable content types: ?Unacceptable content type. Request resource as: application/json, etc. |
| 422 | Invalid request. The request body is parse-able however with invalid content. |
| 429 | Too Many Requests. Rate limited. |
| 500 | Internal Server Error. |





### <a name="get_product_detail_by_id_async"></a>![Method: ](http://apidocs.io/img/method.png "com.uber.api.controllers.APIController.getProductDetailByIDAsync") getProductDetailByIDAsync

> Get product details w.r.t id

```java
void getProductDetailByIDAsync(
        final String productId,
        final APICallBack<Product> callBack)
```

#### Parameters: 

| Parameter | Tags | Description |
|-----------|------|-------------|
| productId |  ``` Required ```  | Unique identifier representing a specific product for a given latitude & longitude. For example, uberX in San Francisco will have a different product_id than uberX in Los Angeles. |



#### Example Usage:
```java
String productId = "product_id";
// Invoking the API call with sample inputs
client.getProductDetailByIDAsync(productId, new APICallBack<Product>() {
    public void onSuccess(HttpContext context, Product response) {
        // TODO success callback handler
    }
    public void onFailure(HttpContext context, Throwable error) {
        // TODO failure callback handler
    }
});

```





### <a name="get_request_details_async"></a>![Method: ](http://apidocs.io/img/method.png "com.uber.api.controllers.APIController.getRequestDetailsAsync") getRequestDetailsAsync

> Get the real time status of an ongoing trip that was created using the Ride Request endpoint.

```java
void getRequestDetailsAsync(
        final String requestId,
        final APICallBack<RequestDetailsCollections> callBack)
```

#### Parameters: 

| Parameter | Tags | Description |
|-----------|------|-------------|
| requestId |  ``` Required ```  | TODO: Add a parameter description |



#### Example Usage:
```java
String requestId = "request_id";
// Invoking the API call with sample inputs
client.getRequestDetailsAsync(requestId, new APICallBack<RequestDetailsCollections>() {
    public void onSuccess(HttpContext context, RequestDetailsCollections response) {
        // TODO success callback handler
    }
    public void onFailure(HttpContext context, Throwable error) {
        // TODO failure callback handler
    }
});

```



#### Errors: 
| Error Code | Error Description |
|------------|-------------------|
| 400 | Malformed request. |
| 401 | Unauthorized the request requires user authentication (not logged in). |
| 403 | Forbidden. Also used for unauthorized requests such as improper OAuth 2.0 scopes or permissions issues. |
| 404 | Not found. |
| 406 | Unacceptable content type. Client sent an accepts header for a content type which does not exist on the server. Body includes a list of acceptable content types, such as ?Unacceptable content type. Request resource as: application/json. |
| 409 | A conflict needs to be resolved before the request can be made. |
| 422 | Invalid request. The request body is parse-able however with invalid content or there are issues with a rider's user account. |
| 429 | Too Many Requests. Rate limited. |
| 500 | Internal Server Error |





### <a name="get_products_types_async"></a>![Method: ](http://apidocs.io/img/method.png "com.uber.api.controllers.APIController.getProductsTypesAsync") getProductsTypesAsync

> The Products endpoint returns information about the Uber products offered at a given location. The response includes the display name and other details about each product, and lists the products in the proper display order.

```java
void getProductsTypesAsync(
        final GetProductsTypesInput input,
        final APICallBack<ProductCollection> callBack)
```

#### Parameters: 

| Parameter | Tags | Description |
|-----------|------|-------------|
| latitude |  ``` Required ```  | Latitude component of location. |
| longitude |  ``` Required ```  | Longitude component of location. |



#### Example Usage:
```java
GetProductsTypesInput collect = new GetProductsTypesInput();

double latitude = 180.674409941153;
collect.setLatitude(latitude);

double longitude = 180.674409941153;
collect.setLongitude(longitude);

// Invoking the API call with sample inputs
client.getProductsTypesAsync(collect, new APICallBack<ProductCollection>() {
    public void onSuccess(HttpContext context, ProductCollection response) {
        // TODO success callback handler
    }
    public void onFailure(HttpContext context, Throwable error) {
        // TODO failure callback handler
    }
}
);

```



#### Errors: 
| Error Code | Error Description |
|------------|-------------------|
| 400 | Malformed request. |
| 401 | Unauthorized the request requires user authentication (not logged in). |
| 403 | Forbidden. Also used for unauthorized requests such as improper OAuth 2.0 scopes or permissions issues. |
| 404 | Not found. |
| 406 | Unacceptable content type. Client sent an accepts header for a content type which does not exist on the server. Body includes a list of acceptable content types: ?Unacceptable content type. Request resource as: application/json, etc. |
| 422 | Invalid request. The request body is parse-able however with invalid content. |
| 429 | Too Many Requests. Rate limited. |
| 500 | Internal Server Error. |





### <a name="get_user_profile_async"></a>![Method: ](http://apidocs.io/img/method.png "com.uber.api.controllers.APIController.getUserProfileAsync") getUserProfileAsync

> The User Profile endpoint returns information about the Uber user that has authorized with the application.

```java
void getUserProfileAsync(final APICallBack<UserProfile> callBack)
```

#### Example Usage:
```java
// Invoking the API call with sample inputs
client.getUserProfileAsync(new APICallBack<UserProfile>() {
    public void onSuccess(HttpContext context, UserProfile response) {
        // TODO success callback handler
    }
    public void onFailure(HttpContext context, Throwable error) {
        // TODO failure callback handler
    }
});

```



#### Errors: 
| Error Code | Error Description |
|------------|-------------------|
| 400 | Malformed request. |
| 401 | Unauthorized the request requires user authentication (not logged in). |
| 403 | Forbidden. Also used for unauthorized requests such as improper OAuth 2.0 scopes or permissions issues. |
| 404 | Not found. |
| 406 | Unacceptable content type. Client sent an accepts header for a content type which does not exist on the server. Body includes a list of acceptable content types: ?Unacceptable content type. Request resource as: application/json, etc. |
| 422 | Invalid request. The request body is parse-able however with invalid content. |
| 429 | Too Many Requests. Rate limited. |
| 500 | Internal Server Error. |





[Back to List of Controllers](#list_of_controllers)

