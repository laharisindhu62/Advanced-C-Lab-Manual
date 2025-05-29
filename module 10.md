EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.

Aim:
To write a C program to search a given element in the given linked list.

Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
Program:
```
#include <stdio.h>
#include <stdlib.h>

// Define structure of a node
struct Node {
    int data;
    struct Node* next;
};

// Function to create a new node
struct Node* createNode(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;
    return newNode;
}

// Function to search an element in the linked list
void searchElement(struct Node* head, int key) {
    int position = 1;
    int found = 0;

    while (head != NULL) {
        if (head->data == key) {
            printf("Element %d found at position %d.\n", key, position);
            found = 1;
            break;
        }
        head = head->next;
        position++;
    }

    if (!found) {
        printf("Element %d not found in the linked list.\n", key);
    }
}

int main() {
    struct Node *head = NULL, *second = NULL, *third = NULL;

    // Create nodes
    head = createNode(10);
    second = createNode(20);
    third = createNode(30);

    // Link nodes
    head->next = second;
    second->next = third;

    int key;
    printf("Enter the element to search: ");
    scanf("%d", &key);

    searchElement(head, key);

    return 0;
}
```

Output:
![image](https://github.com/user-attachments/assets/ac402100-837d-4658-b057-b39908c78ae4)





Result:
Thus, the program to search a given element in the given linked list is verified successfully.


 
EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.

Aim:
To write a C program to insert a node in a linked list.

Algorithm:
1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
Program:
```
#include <stdio.h>
#include <stdlib.h>

// Define the structure for a node
struct Node {
    int data;
    struct Node* next;
};

// Function to insert a new node at the beginning
void insertAtBeginning(struct Node** head_ref, int new_data) {
    // Allocate memory for new node
    struct Node* new_node = (struct Node*)malloc(sizeof(struct Node));

    // Assign data to the new node
    new_node->data = new_data;

    // Make next of new node as head
    new_node->next = *head_ref;

    // Move the head to point to the new node
    *head_ref = new_node;
}

// Function to print the linked list
void printList(struct Node* node) {
    printf("Linked List: ");
    while (node != NULL) {
        printf("%d -> ", node->data);
        node = node->next;
    }
    printf("NULL\n");
}

// Main function
int main() {
    struct Node* head = NULL;

    // Insert nodes
    insertAtBeginning(&head, 30);
    insertAtBeginning(&head, 20);
    insertAtBeginning(&head, 10);

    // Print the list
    printList(head);

    return 0;
}
```
Output:

![image](https://github.com/user-attachments/assets/2f52039a-53cf-4f83-8846-3a212de1b5ec)


 
Result:
Thus, the program to insert a node in a linked list is verified successfully.


 
EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST

Aim:
To write a C program to traverse a doubly linked list.

Algorithm:

1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
Program:
```
#include <stdio.h>
#include <stdlib.h>

// Node structure
struct Node {
    int data;
    struct Node* prev;
    struct Node* next;
};

// Function to create a new node
struct Node* createNode(int data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->prev = NULL;
    newNode->next = NULL;
    return newNode;
}

// Function to insert a node at the end
void insertEnd(struct Node** head_ref, int data) {
    struct Node* newNode = createNode(data);
    struct Node* temp = *head_ref;

    if (*head_ref == NULL) {
        *head_ref = newNode;
        return;
    }

    while (temp->next != NULL)
        temp = temp->next;

    temp->next = newNode;
    newNode->prev = temp;
}

// Function to traverse in forward direction
void traverseForward(struct Node* head) {
    printf("Forward Traversal: ");
    while (head != NULL) {
        printf("%d <-> ", head->data);
        head = head->next;
    }
    printf("NULL\n");
}

// Function to traverse in backward direction
void traverseBackward(struct Node* head) {
    // Move to the last node
    if (head == NULL) return;

    while (head->next != NULL)
        head = head->next;

    // Traverse backward
    printf("Backward Traversal: ");
    while (head != NULL) {
        printf("%d <-> ", head->data);
        head = head->prev;
    }
    printf("NULL\n");
}

// Main function
int main() {
    struct Node* head = NULL;

    // Insert sample data
    insertEnd(&head, 10);
    insertEnd(&head, 20);
    insertEnd(&head, 30);

    // Traverse the list
    traverseForward(head);
    traverseBackward(head);

    return 0;
}
```

Output:

![image](https://github.com/user-attachments/assets/ddc8d706-bfd0-4537-b276-ac7107769a7f)



Result:
Thus, the program to traverse a doubly linked list is verified successfully. 



EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST

Aim:
To write a C program to insert an element in doubly linked list

Algorithm:

1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

// Node structure for a Doubly Linked List
struct Node {
    int data;
    struct Node* prev;
    struct Node* next;
};

// Function to create a new node
struct Node* createNode(int data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->prev = NULL;
    newNode->next = NULL;
    return newNode;
}

// Function to insert at the end
void insertEnd(struct Node** head_ref, int data) {
    struct Node* newNode = createNode(data);
    struct Node* temp = *head_ref;

    // If list is empty
    if (*head_ref == NULL) {
        *head_ref = newNode;
        return;
    }

    // Traverse to the end
    while (temp->next != NULL)
        temp = temp->next;

    temp->next = newNode;
    newNode->prev = temp;
}

// Function to display the list
void displayList(struct Node* head) {
    struct Node* temp = head;
    printf("Doubly Linked List: ");
    while (temp != NULL) {
        printf("%d <-> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

// Main function to test the above
int main() {
    struct Node* head = NULL;

    // Insert elements
    insertEnd(&head, 10);
    insertEnd(&head, 20);
    insertEnd(&head, 30);

    // Display the list
    displayList(head);

    return 0;
}
```

Output:

![image](https://github.com/user-attachments/assets/15e78786-c8ef-446a-9884-ac8c77918cce)



Result:
Thus, the program to insert an element in doubly linked list is verified successfully.




EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST




Aim:
To write a C function that deletes a given element from a linked list.

Algorithm:

1.	Check if the Linked List is Empty:
o	If the head of the linked list is NULL, print a message indicating the list is empty and exit the function.
2.	Traverse the Linked List:
o	Start from the head node and iterate through the list to find the node that contains the given element (data).
3.	Handle Deletion of the First Node:
o	If the element to be deleted is found in the head node:
	Update the head of the linked list to point to the next node (i.e., head = head->next).
	Free the memory allocated to the node to be deleted.
	Exit the function.
4.	Traverse and Delete from the Middle or End:
o	If the element is not in the head node, continue traversing the list by checking each node’s next pointer.
o	When the node with the element is found, update the previous node’s next pointer to point to the next node of the node to be deleted (prev->next = current->next).
o	Free the memory allocated to the node to be deleted.
5.	Handle the Case when the Element is Not Found:
o	If the element is not found in any node, print a message indicating the element is not present in the list.
6.	End the Function.


Program:

```
#include <stdio.h>
#include <stdlib.h>

// Define the structure for a node
struct Node {
    int data;
    struct Node* next;
};

// Function to delete a node with a given key
void deleteNode(struct Node** head_ref, int key) {
    struct Node* temp = *head_ref;
    struct Node* prev = NULL;

    // If head node itself holds the key
    if (temp != NULL && temp->data == key) {
        *head_ref = temp->next; // Change head
        free(temp);             // Free old head
        return;
    }

    // Search for the key to be deleted
    while (temp != NULL && temp->data != key) {
        prev = temp;
        temp = temp->next;
    }

    // If key was not present
    if (temp == NULL)
        return;

    // Unlink the node from linked list
    prev->next = temp->next;
    free(temp);
}

// Helper function to print the linked list
void printList(struct Node* node) {
    while (node != NULL) {
        printf("%d -> ", node->data);
        node = node->next;
    }
    printf("NULL\n");
}

// Helper function to insert a new node at the beginning
void push(struct Node** head_ref, int new_data) {
    struct Node* new_node = (struct Node*)malloc(sizeof(struct Node));
    new_node->data = new_data;
    new_node->next = (*head_ref);
    *head_ref = new_node;
}

// Example usage
int main() {
    struct Node* head = NULL;

    // Create the list 7->1->3->2->NULL
    push(&head, 2);
    push(&head, 3);
    push(&head, 1);
    push(&head, 7);

    printf("Original Linked List:\n");
    printList(head);

    deleteNode(&head, 1);

    printf("\nLinked List after Deletion of 1:\n");
    printList(head);

    return 0;
}
```

Output:


![image](https://github.com/user-attachments/assets/8db94f01-d367-44ac-bb2c-752f35979859)


Result:
Thus, the function that deletes a given element from a linked list is verified successfully.





