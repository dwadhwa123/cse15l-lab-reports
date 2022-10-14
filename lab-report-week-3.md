# CSE15 Week 3 Lab Report 

## Part 1

```
# code block
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;
class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    ArrayList<String> lst = new ArrayList<>();

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format("Size: %d", lst.size());
        } 
        else if (url.getPath().equals("/search")) {
            String[] parameters = url.getQuery().split("=");
            if(parameters[0].equals("s")){
                String r = "";
                for(String s: lst){
                    if(s.contains(parameters[1])){
                        r += s + " ";
                    }
                }
                return r;
            }    

        }
        else if (url.getPath().equals("/print")) {
                String r = "";
                for(String s: lst){
                        r += s + " ";
                }
                
                return r;
            }    
        else {
            if(url.getPath().contains("/add")){
                String[] parameters = url.getQuery().split("=");
                if(parameters[0].equals("s")){
                    lst.add(parameters[1]);
                    return String.format(lst.get(lst.size()-1) + " added");
                    }
                }
            }
            return "404 Not Found!";
        }
    }


class SearchEngine {
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
   
![Screenshot](https://user-images.githubusercontent.com/114367462/195739202-6a84a9c9-4fa1-447f-b761-3630c3f0b8de.png)

For this screenshot, the handleRequest method is called. Since the path begins with "/add", the final if statement in the method runs. The query is split by the equal sign and if the first element of the parameters method is an s, then the second element is added to the list(lst). The program prints out "apple added" to signify that the element has been added. 

![Screenshot](https://user-images.githubusercontent.com/114367462/195739209-7ff85880-c9e0-4b45-b814-531da3cfac83.png)

For this screenshot, the handleRequest method is called. Since the path begins with "/print", the second else if statement in the method runs. The query is split by the equal sign and if the first element of the parameters method is an s, then a for loop is used to print the elements of lst in the order in which they are added. The program prints out "apple water" to show the order of the elements. 

![Screenshot](https://user-images.githubusercontent.com/114367462/195739218-fd466d2c-95eb-4ef8-ac07-2741d93599d4.png)

For this screenshot, the handleRequest method is called. Since the path begins with "/search", the first else if statement in the method runs. The query is split by the equal sign and if the first element of the parameters method is an s, then a for loop is used to print the elements of lst that contain the second element passed into parameters(part after the equal sign). The program prints out "apple" to show that apple is the only string in lst that contains the substring "le". 

## Part 2

testInPlace method

Here are the tests that were ran to test the original code. There is one for an array with even indicies and one for an array with odd indices. The failure-inducing input is the array with length 4({3, 4, 5, 6}).

![Screenshot](https://user-images.githubusercontent.com/114367462/195694281-cd82474c-49a5-42dd-a535-e2baf4129889.png)

The symptom of the array call ArrayExamples.testInPlace({3, 4, 5, 6}) returns {6, 5, 5, 6} rather than {6, 5, 4, 3). The second half remains unchanged.

![Screenshot](https://user-images.githubusercontent.com/114367462/195695276-c0abab23-3d83-41a6-9fb6-11c10bf174f4.png)

Here is the original code. The values in the first half of the array will change correctly to the corresponding values in the second half of the array. However, when it comes to changing the second half of the array, the original values from the first half of the array are not accesible anymore. These values are what the indexes in the second half of the array are to be set to. This is why in the above test the second half of the array remains unchanged. The bug is with both the for loop and the contents inside the for loop. 

![Screenshot](https://user-images.githubusercontent.com/114367462/195694124-2b7cdb3d-da09-42c5-af18-a4407ec19f83.png)

To fix this issue, I first changed the for loop to only iterate through the first half of the list. My plan was to have the corresponding elements of the array switch during the same loop. For example, the first and last switch in the first loop, then the second and the second last and so on. Inside the for loop, I used the variables first and second to store the values at the two indicies to be switched. This is done in order to avoid losing the original values in memory. Then, I set the index in the second half(arr.length-1-i) to first and the index in the first half(i) to second. 

![Screenshot](https://user-images.githubusercontent.com/114367462/195694318-8294b170-98b3-42fe-8347-af74b796b8f4.png)


merge method

Here is the test that was ran to test the original code and the failure-inducing input is merge({"a", "b", "c"}, {"d", "e", "f"}

![Screenshot](https://user-images.githubusercontent.com/114367462/195701976-567a44c2-ea66-4cc8-9608-287a20592b2c.png)

When this test is run, the program results in an out of memory error(symptom). This means that there is likely an infinite loop. 

![Screenshot](https://user-images.githubusercontent.com/114367462/195702026-3a6b594d-791d-47a8-98a8-42e9c357eaab.png)

Here is the original code. The bug is in the final while loop. This bug will only impact the program if the second list passed in has the last element to be merged. Otherwise, the program will have its intended output. The problem is that after the first while loop has ended and index2 < list2.size(), the final while loop in this method will run. This while loop increments index1 instead of index2, which is the bug, leading to the condition index2 < list2.size() always being true. 

![Screenshot](https://user-images.githubusercontent.com/114367462/195701806-a756af88-49ee-409d-8c17-f90d57e73930.png)

The bug has the simple fix of changing the last while loop to update index2 rather than index1. 

![Screenshot](https://user-images.githubusercontent.com/114367462/195701552-5a60d312-7d3d-430a-bc3d-1f25a3fedc8d.png)

