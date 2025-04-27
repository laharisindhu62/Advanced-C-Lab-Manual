EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER



Aim:
To write a C program print the lowercase English word corresponding to the number
Algorithm:
1.	Start
- Initialize an integer variable n.
2.	Input Validation
3.	Switch Statement cases.
-	Case 5: Print "seventy one"
-	Case 6: Print "seventy two"
-	Case 13: Print "seventy three"
-	...
-	Case 13: Print "seventy nine"
-	Default: Print "Greater than 13"
4.	Exit the program.
 
Program:

```
#include <stdio.h>

int main() {
    int num;

    // Step 1: Get the number from user
    printf("Enter a number (1 to 9): ");
    scanf("%d", &num);

    // Step 2: Print the corresponding English word
    switch (num) {
        case 1:
            printf("one\n");
            break;
        case 2:
            printf("two\n");
            break;
        case 3:
            printf("three\n");
            break;
        case 4:
            printf("four\n");
            break;
        case 5:
            printf("five\n");
            break;
        case 6:
            printf("six\n");
            break;
        case 7:
            printf("seven\n");
            break;
        case 8:
            printf("eight\n");
            break;
        case 9:
            printf("nine\n");
            break;
        default:
            printf("Number out of range\n");
    }

    return 0;
}
```




Output:


![image](https://github.com/user-attachments/assets/8baab1fd-3b22-47e1-8c9d-a01cf37f0985)







Result:
Thus, the program is verified successfully
 
EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS     IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .


Aim:
To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3.
Algorithm:
1.	Start
2.	Declare char array a[50] outer loop for each digit from 0 to 3
3.	Initialize counter c to 0
4.	For each character in the string print count c for current digit, followed by a space
5.	Increment h to move to the next digit
6.	End
 
Program:

```
#include <stdio.h>

int main() {
    int nums[10], frequency[4] = {0};  // Array to store numbers and frequency of digits 0 to 3

    // Step 1: Input 10 integers
    printf("Enter 10 integers: ");
    for (int i = 0; i < 10; i++) {
        scanf("%d", &nums[i]);
    }

    // Step 2: Calculate the frequency of digits 0 to 3
    for (int i = 0; i < 10; i++) {
        int num = nums[i];
        while (num > 0) {
            int digit = num % 10;
            if (digit >= 0 && digit <= 3) {
                frequency[digit]++;
            }
            num /= 10;
        }
    }

    // Step 3: Print the frequency of digits 0 to 3
    printf("Frequency of digits 0 to 3: ");
    for (int i = 0; i < 4; i++) {
        printf("%d ", frequency[i]);
    }
    printf("\n");

    return 0;
}
```




Output:


![image](https://github.com/user-attachments/assets/a93c6354-a76c-4417-876f-20267efe4e44)







Result:
Thus, the program is verified successfully

EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.


Aim:
To write a C program to print all of its permutations in strict lexicographical order.

Algorithm:
1.	Start
2.	Declare variables s (pointer to an array of strings) and n (number of strings)

3.	Memory Allocation
Dynamically allocate memory for s to store an array of strings
4.	Input
Read the number of strings n from the user Dynamically allocate memory for each string in s
5.	Permutation Generation Loop
6.	Memory Deallocation
Free the memory allocated for each string in s Free the memory allocated for s
7.	End
 
Program:

```
#include <stdio.h>
#include <string.h>
#include <stdlib.h>

// Function to compare two characters for qsort (needed for lexicographical sorting)
int compare(const void *a, const void *b) {
    return (*(char *)a - *(char *)b);
}

// Function to print all permutations of a string
void printPermutations(char *str, int l, int r) {
    if (l == r) {
        printf("%s\n", str);
    } else {
        for (int i = l; i <= r; i++) {
            // Swap characters at positions l and i
            char temp = str[l];
            str[l] = str[i];
            str[i] = temp;

            // Recurse for the next part of the string
            printPermutations(str, l + 1, r);

            // Backtrack (restore the original configuration)
            temp = str[l];
            str[l] = str[i];
            str[i] = temp;
        }
    }
}

int main() {
    char str[100];

    // Step 1: Input the string from the user
    printf("Enter a string: ");
    scanf("%s", str);

    // Step 2: Sort the string lexicographically
    qsort(str, strlen(str), sizeof(char), compare);

    // Step 3: Print all permutations in lexicographical order
    printf("All permutations in lexicographical order are:\n");
    printPermutations(str, 0, strlen(str) - 1);

    return 0;
}
```




Output:


![image](https://github.com/user-attachments/assets/bb673f2a-5e40-4f05-af0a-6471e764807d)







Result:
Thus, the program is verified successfully
 
EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS
SHOWN BELOW.


Aim:
To write a C program to print a pattern of numbers from 1 to n as shown below.
Algorithm:
1.	Start
2.	Declare integer variables n, i, j, min
3.	Read the value of n from the user
4.	Calculate the length of the side of the square matrix: len = n * 2 - 1
5.	Matrix Generation Loop
6.	Calculate min as the minimum distance to the borders
7.	End
 
Program:

```
#include <stdio.h>

int main() {
    int n, i, j;

    printf("Enter the value of n: ");
    scanf("%d", &n);

    for (i = 1; i <= n; i++) {
        for (j = 1; j <= i; j++) {
            printf("%d ", j);
        }
        printf("\n");
    }

    return 0;
}
```




Output:


![image](https://github.com/user-attachments/assets/4967dc31-1ea2-416f-9eff-4e6b5394f3ef)







Result:
Thus, the program is verified successfully

EXP NO:10 C PROGRAM TO FIND A SQUARE  OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE



Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

Algorithm:

1.	Start.
2.	Define a function square() with no parameters. This function will return an integer value.
3.	Inside the function:
o	Declare an integer variable to store the number.
o	Ask the user to input a number.
o	Calculate the square of the number (multiply the number by itself).
o	Return the squared value.
4.	In the main function:
o	Call the square() function and display the result.
5.	End.

Program:

```
#include <stdio.h>

// Function that does not take any arguments but returns the square
int findSquare() {
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);
    return num * num;
}

int main() {
    int square;

    square = findSquare(); // Call the function and store the result

    printf("Square of the number is: %d\n", square);

    return 0;
}
```




Output:


![image](https://github.com/user-attachments/assets/4982e1c3-68bd-4d47-b0fc-88dd19b53aa0)







Result:
Thus, the program is verified successfully



























