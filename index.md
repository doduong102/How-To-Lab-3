# Grep Time

grep is a unix command that allows us to filter through files given a "keyword" or pattern that we're looking for. Here is the typical syntax:

`grep [options] pattern [files]`

Some options on the menu:

A) `grep -v` : Prints all lines that do not match pattern

B) `grep -c` : Prints line count that matches the pattern

C) `grep -n` : Displays the matched lines and their line numbers.

D) `grep -i` : Ignores case for matching(?)

## PART A 

<img width="381" alt="image" src="https://github.com/doduong102/How-To-Lab-3/assets/130004918/dc2db456-a6d2-4771-850a-57f10c4f9af9">
<img width="378" alt="image" src="https://github.com/doduong102/How-To-Lab-3/assets/130004918/4332613d-48d6-43d3-8c54-bfee1e2315f3">

What `grep -v` is doing in these examples is basically taking our string, file, and returning all the lines and words that do not match out string. The strings I chose did not appear very often relative to the rest of the file so it's quite a mess.

## PART B

<img width="519" alt="image" src="https://github.com/doduong102/How-To-Lab-3/assets/130004918/dc85b548-8ca7-4406-8872-8a611e09d7e2">

`grep -c` is simpler and will just print the number of lines that the string appears in.


## PART C

<img width="511" alt="image" src="https://github.com/doduong102/How-To-Lab-3/assets/130004918/88da8b19-d930-445b-8926-bdcc07c13b67">

`grep -n` I can see personally be quite useful to use on something like a comment section or chat history. What this version of `grep` does in particular is prints every line that matches the pattern and line number than it appears on

<img width="514" alt="image" src="https://github.com/doduong102/How-To-Lab-3/assets/130004918/946f0011-af4a-4d2a-ac16-c2340a6f8aa4">

## PART D
