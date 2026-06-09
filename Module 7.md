EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE

Aim:
To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.

Algorithm:

1. Declare structure eligible with age (integer) and n (character array).
2. Declare variable e of type eligible.
3. Input age and name using scanf, store in e.
4. If e.age <= 6

   * Print "Vaccine Eligibility: No"
     Else
   * Print "Vaccine Eligibility: Yes"
5. Print details (e.age, e.n).
6. Return 0.

Program:

```c
#include <stdio.h>

struct eligible
{
    int age;
    char n[50];
};

int main()
{
    struct eligible e;

    printf("Enter Name: ");
    scanf("%s", e.n);

    printf("Enter Age: ");
    scanf("%d", &e.age);

    if (e.age <= 6)
        printf("Vaccine Eligibility: No\n");
    else
        printf("Vaccine Eligibility: Yes\n");

    printf("Name : %s\n", e.n);
    printf("Age  : %d\n", e.age);

    return 0;
}
```

Output:

```text
Enter Name: Ravi
Enter Age: 10
Vaccine Eligibility: Yes
Name : Ravi
Age  : 10
```

Result:
Thus, the program is verified successfully.

EXP NO:2 C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION

Aim:
To write a C program for passing structure as function and returning a structure from a function.

Algorithm:

1. Define structure numbers with members a and b.
2. Declare variable n of type numbers.
3. Prompt the user to enter values for a and b.
4. Input values for a and b into n using scanf.
5. Call the add function with n as an argument.
6. Print the result returned by the add function.
7. Return 0.

Program:

```c
#include <stdio.h>

struct numbers
{
    int a;
    int b;
};

struct numbers add(struct numbers n)
{
    struct numbers result;
    result.a = n.a + n.b;
    return result;
}

int main()
{
    struct numbers n, res;

    printf("Enter two numbers: ");
    scanf("%d %d", &n.a, &n.b);

    res = add(n);

    printf("Sum = %d\n", res.a);

    return 0;
}
```

Output:

```text
Enter two numbers: 10 20
Sum = 30
```

Result:
Thus, the program is verified successfully.

EXP NO:3 C PROGRAM TO READ A FILE NAME FROM USER AND WRITE THAT FILE USING FOPEN()

Aim:
To write a C program to read a file name from user.

Algorithm:

1. Include the necessary header file stdio.h.
2. Begin the main function.
3. Declare a file pointer p.
4. Declare a character array name to store the file name.
5. Prompt the user to enter a file name.
6. Use scanf to input the file name into the name array.
7. Use fopen to open a file with the name provided by the user in write mode ("w").
8. If successful, continue to the next step.
9. If unsuccessful, print an error message and exit the program.
10. Print a message indicating that the file has been created successfully.
11. Use fclose to close the file.
12. Print a message indicating that the file has been closed.
13. Return 0.

Program:

```c
#include <stdio.h>

int main()
{
    FILE *p;
    char name[50];

    printf("Enter file name: ");
    scanf("%s", name);

    p = fopen(name, "w");

    if (p == NULL)
    {
        printf("File cannot be created.\n");
        return 1;
    }

    printf("File %s created successfully.\n", name);
    printf("File opened successfully.\n");

    fclose(p);

    printf("File closed successfully.\n");

    return 0;
}
```

Output:

```text
Enter file name: sample.txt
File sample.txt created successfully.
File opened successfully.
File closed successfully.
```

Result:
Thus, the program is verified successfully.

EXP NO:4 PROGRAM TO READ A FILE NAME FROM USER, WRITE THAT FILE AND INSERT TEXT INTO THAT FILE

Aim:
To write a C program to read a file and insert text into that file.

Algorithm:

1. Include the necessary header file stdio.h.
2. Begin the main function.
3. Declare a file pointer p.
4. Declare character arrays name and text.
5. Declare an integer variable num.
6. Prompt the user to enter a file name and the number of strings.
7. Open the file in write mode using fopen().
8. If the file cannot be opened, print an error message and terminate.
9. Read strings from the user.
10. Write each string into the file using fputs().
11. Close the file using fclose().
12. Display a success message.
13. Return 0.

Program:

```c
#include <stdio.h>

int main()
{
    FILE *p;
    char name[50], text[100];
    int num, i;

    printf("Enter file name: ");
    scanf("%s", name);

    printf("Enter number of strings: ");
    scanf("%d", &num);

    p = fopen(name, "w");

    if (p == NULL)
    {
        printf("File cannot be opened.\n");
        return 1;
    }

    printf("Enter strings:\n");

    for (i = 0; i < num; i++)
    {
        scanf("%s", text);
        fputs(text, p);
        fputs("\n", p);
    }

    fclose(p);

    printf("Data added successfully.\n");

    return 0;
}
```

Output:

```text
Enter file name: data.txt
Enter number of strings: 3
Enter strings:
Apple
Orange
Mango
Data added successfully.
```

Result:
Thus, the program is verified successfully.

EXP NO:5 C PROGRAM TO DISPLAY STUDENT DETAILS USING STRUCTURE

Aim:
The aim of this program is to dynamically allocate memory to store information about multiple subjects (name and marks), input the details for each subject, and then display the stored information. Finally, it frees the allocated memory to prevent memory leaks.

Algorithm:

1. Input the number of subjects.
2. Read the integer value n from the user.
3. Dynamically allocate memory using malloc().
4. Check whether memory allocation is successful.
5. Input subject name and marks.
6. Store the details in dynamically allocated memory.
7. Display all subject details.
8. Free the allocated memory using free().
9. Return 0.

Program:

```c
#include <stdio.h>
#include <stdlib.h>

struct subject
{
    char name[50];
    int marks;
};

int main()
{
    int n, i;

    printf("Enter number of subjects: ");
    scanf("%d", &n);

    struct subject *s;

    s = (struct subject *)malloc(n * sizeof(struct subject));

    if (s == NULL)
    {
        printf("Memory allocation failed.\n");
        return 1;
    }

    for (i = 0; i < n; i++)
    {
        printf("Enter subject name and marks: ");
        scanf("%s %d", s[i].name, &s[i].marks);
    }

    printf("\nStudent Details:\n");

    for (i = 0; i < n; i++)
    {
        printf("Subject: %s\tMarks: %d\n", s[i].name, s[i].marks);
    }

    free(s);

    return 0;
}
```

Output:

```text
Enter number of subjects: 3
Enter subject name and marks: C 90
Enter subject name and marks: Java 85
Enter subject name and marks: Python 95

Student Details:
Subject: C       Marks: 90
Subject: Java    Marks: 85
Subject: Python  Marks: 95
```

Result:
Thus, the program is verified successfully.
