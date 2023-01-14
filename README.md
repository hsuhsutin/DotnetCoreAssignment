# DotnetCoreAssignment
================Download and Install required  =========

1. We need to download .NET Core SDK 3.1 and install via the link 
   https://dotnet.microsoft.com/en-us/download/dotnet/3.1
   After you've install .NET Core SDK, you can check using Command prompt with the command : dotnet --version -| Enter
   
2. As IDE, can use Visual Studio 2019 or Visual Studio Code 

3. Download Postman and install to test API.
   https://www.postman.com/downloads/
   
================ Software Version ===========

1. .netcore SDK version : 3.1.426


================ Procedure to run the project as local ===============

1. Download and Unzip the attached zip file,"TestProject" and place under D:/

2. Open the project using the Visual Studio 2019 or Visual Studio Code 

3. To Build the Project , Open the terminal ( Ctrl +Shift + ~ ) and run the command to build the application, "dotnet build" -| Enter

4. To Run the Project, in the same terminal, "dotnet run" -| Enter

5. After Application run successfully, can copy the URL "http://localhost:8888" and paste in Crome browser " http://localhost:8888/sum?upto=1" , will see the response 



================ Test for Request method ==========

1. In postman Application, choose various request methods, if we choose other than Get method, will get 405 Method not allow error


=============== Test for Data Type, minimum and maximum value ============
In Chrome browser or Postman method, type the URL like http://localhost:8888/sum?upto=abc 

1. Pass the string value "abc" in Query String, 400 Bad Request will be returned with the following response.
   {
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "|bf96f2a-4806e4eee23d070d.",
    "errors": {
        "upto": [
            "The value 'hu' is not valid."
        ]
    }
}
2. Pass no value in query string, it take as value "0" in Query String "http://localhost:8888/sum?upto", 400 Bad Request will be returned with the following response.
   {
    "success": false,
    "value": 0,
    "error": "minium value should be at lease 1"
}
3. Pass the integer value "1001" in Query String "http://localhost:8888/sum?upto=1001", 400 Bad Request will be returned with the following response.
{
    "success": false,
    "value": 0,
    "error": "value should not be more than 1000"
}

=============== Test with Right Query String Parameter ============
1. Pass the integer value "1" in Query String "http://localhost:8888/sum?upto=1", 200 OK will be returned with the following response.
{
    "success": true,
    "value": 1,
    "error": "null"
}
2. Pass the integer value "3" in Query String "http://localhost:8888/sum?upto=3", 200 OK will be returned with the following response.
{
    "success": true,
    "value": 6,
    "error": "null"
}
3. Pass the integer value "1000" in Query String "http://localhost:8888/sum?upto=1000", 200 OK will be returned with the following response.
{
    "success": true,
    "value": 500500,
    "error": "null"
}
