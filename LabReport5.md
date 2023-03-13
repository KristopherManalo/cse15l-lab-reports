# Lab Report 5 - Lab Report 4 REDUX
## Automization
The solution to make it more streamline is to use a bash script.

Pros:
- All commands will run from in order from a single execution
- Faster

Cons:
- Much more setup time
- Slightly more annoying to edit
    - For example, if there is an error in the bash script, would require to open the file and find the line where the error is happening rather then just modifying the command that errored at command line.

## The original steps
1. Log onto ieng6
2. Clone the fork onto ieng6
3. Run the tests
4. Correct the code
5. Running the tests with corrected code
6. Uploading to GitHub

## Using a bash script
### 1. Making a bash script
In a terminal, we must first touch the bash script file.
Run `touch run.sh` in a terminal
### 2. Adding the commands to the bash script
For the most part each command will stay the same as the previous execution of Lab Report 4 except for one exception: correcting the code.
To work in a bash script without any issue, we will use the `sed` command rather than using a text editor to manually edit it. In this instance, to correct the code, the command to run is `sed 's/index1/index2/9' ListExamples.java`

The full bash script will be
```bash
# Step 2 - Cloning the fork
git clone git@github.com:KristopherManalo/lab7.git

# Step 3 - Running the tests
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar ListExamples.java ListExamplesTests.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar  org.junit.runner.JUnitCore ListExamplesTests

# Step 4 - Correcting the code
sed 's/index1/index2/9' ListExamples.java

# Step 5 - Rerunning the tests
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar ListExamples.java ListExamplesTests.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar  org.junit.runner.JUnitCore ListExamplesTests

# Step 6 - Uploading to GitHub
git add *.java
git commit -m "Updated ListExamples.java"
git push
```

### Prep is complete

##
To complete the tasks of Lab Report 4, all that is required now, instead of the previous 6 steps is 2.
1. Log into ieng6
2. Run `bash run.sh`
