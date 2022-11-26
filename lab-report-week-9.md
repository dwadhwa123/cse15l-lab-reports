grade.sh

```
# Create your grading script here
# set -e
rm -rf student-submission
git clone $1 student-submission
if [ ! -e student-submission/ListExamples.java ] 
    then 
        echo "Student submission does not have the ListExamples file in the correct path or at all: 0 points" 
        exit 1
fi

cp TestListExamples.java student-submission/
cp -r hamcrest-core-1.3.jar student-submission/
cp -r junit-4.13.2.jar student-submission/
cd student-submission 

javac -cp .:lib/hamcrest-core-1.3.jar:list-examples-grader/lib/junit-4.13.2.jar *.java 2> err.txt
if [ ! $? -eq 0 ]
    then   
        echo "Compiler error: 1 point"
        exit 1
fi

java -cp .:lib/hamcrest-core-1.3.jar:list-examples-grader/lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples > results.txt
grep -q "failure" results.txt && echo $
if [ ! $? -eq 0 ]
    then 
        echo "All tests passed: 5 points"

echo "One or more tests failed but compiled succesfully: 2 points "
exit 0
```
![Screenshot](https://user-images.githubusercontent.com/114367462/204074092-222b7824-bf02-4f82-a125-5264a9f8aed7.png)
![Screenshot](https://user-images.githubusercontent.com/114367462/204074094-9160f7e1-45da-4aca-b1a9-da41080c4f35.png)
![Screenshot](https://user-images.githubusercontent.com/114367462/204074213-eb50052e-cc33-46ae-9fb3-47f848c6cdb9.png)




For the second screenshot, here is the trace.

* Line 3: standard output is out.txt and the standard error is err.txt; return code of 0
* Line 4: standard output is git.txt and the standard error is git-err.txt; return code of 0
* Line 5: if statement is true as for this submission there is no student-submission file
* Line 7: return code of 0
* Line 8: exit code of 1 
* Rest of the lines don't run

