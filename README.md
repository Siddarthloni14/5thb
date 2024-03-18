# 5thbBelow is a C program to solve the Tower of Hanoi problem with 'n' disks using recursion:

#include <stdio.h>

// Function prototype
void towerOfHanoi(int n, char source, char auxiliary, char destination);

int main() {
    int numDisks;

    // Input number of disks
    printf("Enter the number of disks: ");
    scanf("%d", &numDisks);

    // Solving Tower of Hanoi problem
    printf("Steps to solve Tower of Hanoi problem with %d disks:\n", numDisks);
    towerOfHanoi(numDisks, 'A', 'B', 'C');

    return 0;
}

// Function to solve Tower of Hanoi problem with 'n' disks
void towerOfHanoi(int n, char source, char auxiliary, char destination) {
    if (n == 1) {
        printf("Move disk 1 from %c to %c\n", source, destination);
        return;
    }
    // Move top n-1 disks from source to auxiliary using destination as auxiliary
    towerOfHanoi(n - 1, source, destination, auxiliary);

    // Move nth disk from source to destination
    printf("Move disk %d from %c to %c\n", n, source, destination);

    // Move n-1 disks from auxiliary to destination using source as auxiliary
    towerOfHanoi(n - 1, auxiliary, source, destination);
}
