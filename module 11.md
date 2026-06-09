EXP NO:21 C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER

Aim:
To write a C program to create a function to find the greatest number.

Algorithm:

1. Include the necessary header file stdio.h.
2. Define a function max_of_four() that accepts four integers.
3. Compare the values using if and else-if statements.
4. Return the greatest value.
5. Read four integers from the user.
6. Call the function and store the result.
7. Display the greatest number.
8. End.

Program:

```c id="0z5r7j"
#include <stdio.h>

int max_of_four(int a, int b, int c, int d)
{
    int max = a;

    if(b > max)
        max = b;

    if(c > max)
        max = c;

    if(d > max)
        max = d;

    return max;
}

int main()
{
    int n1, n2, n3, n4, greater;

    printf("Enter four numbers: ");
    scanf("%d %d %d %d", &n1, &n2, &n3, &n4);

    greater = max_of_four(n1, n2, n3, n4);

    printf("Greatest Number = %d\n", greater);

    return 0;
}
```

Output:

```text id="slc3ml"
Enter four numbers: 10 45 23 18
Greatest Number = 45
```

Result:
Thus, the program that creates a function to find the greatest number is verified successfully.

EXP NO:22 C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND XOR COMPARISONS

Aim:
To write a C program to print the maximum values for the AND, OR and XOR comparisons.

Algorithm:

1. Define a function calculate_the_max().
2. Initialize variables for maximum AND, OR and XOR values.
3. Use nested loops to generate all possible pairs.
4. Compute AND, OR and XOR values.
5. Compare each result with k.
6. Store the maximum valid values.
7. Print the results.
8. End.

Program:

```c id="h2v0xt"
#include <stdio.h>

void calculate_the_max(int n, int k)
{
    int max_and = 0, max_or = 0, max_xor = 0;
    int i, j;

    for(i = 1; i <= n; i++)
    {
        for(j = i + 1; j <= n; j++)
        {
            if((i & j) < k && (i & j) > max_and)
                max_and = i & j;

            if((i | j) < k && (i | j) > max_or)
                max_or = i | j;

            if((i ^ j) < k && (i ^ j) > max_xor)
                max_xor = i ^ j;
        }
    }

    printf("%d\n", max_and);
    printf("%d\n", max_or);
    printf("%d\n", max_xor);
}

int main()
{
    int n, k;

    printf("Enter n and k: ");
    scanf("%d %d", &n, &k);

    calculate_the_max(n, k);

    return 0;
}
```

Output:

```text id="n5kr9u"
Enter n and k: 5 4
2
3
3
```

Result:
Thus, the program to print the maximum values for the AND, OR and XOR comparisons is verified successfully.

EXP NO:23 C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS

Aim:
To write a C program to implement the logic for dynamic array requests.

Algorithm:

1. Read the number of shelves and queries.
2. Create arrays to store books and shelf counts.
3. Process each query.
4. Type 1 query inserts a book.
5. Type 2 query displays a specific book.
6. Type 3 query displays the number of books on a shelf.
7. End.

Program:

```c id="4s5d4o"
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int total_shelves, total_queries;
    scanf("%d %d", &total_shelves, &total_queries);

    int *total_books = (int *)calloc(total_shelves, sizeof(int));
    int **total_pages = (int **)calloc(total_shelves, sizeof(int*));

    while(total_queries--)
    {
        int type;
        scanf("%d", &type);

        if(type == 1)
        {
            int x, y;
            scanf("%d %d", &x, &y);

            total_books[x]++;

            total_pages[x] = realloc(total_pages[x],
                total_books[x] * sizeof(int));

            total_pages[x][total_books[x] - 1] = y;
        }
        else if(type == 2)
        {
            int x, y;
            scanf("%d %d", &x, &y);

            printf("%d\n", total_pages[x][y]);
        }
        else
        {
            int x;
            scanf("%d", &x);

            printf("%d\n", total_books[x]);
        }
    }

    return 0;
}
```

Output:

```text id="7pnzmb"
Input:
2 3
1 0 100
1 0 200
3 0

Output:
2
```

Result:
Thus, the program to write the logic for the requests is verified successfully.

EXP NO:24 C PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY

Aim:
To write a C program to print the sum of the integers in the array.

Algorithm:

1. Read the size of the array.
2. Declare an array.
3. Initialize sum to zero.
4. Read array elements.
5. Add each element to sum.
6. Display the final sum.
7. End.

Program:

```c id="4d7f1x"
#include <stdio.h>

int main()
{
    int n, i, sum = 0;

    printf("Enter size: ");
    scanf("%d", &n);

    int a[n];

    printf("Enter elements:\n");

    for(i = 0; i < n; i++)
    {
        scanf("%d", &a[i]);
        sum += a[i];
    }

    printf("Sum = %d\n", sum);

    return 0;
}
```

Output:

```text id="jlwmwr"
Enter size: 5
Enter elements:
10 20 30 40 50
Sum = 150
```

Result:
Thus, the program prints the sum of the integers in the array and is verified successfully.

EXP NO:25 C PROGRAM TO COUNT THE NUMBER OF WORDS IN A SENTENCE

Aim:
To write a C program that counts the number of words in a given sentence.

Algorithm:

1. Input the sentence.
2. Initialize word count to zero.
3. Traverse each character of the sentence.
4. If a non-space character follows a space or is at the beginning, increment count.
5. Continue until end of string.
6. Display the word count.
7. End.

Program:

```c id="b0um6x"
#include <stdio.h>
#include <string.h>

int main()
{
    char str[200];
    int i, count = 0;

    printf("Enter a sentence:\n");
    fgets(str, sizeof(str), stdin);

    for(i = 0; str[i] != '\0'; i++)
    {
        if((i == 0 && str[i] != ' ') ||
           (str[i] != ' ' && str[i - 1] == ' '))
        {
            count++;
        }
    }

    printf("Number of words = %d\n", count);

    return 0;
}
```

Output:

```text id="r5wz8d"
Enter a sentence:
C programming is easy
Number of words = 4
```

Result:
Thus, the program that counts the number of words in a given sentence is verified successfully.
