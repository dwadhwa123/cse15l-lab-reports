grade.sh

```
# Create your grading script here
# set -e
rm -rf student-submission
git clone $1 student-submission
cp TestListExamples.java student-submission/
cp -r hamcrest-core-1.3.jar student-submission/
cp -r junit-4.13.2.jar student-submission/
if [ ! -e student-submission/ListExamples.java ] 
    then 
        echo "Student submission does not contain proper files: 0 points" 
        exit 1
fi

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
