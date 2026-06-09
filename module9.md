EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY

Aim:
To write a C program to display stack elements using an array.

Algorithm:

1. Include necessary header files.
2. Declare global variables for stack and top.
3. Define the display() function.
4. Initialize stack elements.
5. Check whether the stack is empty.
6. Display all elements from top to bottom.
7. End.

Program:

```c
#include <stdio.h>

#define SIZE 5

int stack[SIZE] = {10, 20, 30, 40, 50};
int top = 4;

void display()
{
    int i;

    if(top == -1)
    {
        printf("Stack is Empty\n");
        return;
    }

    printf("Stack Elements:\n");

    for(i = top; i >= 0; i--)
        printf("%d\n", stack[i]);
}

int main()
{
    display();
    return 0;
}
```

Output:

```text
Stack Elements:
50
40
30
20
10
```

Result:
Thus, the program to display stack elements using an array is verified successfully.

EXP NO:12 PROGRAM TO PUSH THE GIVEN ELEMENT INTO A STACK USING ARRAY

Aim:
To create a C program to push the given element into a stack using array.

Algorithm:

1. Declare stack array and top variable.
2. Define push() function.
3. Check stack overflow condition.
4. Increment top.
5. Insert the new element.
6. Display the stack.
7. End.

Program:

```c
#include <stdio.h>

#define SIZE 5

int stack[SIZE];
int top = -1;

void push(int value)
{
    if(top == SIZE - 1)
    {
        printf("Stack Overflow\n");
        return;
    }

    stack[++top] = value;
}

void display()
{
    int i;

    printf("Stack Elements:\n");

    for(i = top; i >= 0; i--)
        printf("%d\n", stack[i]);
}

int main()
{
    push(10);
    push(20);
    push(30);

    display();

    return 0;
}
```

Output:

```text
Stack Elements:
30
20
10
```

Result:
Thus, the program to push the given element into a stack using array is verified successfully.

EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY

Aim:
To write a C program to display queue elements using array.

Algorithm:

1. Declare queue array, front and rear.
2. Define display() function.
3. Check if queue is empty.
4. Print all queue elements from front to rear.
5. End.

Program:

```c
#include <stdio.h>

int queue[5] = {10, 20, 30, 40, 50};
int front = 0;
int rear = 4;

void display()
{
    int i;

    if(front > rear)
    {
        printf("Queue is Empty\n");
        return;
    }

    printf("Queue Elements:\n");

    for(i = front; i <= rear; i++)
        printf("%d ", queue[i]);
}

int main()
{
    display();

    return 0;
}
```

Output:

```text
Queue Elements:
10 20 30 40 50
```

Result:
Thus, the program to display queue elements using array is verified successfully.

EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY

Aim:
To write a C program to insert elements in queue using array.

Algorithm:

1. Declare queue array, front and rear.
2. Define enqueue() function.
3. Check queue overflow condition.
4. Insert element at rear position.
5. Increment rear.
6. Display queue contents.
7. End.

Program:

```c
#include <stdio.h>

#define SIZE 5

int queue[SIZE];
int front = 0;
int rear = -1;

void enqueue(int value)
{
    if(rear == SIZE - 1)
    {
        printf("Queue Overflow\n");
        return;
    }

    queue[++rear] = value;
}

void display()
{
    int i;

    printf("Queue Elements:\n");

    for(i = front; i <= rear; i++)
        printf("%d ", queue[i]);
}

int main()
{
    enqueue(10);
    enqueue(20);
    enqueue(30);

    display();

    return 0;
}
```

Output:

```text
Queue Elements:
10 20 30
```

Result:
Thus, the program to insert elements in queue using array is verified successfully.

EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY

Aim:

To create a function in C that deletes an element from a queue implemented using an array.

Algorithm:

1. Check if the queue is empty.
2. If front == -1, display "Queue Empty".
3. Otherwise delete the front element.
4. Increment front.
5. If front becomes greater than rear, reset both front and rear to -1.
6. Display the updated queue.
7. End.

Program:

```c
#include <stdio.h>

int queue[5] = {10, 20, 30, 40, 50};
int front = 0;
int rear = 4;

void dequeue()
{
    if(front == -1 || front > rear)
    {
        printf("Queue Empty\n");
        return;
    }

    printf("Deleted Element = %d\n", queue[front]);
    front++;

    if(front > rear)
    {
        front = rear = -1;
    }
}

void display()
{
    int i;

    if(front == -1)
    {
        printf("Queue Empty\n");
        return;
    }

    printf("Queue Elements:\n");

    for(i = front; i <= rear; i++)
        printf("%d ", queue[i]);

    printf("\n");
}

int main()
{
    display();

    dequeue();

    display();

    return 0;
}
```

Output:

```text
Queue Elements:
10 20 30 40 50

Deleted Element = 10

Queue Elements:
20 30 40 50
```

Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
