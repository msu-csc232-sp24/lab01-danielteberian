[![Open in Codespaces](https://classroom.github.com/assets/launch-codespace-7f7980b617ed060a017424585567c406b6ee15c891e84e1186181d67ecf80aa0.svg)](https://classroom.github.com/open-in-codespaces?assignment_repo_id=13540740)
# LAB01 - Iterative Array Processing

This lab provides the student experience declaring and processing built-in arrays in C++.

## Background

Before proceeding with this lab, the student should take the time to read the following topics as needed:

* [A.1 Language Basics](https://online.vitalsource.com/reader/books/9780134477473/epubcfi/6/440%5B%3Bvnd.vst.idref%3DP7001011925000000000000000006511%5D!/4/2%5BP7001011925000000000000000006511%5D/2/2%5BP700101192500000000000000000DF81%5D/3:14%5Basi%2Ccs%5D)
* [A.2 Input and Output using `iostream`](https://online.vitalsource.com/reader/books/9780134477473/epubcfi/6/442%5B%3Bvnd.vst.idref%3DP70010119250000000000000000066A3%5D!/4/2%5BP70010119250000000000000000066A3%5D/2/2%5BP700101192500000000000000000E0C7%5D/4%5BP700101192500000000000000000E0C8%5D/1:6%5Btre%2Cam%5D)
* [A.3 Functions](https://online.vitalsource.com/reader/books/9780134477473/epubcfi/6/444%5B%3Bvnd.vst.idref%3DP7001011925000000000000000006761%5D!/4/2%5BP7001011925000000000000000006761%5D/2/2%5BP700101192500000000000000000E163%5D/3:8%5Btio%2Cns%5D)
* [A.4 Selection Statements](https://online.vitalsource.com/reader/books/9780134477473/epubcfi/6/446%5B%3Bvnd.vst.idref%3DP7001011925000000000000000006803%5D!/4/2%5BP7001011925000000000000000006803%5D/2/2%5BP700101192500000000000000000E1E4%5D/5:19%5Bmen%2Cts%5D)
* [A.5 Iteration Statements](https://online.vitalsource.com/reader/books/9780134477473/epubcfi/6/446%5B%3Bvnd.vst.idref%3DP7001011925000000000000000006803%5D!/4/2%5BP7001011925000000000000000006803%5D/8%5BP7001011925000000000000000006862%5D/2/2%5BP700101192500000000000000000E232%5D/3:19%5Bmen%2Cts%5D)
* [A.6. Arrays](https://online.vitalsource.com/reader/books/9780134477473/epubcfi/6/446%5B%3Bvnd.vst.idref%3DP7001011925000000000000000006803%5D!/4/2%5BP7001011925000000000000000006803%5D/10%5BP70010119250000000000000000068CC%5D/2/2%5BP700101192500000000000000000E285%5D/3:5%5Brra%2Cys%5D)

## Objectives

Upon successful completion of this lab, the student has learned how to

* declare and access elements of one- and two-dimensional arrays
* pass arrays to functions
* process the elements of an array

## Getting Started

After accepting this assignment with the provided [GitHub Classroom Assignment link](https://classroom.github.com/a/81fKAffH), open the repository that is created in your account in Codespaces.

Alternatively, clone this repository. If you have cloned the repository from the command line prompt, navigate into the newly created directory

```bash
cd lab01-github-username
```

Next, create a branch named `develop`. Please note: The name of this branch **must** be as specified and will be, to the grading scripts, case-sensitive.

```bash
git checkout -b develop
```

Make sure you are on the `develop` branch before you get started. Make all your commits on the `develop` branch.

```bash
git status
```

_You may have to type the `q` character to get back to the command line prompt after viewing the status._

## Tasks

This lab consists of three tasks:

* Task 1: Declaring arrays
* Task 2: Declaring array parameters
* Task 3: Processing arrays

Again, before you start, make sure you are working on your `develop` branch as specified [above](#getting-started).

### Task 1: Declaring Arrays

#### One-Dimensional Arrays

When declaring a one-dimensional array, one must specify both the type of each element that will be stored in the array as well as the size of the array itself. Note: This size must be known at compile time, and as such, is often declared using a named constant. A one-dimensional array declaration essentially has the following canonical form:

```c++
type arrayName[arraySize];
```

For example, to declare an array that will store seven floating-point values meant to store the daily maximum temperatures for a given week, one could do so as follows:

```c++
const int DAYS_PER_WEEK = 7;
double maxTemps[DAYS_PER_WEEK];
```

The bracket notation `[ ]` declares `maxTemps` as an array that can contain no more than seven floating-point values. The brackets provide the means necessary to access particular elements of this array by supplying an array index. The valid values of these indices are 0 to the declared size - 1. So for example:

```c++
double temp = maxTemps[0]; // access first element
temp = maxTemps[1];        // access second element
temp = maxTemps[6];        // access last element
temp = maxTemps[DAYS_PER_WEEK - 1]; // same as above
```

##### One-Dimensional Array Subtasks

1. Locate `TODO: 1.1` (in [csc232.h](include/csc232.h)) and declare a named constant `ROSTER_SIZE` of type integer initialized to the value `5`.
2. Locate `TODO: 1.2` (in [csc232.h](include/csc232.h)) and declare an array named `grades` whose size is `ROSTER_SIZE`, that stores floating-point numbers (i.e., `double` values).

Be careful accessing array elements! While there are _valid_ values to use when accessing array elements, C++ does not enforce the validity of these indexes. Using indexes outside the valid range is syntactically valid, but semantically incorrect.

#### Two-Dimensional Arrays

You can also declare multidimensional arrays. You use more than one index to designate an element in a multidimensional array. Suppose that you wanted to represent the minimum temperature for each day during 52 weeks. The following statements declare a two-dimensional array, `minTemps`:

```c++
const int DAYS_PER_WEEK = 7;
const int WEEKS_PER_YEAR = 52;
double minTemps[DAYS_PER_WEEK][WEEKS_PER_YEAR];
```

These statements specify the ranges for two indices: The first index can range from 0 to 6, while the second index can range from 0 to 51. Most people picture a two-dimensional array as a rectangular arrangement, or matrix, of elements that form rows and columns. Here, the first index would represent the rows and the second index would represent the columns.

##### Two-Dimensional Array Declaration Subtasks

1. Locate `TODO: 1.3` (in [csc232.h](include/csc232.h)) and declare a named constant `NUM_COURSES` of type integer initialized the value `3`.
2. Locate `TODO: 1.4` (in [csc232.h](include/csc232.h)) and declare a two-dimensional array named `gradeBook` that has `NUM_COURSES` rows and `ROSTER_SIZE` columns.

#### Completing Task 1

1. If you have not done so already, create a new branch named `develop` (`git checkout -b develop`).
2. Toggle the `TEST_TASK1` macro (in [csc232.h](include/csc232.h)) from `FALSE` to `TRUE`.
3. Run the `task1-tests` target to verify the correctness of your code.
4. When you are satisfied with the results, stage (`git add ...`) and commit (`git commit -m"..."`, using an appropriate commit message, e.g., `-m"Complete task 1"`) your changes (again, making sure you're doing so in the `develop` branch).
5. Push your commits to GitHub (`git push -u origin develop` -- assuming this is your first push to GitHub).

### Task 2: Declaring array parameters

One important thing for passing multidimensional arrays is, first array dimension does not have to be specified. The second (and any subsequent) dimensions must be given.

When both dimensions of a two-dimensional array are available globally (either as a macro or a global constant), the parameters could be declared with their dimensions in place:

```c++
const int NUM_ROWS{3};
const int NUM_COLS{3};

void processIntArray(int data[NUM_ROWS][NUM_COLS]) {
    // ... do some processing
}
```

When only second dimension is available globally (either as a macro or as a global constant), the parameters could be declared as such:

```c++
const int NUM_COLS{3};

void processIntTable(int data[][NUM_COLS], int numRows) {
    // ... do some processing
}
```

If your compiler is C99 compatible, C language supports variable sized arrays to be passed simply by specifying the variable dimensions, as shown here:

```c++
void processIntTable(int numRows, int numCols, int table[][numCols]) {
    // ... do some processing
}
```

#### Array Processing Function Declaration Subtasks

1. Locate `TODO: 2.1` (in [csc232.h](include/csc232.h)) and declare a function named `maxGrade` that specifies two parameters. The first parameter is for an array of doubles, and the second parameter is an integer that specifies the number of elements in the array to process.
2. Locate `TODO: 2.2` (in [csc232.h](include/csc232.h)) and declare a function named `indexOfMaxGrade` that specifies three parameters. The first parameter is for a two-dimensional array of doubles. The second parameter is an integer representing the number of rows to process. The third parameter is an integer representing the number of columns to process. The function will return the index of the course that has the maximum grade. That index is modeled as an integer.

#### Completing Task 2

1. If you have not done so already, create a new branch named `develop` (`git checkout -b develop`).
2. Toggle the `TEST_TASK2` macro (in [csc232.h](include/csc232.h)) from `FALSE` to `TRUE`.
3. Run the `task2-tests` target to verify the correctness of your code.
4. When you are satisfied with the results, stage (`git add ...`) and commit (`git commit -m"..."`, using an appropriate commit message, e.g., `-m"Complete task 2"`) your changes (again, making sure you're doing so in the `develop` branch).
5. Push your commits to GitHub (`git push -u origin develop` -- assuming this is your first push to GitHub, otherwise, it's simply `git push`).

### Task 3: Processing arrays

Processing arrays amounts to using loops to iterate through the data in the array. For one dimensional arrays, this is simply a single loop; for multi-dimensional arrays, depending on the needs, the could amount to nested loops, one for each dimension.

#### Processing arrays subtasks

1. Locate `TODO: 3.1` (in [csc232.h](include/csc232.h)) and implement the `maxGrade`.
2. Locate `TODO: 3.2` (in [csc232.h](include/csc232.h)) and implement the `indexOfMaxGrade`.

## Submission Details

Before submitting your assignment, be sure you have pushed all your changes to GitHub. If this is the first time you're pushing your changes, the push command will look like:

```bash
git push -u origin develop
```

If you've already set up remote tracking (using the `-u origin develop` switch), then all you need to do is type

```bash
git push
```

As usual, prior to submitting your assignment on Microsoft Teams, be sure that you have committed and pushed your final changes to GitHub. Once your final changes have been pushed, create a pull request that seeks to merge the changes in your `develop` branch into your `trunk` branch. Once your pull request has been created, submit the URL of your assignment _repository_ (i.e., _not_ the URL of the pull request) as a Link Resource on Microsoft Teams. Please note: the timestamp of the submission on Microsoft Teams is used to assess any late penalties if and when warranted, _not_ the date/time you create your pull request. **No exceptions will be granted for this oversight**.

### Due Date

Your assignment submission is due by the end of your lab period. Write permissions to your repository will expire at 23:59, Saturday, January 27, 2024.

### Grading Rubric

This assignment is worth **3 points**.

| Criteria           | Exceeds Expectations         | Meets Expectations                  | Below Expectations                  | Failure                                        |
|--------------------|------------------------------|-------------------------------------|-------------------------------------|------------------------------------------------|
| Pull Request (20%) | Submitted early, correct url | Submitted on-time; correct url      | Incorrect URL                       | No pull request was created or submitted       |
| Code Style (20%)   | Exemplary code style         | Consistent, modern coding style     | Inconsistent coding style           | No style whatsoever or no code changes present |
| Correctness^ (60%) | All unit tests pass          | At least 80% of the unit tests pass | At least 60% of the unit tests pass | Less than 50% of the unit tests pass           |

^ _The Google Test unit runner will calculate the correctness points based purely on the fraction of tests passed_.

### Late Penalty

* In the first 24-hour period following the due date, this lab will be penalized 0.6 point meaning the grading starts at 2.4 (out of 3 total possible) points.
* In the second 24-hour period following the due date, this lab will be penalized 1.2 points meaning the grading starts at 1.8 (out of 3 total possible) points.
* After 48 hours, the assignment will not be graded and thus earns no points, i.e., 0 out of 3 possible points.
