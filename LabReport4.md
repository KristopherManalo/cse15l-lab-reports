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
Type into terminal the following:
`vim ListExamples.java`
This will open vim, a text editor
![Image](https://github.com/KristopherManalo/cse15l-lab-reports/blob/9a47ca897562bd87463505739d00fd0f4b26590f/labReport4Images/Step7.1.png)
### Navigating the Editor
On your keyboard press: `42j`
This will navigate you to 42 lines after your current, in this case, the 43 line.
![Image](https://github.com/KristopherManalo/cse15l-lab-reports/blob/9a47ca897562bd87463505739d00fd0f4b26590f/labReport4Images/Step7.2.png)
### Editing the Code
On your keyboard press: `w`
- This will move the cursor forward where it is before the word "index1" on line 43,
On your keyboard press: `dw`
- This will delete the word after your cursor.
On your keyboard press: `iindex2`
- The first i will put vim into insert mode and then type into text "index2" 
On your keybaord press: `<escape>`
- This will return you back to normal mode
![Image](https://github.com/KristopherManalo/cse15l-lab-reports/blob/9a47ca897562bd87463505739d00fd0f4b26590f/labReport4Images/Step7.3.png)
### Exiting vim
On your keyboard press: `:wq`
- The colon enters a command mode in the bottom of vim, the w writes the file and the q quits vim
## 5. Running the tests with corrected code
The code is now corrected so we run the JUnit tests again
Type into the terminal the following:
```
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar ListExamples.java ListExamplesTests.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar  org.junit.runner.JUnitCore ListExamplesTests
```
![Image](https://github.com/KristopherManalo/cse15l-lab-reports/blob/9a47ca897562bd87463505739d00fd0f4b26590f/labReport4Images/Step8.png)
## 6. Uploading to Github
Type into the terminal the following:
```
git add *.java
git commit -m "Updated ListExamples.java"
git push
```
- The first command will stage the changes done to all java files
- The second command will commit the changes and assert an update message
- The third command will push the changes to the github repository initially cloned from
![Image](https://github.com/KristopherManalo/cse15l-lab-reports/blob/9a47ca897562bd87463505739d00fd0f4b26590f/labReport4Images/Step9.png)

## The process is complete
