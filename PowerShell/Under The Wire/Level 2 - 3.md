
The password for Century3 is the combination of the name of a specific built-in cmdlet in PowerShell and the name of a file located on the desktop.

Here are the rules for forming the password:

- Take the name of the cmdlet that performs a function similar to `wget` within PowerShell.
- Append the name of the file on the desktop to the cmdlet name without any spaces.
- Make sure the entire password is in lowercase, regardless of how it appears on the screen.

For example, if the cmdlet name is "get-web" and the file on the desktop is named "1234", the resulting password would be "get-web1234".

Remember to follow these guidelines to create the correct password for Century3.

## Solution

To find the next password you have to look into the files using the following command.
```
ls
```

## Result output command

```
PS C:\users\century2\desktop> ls


    Directory: C:\users\century2\desktop


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        8/30/2018   3:29 AM            693 443
```

## Conclusion

After running the `ls` command we can find in the results under `Name` the number `443` that we need to complete the password.

To complete the password we need to use cmdlet `Invoke-WebRequest` which is similar to wget used in Linux.

*The `Invoke-WebRequest` is used to retrieve data from a web server*

#### Result

```
password becomes: invoke-webrequest443
user login command: ssh century3@century.underthewire.tech
```

### Here's an explanation of the command and its logic:

Example:
```
Invoke-WebRequest -Uri "https://example.com" -Method GET
```

1. **Command Name**: `Invoke-WebRequest`
   - This is the name of the command or cmdlet in PowerShell that you use to perform web requests.

2. **Parameters**:
   - `-Uri`: This parameter specifies the web address or URL of the web resource you want to access. In our example, the URI is `"https://example.com"`, which is the website we want to retrieve data from.
   - `-Method`: This optional parameter specifies the HTTP method to use for the request. In our example, the method is `"GET"`, which retrieves the content of the specified URI.

3. **Execution**:
   - When you execute the `Invoke-WebRequest` command, PowerShell sends an HTTP GET request to the specified URL, which is `"https://example.com"` in our example.
   - The command waits for the server to process the request and retrieves the response from the server.

4. **Response**:
   - The response from the server is an object that contains various properties and methods.
   - In our example, we can access properties of the response object to gather information about the request:
     - `StatusCode`: The HTTP status code of the response. For example, if the status code is `200`, it means the request was successful.
     - `Headers`: The headers sent by the server in the response, such as content type or server information.
     - `Content`: The content of the response, which can be HTML, JSON, or other data formats. This is the data we retrieve from the web resource.
     - `RawContent`: The raw content of the response, including any binary data if applicable.
     - `Cookies`: Any cookies sent by the server as part of the response.

So, in the example we provided, the `Invoke-WebRequest` command is used to send an HTTP GET request to `"https://example.com"`. It retrieves the content of the web page and returns the response from the server, which can be accessed through the properties of the response ob

