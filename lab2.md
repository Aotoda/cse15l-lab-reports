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

### Part 2: reverseInPlace
#### Failure-inducing Test
```
  @Test 
	public void testReverseInPlacex() {
    int[] input1 = { 3 , 2 , 1 , 0 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 0, 1 , 2 , 3 }, input1);
	}
```

#### Non-failure-inducing test
```
	@Test 
	public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
	}
```

#### Symptoms
![image](https://user-images.githubusercontent.com/116617731/215539619-8d241d9c-08ef-4023-b7d4-8a39443f2b23.png)
(Failure-inducing)

![image](https://user-images.githubusercontent.com/116617731/215539460-0d8cb826-e32b-406f-930c-0785077c4fa0.png)
(Non-failure-inducing)

#### Bug and Fix
Old code:
```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

New code:
```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length/2; i += 1) {
      int hold = arr[i];
      arr[i] = arr[arr.length-1-i];
      arr[arr.length-1-i] = hold;
    }
  }
```

The new code adds a "hold" variable which can hold the value of the left-of-center variables as they are overwritten so that they can be accordingly assigned to the right-of-center variables.

### Part 3
I had no idea how to manipulate or use let alone create localhost servers before the last few labs. Now I know the basics of how they work, and can create and modify them myself in java files.
