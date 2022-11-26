grade.sh

```
# Create your grading script here
# set -e
rm -rf student-submission
git clone $1 student-submission
if [ ! -e student-submission/ListExamples.java ] 
    then 
        echo "Student submission does not contain proper files: 0 points" 
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
grep -q "OK" results.txt && echo $
if [ ! $? -eq 0 ]
    then 
        echo "Test Failed: 2 points "

echo "Test passed: 5 points"
exit 0
```
![Screenshot](https://user-images.githubusercontent.com/114367462/204072847-3d30591c-d451-452a-8c8b-621067130860.png)
![Screenshot](https://user-images.githubusercontent.com/114367462/204072849-dd819b55-2b9a-4e5d-a09c-cb05a31e7b01.png)
![Screenshot](https://user-images.githubusercontent.com/114367462/204072850-255f5272-4b19-4b97-9079-9fe3059db6d9.png)

For the first screenshot, here is the trace

Line 3: standard output is out.txt and the standard error is err.txt; return code of 0
Line 4: standard output is git.txt and the standard error is git-err.txt; return code of 0
Line 5: if statement is true as for this submission there is no student-submission file
Line 7: return code of 0
Line 8: exit code of 1 
Rest of the lines don't run

