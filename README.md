# CS 445 Recitation 3: Array vs. Linked Implementations; Unit Tests with Gradle

## Introduction

In this recitation exercise, you will explore the implementation of the ADT bag using
arrays and linked chains. You will override the `equals` method so that it will
determine if two bags are equal based on their contents. You will then implement
the `removeDuplicatesOf` method, which will remove any extra copies of a
specific entry; it will leave the first instance of that entry while removing
any copy of it later in the array/linked chain. Lastly, you will implement the
`removeAllDuplicates` method, which will remove any extra copies of all entries
in the bag.

The primary goal of this exercise is to practice solving the problems that arise
when developing implementations of data structures alternately array- and
linked-based. A secondary goal is to exercise good code reuse practices, as
existing Bag methods (even private methods!) may be useful in implementing those
you will be writing in the exercise.

As we have seen in lecture, a bag is an unordered collection of items that may
contain duplicates. Before completing this exercise you should review the
methods available to you in the Bag ADT, as well as the implementation
techniques we used to construct the array- and linked-based implementations of
this ADT.

## Unit Tests with Gradle

With this exercise, we will introduce the process of building and running unit
tests with JUnit and the gradle build tool. In Recitation 2, you learned how to
build and run code using gradle. In this exercise, in addition to using
`./gradlew run` (or `gradlew.bat run` on DOS-like terminals) to run a sample
client program, you can also use `./gradlew test` (or `gradlew.bat test` on
DOS-like terminals) to execute pre-written unit tests. These tests use JUnit and
attempt to reveal whether the assigned methods work as expected. Follow along
closely and/or take notes as your TA introduces you to the concept of unit
testing and the resulting output.

Note that your programming assignments will come with starter code including a
few example unit tests to help you determine whether your code works. However,
you will not be expected to have deep knowledge of JUnit for this course. You
will be required to test your assignment submissions thoroughly (beyond what is
tested by our example tests) in advance of your final submission before the
deadline, but you are free to accomplish this however you are most comfortable.
That is, you will be free to adapt what you learn from our unit tests **or**
rely on simple print statements to verify that your methods work as expected.

## Exercise

1. Download the provided code by cloning this [Recitation 3
repository](https://github.com/2217-cs445/cs445-rec3). The starting code for
this exercise, as usual, is found in subdirectory `app/src/main/java/`. Navigate
to this subdirectory, then into the `cs445/rec3/` package folder within it. Note
the following provided Java files:

   - `BagInterface.java` is a Java interface representing the ADT Bag.
   - `ArrayBag.java` is a dynamic capacity array-based implementation of ADT
     Bag. It has non-functional stubs for the three methods that you will write
     in this exercise.
   - `LinkedBag.java` is a linked implementation of ADT Bag. It also has a
     non-functional stub for the three assigned methods.
   - `BagClient.java` is a simple example client that uses both an `ArrayBag`
     and a `LinkedBag` based on command-line arguments.

   In addition to the main portion of the code, we have also provided test
   classes that can be found in subdirectory `app/src/test/java/`. Navigate to
   this subdirectory, then into the `cs445/rec3/` package folder within it. Note
   the following provided Java files:

   - `ArrayBagTest.java` contains example test cases for the ArrayBag class.
   - `LinkedBagTest.java` contains example test cases for the LinkedBag class.
   - `Util.java` contains a helper function that is used for shuffling arrays.

2. Devise an algorithm for comparing two bags to determine if they contain the
same contents. Here are some steps you may want to follow:

   - Consider two "equal" bags. What items and frequencies need to be compared
     to determine that they are equal? What existing bag methods can you reuse
     to accomplish this?
   - Determine an example of two bags that cannot be equal, yet no item
     comparisons are needed to make that determination.
   - Consider any special cases that may arise, given invalid inputs.
   - Write an algorithm for each of `ArrayBag` and `LinkedBag` that returns true
     if two bags contain the same entries. Remember to consider the examples
     from the previous bullets.

3. Implement your algorithm(s) as method `boolean equals(Object other)` in each
class. Since this is overriding a method from the `Object` class, you cannot
change the method signature, which means you cannot accept a parameter of type
`ArrayBag` (or `LinkedBag`). Consider using the `instanceof` notation to
determine whether the input is the correct type. Remember, casting can be used
to interpret a reference as if it were a different type **only if** the object
is a compatible type.

4. Test your `equals` method. You can run the provided tests automatically using
gradle:

   - `./gradlew test` (on Unix-like terminals such as those found on Mac, Linux,
     or Windows Subsystem for Linux)
   - `gradlew.bat test` (on DOS-like terminals such as the more traditional
     Windows terminal)

   Correct any bugs you find.

   ------

5. Devise an algorithm for removing any duplicates of a *specific* entry from a
bag. Here are some steps you may want to follow:

   - Consider using a loop that removes the instances of a provided object,
     excluding the first.
   - Consider what happens if the entry is not present in the bag, and any other
     forms of invalid input.

6. Implement your algorithm as method `void removeDuplicatesOf(E elem)` in both
`ArrayBag` and `LinkedBag`. Some details may be different, but your overall
approach should be very similar.

7. Test your `removeDuplicatesOf` method. You can run the provided tests using
the gradle command given above. Correct any bugs you find.

   ------

8. Devise an algorithm for removing any duplicates of **all** entries in a bag.
Here are some steps you may want to follow:

   - Consider using a loop that scans over the items in the bag, removing
     duplicates of each one.
   - Consider approaches for actually removing the duplicates. Consider what
     existing methods may be helpful in this task.
   - Consider what happens when several duplicates exist adjacent to one
     another. Will your approach miss any?

9. Implement your algorithm as method `void removeAllDuplicates()` in both
`ArrayBag` and `LinkedBag`. Some details may be different, but your overall
approach should be very similar.

10. Test your `removeAllDuplicates` method. You can run the provided tests using
the gradle command given above. Correct any bugs you find.


## Conclusion

In this exercise, you wrote implementation code for the array- and linked-based
implementations of the ADT Bag. Throughout the term, you should take the time to
practice implementing useful methods for the data structures that we study. You
may either choose to implement additional methods, as in this exercise, or
simply re-implement existing methods without looking at the provided code. The
techniques demonstrated are best learned through repeated practice.

