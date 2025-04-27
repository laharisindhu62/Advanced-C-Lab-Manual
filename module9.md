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

#define MAX 5  // Defining the maximum size of the stack

// Stack structure
struct Stack {
    int arr[MAX];
    int top;
};

// Function to initialize the stack
void initializeStack(struct Stack* s) {
    s->top = -1;  // Stack is initially empty
}

// Function to check if the stack is empty
int isEmpty(struct Stack* s) {
    return s->top == -1;
}

// Function to push an element into the stack
void push(struct Stack* s, int value) {
    if (s->top == MAX - 1) {
        printf("Stack Overflow! Cannot push %d\n", value);
    } else {
        s->top++;
        s->arr[s->top] = value;
        printf("%d pushed into the stack.\n", value);
    }
}

// Function to display the stack elements
void displayStack(struct Stack* s) {
    if (isEmpty(s)) {
        printf("Stack is empty!\n");
    } else {
        printf("Stack elements: ");
        for (int i = 0; i <= s->top; i++) {
            printf("%d ", s->arr[i]);
        }
        printf("\n");
    }
}

int main() {
    struct Stack s;
    initializeStack(&s);

    // Pushing elements into the stack
    push(&s, 10);
    push(&s, 20);
    push(&s, 30);
    push(&s, 40);
    push(&s, 50);

    // Display the current state of the stack
    displayStack(&s);

    return 0;
}
```

Output:

![image](https://github.com/user-attachments/assets/6fee009a-3a63-42ac-afd8-5c8ccdd2dad6)




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

#define MAX 5  // Defining the maximum size of the stack

// Stack structure
struct Stack {
    int arr[MAX];
    int top;
};

// Function to initialize the stack
void initializeStack(struct Stack* s) {
    s->top = -1;
}

// Function to check if the stack is full
int isFull(struct Stack* s) {
    return s->top == MAX - 1;
}

// Function to check if the stack is empty
int isEmpty(struct Stack* s) {
    return s->top == -1;
}

// Function to push an element into the stack
void push(struct Stack* s, int value) {
    if (isFull(s)) {
        printf("Stack Overflow! Cannot push %d\n", value);
    } else {
        s->top++;
        s->arr[s->top] = value;
        printf("%d pushed into the stack.\n", value);
    }
}

// Function to display the stack elements
void displayStack(struct Stack* s) {
    if (isEmpty(s)) {
        printf("Stack is empty!\n");
    } else {
        printf("Stack elements: ");
        for (int i = 0; i <= s->top; i++) {
            printf("%d ", s->arr[i]);
        }
        printf("\n");
    }
}

int main() {
    struct Stack s;
    initializeStack(&s);

    // Pushing elements into the stack
    push(&s, 10);
    push(&s, 20);
    push(&s, 30);
    push(&s, 40);
    push(&s, 50);

    // Display the current state of the stack
    displayStack(&s);

    // Trying to push one more element to check for overflow
    push(&s, 60);

    return 0;
}
```

Output:

