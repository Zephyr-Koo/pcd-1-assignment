Programming Concepts and Design I (Assignment Demo) :star:
==========================================================

This repository consists of 2 sets of C source code (i.e. MathQuiz.c, MathQuizExtra.c) for your reference purpose.


There are 2 simple approaches to determine difficulty level for the quiz:-

| Approach             | Number of operand              | Number of digit for each operand  |
| :------------------- | :----------------------------- | :-------------------------------- |
| 1 (Basic)            | Fixed (2)                      | Varies depending on the level     |
| 2 (Intermediate)     | Varies depending on the level  | Maximum 2 digit integer (1 to 99) |

In both approaches, `rand()` function was used to generate random number.

## Source code :page_facing_up:

### MathQuiz.c

This is a simple program that demonstrate Approach 1 as shown as above which fulfills the minimum requirement of the assignment.


### MathQuizExtra.c

This is a combination of 2 approaches above in a single program. The code author can always switch between each of the approach by calling different function in the program entry point (`main`). (i.e. `runQuizGenerator` and `runQuizGenerator_Version2`)

:heavy_exclamation_mark: Please ensure you understand the code in MathQuiz.c before study the code in MathQuizExtra.c to prevent confusion.


## Key Concepts :pencil:

1. [Preprocessor directive](#preprocessor-directive)
2. Constant
    1. [Defined constant](#defined-constant)
    2. [Memory constant](#memory-constant)
    3. [Literal constant](#literal-constant)
3. [Escaped character](#escaped-character)
4. [Format specifier](#format-specifier)
5. Variable declaration
    1. [Basic declaration](#variable-declaration)
    2. [With initialization](#variable-declaration-with-initialization)
6. [shorthand operator](#shorthand-operator)
7. Function declaration
    1. [Without parameter / argument](#function-declaration-no-parameter)
    2. [With parameter / argument](#function-declaration-with-parameter)
    3. [Without return statement (void)](#function-declaration-no-return)
    4. [With return statement](#function-declaration-with-return)
8. Function definition
    1. [Without parameter / argument](#function-definition-no-parameter)
    2. [With parameter / argument](#function-definition-with-parameter)
    3. [Without return statement (void)](#function-definition-no-return)
    4. [With return statement](#function-definition-with-return)
9. Function call
    1. [Without parameter / argument](#function-call-no-parameter)
    2. [With parameter / argument](#function-call-with-parameter)
10. Condition
    1. [if-else](#if-else-statement)
    2. [Chaining multiple if statement](#chaining-multiple-if-statement)
    3. [switch statement](#switch-statement)
    4. [Conditional operator (if-then-else)](#conditional-operator-if-then-else)
11. Loops
    1. Pre-test loop
        1. [while loop](#while-loop)
        2. [for loop](#for-loop)
    2. Post-test loop
        1. [do-while loop](#do-while-loop)

## Additional Concepts :heavy_plus_sign:

12. [Clear input buffer](#clear-input-buffer)
13. [Suppress deprecated function call](#suppress-deprecated-function-call)
14. [Clear screen display / output](#clear-screen-output)
15. [Reset seed for random number generation](#reset-seed-for-random-number-generation)

------------

## Preprocessor directive

**Line number**:

6 to 9

**Code snippet**:

    #include <stdio.h>  // required for printf, scanf, puts functions etc.    
    #include <stdlib.h> // required for system, rand, srand functions etc.    
    #include <ctype.h>  // required for toupper function    
    #include <time.h>   // required for time function
    

## Defined constant

**Line number**:

13 to 25

**Code snippet**: 

    #define OPERATION_ADDITION       1    
    #define OPERATION_SUBTRACTION    2    
    #define OPERATION_MULTIPLICATION 3

## Memory constant

**Line number**:

27 to 29

**Code snippet**:

    const char CONFIRM_YES       = 'Y';
    const char INVALID_MESSAGE[] = "\aInvalid selection. Please try again.";
    const char ERROR_MESSAGE[]   = "Something went wrong. Please contact system administrator.";

## Literal constant

**Line number**:

56, 122, 132, 147, 152, 155, 158, ...

**Code snippet**:

    system("cls");

**Description**:

You can identify a literal constant in the program as long as the value doesn't belong to any variable (identifier).

## Escaped character

**Line number**:

28, 85, 122, ...

**Code snippet**:

    puts("\nBye bye~");

**Description**:

An escaped character can be identified with a backslash '\\' prefix. (i.e. \a for bell character and \n for new line character)

## Format-specifier

**Line number**:

86, 100, 122, 177, 181, 185 ...

**Code snippet**:

    printf("Your score is %d. ", score);

**Description**:

A format specifier can be identified with a percent '%' prefix. (i.e %c for character and %d for integer)

## Variable declaration

**Line number**:

49 to 52, 195, 212, ...

**Code snippet**:

    int menuSelection, subMenuSelection, currentOperation, currentLevel;

## Variable declaration with initialization

**Line number**:

76, 265, ...

**Code snippet**:

    int noOfCorrectAnswer = 0;
    int leftOperand       = getOperandByLevel(level);

## Shorthand operator

**Line number**:

207, 212, 217 (in MathQuizExtra.c)

**Code snippet**:

    correctAnswer += randomNumber; // equivalent to correctAnswer = correctAnswer + randomNumber
    correctAnswer *= randomNumber; // equivalent to correctAnswer = correctAnswer * randomNumber

## Function declaration (no parameter)

**Line number**:

36

**Code snippet**:

    int operationMenuSelection();


## Function declaration (with parameter)

**Line number**:

31 to 34, 37, ...

**Code snippet**:

    void displayQuizMenu(int operation, int level);

## Function declaration (no return)

**Line number**:

31 to 34

**Code snippet**:

    void displayOperationMenu(int operation);
    void displayLevelMenu(int level);
    void displayQuizMenu(int operation, int level);
    void displayQuizQuestion(int operation, int nthQuestion, int leftOperand, int rightOperand);


## Function declaration (with return)

**Line number**:

36, 37, 39, ...

**Code snippet**:

    int operationMenuSelection();
    int levelMenuSelection(int operation);


## Function definition (no parameter)

**Line number**:

193

**Code snippet**:

    int operationMenuSelection()
    {
        int operation;

        // algorithm
        
        printf("Your selection: ");
        scanf("%d", &operation);

        return operation;
    }

## Function definition (with parameter)

**Line number**:

135, 145, 165, ...

**Code snippet**:

    void displayOperationMenu(int operation)
    {
        // algorithm
    }


## Function definition (no return)

**Line number**:

135, 145, 165, ...

**Code snippet**:

    void displayQuizMenu(int operation, int level)
    {
        displayOperationMenu(operation);
        displayLevelMenu(level);
    }

## Function definition (with return)

**Line number**:

193 to 208, 210 to 228, 230 to 235, ...

**Code snippet**:

    int operationMenuSelection()
    {
        int operation;

        // algorithm
        
        printf("Your selection: ");
        scanf("%d", &operation);

        return operation;
    }

## Function call (no parameter)

**Line number**:

58, 247, 249, 250

**Code snippet**:

    int menuSelection = operationMenuSelection();
    int randomNumber  = rand();

## Function call (with parameter)

**Line number**:

61, 67, 76, ...

**Code snippet**:

    isValidOperation(currentOperation);


## if else statement

**Line number**:

81 to 106, 281 to 289

**Code snippet**:

    if (userAnswer == systemAnswer)
    {
        noOfCorrectAnswer++;
        puts("\nYou've got it right! ^_^\n");
    }
    else
    {
        puts("\n\aWrong answer. =(\n");
    }


## Chaining multiple if statement

**Line number**:

70 to 117, 137 to 142, 175 to 190, ...

**Code snippet**:

    if (operation == OPERATION_ADDITION)
    {
        printf("%d + %d = ", leftOperand, rightOperand);
    }
    else if (operation == OPERATION_SUBTRACTION)
    {
        printf("%d - %d = ", leftOperand, rightOperand);
    }
    else if (operation == OPERATION_MULTIPLICATION)
    {
        printf("%d x %d = ", leftOperand, rightOperand);
    }
    else
    {
        printf(ERROR_MESSAGE);
    }

## switch statement

**Line number**:

149 to 162

**Code snippet**:

    switch (level)
    {
        case LEVEL_BEGINNER:
            puts("BEGINNER");
            break;
        case LEVEL_INTERMEDIATE:
            puts("INTERMEDIATE");
            break;
        case LEVEL_ADVANCED:
            puts("ADVANCED");
            break;
        default:
            puts(ERROR_MESSAGE);
    }

## Conditional operator (if-then-else)

**Line number**:

246 to 250, 255 to 260 | 197, 212 (in MathQuizExtra.c)

**Code snippet**:

    int correctAnswer = (operation == OPERATION_MULTIPLICATION ? 1 : 0); // initialize with identity element

## while loop

**Line number**:

72 to 107

**Code snippet**:

    while (isValidLevel(currentLevel))
    {
        // loop body
    }

## for loop

**Line number**:

267 to 292

**Code snippet**:

    for (int n = 1; n <= NO_OF_QUESTION; n++)
    {
        // loop body
    }

## do-while loop

**Line number**:

54 to 130, 63 to 118

**Code snippet**:

    do
    {
        // loop body
    }  while (menuSelection != MENU_EXIT);

## Clear input buffer

**Line number**:

83, 97

**Code snippet**:

    rewind(stdin); // clear input buffer to remove the line feed (LF) character generated by the "Enter" key

## Suppress warning of deprecated function call

Line number: 11

**Code snippet**:

    #pragma warning(disable: 4996) // required to suppress warning of deprecated function call (e.g. scanf)

## Clear screen output

**Line number**:

56, 65, 74, ...

**Code snippet**:

    system("cls");

## Reset seed for random number generation

**Line number**:

270

**Code snippet**:

    srand(time(NULL));
    
----------
<h3 align="center">Happy Programming! :smile: :computer:</h3>
