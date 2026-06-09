EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST

Aim:
To write a C program to search a given element in the given linked list.

Algorithm:

1. Define the structure for a node in a linked list.
2. Create nodes and link them together.
3. Define the search function to find a specific element.
4. Traverse the linked list node by node.
5. Compare each node's data with the search element.
6. If found, display the position.
7. Otherwise display "Element not found".
8. End.

Program:

```c
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

void search(struct Node *head, int key)
{
    int pos = 1;

    while(head != NULL)
    {
        if(head->data == key)
        {
            printf("Element found at position %d\n", pos);
            return;
        }
        head = head->next;
        pos++;
    }

    printf("Element not found\n");
}

int main()
{
    struct Node *head, *second, *third;

    head = (struct Node *)malloc(sizeof(struct Node));
    second = (struct Node *)malloc(sizeof(struct Node));
    third = (struct Node *)malloc(sizeof(struct Node));

    head->data = 10;
    head->next = second;

    second->data = 20;
    second->next = third;

    third->data = 30;
    third->next = NULL;

    search(head, 20);

    return 0;
}
```

Output:

```text
Element found at position 2
```

Result:
Thus, the program to search a given element in the given linked list is verified successfully.

EXP NO:17 PROGRAM TO INSERT A NODE IN A LINKED LIST

Aim:
To write a C program to insert a node in a linked list.

Algorithm:

1. Define the structure for a node.
2. Create a new node dynamically.
3. Store data in the new node.
4. If the list is empty, make the new node the head.
5. Otherwise traverse to the end of the list.
6. Insert the node at the end.
7. Display the linked list.
8. End.

Program:

```c
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

void insert(struct Node **head, int value)
{
    struct Node *newNode, *temp;

    newNode = (struct Node *)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;

    if(*head == NULL)
    {
        *head = newNode;
        return;
    }

    temp = *head;

    while(temp->next != NULL)
        temp = temp->next;

    temp->next = newNode;
}

void display(struct Node *head)
{
    while(head != NULL)
    {
        printf("%d ", head->data);
        head = head->next;
    }
}

int main()
{
    struct Node *head = NULL;

    insert(&head, 10);
    insert(&head, 20);
    insert(&head, 30);

    display(head);

    return 0;
}
```

Output:

```text
10 20 30
```

Result:
Thus, the program to insert a node in a linked list is verified successfully.

EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST

Aim:
To write a C program to traverse a doubly linked list.

Algorithm:

1. Create nodes for a doubly linked list.
2. Connect nodes using next and prev pointers.
3. Initialize temp pointer to head.
4. Traverse until temp becomes NULL.
5. Print the data of each node.
6. End.

Program:

```c
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *prev;
    struct Node *next;
};

int main()
{
    struct Node *head, *second, *third, *temp;

    head = (struct Node *)malloc(sizeof(struct Node));
    second = (struct Node *)malloc(sizeof(struct Node));
    third = (struct Node *)malloc(sizeof(struct Node));

    head->data = 10;
    head->prev = NULL;
    head->next = second;

    second->data = 20;
    second->prev = head;
    second->next = third;

    third->data = 30;
    third->prev = second;
    third->next = NULL;

    temp = head;

    printf("Doubly Linked List:\n");

    while(temp != NULL)
    {
        printf("%d ", temp->data);
        temp = temp->next;
    }

    return 0;
}
```

Output:

```text
Doubly Linked List:
10 20 30
```

Result:
Thus, the program to traverse a doubly linked list is verified successfully.

EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST

Aim:
To write a C program to insert an element in doubly linked list.

Algorithm:

1. Create a new node.
2. Assign data to the new node.
3. If list is empty, make it the head node.
4. Otherwise traverse to the last node.
5. Connect the new node using next and prev links.
6. Display the doubly linked list.
7. End.

Program:

```c
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *prev;
    struct Node *next;
};

void insert(struct Node **head, int value)
{
    struct Node *newNode, *temp;

    newNode = (struct Node *)malloc(sizeof(struct Node));

    newNode->data = value;
    newNode->next = NULL;

    if(*head == NULL)
    {
        newNode->prev = NULL;
        *head = newNode;
        return;
    }

    temp = *head;

    while(temp->next != NULL)
        temp = temp->next;

    temp->next = newNode;
    newNode->prev = temp;
}

void display(struct Node *head)
{
    while(head != NULL)
    {
        printf("%d ", head->data);
        head = head->next;
    }
}

int main()
{
    struct Node *head = NULL;

    insert(&head, 10);
    insert(&head, 20);
    insert(&head, 30);

    display(head);

    return 0;
}
```

Output:

```text
10 20 30
```

Result:
Thus, the program to insert an element in doubly linked list is verified successfully.

EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST

Aim:
To write a C function that deletes a given element from a linked list.

Algorithm:

1. Check if the linked list is empty.
2. Compare the head node with the element.
3. If found at the first node, update head.
4. Otherwise traverse the linked list.
5. Locate the node containing the element.
6. Update links to remove the node.
7. Free the deleted node.
8. Display the updated linked list.
9. End.

Program:

```c
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

void deleteNode(struct Node **head, int key)
{
    struct Node *temp = *head;
    struct Node *prev = NULL;

    if(temp != NULL && temp->data == key)
    {
        *head = temp->next;
        free(temp);
        return;
    }

    while(temp != NULL && temp->data != key)
    {
        prev = temp;
        temp = temp->next;
    }

    if(temp == NULL)
    {
        printf("Element not found\n");
        return;
    }

    prev->next = temp->next;
    free(temp);
}

void display(struct Node *head)
{
    while(head != NULL)
    {
        printf("%d ", head->data);
        head = head->next;
    }
}

int main()
{
    struct Node *head, *second, *third;

    head = (struct Node *)malloc(sizeof(struct Node));
    second = (struct Node *)malloc(sizeof(struct Node));
    third = (struct Node *)malloc(sizeof(struct Node));

    head->data = 10;
    head->next = second;

    second->data = 20;
    second->next = third;

    third->data = 30;
    third->next = NULL;

    deleteNode(&head, 20);

    printf("Linked List after deletion:\n");
    display(head);

    return 0;
}
```

Output:

```text
Linked List after deletion:
10 30
```

Result:
Thus, the function that deletes a given element from a linked list is verified successfully.
