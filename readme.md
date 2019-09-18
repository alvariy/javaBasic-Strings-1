# Overview

This repository is a part of the Java language training plan. Please read the following guidelines before start.

# Getting Start

## Basic Principals

Each repository contains a gradle java project with a number of unit tests. The initial state of all unit tests are *FAILED*. So the aim is to correct the failed test. Please follow the following steps to get the best experience:

* Read the test code and try to understand what it says.
* Trying to fix the test **WITHOUT RUNNING**. This is very important. Because once you run the test, you may find the failure message of the test telling you the expected result. That means you may lose the chance to figure it out by yourself. Note that you should **ONLY** be able to modify code within the **TODO AREA**. The code outside the **TODO AREA** is **NOT** changable.
* Run the test to examine if the fix is correct.
* Answer the following 4 questions after the test is passed.

The 4 questions are:

1. What is the knowledge point of the test? Where is the offical document to the knowledge point?
1. Why the test failed at first?
1. Why you corrected the test that way?
1. Do you have further questions on this knowledge point?

## Example

Let's take a look at an example:

```java
@Test
void should_pass_by_value() {
  int value = 5;

  tryingToUpdateValue(value);

  // TODO: please modify the following code to pass the test
  // <--start
  final int expected = 0;
  // --end-->

  assertEquals(expected, value);
}
```

First, read the test. From the title and code we can know that the test what to examine the behavior when passing an argument. We are not sure what `tryingToUpdateValue` does, so we can jump into its implementation:

```java
private static void tryingToUpdateValue(int value) {
  value += 2;
}
```

Now we have got the full context of the test. The argument is passed by value so the integer will be copied when passing into `tryingToUpdateValue`. Thus the value from the caller site will not change.

Notice that the todo area is in the test method. So we can modify codes within the todo area to pass the test:

```java
  // TODO: please modify the following code to pass the test
  // <--start
  final int expected = 5;
  // --end-->
```

Please note that not all todo areas are located in test method. And some todo area may have further restrictions, for example:

```java
  // TODO: You should not write concrete number here. Please find a property or constant instead.
  // <!--start
  final int maximumSymbol = 0;
  final int minimumSymbol = 0;
  // --end-->
```

The hint indicates that we should not write concrete number here. So I should not write `3` or `0xffffffff`, but write symbol (e.g. `Integer.MAX_VALUE`).

## Running Test

You could run unit tests with the help of IntelliJ. But it is also possible to run unit test via command line: `./gradlew build`.

If you just want to build your code without running test. Please use `./gradlew build -x test
`

Answers:

Aswer for,

should_be_immutable:
1.What is the knowledge point of the test? Where is the official document to the knowledge point?
- Using replace function for the string, the "original" word inside the string then it was replaced by "new"
2.Why the test failed at first?
- areSame is returning a null value.
3.Why you corrected the test that way?
- Because the "of" function of the Optional class returns the same value of it's parameter and originalString is not equal to modifiedString
4.Do you have further questions on this knowledge point?
- None

all_modification_method_will_create_new_string:
1.What is the knowledge point of the test? Where is the official document to the knowledge point?
- Using trim function for the string with whitespace, it was able to eliminate the whitespaces for modifiedString.
2.Why the test failed at first?
- areSame is returning a null value.
3.Why you corrected the test that way?
- I'm not sure on what is the reason of modifiedString and originalString not being equal after triggering the trim function.
4.Do you have further questions on this knowledge point?
- Is there any factors or why is those 2 variables not equal even after trim?

will_create_new_string_when_concat
1.What is the knowledge point of the test? Where is the official document to the knowledge point?
- Using +=  for the string of originalString, it was able to concat the string "Part One" and "Part two"
2.Why the test failed at first?
- areSame is returning a null value.
3.Why you corrected the test that way?
- I'm not sure on what is the reason of modifiedString and originalString not being equal after triggering the concatenation.
4.Do you have further questions on this knowledge point?
- Is there any factors or why is those 2 variables not equal even after trim?


