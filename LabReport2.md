# CSE15l Lab Report 2
## StringServer.java
```
  1 import java.io.IOException;
  2 import java.net.URI;
  3
  4 class Handler implements URLHandler {
  5     String returnString = "";
  6     public String handleRequest(URI url) {
  7     |   if(url.getPath().contains("/add-message")) {
  8     |   |   String[] parameters = url.getQuery().split("=");
  9     |   |   if(parameters[0].equals("s")) {
 10     |   |   |   returnString = returnString + parameters[1] + "\n";
 11     |   |   |   return String.format(returnString);
 12     |   |   }
 13     |   }
 14     return "404 Not Found";
 15     }
 16 }
 17
 18 class StringServer {
 19     public static void main(String[] args) throws IOException {
 20     |   if(args.length == 0) {
 21     |   System.out.println("Missing port number: Insert number 1024 to 49151");
 22     |   return;
 23     |   }
 24     |   int port = Integer.parseInt(args[0]);
 25     |   Server.start(port, new Handler());
 26     }
 27 }
```
![Image](https://github.com/KristopherManalo/cse15l-lab-reports/blob/cdf2fac8c931a93bf6dc2da7660542f5662d0f27/lab2Images/lab2image1.png)
![Image](https://github.com/KristopherManalo/cse15l-lab-reports/blob/cdf2fac8c931a93bf6dc2da7660542f5662d0f27/lab2Images/lab2image2.png)

