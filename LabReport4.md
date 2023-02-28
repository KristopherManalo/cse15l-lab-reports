# Lab Report 4
## 1. Log onto ieng6
Type into terminal the following:
`ssh cs15lwi23aud@ieng6.ucsd.edu`
- Normally, this would require a password quiry, but by generating a SSH key, you can circumvent this requirement
![Image](https://github.com/KristopherManalo/cse15l-lab-reports/blob/2860c0f4e7393cb2f0b06edc71f0f79160a8805d/labReport4Images/Step%204.png)
## 2. Clone the fork onto ieng6
Type into terminal the following:
`git clone git@github.com:KristopherManalo/lab7.git`
- The command is using the ssh option of cloning from github
![Image](https://github.com/KristopherManalo/cse15l-lab-reports/blob/9a47ca897562bd87463505739d00fd0f4b26590f/labReport4Images/Step%205.png)
## 3. First time running the tests
Type into terminal the following:
```
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar ListExamples.java ListExamplesTests.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar  org.junit.runner.JUnitCore ListExamplesTests
```
These commands will run the attached JUnit Tests onto the code.
One of the tests will fail due to bugged implementation.
![Image](https://github.com/KristopherManalo/cse15l-lab-reports/blob/9a47ca897562bd87463505739d00fd0f4b26590f/labReport4Images/Step6.png)
## 4. Correcting the code
### Opening the Editor
![Image](https://github.com/KristopherManalo/cse15l-lab-reports/blob/9a47ca897562bd87463505739d00fd0f4b26590f/labReport4Images/Step7.1.png)
### Navigating the Editor
![Image](https://github.com/KristopherManalo/cse15l-lab-reports/blob/9a47ca897562bd87463505739d00fd0f4b26590f/labReport4Images/Step7.2.png)
### Editing the Code
![Image](https://github.com/KristopherManalo/cse15l-lab-reports/blob/9a47ca897562bd87463505739d00fd0f4b26590f/labReport4Images/Step7.3.png)
### Exiting vim
## 5. Running the tests with corrected code
![Image](https://github.com/KristopherManalo/cse15l-lab-reports/blob/9a47ca897562bd87463505739d00fd0f4b26590f/labReport4Images/Step8.png)
## 6. Uploading to Github
![Image](https://github.com/KristopherManalo/cse15l-lab-reports/blob/9a47ca897562bd87463505739d00fd0f4b26590f/labReport4Images/Step9.png)
