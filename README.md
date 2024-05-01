# restassuredAPI

  1. // Basic Authentication:

  given()
    .auth()
    .basic(username, password)
.when()
    .get("/endpoint")
.then()
    .statusCode(200);

 ----------------------------------------

2. // OAuth 1.0a Authentication:

 given()
 .auth()
 .oauth(consumerKey, consumerSecret, accessToken, accessTokenSecret)
 .when()
 .get("/endpoint")
 .then()
 .statusCode(200);

 --------------------------------------------------

 3. // OAuth 2.0 Authentication:

 given()
 .auth()
 .oauth2(accessToken)
 .when()
 .get("/endpoint")
 .then()
 .statusCode(200);


 ---------------------------------------------

4. //Bearer Token Authentication:

 given()
 .header("Authorization", "Bearer " + token)
 .when()
 .get("/endpoint")
 .then()
 .statusCode(200);


 --------------------------------------------
5. // Form-based Authentication:

 given()
 .formParam("username", username)
 .formParam("password", password)
 .when()
 .post("/login")
 .then()
 .statusCode(200);

----------------------------------------------------------

 6. //JWT Authentication:

 given()
 .header("Authorization", "Bearer " + jwtToken)
 .when()
 .get("/endpoint")
 .then()
 .statusCode(200);




