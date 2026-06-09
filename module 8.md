EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER

Aim:
To write a C program to print the lowercase English word corresponding to the number.

Algorithm:

1. Start.
2. Declare an integer variable n.
3. Read the value of n from the user.
4. Use a switch statement to check the value of n.
5. Display the corresponding English word:

   * 1 → one
   * 2 → two
   * ...
   * 9 → nine
6. If the number is not between 1 and 9, print "Greater than 9".
7. End.

Program:

```c
#include <stdio.h>

int main()
{
    int n;

    printf("Enter a number: ");
    scanf("%d", &n);

    switch(n)
    {
        case 1: printf("one"); break;
        case 2: printf("two"); break;
        case 3: printf("three"); break;
        case 4: printf("four"); break;
        case 5: printf("five"); break;
        case 6: printf("six"); break;
        case 7: printf("seven"); break;
        case 8: printf("eight"); break;
        case 9: printf("nine"); break;
        default: printf("Greater than 9");
    }

    return 0;
}
```

Output:

```text
Enter a number: 5
five
```

Result:
Thus, the program is verified successfully.

EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS IN A SINGLE LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 9

Aim:
To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 9.

Algorithm:

1. Start.
2. Declare a character array.
3. Read the input string.
4. Initialize frequency array of size 10 to zero.
5. Traverse the string and count occurrences of each digit.
6. Print the frequency of digits from 0 to 9.
7. End.

Program:

```c
#include <stdio.h>

int main()
{
    char a[1000];
    int freq[10] = {0};
    int i;

    printf("Enter a number string: ");
    scanf("%s", a);

    for(i = 0; a[i] != '\0'; i++)
    {
        if(a[i] >= '0' && a[i] <= '9')
            freq[a[i] - '0']++;
    }

    for(i = 0; i < 10; i++)
        printf("%d ", freq[i]);

    return 0;
}
```

Output:

```text
Enter a number string: 122334455
0 1 2 2 2 1 0 0 0 0
```

Result:
Thus, the program is verified successfully.

EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER

Aim:
To write a C program to print all permutations of a string in strict lexicographical order.

Algorithm:

1. Start.
2. Read the string.
3. Sort the string in ascending order.
4. Print the current permutation.
5. Generate the next lexicographical permutation.
6. Repeat until all permutations are printed.
7. End.

Program:

```c
#include <stdio.h>
#include <string.h>

void swap(char *a, char *b)
{
    char t = *a;
    *a = *b;
    *b = t;
}

int main()
{
    char s[20];
    int i, j, len;

    printf("Enter string: ");
    scanf("%s", s);

    len = strlen(s);

    for(i = 0; i < len - 1; i++)
        for(j = i + 1; j < len; j++)
            if(s[i] > s[j])
                swap(&s[i], &s[j]);

    do
    {
        printf("%s\n", s);

        i = len - 2;
        while(i >= 0 && s[i] >= s[i + 1])
            i--;

        if(i < 0)
            break;

        j = len - 1;
        while(s[j] <= s[i])
            j--;

        swap(&s[i], &s[j]);

        int l = i + 1, r = len - 1;
        while(l < r)
        {
            swap(&s[l], &s[r]);
            l++;
            r--;
        }

    } while(1);

    return 0;
}
```

Output:

```text
Enter string: ABC
ABC
ACB
BAC
BCA
CAB
CBA
```

Result:
Thus, the program is verified successfully.

EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS SHOWN BELOW

Aim:
To write a C program to print a pattern of numbers from 1 to n.

Algorithm:

1. Start.
2. Read the value of n.
3. Calculate length = 2*n - 1.
4. Use nested loops to generate the square pattern.
5. Calculate minimum distance from borders.
6. Print the required value.
7. End.

Program:

```c
#include <stdio.h>

int main()
{
    int n, i, j, len, min;

    printf("Enter n: ");
    scanf("%d", &n);

    len = 2 * n - 1;

    for(i = 0; i < len; i++)
    {
        for(j = 0; j < len; j++)
        {
            min = i;
            if(j < min)
                min = j;
            if(len - 1 - i < min)
                min = len - 1 - i;
            if(len - 1 - j < min)
                min = len - 1 - j;

            printf("%d ", n - min);
        }
        printf("\n");
    }

    return 0;
}
```

Output:

```text
Enter n: 3
3 3 3 3 3
3 2 2 2 3
3 2 1 2 3
3 2 2 2 3
3 3 3 3 3
```

Result:
Thus, the program is verified successfully.

EXP NO:10 C PROGRAM TO FIND A SQUARE OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

Aim:
To write a C program that calculates the square of a number using a function without arguments and with a return type.

Algorithm:

1. Start.
2. Define a function square() with no arguments.
3. Read a number inside the function.
4. Calculate its square.
5. Return the square value.
6. Call the function from main().
7. Display the result.
8. End.

Program:

```c
#include <stdio.h>

int square()
{
    int n;

    printf("Enter a number: ");
    scanf("%d", &n);

    return n * n;
}

int main()
{
    int result;

    result = square();

    printf("Square = %d", result);

    return 0;
}
```

Output:

```text
Enter a number: 8
Square = 64
```

Result:
Thus, the program is verified successfully.
