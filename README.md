# Client-Server-JavaHere are the solutions to the given problems:

*Q1: Linear Search Program*

This program will take an array and a target value as input from the user and perform a linear search to find the target value.
import java.util.Scanner;

public class LinearSearch {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter the size of the array: ");
        int size = scanner.nextInt();
        int[] array = new int[size];

        System.out.println("Enter the elements of the array:");
        for (int i = 0; i < size; i++) {
            array[i] = scanner.nextInt();
        }

        System.out.print("Enter the target value: ");
        int target = scanner.nextInt();

        int result = linearSearch(array, target);

        if (result == -1) {
            System.out.println("Target value not found in the array.");
        } else {
            System.out.println("Target value found at index " + result);
        }
    }

    public static int linearSearch(int[] array, int target) {
        for (int i = 0; i < array.length; i++) {
            if (array[i] == target) {
                return i;
            }
        }
        return -1;
    }
}
*Q2: Sort Names List using Selection Sort*

This program will take a list of names as input from the user and sort them using the selection sort algorithm.
import java.util.Scanner;

public class SelectionSort {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter the number of names: ");
        int size = scanner.nextInt();
        String[] names = new String[size];

        System.out.println("Enter the names:");
        for (int i = 0; i < size; i++) {
            names[i] = scanner.next();
        }

        selectionSort(names);

        System.out.println("Sorted names:");
        for (String name : names) {
            System.out.println(name);
        }
    }

    public static void selectionSort(String[] array) {
        for (int i = 0; i < array.length - 1; i++) {
            int minIndex = i;
            for (int j = i + 1; j < array.length; j++) {
                if (array[j].compareTo(array[minIndex]) < 0) {
                    minIndex = j;
                }
            }
            String temp = array[i];
            array[i] = array[minIndex];
            array[minIndex] = temp;
        }
    }
}
*Q3: Bubble Sort Program*

This program will take an array as input from the user and sort it using the bubble sort algorithm.
import java.util.Scanner;

public class BubbleSort {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter the size of the array: ");
        int size = scanner.nextInt();
        int[] array = new int[size];

        System.out.println("Enter the elements of the array:");
        for (int i = 0; i < size; i++) {
            array[i] = scanner.nextInt();
        }

        bubbleSort(array);

        System.out.println("Sorted array:");
        for (int element : array) {
            System.out.print(element + " ");
        }
    }

    public static void bubbleSort(int[] array) {
        for (int i = 0; i < array.length - 1; i++) {
            for (int j = 0; j < array.length - i - 1; j++) {
                if (array[j] > array[j + 1]) {
                    int temp = array[j];
                    array[j] = array[j + 1];
                    array[j + 1] = temp;
                }
            }
        }
    }
}
*Q4: Linked List Program and Print in Sorted Order*

This program will create a linked list, insert nodes, and print the list in sorted order.
import java.util.Scanner;

class Node {
    int data;
    Node next;

    public Node(int data) {
        this.data = data;
        this.next = null;
    }
}

public class LinkedList {
    Node head;

    public void insert(int data) {
        Node newNode = new Node(data);
        if (head == null) {
            head = newNode;
        } else {
            Node current = head;
            while (current.next != null) {
                current = current.next;
            }
            current.next = newNode;
        }
    }

    public void printList() {
        Node current = head;
        while (current != null) {
            System.out.print(current.data + " ");
            current = current.next;
        }
        System.out.println();
    }

    public void sortList() {
        Node current