![image](https://github.com/user-attachments/assets/0bd79e3e-81b1-479d-95a7-943ad50b0def)





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

#define MAX 5  // Defining the maximum size of the queue

// Queue structure
struct Queue {
    int arr[MAX];
    int front, rear;
};

// Function to initialize the queue
void initializeQueue(struct Queue* q) {
    q->front = -1;
    q->rear = -1;
}

// Function to check if the queue is full
int isFull(struct Queue* q) {
    return q->rear == MAX - 1;
}

// Function to check if the queue is empty
int isEmpty(struct Queue* q) {
    return q->front == -1;
}

// Function to enqueue (insert) an element in the queue
void enqueue(struct Queue* q, int value) {
    if (isFull(q)) {
        printf("Queue is full! Cannot enqueue %d\n", value);
    } else {
        if (q->front == -1) {  // If the queue is empty, initialize front
            q->front = 0;
        }
        q->rear++;
        q->arr[q->rear] = value;
        printf("%d enqueued to the queue.\n", value);
    }
}

// Function to display the queue elements
void displayQueue(struct Queue* q) {
    if (isEmpty(q)) {
        printf("Queue is empty!\n");
    } else {
        printf("Queue elements: ");
        for (int i = q->front; i <= q->rear; i++) {
            printf("%d ", q->arr[i]);
        }
        printf("\n");
    }
}

int main() {
    struct Queue q;
    initializeQueue(&q);

    // Inserting elements in the queue
    enqueue(&q, 10);
    enqueue(&q, 20);
    enqueue(&q, 30);
    enqueue(&q, 40);
    enqueue(&q, 50);

    // Display the current state of the queue
    displayQueue(&q);

    return 0;
}
```

Output:

![image](https://github.com/user-attachments/assets/e03b8fcd-3169-459d-9c7e-2b899a80d5c4)


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

#define MAX 5  // Defining the maximum size of the queue

// Queue structure
struct Queue {
    int arr[MAX];
    int front, rear;
};

// Function to initialize the queue
void initializeQueue(struct Queue* q) {
    q->front = -1;
    q->rear = -1;
}

// Function to check if the queue is full
int isFull(struct Queue* q) {
    return q->rear == MAX - 1;
}

// Function to check if the queue is empty
int isEmpty(struct Queue* q) {
    return q->front == -1;
}

// Function to enqueue (insert) an element in the queue
void enqueue(struct Queue* q, int value) {
    if (isFull(q)) {
        printf("Queue is full! Cannot enqueue %d\n", value);
    } else {
        if (q->front == -1) {  // If the queue is empty, initialize front
            q->front = 0;
        }
        q->rear++;
        q->arr[q->rear] = value;
        printf("%d enqueued to the queue.\n", value);
    }
}

// Function to display the queue
void displayQueue(struct Queue* q) {
    if (isEmpty(q)) {
        printf("Queue is empty!\n");
    } else {
        printf("Queue elements: ");
        for (int i = q->front; i <= q->rear; i++) {
            printf("%d ", q->arr[i]);
        }
        printf("\n");
    }
}

int main() {
    struct Queue q;
    initializeQueue(&q);

    // Inserting elements in the queue
    enqueue(&q, 10);
    enqueue(&q, 20);
    enqueue(&q, 30);
    enqueue(&q, 40);
    enqueue(&q, 50);

    // Display the current state of the queue
    displayQueue(&q);

    // Trying to insert one more element to check if the queue is full
    enqueue(&q, 60);

    return 0;
}
```

Output:

![image](https://github.com/user-attachments/assets/2886f85f-6438-4497-a19c-f3b4ed04d1e5)


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

#define MAX 5 // Defining the maximum size of the queue

// Queue structure
struct Queue {
    int arr[MAX];
    int front, rear;
};

// Initialize the queue
void initializeQueue(struct Queue* q) {
    q->front = -1;
    q->rear = -1;
}

// Check if the queue is empty
int isEmpty(struct Queue* q) {
    return q->front == -1;
}

// Check if the queue is full
int isFull(struct Queue* q) {
    return q->rear == MAX - 1;
}

// Enqueue function to add an element to the queue
void enqueue(struct Queue* q, int value) {
    if (isFull(q)) {
        printf("Queue is full! Cannot enqueue %d\n", value);
    } else {
        if (q->front == -1) {  // If the queue is empty
            q->front = 0;
        }
        q->rear++;
        q->arr[q->rear] = value;
        printf("%d enqueued to queue\n", value);
    }
}

// Dequeue function to remove an element from the queue
int dequeue(struct Queue* q) {
    if (isEmpty(q)) {
        printf("Queue is empty! Cannot dequeue.\n");
        return -1; // Indicates queue is empty
    } else {
        int value = q->arr[q->front];
        // If only one element was in the queue
        if (q->front == q->rear) {
            q->front = q->rear = -1; // Reset queue to empty
        } else {
            q->front++;
        }
        return value;
    }
}

// Function to delete an element from the queue (shift elements)
void deleteElement(struct Queue* q, int value) {
    if (isEmpty(q)) {
        printf("Queue is empty! Cannot delete element.\n");
        return;
    }

    int i, found = 0;
    for (i = q->front; i <= q->rear; i++) {
        if (q->arr[i] == value) {
            found = 1;
            break;
        }
    }

    if (!found) {
        printf("Element %d not found in the queue.\n", value);
        return;
    }

    // Shift the elements to fill the gap
    for (int j = i; j < q->rear; j++) {
        q->arr[j] = q->arr[j + 1];
    }
    q->rear--;  // Decrease rear as we removed an element

    if (q->rear == -1) {
        q->front = -1; // Reset the queue if it's empty after deletion
    }

    printf("Element %d deleted from the queue.\n", value);
}

// Function to display the queue
void display(struct Queue* q) {
    if (isEmpty(q)) {
        printf("Queue is empty!\n");
        return;
    }
    printf("Queue elements: ");
    for (int i = q->front; i <= q->rear; i++) {
        printf("%d ", q->arr[i]);
    }
    printf("\n");
}

int main() {
    struct Queue q;
    initializeQueue(&q);

    enqueue(&q, 10);
    enqueue(&q, 20);
    enqueue(&q, 30);
    enqueue(&q, 40);
    enqueue(&q, 50);

    display(&q);

    // Deleting an element from the queue
    deleteElement(&q, 30);  // Delete element 30

    display(&q);

    // Deleting an element not present in the queue
    deleteElement(&q, 100);

    display(&q);

    return 0;
}
```

Output:

![image](https://github.com/user-attachments/assets/162ff8b9-db21-4b2e-a086-da5d52ef47eb)



Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
