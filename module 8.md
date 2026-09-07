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
    int n;
    scanf("%d", &n);

    if (n == 1)
        printf("one");
    else if (n == 2)
        printf("two");
    else if (n == 3)
        printf("three");
    else if (n == 4)
        printf("four");
    else if (n == 5)
        printf("five");
    else if (n == 6)
        printf("six");
    else if (n == 7)
        printf("seven");
    else if (n == 8)
        printf("eight");
    else if (n == 9)
        printf("nine");
    else
        printf("Greater than 9");

    return 0;
}

```



Output:


<img width="557" height="252" alt="image" src="https://github.com/user-attachments/assets/561eb007-2f38-44e8-8147-286cdc53059c" />






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
    char str[1000];
    int count[10] = {0};
    int i;
    scanf("%s", str);
    for (i = 0; str[i] != '\0'; i++) {
        if (str[i] >= '0' && str[i] <= '9') {
            count[str[i] - '0']++;
        }
    }
    for (i = 0; i < 10; i++) {
        printf("%d ", count[i]);
    }

    return 0;
}

```



Output:


<img width="726" height="227" alt="image" src="https://github.com/user-attachments/assets/5d0fec5e-27d1-4617-8347-2882027c646a" />






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
#include <stdlib.h>
#include <string.h>

int next_permutation(int n, char **s){
    int i = n - 2;
    while (i >= 0 && strcmp(s[i], s[i + 1]) >= 0)
        i--;

    if (i < 0)
        return 0;
    int j = n - 1;
    while (strcmp(s[j], s[i]) <= 0)
        j--;

    char *temp = s[i];
    s[i] = s[j];
    s[j] = temp;
    int left = i + 1;
    int right = n - 1;
    while (left < right){
        temp = s[left];
        s[left] = s[right];
        s[right] = temp;

        left++;
        right--;
    }
    return 1;
}
int main(){
    int n;
    scanf("%d", &n);
    char **s = malloc(n * sizeof(char *));
    for (int i = 0; i < n; i++){
        s[i] = malloc(11 * sizeof(char));
        scanf("%s", s[i]);
    }
    do{
        for (int i = 0; i < n; i++){
            printf("%s", s[i]);
            if (i != n - 1)
                printf(" ");
        }
        printf("\n");
    }
    while (next_permutation(n, s));

    for (int i = 0; i < n; i++)
        free(s[i]);
    free(s);
    return 0;
}

```



Output:


<img width="456" height="358" alt="image" src="https://github.com/user-attachments/assets/3a4d54cf-d02e-4312-8664-e39c8dd9bcf0" />






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
int main(){
    int n;
    scanf("%d", &n);
    int size = 2 * n - 1;
    for (int i = 0; i < size; i++){
        for (int j = 0; j < size; j++){
            int top = i;
            int left = j;
            int bottom = size - 1 - i;
            int right = size - 1 - j;

            int min = top;

            if (left < min)
                min = left;
            if (bottom < min)
                min = bottom;
            if (right < min)
                min = right;

            printf("%d ", n - min);
        }
        printf("\n");
    }
    return 0;
}

```




Output:



<img width="601" height="675" alt="image" src="https://github.com/user-attachments/assets/6f8f0292-9f12-44fd-9932-301b3ab5f3a5" />



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

int sumOfDigits()
{
    int n;
    scanf("%d", &n);

    int sum = 0;

    sum = sum + (n % 10);
    n = n / 10;

    sum = sum + (n % 10);
    n = n / 10;

    sum = sum + (n % 10);
    n = n / 10;

    sum = sum + (n % 10);
    n = n / 10;

    sum = sum + (n % 10);

    return sum;
}

int main()
{
    int sum;

    sum = sumOfDigits();

    printf("%d", sum);

    return 0;
}

```



Output:


<img width="575" height="315" alt="image" src="https://github.com/user-attachments/assets/99306b69-e6ad-490d-ba04-318b845aa429" />






Result:
Thus, the program is verified successfully



























