# Part 1: Bugs

## Failure-inducing input
`@Test
public void testReversed() {
int[] input1 = { 1, 2, 3, 4 };
assertArrayEquals(new int[] { 4, 3, 2, 1 }, ArrayExamples.reversed(input1));
}`
<img width="834" alt="Screenshot 2024-02-13 at 7 06 38 PM" src="https://github.com/aaj005/cse15l-lab-reports/assets/156254216/7a7c3e11-c08c-4c30-895b-c470dee4a2ac">

## Input that doesn't induce failure
`@Test
public void testReversed() {
int[] input1 = { 0 };
assertArrayEquals(new int[] { 0 }, ArrayExamples.reversed(input1));
}`

### Buggy
`static int[] reversed(int[] arr) {
int[] newArray = new int[arr.length];
for(int i = 0; i < arr.length; i += 1) {
arr[i] = newArray[arr.length - i - 1];
}
return arr;
}`

### Fixed
`static int[] reversed(int[] arr) {
int[] newArray = new int[arr.length];
for(int i = 0; i < arr.length; i += 1) {
newArray[arr.length - i - 1] = arr[i];
}
return newArray;
}`

The buggy code updated the wrong index and did not return or update `int[] newArray` either. The fixed
code updates `int[] newArray` properly with `arr` and returns it as well.


# Part 2: Researching commands

`grep -c "text" (file)`
Shows the number of matches of `"text"` in the file.
Source: https://www.baeldung.com/grep-in-java

## Example 1
`$ grep -c "Acropolis" Athens-WhatToDo.txt
1`
In this example, I used the `grep` command to see if the word "Acropolis" appears 
in `Athens-WhatToDo.txt`. It was useful because it returned `1`, which means that the text did
in fact mention the Acropolis. 

## Example 2
`$ grep -c "the" Bahamas-Intro.txt
12`
In this example, I used the `grep` command to see if the word "the" appears 
in `Bahamas-Intro.txt`. It was useful because it returned `12`, which means that the text did
in fact contain the word 12 times. 

`grep -l "text"`
Using grep -l displays the files that contain the given string. 
Source: https://www.geeksforgeeks.org/grep-command-in-unixlinux/

## Example 3
`$ grep -l "Greece" *
Athens-History.txt
Athens-Intro.txt
Athens-WhatToDo.txt
Athens-WhereToGo.txt
Barcelona-WhereToGo.txt
Budapest-History.txt
CostaBlanca-History.txt
Crete-History.txt
Crete-WhatToDo.txt
Crete-WhereToGo.txt`
I used `grep -l` to find the files that mention the phrase “Greece”. This is useful because it enabled 
me to find out which files mentioned Greece. 

## Example 4 
`$ grep -l "climbing" *
Bali-WhatToDo.txt
Beijing-WhatToDo.txt
Berlin-WhatToDo.txt
Budapest-WhereoGo.txt
California-WhatToDo.txt
California-WhereToGo.txt
Canada-WhereToGo.txt
CanaryIslands-WhereToGo.txt
Cuba-WhereToGo.txt
Nepal-WhatToDo.txt
Nepal-WhereToGo.txt
Paris-WhereToGo.txt
Portugal-WhereToGo.txt
PuertoRico-WhereToGo.txt
Vallarta-WhereToGo.txt`
I used `grep -l` to see which files mentioned climbing, which I am interested in. This is useful because
the command gave me all the files which mentioned climbing.

`grep -v "text" (file)`
Using `grep -v` inverts the output and shows all lines that don’t match. 
Source: https://www.geeksforgeeks.org/grep-command-in-unixlinux/

## Example 5
`grep -v "the" China-History.txt
A Brief History
The First Dynasty
The Chinese Empire
Under Mongol Rule
The Elegance of Ming
Pigtails and Prosperity
The Bitter Years of War`
I used the `grep -v` command to see which lines didn't mention "the". This command is useful because
it let me see which lines didn't mention "the".

## Example 6
`grep -v "surfing" California-WhatToDo.txt
What to Do
Sports
Watersports`
I used `grep -v` to find the lines that don’t mention the phrase “surfing”. Since I don't know
how to surf, it is useful for me to find the lines that don't mention it. 

`grep -n "text" (file)`
Using grep -n shows the line number when displaying the output. 
Source: https://www.geeksforgeeks.org/grep-command-in-unixlinux/

## Example 7
`$ grep -n "fishing" Cuba-WhatToDo.txt
48:Deep-sea fishing is one of Cuba’s great attractions, though as of yet not well known (or over-fished).
49:For information on fishing excursions, contact Puertosol (Calle Cobre, 3404, Villa Marina, Havana; Tel. 33-3510).`
I used `grep -n` to find the line numbers that contained "fishing". This command is useful because I am
interested in fishing and it allowed me to find the specific lines that mentioned it. 

## Example 8
`$ grep -n "cafés" Cuba-WhatToDo.txt
25:Both bars and cafés are places to have a mojito, daiquiri, or shot of ron (rum)`
I used `grep -n` to find the line number that contained "cafés". This command is useful because I am
interested in cafés and it allowed me to find the specific line that mentioned them.



