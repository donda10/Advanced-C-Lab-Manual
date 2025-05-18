

EXP NO:21 C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER
Aim:
To write a C program to create a function to find the greatest number

Algorithm:
1.	Include the necessary header #include <stdio.h>.
2.	Use a series of if and else if statements to compare the values and return the maximum among them.
3.	Declare variables n1, n2, n3, n4, and greater to store user input and the result.
4.	Use scanf to take four integers as input.
5.	Call the max_of_four function with the input integers and store the result in the greater variable
 
Program:
```
#include <stdio.h>

int max_of_four(int a, int b, int c, int d) {
    int max = a;

    if (b > max)
        max = b;
    if (c > max)
        max = c;
    if (d > max)
        max = d;

    return max;
}

int main() {
    int n1, n2, n3, n4, greater;

    printf("Enter four integers: ");
    scanf("%d %d %d %d", &n1, &n2, &n3, &n4);

    greater = max_of_four(n1, n2, n3, n4);

    printf("The greatest number is: %d\n", greater);

    return 0;
}


```

Output:


![image](https://github.com/user-attachments/assets/d117f27e-f819-4424-b83f-98faf674d187)

Result:
Thus, the program  that create a function to find the greatest number is verified successfully.


 
EXP NO:22 C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND  XOR COMPARISONS
Aim:
To write a C program to print the maximum values for the AND, OR and XOR comparisons

Algorithm:
1.	Define a function calculate_the_max that takes two integers n and k as parameters.
2.	Declare variables a, o, and x to store the maximum values for AND, OR, and XOR operations, respectively.
3.	Use nested loops to iterate through pairs of integers (i, j) from 1 to n.
4.	Within the loops, check conditions for AND, OR, and XOR operations and update the corresponding maximum values (a, o, x).
5.	Declare variables n and k to store user input.
6.	Use scanf to take two integers as input.
7.	Call the calculate_the_max function with input values.
 
Program:
```
#include <stdio.h>

void calculate_the_max(int n, int k) {
    int a = 0, o = 0, x = 0;
    for (int i = 1; i <= n; i++) {
        for (int j = i + 1; j <= n; j++) {
            int and_val = i & j;
            int or_val = i | j;
            int xor_val = i ^ j;

            if (and_val > a && and_val < k)
                a = and_val;
            if (or_val > o && or_val < k)
                o = or_val;
            if (xor_val > x && xor_val < k)
                x = xor_val;
        }
    }
    printf("Maximum AND value < k: %d\n", a);
    printf("Maximum OR value  < k: %d\n", o);
    printf("Maximum XOR value < k: %d\n", x);
}

int main() {
    int n, k;
    printf("Enter values for n and k: ");
    scanf("%d %d", &n, &k);
    calculate_the_max(n, k);
    return 0;
}


```

Output:

![image](https://github.com/user-attachments/assets/a5fd4d62-a6af-4401-af4f-148d70fe322a)

Result:
Thus, the program to print the maximum values for the AND, OR and XOR comparisons
is verified successfully.


 
EXP NO:23 C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS
Aim:
To write a C program to write the logic for the requests

Algorithm:
1.	Declare variables noshel and noque to store the number of shelves and the number of queries, respectively.
2.	Use scanf to take two integers as input for the number of shelves and queries.
3.	Declare a 2D array shelarr to represent shelves and books, and an array nobookarr to store the number of books on each shelf.
4.	Declare variables k and c to keep track of the book index and the total number of books.
5.	Use a for loop to iterate over the queries.
 
Program:
```
#include <stdio.h>
#include <stdlib.h>

#define MAX_SHELVES 100

int main() {
    int noshel, noque;

    printf("Enter the number of shelves and number of queries: ");
    scanf("%d %d", &noshel, &noque);

    int* nobookarr = (int*)calloc(noshel, sizeof(int));
    int** shelarr = (int**)malloc(noshel * sizeof(int*));

    for (int i = 0; i < noshel; i++) {
        shelarr[i] = (int*)malloc(1100 * sizeof(int));
    }

    printf("\nQuery Types:\n");
    printf("1 x y : Insert book with y pages into shelf x\n");
    printf("2 x y : Print number of pages in the y-th book on shelf x\n");
    printf("3 x   : Print number of books on shelf x\n\n");

    for (int i = 0; i < noque; i++) {
        int type;
        printf("Enter query type (1, 2, or 3): ");
        scanf("%d", &type);

        if (type == 1) {
            int x, y;
            printf("Enter shelf index and number of pages (x y): ");
            scanf("%d %d", &x, &y);
            shelarr[x][nobookarr[x]] = y;
            nobookarr[x]++;
        } else if (type == 2) {
            int x, y;
            printf("Enter shelf index and book index (x y): ");
            scanf("%d %d", &x, &y);
            printf("Number of pages: %d\n", shelarr[x][y]);
        } else if (type == 3) {
            int x;
            printf("Enter shelf index (x): ");
            scanf("%d", &x);
            printf("Number of books on shelf %d: %d\n", x, nobookarr[x]);
        } else {
            printf("Invalid query type.\n");
        }
    }

    for (int i = 0; i < noshel; i++) {
        free(shelarr[i]);
    }
    free(shelarr);
    free(nobookarr);

    return 0;
}

```
Output:

![image](https://github.com/user-attachments/assets/b7c0ba96-dafe-47eb-8f23-5907617ed1c7)



Result:
Thus, the program to write the logic for the requests is verified successfully.


 
EXP NO:24 C PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY.
Aim:
To write a C program print the sum of the integers in the array.

Algorithm:
1.	Declare a variable n to store the number of integers.
2.	Use scanf to take an integer n as input.
3.	Declare an array a of size n to store the integers.
4.	Declare a variable sum and initialize it to zero.
5.	Use a for loop to iterate n times:
6.	Use scanf to input each integer and add it to the sum.
7.	Print the final sum using printf.



Program:
```
#include <stdio.h>

int main() {
    int n, sum = 0;

    printf("Enter the number of integers: ");
    scanf("%d", &n);

    int a[n];

    printf("Enter %d integers:\n", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &a[i]);
        sum += a[i];
    }

    printf("The sum of the integers is: %d\n", sum);

    return 0;
}

```

Output:


![image](https://github.com/user-attachments/assets/c9ac1462-a5f9-42e3-ac49-a8b6687a3d67)


 


Result:
Thus, the program prints the sum of the integers in the array is verified successfully.


 
EXP NO 25: C PROGRAM TO COUNT THE NUMBER OF WORDS IN A      SENTENCE
Aim:

To write a C program that counts the number of words in a given sentence.

Algorithm:

1.	Input the sentence: Take a sentence from the user.
2.	Initialize a counter variable: This will keep track of the number of words.
3.	Process each character of the sentence:
o	Iterate through the sentence, checking each character.
o	If a character is not a space, it may belong to a word. If it's the first non-space character after a space or at the start, increment the word count.
4.	Handle spaces and punctuation: Skip over spaces, punctuation marks, and consider each word as a sequence of characters separated by spaces.
5.	Display the result: After processing the sentence, output the total word count.



Program:
```
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main() {
    char sentence[1000];
    int i, words = 0;
    int inWord = 0;

    printf("Enter a sentence: ");
    fgets(sentence, sizeof(sentence), stdin);

    for (i = 0; sentence[i] != '\0'; i++) {
        if (isspace(sentence[i])) {
            inWord = 0;
        } else if (inWord == 0) {
            inWord = 1;
            words++;
        }
    }

    printf("The number of words in the sentence is: %d\n", words);

    return 0;
}

```

Output:


![image](https://github.com/user-attachments/assets/872f5d8e-33e1-4cd7-ae82-14f5922ef588)



Result:

Thus, the program that counts the number of words in a given sentence is verified 
successfully.
