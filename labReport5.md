**Lab Report 5**<br>
**Part 1 - Debugging Scenario**<br>
**1. Student:** I am not sure with what is wrong with my reverseArray method. Could it be possible that I am accessing an index that is out of bounds?<br>
![Image](image1.png) <br>
**2. TA:** Take a look at your reverseArray method and see if you have an array of size 5 what the first iteration would do. If the array length is 5, can you access the index 5? And also, can you do assertEquals with 2 arrays?<br>
**3. Student:** ![Image](image7.png) <br>
The bug was that the array was accessing an element outside the index. The first iteration of the loop was accessing the array size index which an error comes up. <br>
**4.**
![Image](image5.png) <br>
![Image](image2.png) <br>
![Image](image3.png) <br>
![Image](image4.png) <br>
![Image](image1.png) <br>
To fix the bug, I changed the reverseMethod to have ```list[list.length - 1 - i]``` so that it does not get an ```IndexOutOfBoundsException```. I also changed ```assertEquals``` to ```assertArrayEquals```. The bug was fixes after these edits.<br>
**Part 2 - Reflection**<br>
In the second half of this quarter, one thing I learned was how to use the VIM editor. I found it really cool that we don't need a code editor and we can edit code through the terminal window. For my CSE 12 class, I experimented with editing the code through VIM and running it through commands for fun and it was fascinating. Overall, I learned a lot from this class and my experience was wonderful with the help of the CSE 15L Staff!
