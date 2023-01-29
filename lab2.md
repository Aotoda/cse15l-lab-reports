## Lab Report 2
### Part 1
#### `StringServer.java` code
```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    String message = "";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            System.out.println(message);
            return message;
        } else {
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/add-message")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    message = message.concat(parameters[1]);
                    System.out.println(message);
                    return message;
                }
            }
            return "404 Not Found!";
        }
    }
}

class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}

```

#### `/add-message`
![image](https://user-images.githubusercontent.com/116617731/215346410-2f04494e-844c-4591-a842-0af1e0b0409f.png)
![image](https://user-images.githubusercontent.com/116617731/215346430-bfd1afe4-430a-45eb-bf8f-951e60e86e43.png)

Both /add-message calls are processed by the handleRequest(url) method which in turn use the .getPath() method, comparing the returned path using the .equals("/") and then .contains("/add-message") methods. The the parameters are obtained using the .getQuery().split("=") and .equals("s") methods. Splitting the parameters by the "=" sign, the message is isolated and then displayed using the .concat(message) and println() methods.

The value of the string changes when the parameter is concatenated to it to be displayed.

### Part 2
