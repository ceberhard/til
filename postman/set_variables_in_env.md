## How to set postman variables in an environment dynamically

In order to set variables after a request runs, you need to use the "Tests" tab and enter javascript:
```javascript
var jsonData = JSON.parse(responseBody);
var token = jsonData.api_token;
var enc_token = window.btoa(token);
postman.setEnvironmentVariable("api_token", enc_token);
```

If you need to manipulate the variable before running the request, use the "Pre-request Script" tab:
```javascript
var creds = environment["user_creds"]
var enc_creds = window.btoa(creds);
postman.setEnvironmentVariable("enc_creds", enc_creds);
```

*Notice the "responseBody" and "environment" variables, as well as the postman.setEnvironmentVariable method*

### References
https://www.getpostman.com/docs/environments

http://blog.getpostman.com/2014/01/27/extracting-data-from-responses-and-chaining-requests/
