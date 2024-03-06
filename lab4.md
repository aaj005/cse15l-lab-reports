# Lab Report 4- Vim

## Step 1: log into ieng6
<img width="567" alt="Screenshot 2024-02-21 at 2 43 41 PM" src="https://github.com/aaj005/cse15l-lab-reports/assets/156254216/79aa7d4b-3592-4a48-8ac7-38b80c006f62">

`ssh aaj005@ieng6.ucsd.edu`
Logged into ieng6

## Step 2: cloning the repository
<img width="569" alt="Screenshot 2024-02-21 at 2 44 56 PM" src="https://github.com/aaj005/cse15l-lab-reports/assets/156254216/c410cc44-f7dc-4902-9e1c-f3fc754c59d2">

`ctrl c` to copy the repo
`git clone ` + `ctrl v`
Cloned the forked lab7 repository

## Step 3: running the tests
<img width="564" alt="Screenshot 2024-02-21 at 2 45 19 PM" src="https://github.com/aaj005/cse15l-lab-reports/assets/156254216/9dab45e4-cd3c-4973-a947-1c07c77fea3d">

`bash test.sh`
Ran the bash script that tests ListExamples.java

## Step 4: editing the code file 
<img width="569" alt="Screenshot 2024-02-21 at 3 00 54 PM" src="https://github.com/aaj005/cse15l-lab-reports/assets/156254216/f4982148-114d-4582-b7ca-4b5cb8abaac4">

`vim ListExamples.java`
`i` `<backspace>1<esc>` `:w :q`

Used vim to edit the code file. `i` enters insert mode (was already in that spot in the file), replaced `index2` with `index1`. 

`:w` to save the file and `:q` to quit.

## Step 5: rerunning the tests
<img width="419" alt="Screenshot 2024-02-21 at 3 02 55 PM" src="https://github.com/aaj005/cse15l-lab-reports/assets/156254216/85c20947-5592-4236-b9cf-e24faa63fedc">

`<up><up><enter>`

The `bash test.sh` command was 2 up in the search history, so I pressed the up arrow twice and then enter to run it. 

## Step 6: committing to GitHub
<img width="569" alt="Screenshot 2024-02-21 at 3 06 06 PM" src="https://github.com/aaj005/cse15l-lab-reports/assets/156254216/86b05728-3a43-4e70-bc09-e90f7bf8c7f9">

`git add ListExamples.java`
`git commit -m "tests pass"`
`git push`

This `git add` command adds a file to be committed, and the `git commit` command commits all files. The `git push` command sends all pending changes to the repository. 
