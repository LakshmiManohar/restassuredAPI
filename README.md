# restassuredAPI

  1. **Basic Authentication:** Basic authentication involves sending the username and password with each request. Rest Assured provides a simple way to set up basic authentication using the auth().basic() method. This method takes the username and password as parameters and automatically generates the required Authorization header.

  given()
    .auth()
    .basic(username, password)
.when()
    .get("/endpoint")
.then()
    .statusCode(200);

 ----------------------------------------

2. **OAuth 1.0a Authentication:** OAuth 1.0a is an authentication protocol that allows secure authorization in a standard way. Rest Assured provides support for OAuth 1.0a authentication using the auth().oauth() method. You need to provide the consumer key, consumer secret, access token, and access token secret.

 given()
 .auth()
 .oauth(consumerKey, consumerSecret, accessToken, accessTokenSecret)
 .when()
 .get("/endpoint")
 .then()
 .statusCode(200);

 --------------------------------------------------

 3. **OAuth 2.0 Authentication:** OAuth 2.0 is a widely-used authentication framework. Rest Assured allows OAuth 2.0 authentication using the auth().oauth2() method. You only need to provide the access token.

 given()
 .auth()
 .oauth2(accessToken)
 .when()
 .get("/endpoint")
 .then()
 .statusCode(200);


 ---------------------------------------------

4. **Bearer Token Authentication:** Bearer token authentication involves sending a token in the Authorization header with each request. Rest Assured enables bearer token authentication by adding the token directly to the Authorization header.

 given()
 .header("Authorization", "Bearer " + token)
 .when()
 .get("/endpoint")
 .then()
 .statusCode(200);


 --------------------------------------------
5. **Form-based Authentication:** Form-based authentication is commonly used with web applications. Rest Assured allows you to simulate form-based authentication by sending form parameters with a POST request.

 given()
 .formParam("username", username)
 .formParam("password", password)
 .when()
 .post("/login")
 .then()
 .statusCode(200);

----------------------------------------------------------

 6. **JWT Authentication:** JWT (JSON Web Token) is a compact, URL-safe means of representing claims to be transferred between two parties. Rest Assured allows JWT authentication by adding the token directly to the Authorization header.

 given()
 .header("Authorization", "Bearer " + jwtToken)
 .when()
 .get("/endpoint")
 .then()
 .statusCode(200);


----------------------------------------------------------
_**Parameters**_

**1. Query Parameters:** Query parameters are passed in the URL after the ? symbol. 
For example:

given()
    .queryParam("key1", "value1")
    .queryParam("key2", "value2")
.when()
    .get("/endpoint")
.then()
    .statusCode(200);

**2. Form Parameters:** Form parameters are used in HTTP POST requests with the application/x-www-form-urlencoded content type. 
For example:

given()
    .formParam("username", "user1")
    .formParam("password", "pass123")
.when()
    .post("/login")
.then()
    .statusCode(200);

**3.Path Parameters:** Path parameters are part of the URL path and are used to parameterize the endpoint. 
For example:

given()
    .pathParam("userId", 123)
.when()
    .get("/users/{userId}")
.then()
    .statusCode(200);

**4. Request Parameters:** Request parameters are used in HTTP GET requests to pass data in the URL. They are similar to query parameters. 
For example:

given()
    .param("search", "keyword")
.when()
    .get("/search")
.then()
    .statusCode(200);

**5. Multi-Value Parameters:** RestAssured supports passing multi-value parameters, such as multiple values for the same parameter key. 
For example:

given()
    .queryParams("key", "value1", "value2", "value3")
.when()
    .get("/endpoint")
.then()
    .statusCode(200);