should_taken_string_apart_continued:
1.What is the knowledge point of the test? Where is the official document to the knowledge point?
- The knowledge point is to be familiarized with consist function
- https://www.edureka.co/blog/java-string/
2.Why the test failed at first?
- no failed case.
3.Why you corrected the test that way?
- Because I think using contains function is the easiest way to success the test
4.Do you have further questions on this knowledge point?
- Is there any way for the solution to be more short? And How?

should_break_string_into_words:
1.What is the knowledge point of the test? Where is the official document to the knowledge point?
- The knowledge point is to be familiarized with split function
- https://www.edureka.co/blog/split-string-method-in-java/
2.Why the test failed at first?
- no failed case.
3.Why you corrected the test that way?
- Because I think using split function is the easiest way to success the test
4.Do you have further questions on this knowledge point?
- Is there any way for the solution to be more short? And How?

should_break_string_into_words_customized
1.What is the knowledge point of the test? Where is the official document to the knowledge point?
- The knowledge point is to be familiarized with split function
- https://www.edureka.co/blog/split-string-method-in-java/
2.Why the test failed at first?
- no failed case.
3.Why you corrected the test that way?
- Because I think using split function with regex = '/' is the easiest way to success the test
4.Do you have further questions on this knowledge point?
- Is there any way for the solution to be more short? And How?

should_create_ascii_art
1.What is the knowledge point of the test? Where is the official document to the knowledge point?
- The knowledge point is to be familiarized with String Builder and Append function
- https://www.edureka.co/blog/java-string/
2.Why the test failed at first?
- no failed case.
3.Why you corrected the test that way?
- Because I think using height only instead of using both heigh and weight is the easiest way to success the test
4.Do you have further questions on this knowledge point?
- Is there any way for the solution to be more short? And How?

should_calculate_checksum_of_a_string
1.What is the knowledge point of the test? Where is the official document to the knowledge point?
- If you convert a char to an int, it will give you its ASCII equivalent
- https://www.javatpoint.com/java-char-to-int
2.Why the test failed at first?
- no failed case.
3.Why you corrected the test that way?
- Because converting a letter to an int will give me the ASCII equivalent of each letters in the string is the easiest way to success the test
4.Do you have further questions on this knowledge point?
- Is there any way for the solution to be more short? And How?



should_reverse_a_string
1.What is the knowledge point of the test? Where is the official document to the knowledge point?
- used a for loop and charAt to manipulate the string
- https://www.tutorialspoint.com/java/java_string_charat.htm
2.Why the test failed at first?
- I forgot to assigned the array to descending fashion.
3.Why you corrected the test that way?
- Becuase using a for loop and using the string Index is one way of reversing a string.
4.Do you have further questions on this knowledge point?
- Is there any way for the solution to be more short? And How?

should_convert_unicode_escape
1.What is the knowledge point of the test? Where is the official document to the knowledge point?
- we can use an escape to display a unicode. Example: "\u306a" for な"
2.Why the test failed at first?
- I keep included the "+" in the unicode.
3.Why you corrected the test that way?
- Becuase that is the simplest way to display the special characters
4.Do you have further questions on this knowledge point?
- Is there any way for the solution to be more short? And How?

should_compare_string_with_different_cases
1.What is the knowledge point of the test? Where is the official document to the knowledge point?
- The type is also Boolean,  
2.Why the test failed at first?
- No test failure
3.Why you corrected the test that way?
- Due to the use or function of the format method.
4.Do you have further questions on this knowledge point?
- Is there any way for the solution to be more short? And How?


should_format_string
1.What is the knowledge point of the test? Where is the official document to the knowledge point?
- We can use format to concat some strings and even int at certain parts of the string using this symbol "%" followed by a letter 
- https://www.tutorialspoint.com/java/java_strings.htm
2.Why the test failed at first?
- No test failure
3.Why you corrected the test that way?
- Due to the use or function of the format method.
4.Do you have further questions on this knowledge point?
- Is there any way for the solution to be more short? And How?















