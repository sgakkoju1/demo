# demo
demo project

Prior implementing the harness. We need to engage with dev team/architect, Business User and qa to create Test Approach and have team agreements. 
- what type of data can be used to test
- What volume of data should be used 
- Identify the usage of application when in prod(wrt to number is users accessing)
- Coverage of Positive and Negative scenarios
- Identify the Date1 scenarios
- Identify Date roll scenarios
- Identity High Availability and Fault Tolerance scenarios 
- Identify failover scenarios
- Identify peak loads and simulate through harness 



----
https://www.toolsqa.com/rest-assured/post-request-using-rest-assured/

https://stackoverflow.com/questions/4205980/java-sending-http-parameters-via-post-method-easily


// send params with Hash Map
    HashMap<String, String> params = new HashMap<String, String>();
    params.put("email","me@example.com");
    params.put("password","12345");

    //server url
    String url = "http://www.example.com";

    // static class "HttpUtility" with static method "newRequest(url,method,callback)"
    HttpUtility.newRequest(url,HttpUtility.METHOD_POST,params, new HttpUtility.Callback() {
        @Override
        public void OnSuccess(String response) {
        // on success
           System.out.println("Server OnSuccess response="+response);
        }
        @Override
        public void OnError(int status_code, String message) {
        // on error
              System.out.println("Server OnError status_code="+status_code+" message="+message);
        }
    });
