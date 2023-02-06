# Description

`HelloWorld_ErrorHandler` application is a demonstration of the possibilities of working on the IBM ACE bus version 12.0.5. It does not execute business functionality. 

The application receives data from client, and then returns "Hello"  + {*yourName*} string to the client in .json format and provides the following endpoint:

**`/acehelloworld/v3:`**

![Alt text](images/flowErrorHandler.png)

Using a *POST* method, it sends a data to the application and receives in response a string "Hello" + yourName. If the input data contains errors, the application sends an **error message** to the client through the error handling track. 


# Implementation

**`HelloWorld_ErrorHandler`**

![Alt text](images/flowErrorHandler.png)

The `Get the message` - HTTP Input node - receives the request with data containing a json object with key and value. The `CreatingMessage` compute node creates the message tree and message body:

![Alt text](images/compute.png)

 Finally, `Reply` sends the message to the client.

 If the input data contains errors, the application sends an **error message** to the client through `errorHandler` compute node to HTTP reply `ReplyError`:

![Alt text](images/computeNode.png) 

 # Format

 The app uses .json 