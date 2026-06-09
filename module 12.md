EXP NO:26 C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST

Aim:
To write a C program to display stack elements using linked list.

Algorithm:

1. Define a structure Node with data and next pointer.
2. Create nodes dynamically.
3. Link the nodes to form a stack.
4. Define a display() function.
5. Traverse the linked list from head.
6. Print each node's data.
7. End.

Program:

```c id="a2ynr5"
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

struct Node *head = NULL;

void display()
{
    struct Node *p = head;

    printf("Stack Elements:\n");

    while(p != NULL)
    {
        printf("%d\n", p->data);
        p = p->next;
    }
}

int main()
{
    struct Node *n1, *n2, *n3;

    n1 = (struct Node *)malloc(sizeof(struct Node));
    n2 = (struct Node *)malloc(sizeof(struct Node));
    n3 = (struct Node *)malloc(sizeof(struct Node));

    n1->data = 30;
    n1->next = n2;

    n2->data = 20;
    n2->next = n3;

    n3->data = 10;
    n3->next = NULL;

    head = n1;

    display();

    return 0;
}
```

Output:

```text id="djlwmv"
Stack Elements:
30
20
10
```

Result:
Thus, the program to display stack elements using linked list is verified successfully.

EXP NO:27 C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING LINKED LIST

Aim:
To write a C program to pop an element from the given stack using linked list.

Algorithm:

1. Check whether the stack is empty.
2. If head is NULL, display "Stack is empty".
3. Otherwise store the top node in a temporary pointer.
4. Move head to the next node.
5. Display the deleted element.
6. Free the deleted node.
7. End.

Program:

```c id="px8qqz"
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

struct Node *head = NULL;

void pop()
{
    struct Node *temp;

    if(head == NULL)
    {
        printf("Stack is Empty\n");
        return;
    }

    temp = head;

    printf("Popped Element = %d\n", temp->data);

    head = head->next;

    free(temp);
}

void display()
{
    struct Node *p = head;

    while(p != NULL)
    {
        printf("%d ", p->data);
        p = p->next;
    }
}

int main()
{
    struct Node *n1, *n2;

    n1 = (struct Node *)malloc(sizeof(struct Node));
    n2 = (struct Node *)malloc(sizeof(struct Node));

    n1->data = 20;
    n1->next = n2;

    n2->data = 10;
    n2->next = NULL;

    head = n1;

    pop();

    printf("Stack After Pop:\n");
    display();

    return 0;
}
```

Output:

```text id="o0z95z"
Popped Element = 20
Stack After Pop:
10
```

Result:
Thus, the program to pop an element from the given stack using linked list is verified successfully.

EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST

Aim:
To write a C program to display queue elements using linked list.

Algorithm:

1. Check whether the queue is empty.
2. Set a pointer to front.
3. Traverse until NULL.
4. Print each node's data.
5. Move to the next node.
6. End.

Program:

```c id="mab3uy"
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

struct Node *front = NULL;

void display()
{
    struct Node *temp = front;

    if(front == NULL)
    {
        printf("Queue is Empty\n");
        return;
    }

    printf("Queue Elements:\n");

    while(temp != NULL)
    {
        printf("%d ", temp->data);
        temp = temp->next;
    }
}

int main()
{
    struct Node *n1, *n2, *n3;

    n1 = (struct Node *)malloc(sizeof(struct Node));
    n2 = (struct Node *)malloc(sizeof(struct Node));
    n3 = (struct Node *)malloc(sizeof(struct Node));

    n1->data = 10;
    n1->next = n2;

    n2->data = 20;
    n2->next = n3;

    n3->data = 30;
    n3->next = NULL;

    front = n1;

    display();

    return 0;
}
```

Output:

```text id="yq2m6v"
Queue Elements:
10 20 30
```

Result:
Thus, the program to display queue elements using linked list is verified successfully.

EXP NO:29 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

Aim:
To write a C program to insert elements in queue using linked list.

Algorithm:

1. Allocate memory for a new node.
2. Store data in the node.
3. Set next pointer to NULL.
4. If queue is empty, assign front and rear to new node.
5. Otherwise link the new node at the rear.
6. Update rear pointer.
7. Display the queue.
8. End.

Program:

```c id="g0iyel"
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

struct Node *front = NULL;
struct Node *rear = NULL;

void enqueue(int value)
{
    struct Node *p;

    p = (struct Node *)malloc(sizeof(struct Node));

    p->data = value;
    p->next = NULL;

    if(front == NULL)
    {
        front = rear = p;
    }
    else
    {
        rear->next = p;
        rear = p;
    }
}

void display()
{
    struct Node *temp = front;

    while(temp != NULL)
    {
        printf("%d ", temp->data);
        temp = temp->next;
    }
}

int main()
{
    enqueue(10);
    enqueue(20);
    enqueue(30);

    printf("Queue Elements:\n");

    display();

    return 0;
}
```

Output:

```text id="ttccg5"
Queue Elements:
10 20 30
```

Result:
Thus, the program to insert elements in queue using linked list is verified successfully.

EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST

Aim:

The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list.

Algorithm:

1. Check whether the queue is empty.
2. If front is NULL, display an error message.
3. Otherwise access the data stored in the front node.
4. Return the front element.
5. End.

Program:

```c id="8n4v4m"
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

struct Node *front = NULL;
struct Node *rear = NULL;

int peek()
{
    if(front == NULL)
    {
        printf("Queue is Empty\n");
        return -1;
    }

    return front->data;
}

void enqueue(int value)
{
    struct Node *p;

    p = (struct Node *)malloc(sizeof(struct Node));

    p->data = value;
    p->next = NULL;

    if(front == NULL)
    {
        front = rear = p;
    }
    else
    {
        rear->next = p;
        rear = p;
    }
}

int main()
{
    enqueue(10);
    enqueue(20);
    enqueue(30);

    printf("Front Element = %d\n", peek());

    return 0;
}
```

Output:

```text id="i6h22i"
Front Element = 10
```

Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.
