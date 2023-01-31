# CSE15l Lab Report 2
## StringServer.java - Part 1
The following block is my implementation of two classes: Handler and StringServer.
```java
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
The following two images showcase two examples of the code being executed:
* The method acquires the path of the url, splits the path using delimiter "=" and adds from the url, anything after the "=" sign to the page's display.
* The variable returnString changes each request that doesn't result in an error, where a string from the url is appended to a new line of returnString. 
![Image](https://github.com/KristopherManalo/cse15l-lab-reports/blob/main/lab2Images/lab2image1.png?raw=true)
* The method being called is handleRequest.
* The relevant argument is the url of the page, where the path "/add-message?s=YOO" is being split, where "s" is parameters[0] and "YOO" is saved into parameters[1].
* The variable returnString is being appended with the value of parameters[1] and a new line.
![Image](https://github.com/KristopherManalo/cse15l-lab-reports/blob/main/lab2Images/lab2image2.png?raw=true)
* The method being called is handleRequest.
* The relevant argument is the url of the page, where the path "/add-message?s=MAMA" is being split, where "s" is parameters[0] and "MAMA" is saved into parameters[1].
* The variable returnString is being appended with the value of parameters[1] and a new line. The new value of return String is now:
```
YOO
MAMA
```
## JUNIT Bug Fix - Part 2
I chose to fix the bugs of averageWithoutLowest.
Failure inducing JUnit test:
```java
  @Test
  public void testAverage3() {
    double[] input6 = {1.0, 1.0};
    assertEquals(ArrayExamples.averageWithoutLowest(input6), 1.0, 0.1);
  }
```
Succesfful JUnit test:
```java
  @Test
  public void testAverage() {
    double[] input4 = {5,6,7,8,9};
    assertEquals(ArrayExamples.averageWithoutLowest(input4), 7.5, 0.01);
  }
```
### Symptom
The code skips all instances of the recorded value, therefore, if there are multiple instances of the same lowest value, all instances will be skipped instead of just one. 
Attempt to run the tests with the buggy code:
![Image](https://github.com/KristopherManalo/cse15l-lab-reports/blob/main/lab2Images/lab2bug.png?raw=true)
Code with bug:
```java
  static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { return 0.0; }
    double lowest = arr[0];
    for(double num: arr) {
      if(num < lowest) { lowest = num; }
    }
    double sum = 0;
    for(double num: arr) {
      if(num != lowest) { sum += num; }
    }
    return sum / (arr.length - 1);
  }
```
Code fixed, without bug:
```java
  static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { return 0.0; }
    double lowest = arr[0];
    for(double num: arr) {
      if(num < lowest) { lowest = num; }
    }
    double sum = 0;
    boolean skipped = false;
    for(double num: arr) {
      if(!(skipped) && num == lowest) {
        skipped = true;
        continue;
      }
      sum += num;
    }
    return sum / (arr.length - 1);
```
Running the tests after fixing the code:
![Image](https://github.com/KristopherManalo/cse15l-lab-reports/blob/main/lab2Images/lab2fix.png?raw=true)
### The Fix
The solution is to create a boolean value that represents a flag of whether the lowest value is skipped. Once it detects true, it will no longer skip any values, preventing situations where multiple instances of the same value are skipped.
## What I learned - Part 3
