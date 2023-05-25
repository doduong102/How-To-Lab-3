# Grep Time

grep is a unix command that allows us to filter through files given a "keyword" or pattern that we're looking for. Here is the typical syntax:

`grep [options] pattern [files]`

Some options on the menu:

A) `grep -v` : Prints all lines that do not match pattern

B) `grep -c` : Prints line count that matches the pattern

C) `grep -n` : Displays the matched lines and their line numbers.

D) `grep -i` : Ignores case for matching(?)

## Part A 

<img width="381" alt="image" src="https://github.com/doduong102/How-To-Lab-3/assets/130004918/dc2db456-a6d2-4771-850a-57f10c4f9af9">
<img width="378" alt="image" src="https://github.com/doduong102/How-To-Lab-3/assets/130004918/4332613d-48d6-43d3-8c54-bfee1e2315f3">

What `grep -v` is doing in these examples is basically taking our string, file, and returning all the lines and words that do not match out string. The strings I chose did not appear very often relative to the rest of the file so it's quite a mess.

# PART B

![image](https://user-images.githubusercontent.com/130004918/234176128-f3412890-b350-4aae-a712-0dc7ccce099b.png)

Running these two commands
```
javac -cp ".;lib/hamcrest-core-1.3.jar;lib/junit-4.13.2.jar" *.java 
java -cp ".;lib/junit-4.13.2.jar;lib/hamcrest-core-1.3.jar" org.junit.runner.JUnitCore ArrayTests
```
Causes a failure from our JUnit test that we wrote
```
@Test 
public void testReverseInPlace1() {
int[] input1 = {3, 2, 1};
ArrayExamples.reverseInPlace(input1);
assertArrayEquals(new int[]{1, 2, 3}, input1);
}
```

This JUnit test broke the following method from our ArrayExamples file:

```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

For the same method `reverseInPlace`, here's a non-failure inducing JUnit test:
```
@Test 
public void testReverseInPlace() {
int[] input1 = { 3 };
ArrayExamples.reverseInPlace(input1);
assertArrayEquals(new int[]{ 3 }, input1);
}
```

Running these two commands
```
javac -cp ".;lib/hamcrest-core-1.3.jar;lib/junit-4.13.2.jar" *.java 
java -cp ".;lib/junit-4.13.2.jar;lib/hamcrest-core-1.3.jar" org.junit.runner.JUnitCore ArrayTests
```
Should tell us something along the lines of two tests ran and one test failed. Here's the screenshot of our output.

<img width="767" alt="image" src="https://github.com/doduong102/How-to-Lab-2/assets/130004918/2e89e8da-d61a-410b-8cce-c98a890f46d3">

Our broken method from earlier:
```
//BEFORE
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```
And fixed method:
```
//AFTER
  static void reverseInPlace(int[] arr) {
    int mid = arr.length / 2;
    for(int i = 0; i < mid; i++) {
      int j = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = j;
    }
  }
```
Our old method was broken because it was just replacing it element for element, our main issue comes from when we get towards the end of our array it will replace the ending elements with the newly changed end elements, basically making it the same. We run the original loop over the first half of the array, then for the second half using variable j to properly replace the end elements


# Part C| Reflections

![image](https://user-images.githubusercontent.com/130004918/234176285-6979e4d3-15af-475d-8b23-b793aae8dd8a.png)

I was in CSE12 and I didn't know that you could run JUnit tests outside of eclipse. Technically I knew it existed but it was nice to see it implemented directly like this because I don't actually like eclipse.
