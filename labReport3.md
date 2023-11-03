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
Command: ```find```<br><br>
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
```
technical/
technical/911report
technical/biomed
technical/government
technical/plos
```
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

3. ```-ls```<br>
**Example 1:**<br>
Command: ```find technical/government/Alcohol_Problems/ -ls```<br>
Output:
```
5629499534318828      4 drwxr-xr-x   1 joshu    197609          0 Oct 31 12:10 technical/government/Alcohol_Problems/
6473924464450797     32 -rw-r--r--   1 joshu    197609      32413 Oct 31 12:10 technical/government/Alcohol_Problems/DraftRecom-PDF.txt
7599824371293423     36 -rw-r--r--   1 joshu    197609      36564 Oct 31 12:10 technical/government/Alcohol_Problems/Session2-PDF.txt
6192449487740146     96 -rw-r--r--   1 joshu    197609      95891 Oct 31 12:10 technical/government/Alcohol_Problems/Session3-PDF.txt
6755399441161459     80 -rw-r--r--   1 joshu    197609      81409 Oct 31 12:10 technical/government/Alcohol_Problems/Session4-PDF.txt
```
In this example, it is listing the contents of the path(technical/government/Alcohol_Problems) given in the command and it also searches the subdirectories. This is helpful when you want to see what the directory contains through command.<br>

**Example 2:**<br>
Command: ```find technical/911report/ -ls```<br>
Output: 
```8725724278087991      4 drwxr-xr-x   1 joshu    197609          0 Oct 31 12:10 technical/911report/
9851624184930618    120 -rw-r--r--   1 joshu    197609     119387 Oct 31 12:10 technical/911report/chapter-1.txt
14636698789011795     48 -rw-r--r--   1 joshu    197609      47910 Oct 31 12:10 technical/911report/chapter-10.txt
20547673299935584     72 -rw-r--r--   1 joshu    197609      71968 Oct 31 12:10 technical/911report/chapter-11.txt
 7599824371245409    128 -rw-r--r--   1 joshu    197609     129126 Oct 31 12:10 technical/911report/chapter-12.txt
 7036874417824099     92 -rw-r--r--   1 joshu    197609      90943 Oct 31 12:10 technical/911report/chapter-13.1.txt
13229323905458537    112 -rw-r--r--   1 joshu    197609     111804 Oct 31 12:10 technical/911report/chapter-13.2.txt
 9570149208220015    152 -rw-r--r--   1 joshu    197609     152185 Oct 31 12:10 technical/911report/chapter-13.3.txt
 5348024557560183    264 -rw-r--r--   1 joshu    197609     268853 Oct 31 12:10 technical/911report/chapter-13.4.txt
14918173765722494    288 -rw-r--r--   1 joshu    197609     294230 Oct 31 12:10 technical/911report/chapter-13.5.txt
23643898043752852     80 -rw-r--r--   1 joshu    197609      80751 Oct 31 12:10 technical/911report/chapter-2.txt
15199648742433184    264 -rw-r--r--   1 joshu    197609     267519 Oct 31 12:10 technical/911report/chapter-3.txt
11821949021905317    100 -rw-r--r--   1 joshu    197609     100212 Oct 31 12:10 technical/911report/chapter-5.txt
12384898975326636    148 -rw-r--r--   1 joshu    197609     150961 Oct 31 12:10 technical/911report/chapter-6.txt
22517998136910261    128 -rw-r--r--   1 joshu    197609     129949 Oct 31 12:10 technical/911report/chapter-7.txt
 6473924464402894     84 -rw-r--r--   1 joshu    197609      85871 Oct 31 12:10 technical/911report/chapter-8.txt
 8162774324666853    148 -rw-r--r--   1 joshu    197609     151529 Oct 31 12:10 technical/911report/chapter-9.txt
 6192449487692300     12 -rw-r--r--   1 joshu    197609       9440 Oct 31 12:10 technical/911report/preface.txt
```
In this example, it is listing the contents of the path(technical/911report) given in the command and it also searches the subdirectories. This is helpful when you want to see what the directory contains through command.<br>


4. ```-```<br>
**Example 1:**<br>
Command: ```find -name "chapter-1.txt"```<br>
Output: ```./technical/911report/chapter-1.txt```<br>
In this example, the command is looking for the chapter-1.txt and it returns the file path. This is helpful because rather than trying to find the file by searching manually this command can speed the process.<br>

**Example 2:**<br>
Command: ```find -name "Alcohol_Problems"```<br>
Output: ```./technical/government/Alcohol_Problems```<br>
In this example, the command is looking for the Alcohol_Problems directory and it returns the directory path. This is helpful because rather than trying to find the directory by searching manually this command can speed the process.<br>
