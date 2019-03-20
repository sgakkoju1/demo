# demo
demo project


----
https://www.toolsqa.com/rest-assured/post-request-using-rest-assured/



@Test
public void RegistrationSuccessful()
{ 
 RestAssured.baseURI ="http://restapi.demoqa.com/customer";
 RequestSpecification request = RestAssured.given();
 
 JSONObject requestParams = new JSONObject();
 requestParams.put("FirstName", "Virender"); // Cast
 requestParams.put("LastName", "Singh");
 requestParams.put("UserName", "sdimpleuser2dd2011");
 requestParams.put("Password", "password1");
 
 requestParams.put("Email",  "sample2ee26d9@gmail.com");
 request.body(requestParams.toJSONString());
 Response response = request.post("/register");
 
 int statusCode = response.getStatusCode();
 Assert.assertEquals(statusCode, "201");
 String successCode = response.jsonPath().get("SuccessCode");
 Assert.assertEquals( "Correct Success code was returned", successCode, "OPERATION_SUCCESS");
}
