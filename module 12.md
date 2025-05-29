

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

// Define node structure
struct Node {
    int data;
    struct Node* next;
};

// Push an element onto the stack
void push(struct Node** top, int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = *top;
    *top = newNode;
    printf("%d pushed onto stack.\n", value);
}

// Display the stack elements
void display(struct Node* top) {
    if (top == NULL) {
        printf("Stack is empty.\n");
        return;
    }

    printf("Stack elements (top to bottom): ");
    while (top != NULL) {
        printf("%d ", top->data);
        top = top->next;
    }
    printf("\n");
}

// Main function
int main() {
    struct Node* stackTop = NULL;

    // Push elements onto the stack
    push(&stackTop, 10);
    push(&stackTop, 20);
    push(&stackTop, 30);

    // Display stack elements
    display(stackTop);

    return 0;
}
```
Output:


![image](https://github.com/user-attachments/assets/c91520e3-de45-4f2c-ae5e-cdfb234dcd58)



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

// Define node structure
struct Node {
    int data;
    struct Node* next;
};

// Push an element onto the stack
void push(struct Node** top, int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = *top;
    *top = newNode;
    printf("%d pushed onto stack.\n", value);
}

// Pop an element from the stack
void pop(struct Node** top) {
    if (*top == NULL) {
        printf("Stack is empty. Nothing to pop.\n");
        return;
    }

    struct Node* temp = *top;
    printf("%d popped from stack.\n", temp->data);
    *top = (*top)->next;
    free(temp);
}

// Display the stack
void display(struct Node* top) {
    if (top == NULL) {
        printf("Stack is empty.\n");
        return;
    }

    printf("Stack elements: ");
    while (top != NULL) {
        printf("%d ", top->data);
        top = top->next;
    }
    printf("\n");
}

// Main function
int main() {
    struct Node* stackTop = NULL;

    push(&stackTop, 10);
    push(&stackTop, 20);
    push(&stackTop, 30);

    display(stackTop);

    pop(&stackTop);
    display(stackTop);

    pop(&stackTop);
    display(stackTop);

    return 0;
}
```

Output:

![image](https://github.com/user-attachments/assets/bcb9155b-7518-489f-a019-b0038f535f55)



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

// Define node structure
struct Node {
    int data;
    struct Node* next;
};

// Define queue structure
struct Queue {
    struct Node *front, *rear;
};

// Function to create a new node
struct Node* createNode(int value) {
    struct Node* temp = (struct Node*)malloc(sizeof(struct Node));
    temp->data = value;
    temp->next = NULL;
    return temp;
}

// Initialize the queue
void initQueue(struct Queue* q) {
    q->front = q->rear = NULL;
}

// Enqueue (insert) element into queue
void enqueue(struct Queue* q, int value) {
    struct Node* temp = createNode(value);

    if (q->rear == NULL) {
        q->front = q->rear = temp;
        return;
    }

    q->rear->next = temp;
    q->rear = temp;
}

// Display all elements of the queue
void displayQueue(struct Queue* q) {
    struct Node* temp = q->front;

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

// Main function
int main() {
    struct Queue q;
    initQueue(&q);

    // Enqueue some test data
    enqueue(&q, 10);
    enqueue(&q, 20);
    enqueue(&q, 30);

    // Display the queue
    displayQueue(&q);

    return 0;
}
```

Output:

![image](https://github.com/user-attachments/assets/a6a57627-3ed7-4f1c-8afa-429b46316517)


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

// Node structure
struct Node {
    int data;
    struct Node* next;
};

// Queue structure
struct Queue {
    struct Node *front, *rear;
};

// Function to create a new node
struct Node* createNode(int value) {
    struct Node* temp = (struct Node*)malloc(sizeof(struct Node));
    temp->data = value;
    temp->next = NULL;
    return temp;
}

// Initialize an empty queue
void initQueue(struct Queue* q) {
    q->front = q->rear = NULL;
}

// Enqueue function (insert at rear)
void enqueue(struct Queue* q, int value) {
    struct Node* temp = createNode(value);

    if (q->rear == NULL) {
        q->front = q->rear = temp;
        printf("%d inserted into the queue.\n", value);
        return;
    }

    q->rear->next = temp;
    q->rear = temp;
    printf("%d inserted into the queue.\n", value);
}

// Display the queue
void displayQueue(struct Queue* q) {
    struct Node* temp = q->front;
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

// Main function
int main() {
    struct Queue q;
    initQueue(&q);

    int choice, value;

    while (1) {
        printf("\n--- Menu ---\n");
        printf("1. Enqueue (Insert)\n");
        printf("2. Display Queue\n");
        printf("3. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter value to insert: ");
                scanf("%d", &value);
                enqueue(&q, value);
                break;
            case 2:
                displayQueue(&q);
                break;
            case 3:
                printf("Exiting program.\n");
                exit(0);
            default:
                printf("Invalid choice. Try again.\n");
        }
    }

    return 0;
}
```


Output:

![image](https://github.com/user-attachments/assets/8df16023-692d-445b-8f4d-2519eddb6724)



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

// Node structure
struct Node {
    int data;
    struct Node* next;
};

// Queue structure
struct Queue {
    struct Node *front, *rear;
};

// Create a new node
struct Node* newNode(int value) {
    struct Node* temp = (struct Node*)malloc(sizeof(struct Node));
    temp->data = value;
    temp->next = NULL;
    return temp;
}

// Initialize an empty queue
void initQueue(struct Queue* q) {
    q->front = q->rear = NULL;
}

// Enqueue operation
void enqueue(struct Queue* q, int value) {
    struct Node* temp = newNode(value);

    if (q->rear == NULL) {
        q->front = q->rear = temp;
        return;
    }

    q->rear->next = temp;
    q->rear = temp;
}

// Peek operation: return front element without removing it
int peek(struct Queue* q) {
    if (q->front == NULL) {
        printf("Queue is empty.\n");
        return -1; // or some error indicator
    }
    return q->front->data;
}

// Dequeue operation (optional for demonstration)
void dequeue(struct Queue* q) {
    if (q->front == NULL) {
        printf("Queue is empty.\n");
        return;
    }

    struct Node* temp = q->front;
    q->front = q->front->next;

    if (q->front == NULL)
        q->rear = NULL;

    free(temp);
}

// Main function to demonstrate
int main() {
    struct Queue q;
    initQueue(&q);

    enqueue(&q, 10);
    enqueue(&q, 20);
    enqueue(&q, 30);

    printf("Front element (peek): %d\n", peek(&q));

    dequeue(&q);
    printf("Front element after one dequeue: %d\n", peek(&q));

    return 0;
}
```

Output:

![image](https://github.com/user-attachments/assets/58149249-ffdb-448f-9bd3-88fcf5a10e32)




Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.


