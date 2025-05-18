

EXP NO 26: C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display stack elements using linked list.

Algorithm:
1.	Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
2.	Declare a global variable head representing the starting node of the linked list.
3.	Define a function display to print the elements of the linked list.
4.	Declare a pointer p and initialize it with the head of the linked list.
5.	Use a while loop to traverse the linked list:
6.	Print the data of the current node.
7.	Move to the next node using the next pointer.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

struct Node* head = NULL;

void push(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = head;
    head = newNode;
}

void display() {
    struct Node* p = head;
    if (p == NULL) {
        printf("Stack is empty.\n");
        return;
    }

    printf("Stack elements:\n");
    while (p != NULL) {
        printf("%d\n", p->data);
        p = p->next;
    }
}

int main() {
    int n, val;

    printf("Enter the number of elements to push into the stack: ");
    scanf("%d", &n);

    for (int i = 0; i < n; i++) {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &val);
        push(val);
    }

    display();

    return 0;
}


```

Output:


![image](https://github.com/user-attachments/assets/628ab139-4d32-427c-9a9e-9f197b7e50d1)



Result:
Thus, the program to display stack elements using linked list is verified successfully. 



EXP.NO 27: C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING 
LINKED LIST.
Aim:
To write a C program to pop an element from the given stack using liked list.

Algorithm:
1.	Check for Empty Stack
2.	If head is equal to NULL, Print "Stack is empty."
3.	Else Proceed to the next step.
4.	Set head to point to the next node in the stack.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

struct Node* head = NULL;

void push(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = head;
    head = newNode;
}

void pop() {
    if (head == NULL) {
        printf("Stack is empty.\n");
        return;
    }

    struct Node* temp = head;
    printf("Popped element: %d\n", temp->data);
    head = head->next;
    free(temp);
}

void display() {
    struct Node* p = head;
    if (p == NULL) {
        printf("Stack is empty.\n");
        return;
    }

    printf("Stack elements:\n");
    while (p != NULL) {
        printf("%d\n", p->data);
        p = p->next;
    }
}

int main() {
    int n, val;

    printf("Enter the number of elements to push into the stack: ");
    scanf("%d", &n);

    for (int i = 0; i < n; i++) {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &val);
        push(val);
    }

    printf("\nBefore popping:\n");
    display();

    printf("\nPerforming pop operation...\n");
    pop();

    printf("\nAfter popping:\n");
    display();

    return 0;
}

```

Output:


![image](https://github.com/user-attachments/assets/47e38d49-07a6-408f-b540-b9c5231fc2d5)




Result:
Thus, the program to pop an element from the given stack using liked list is verified successfully.

 
EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display queue elements using linked list.
Algorithm:
1.	Check if Queue is Empty
2.	Display Queue Elements
3.	Print the data of the current node pointed to by front
4.	Update front to point to the next node.
5.	End the display function.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

struct Node* front = NULL;
struct Node* rear = NULL;

void enqueue(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;

    if (rear == NULL) {
        front = rear = newNode;
    } else {
        rear->next = newNode;
        rear = newNode;
    }
}

void display() {
    struct Node* temp = front;

    if (temp == NULL) {
        printf("Queue is empty.\n");
        return;
    }

    printf("Queue elements:\n");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    int n, val;

    printf("Enter number of elements to enqueue: ");
    scanf("%d", &n);

    for (int i = 0; i < n; i++) {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &val);
        enqueue(val);
    }

    display();

    return 0;
}

```

Output:


![image](https://github.com/user-attachments/assets/d6283b76-e61d-450e-9432-cfa777e639b5)


Result:
Thus, the program to display queue elements using linked list is verified successfully.


 
EXP NO:29 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

Aim:
To write a C program to insert elements in queue using linked list

Algorithm:
1.	Allocate Memory for New Node
2.	Set Data and Next Pointer
3.	Check if Queue is Empty
4.	Set both front and rear to point to the new node p.
5.	Set the next pointer of the current rear to point to the new node p.
6.	End of Enqueue Operation
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

struct Node* front = NULL;
struct Node* rear = NULL;

void enqueue(int value) {
    struct Node* p = (struct Node*)malloc(sizeof(struct Node));
    p->data = value;
    p->next = NULL;

    if (front == NULL && rear == NULL) {
        front = rear = p;
    } else {
        rear->next = p;
        rear = p;
    }

    printf("Inserted: %d\n", value);
}

void display() {
    struct Node* temp = front;

    if (temp == NULL) {
        printf("Queue is empty.\n");
        return;
    }

    printf("Queue elements: ");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    int n, val;

    printf("Enter number of elements to insert into queue: ");
    scanf("%d", &n);

    for (int i = 0; i < n; i++) {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &val);
        enqueue(val);
    }

    display();

    return 0;
}

```

Output:


![image](https://github.com/user-attachments/assets/1cb8225f-b044-4c73-bc18-58f1a2f34701)


Result:
Thus, the program to insert elements in queue using linked list is verified successfully.



EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.


Aim:

The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

Algorithm:

1.	Check if the queue is empty:
o	If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
2.	Access the front element:
o	If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).

Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

struct Node* front = NULL;
struct Node* rear = NULL;

void enqueue(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;

    if (front == NULL) {
        front = rear = newNode;
    } else {
        rear->next = newNode;
        rear = newNode;
    }
}

void peek() {
    if (front == NULL) {
        printf("Queue is empty. Cannot peek.\n");
    } else {
        printf("Peek (front element): %d\n", front->data);
    }
}

void display() {
    struct Node* temp = front;

    if (temp == NULL) {
        printf("Queue is empty.\n");
        return;
    }

    printf("Queue elements: ");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    int n, val;

    printf("Enter number of elements to enqueue: ");
    scanf("%d", &n);

    for (int i = 0; i < n; i++) {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &val);
        enqueue(val);
    }

    display();

    peek();

    return 0;
}

```

Output:


![image](https://github.com/user-attachments/assets/1b953664-75d4-4adf-aeeb-a5b73dec7542)




Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.


