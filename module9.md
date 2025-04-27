EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

Aim:
To write a C program to display stack elements using an array.
Algorithm:
1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Function
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
Program:

```
#include <stdio.h>

#define MAX 10

int stack[MAX];
int top = -1;

void display() {
    int i;
    if(top == -1) {
        printf("Stack is empty.\n");
    } else {
        printf("Stack elements are:\n");
        for(i = top; i >= 0; i--) {
            printf("%d\n", stack[i]);
        }
    }
}

void push(int value) {
    if(top == MAX - 1) {
        printf("Stack Overflow.\n");
    } else {
        top++;
        stack[top] = value;
    }
}

void pop() {
    if(top == -1) {
        printf("Stack Underflow.\n");
    } else {
        top--;
    }
}

int main() {
    int choice, value;
    while(1) {
        printf("\n1.Push\n2.Pop\n3.Display\n4.Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);
        switch(choice) {
            case 1:
                printf("Enter value to push: ");
                scanf("%d", &value);
                push(value);
                break;
            case 2:
                pop();
                break;
            case 3:
                display();
                break;
            case 4:
                return 0;
            default:
                printf("Invalid choice.\n");
        }
    }
}

```
Output:

![image](https://github.com/user-attachments/assets/367b8c31-c00c-4780-ab7b-4d85f43b10fe)


![image](https://github.com/user-attachments/assets/46190f67-8ddb-4ac1-89d7-3e36111d0034)




Result:
Thus, the program to display stack elements using an array is verified successfully.
 

EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.
Aim:
To create a C program to push the given element in to a stack using array.
Algorithm:
1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
Program:
```
#include <stdio.h>

#define SIZE 10

float stack[SIZE];
int top = -1;

void push(float value) {
    if(top == SIZE - 1) {
        printf("Stack Overflow.\n");
    } else {
        top++;
        stack[top] = value;
        printf("%.2f pushed into the stack.\n", value);
    }
}

int main() {
    int n, i;
    float value;
    printf("Enter number of elements to push: ");
    scanf("%d", &n);
    for(i = 0; i < n; i++) {
        printf("Enter value to push: ");
        scanf("%f", &value);
        push(value);
    }
    return 0;
}
```
Output:

![image](https://github.com/user-attachments/assets/71678404-a1dc-403c-9fa0-2a18b000cf0d)





Result:
Thus, the program to push the given element in to a stack using array is verified successfully


 
EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.
Aim:
To write a C program to display queue elements using array

Algorithm:
1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
Program:
```
#include <stdio.h>

#define SIZE 10

int queue[SIZE];
int front = -1, rear = -1;

void display() {
    int i;
    if(front == -1 || front > rear) {
        printf("Queue is empty.\n");
    } else {
        printf("Queue elements are:\n");
        for(i = front; i <= rear; i++) {
            printf("%d ", queue[i]);
        }
        printf("\n");
    }
}

void enqueue(int value) {
    if(rear == SIZE - 1) {
        printf("Queue Overflow.\n");
    } else {
        if(front == -1) front = 0;
        rear++;
        queue[rear] = value;
    }
}

void dequeue() {
    if(front == -1 || front > rear) {
        printf("Queue Underflow.\n");
    } else {
        front++;
    }
}

int main() {
    int choice, value;
    while(1) {
        printf("\n1.Enqueue\n2.Dequeue\n3.Display\n4.Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);
        switch(choice) {
            case 1:
                printf("Enter value to enqueue: ");
                scanf("%d", &value);
                enqueue(value);
                break;
            case 2:
                dequeue();
                break;
            case 3:
                display();
                break;
            case 4:
                return 0;
            default:
                printf("Invalid choice.\n");
        }
    }
}

```
Output:
![image](https://github.com/user-attachments/assets/f7a0fbae-4df5-44ec-800f-b58809cdafc1)

![image](https://github.com/user-attachments/assets/4ca00941-4bcd-4e15-8dbf-3166fa44e8c2)



Result:
Thus, the program to display queue elements using array is verified successfully.


 
EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.
Aim:
To write a C program to insert elements in queue using array.

Algorithm:
1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

Program:

```
#include <stdio.h>

#define SIZE 10

float queue[SIZE];
int front = -1, rear = -1;

void enqueue(float value) {
    if(rear == SIZE - 1) {
        printf("Queue Overflow.\n");
    } else {
        if(front == -1) front = 0;
        rear++;
        queue[rear] = value;
        printf("%.2f inserted into queue.\n", value);
    }
}

int main() {
    int n, i;
    float value;
    printf("Enter number of elements to insert: ");
    scanf("%d", &n);
    for(i = 0; i < n; i++) {
        printf("Enter value to insert: ");
        scanf("%f", &value);
        enqueue(value);
    }
    return 0;
}

```

Output:

![image](https://github.com/user-attachments/assets/980a7301-5508-4541-b0d5-ed74c592e50c)


Result:
Thus, the program to insert elements in queue using array is verified successfully.



 
EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY



Aim:

To create a function in C that deletes an element from a queue implemented using an array.

Algorithm:

1.	Check if the Queue is Empty
o	If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
2.	Delete the Front Element
o	If the queue is not empty, the element at the front index is deleted.
o	Increment the front pointer by 1 to remove the element and point to the next element in the queue.
3.	Check if the Queue Becomes Empty After Deletion:
o	After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
4.	End the Function.



Program:

```
#include <stdio.h>

#define SIZE 10

int queue[SIZE];
int front = -1, rear = -1;

void dequeue() {
    if(front == -1 || front > rear) {
        printf("Queue is empty. No elements to delete.\n");
    } else {
        printf("Deleted element: %d\n", queue[front]);
        front++;
        if(front > rear) {
            front = -1;
            rear = -1;
        }
    }
}

int main() {
    int n, i, value;
    printf("Enter number of elements to insert: ");
    scanf("%d", &n);
    for(i = 0; i < n; i++) {
        printf("Enter value to insert: ");
        scanf("%d", &value);
        if(rear == SIZE - 1) {
            printf("Queue Overflow.\n");
            break;
        }
        if(front == -1) front = 0;
        rear++;
        queue[rear] = value;
    }
    dequeue();
    dequeue();
    return 0;
}

```
Output:

![image](https://github.com/user-attachments/assets/b675ea46-2dc1-4373-85e8-c5187951e07c)



Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
