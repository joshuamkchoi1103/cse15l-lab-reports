**Part 1**<br>
Bug: reverseInPlace() in ArrayExamples

- 
```
	@Test 
	public void testReverseInPlace1() {
    int[] input1 = {3, 2};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{2, 3}, input1);
	}
```
- 
```
	@Test 
	public void testReverseInPlace2() {
    int[] input1 = {3};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{3}, input1);
	}
```
  - ![Image](Screenshot20231102172002.png)
  -
BEFORE:
```
      static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```
AFTER:
```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length / 2; i += 1) {
      int temp = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i -1] = temp;
    }
  }
```
This fix addresses the issue because before, in the method it would forget the value of arr[i] and we would be losing track of it. Therefore, a temp variable is necessary to remember that value so that it can be assigned to the other index as a result of reversing the order.


**Part 2**<br>
Command: ```find```<br>
1. ```-name```<br>
**Example 1:**<br>
Command: ```find -name "chapter-1.txt"```<br>
Output: ```./technical/911report/chapter-1.txt```<br>
In this example, the command is looking for the chapter-1.txt and it returns the file path. This is helpful because rather than trying to find the file by searching manually this command can speed the process.<br>

**Example 2:**<br>
Command: ```find -name "Alcohol_Problems"```<br>
Output: ```./technical/government/Alcohol_Problems```<br>
In this example, the command is looking for the Alcohol_Problems directory and it returns the directory path. This is helpful because rather than trying to find the directory by searching manually this command can speed the process.<br>

2. ```-maxdepth```<br>
**Example 1:**<br>
Command: ```find technical/ -maxdepth 1```<br>
Output:
```technical/
technical/911report
technical/biomed
technical/government
technical/plos```
In this example, the command is finding all the files and directories that is only 1 level deep within the technical directory. This is a useful command when you want to take a look at your file structure at a specific depth/level.<br>

**Example 2:**<br>
Command: ```find technical/government/ -maxdepth 1```<br>
Output: 
```
technical/government/
technical/government/About_LSC
technical/government/Alcohol_Problems
technical/government/Env_Prot_Agen
technical/government/Gen_Account_Office
technical/government/Media
technical/government/Post_Rate_Comm
```
In this example, the command is finding all the files and directories within the technical/government directory that is only 1 depth deep maximum. This is convenient because it allows you to put a limit on the depth of the directory tree.
