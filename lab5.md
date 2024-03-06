# Part 1- debugging

## original student post 
I am attempting to write code that takes in a set of numbers and computes the average. However, my code is not working as expected. Instead of
computing the average, I am getting a message that says "No valid numbers entered". I have included a screenshot below. 
I think the problem might be with the bash script. Any help would be appreciated.

<img width="426" alt="Screenshot 2024-03-06 at 2 47 29 PM" src="https://github.com/aaj005/cse15l-lab-reports/assets/156254216/812ab913-f933-4e9f-85f5-a89e026cad7d">
<img width="340" alt="Screenshot 2024-03-06 at 2 49 33 PM" src="https://github.com/aaj005/cse15l-lab-reports/assets/156254216/ee981047-604d-46a5-a767-82d510675c36">

## TA response 
Your bash script seems to be correct, which leads me to believe the problem is in your java file. Have you tried checking the conditions upon 
which the program decides what output to print? I would suggest using vim in your terminal to open and edit your code. After running the command
`vim filename`, you can press `i` to enter insert mode. After making the necessary changes, you can press `esc` and then `:w` and `:q` to 
save and quit, respectively. 

## student fix and bug identified
Thank you for your response. After following your suggestions and opening the file in vim, I discovered that there was an error in my logic. I was
only displaying the average if the total sum was less than 0 instead of greater than 0. Below are screenshots of the bug before and after it was
corrected. Thank you again for your help. 

<img width="441" alt="Screenshot 2024-03-06 at 2 53 00 PM" src="https://github.com/aaj005/cse15l-lab-reports/assets/156254216/c07918a6-597c-4b31-a9d5-57f130b979a0">
<img width="444" alt="Screenshot 2024-03-06 at 2 53 47 PM" src="https://github.com/aaj005/cse15l-lab-reports/assets/156254216/cfb223f0-fd88-4fbe-97e0-f01c92c9a936">

# complete setup information 
## File and directory structure: one java file and one bash script

<img width="268" alt="Screenshot 2024-03-06 at 2 56 35 PM" src="https://github.com/aaj005/cse15l-lab-reports/assets/156254216/dc1fa9cf-7273-4219-99d3-d05089225a65">

## Java file before fixing the bug:
<img width="593" alt="Screenshot 2024-03-06 at 2 58 34 PM" src="https://github.com/aaj005/cse15l-lab-reports/assets/156254216/7ee03761-a40a-4fc6-861c-0c27b1bee0f2">

## Bash script:
<img width="221" alt="Screenshot 2024-03-06 at 2 58 50 PM" src="https://github.com/aaj005/cse15l-lab-reports/assets/156254216/9936434f-3f38-476f-a021-12fe9a535fd5">

## Java file after fixing bug:
<img width="592" alt="Screenshot 2024-03-06 at 2 59 22 PM" src="https://github.com/aaj005/cse15l-lab-reports/assets/156254216/5df568d5-bb32-43b6-b899-82ca12ceed1b">

## Command lines ran to trigger bug:
`sh test.sh` (run bash script)

## Edits made to fix bug:
`vim average.java`

`i` (enter insert mode)

Changed `if (count<0)` to `if (count>0)` 

`<esc> :w :q` (exit insert mode, save, and quit)

`sh test.sh` (rerun bash script)


# Part 2- reflection
One thing I learned from this lab experience in the second half of the quarter was how to edit and run files all within the terminal. Before I learned
this, I was dependent on text editors and the terminals in them to edit and run java files. Now, after learning about vim and jdb, I can edit, debug,
and run files all within the terminal. This is very helpful for small edits and is much quicker. 

