# CSE15 Week 3 Lab Report 

## Part 1

## Part 2

testInPlace method

Here are the tests that were ran to test the original code. There is one for an array with even indicies and one for an array with odd indices.

![Screenshot](https://user-images.githubusercontent.com/114367462/195694281-cd82474c-49a5-42dd-a535-e2baf4129889.png)

The test for the array call ArrayExamples.testInPlace({3, 4, 5, 6}) returns {6, 5, 5, 6} rather than {6, 5, 4, 3). 

![Screenshot](https://user-images.githubusercontent.com/114367462/195695276-c0abab23-3d83-41a6-9fb6-11c10bf174f4.png)

Here is the original code. The values in the first half of the array will change correctly to the corresponding values in the second half of the array. However, when it comes to changing the second half of the array, the original values from the first half of the array are not accesible anymore. This is why in the above test the second half of the array remains unchanged. The bug is with both the for loop and the contents inside the for loop. 

![Screenshot](https://user-images.githubusercontent.com/114367462/195694124-2b7cdb3d-da09-42c5-af18-a4407ec19f83.png)

To fix this issue, I first changed the for loop to only iterate through the first half of the list. My plan was to have the corresponding elements of the array switch during the same loop. For example, the first and last switch in the first loop, then the second and the second last and so on. Inside the for loop, I used the variables first and second to store the values at the two indicies to be switched. This is done in order to avoid losing the original values in memory. Then, I set the index in the second half(arr.length-1-i) to first and the index in the first half(i) to second. 

![Screenshot](https://user-images.githubusercontent.com/114367462/195694318-8294b170-98b3-42fe-8347-af74b796b8f4.png)


merge method

![Screenshot](https://user-images.githubusercontent.com/114367462/195701806-a756af88-49ee-409d-8c17-f90d57e73930.png)

![Screenshot](https://user-images.githubusercontent.com/114367462/195701976-567a44c2-ea66-4cc8-9608-287a20592b2c.png)

![Screenshot](https://user-images.githubusercontent.com/114367462/195702026-3a6b594d-791d-47a8-98a8-42e9c357eaab.png)

![Screenshot](https://user-images.githubusercontent.com/114367462/195701552-5a60d312-7d3d-430a-bc3d-1f25a3fedc8d.png)

