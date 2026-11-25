# Lab-task-2 
#include <iostream>
using namespace std;

void insertElement(int arr[], int &size, int capacity, int value, int position) {
    if (size >= capacity || position < 0 || position > size) {
        cout << "Invalid position or array is full.\n";
        return;
    }

    for (int i = size; i > position; i--) {
        arr[i] = arr[i - 1];
    }

    arr[position] = value;
    size++;
}

void deleteElement(int arr[], int &size, int position) {
    if (position < 0 || position >= size) {
        cout << "Invalid position.\n";
        return;
    }

    for (int i = position; i < size - 1; i++) {
        arr[i] = arr[i + 1];
    }

    size--;
}

void display(int arr[], int size) {
    cout << "Array: ";
    for (int i = 0; i < size; i++)
        cout << arr[i] << " ";
    cout << '\n';
}

int main() {
    const int capacity = 100;
    int arr[capacity] = {10, 20, 30, 40, 50};
    int size = 5;

    cout << "Original ";
    display(arr, size);

    insertElement(arr, size, capacity, 25, 2);
    cout << "After insertion: ";
    display(arr, size);

    deleteElement(arr, size, 3);
    cout << "After deletion: ";
    display(arr, size);

    return 0;
}
