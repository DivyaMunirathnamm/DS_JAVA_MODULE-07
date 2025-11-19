# Ex7 Removal of Nodes with a Specific Value from a Linked List
## AIM:
To write a java  program that removes all nodes from a linked list whose value matches a given integer (val) and returns the new head of the modified linked list.

## Algorithm
1. 
2. 
3. 
4.  
5.   

## Program:
```
/*
program that removes all nodes from a linked list whose value matches a given integer (val) and returns the new head of the modified linked list.
Developed by: DIVYA M
RegisterNumber:  212223040043
*/
import java.util.Scanner;

class Node {
    int data;
    Node next;

    Node(int data) {
        this.data = data;
        this.next = null;
    }
}

class LinkedList {
    Node head;

    // Insert node at end
    public void insert(int data) {
        Node newNode = new Node(data);

        if (head == null) {
            head = newNode;
        } else {
            Node temp = head;
            while (temp.next != null)
                temp = temp.next;
            temp.next = newNode;
        }
    }

    // Right rotate linked list by k positions
    public void rightRotate(int k) {
        if (head == null || k == 0)
            return;

        Node temp = head;
        int len = 1;

        while (temp.next != null) {
            temp = temp.next;
            len++;
        }

        // Make circular
        temp.next = head;

        k = k % len;  // Effective rotation
        int stepsToNewHead = len - k;

        Node newTail = temp;
        while (stepsToNewHead-- > 0) {
            newTail = newTail.next;
        }

        head = newTail.next;
        newTail.next = null;
    }

    // Display list
    public void display() {
        Node temp = head;
        while (temp != null) {
            System.out.print(temp.data + " ");
            temp = temp.next;
        }
        System.out.println();
    }
}

public class RightRotationLinkedList {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        LinkedList list = new LinkedList();

        System.out.print("Enter number of nodes: ");
        int n = sc.nextInt();

        System.out.println("Enter " + n + " elements:");
        for (int i = 0; i < n; i++) {
            list.insert(sc.nextInt());
        }

        System.out.print("Enter k (positions to rotate): ");
        int k = sc.nextInt();

        list.rightRotate(k);

        System.out.println("Rotated Linked List:");
        list.display();

        sc.close();
    }
}

```

## Output:

<img width="571" height="232" alt="image" src="https://github.com/user-attachments/assets/cb2574cc-4d6e-4b22-a44a-45d7ba7b0912" />


## Result:
The java program successfully removes all nodes with the specified value (val) from the linked list and returns the new head.
