#include <iostream>
using namespace std;

// Function to find a local minima in the array
int findLocalMinima(int arr[], int low, int high, int n) {
    // Find the mid index
    int mid = low + (high - low) / 2;

    // Check if the mid element is a local minima
    if ((mid == 0 || arr[mid - 1] > arr[mid]) && 
        (mid == n - 1 || arr[mid + 1] > arr[mid])) {
        return mid;
    }

    // If the left neighbor is smaller, move to the left half
    else if (mid > 0 && arr[mid - 1] < arr[mid]) {
        return findLocalMinima(arr, low, mid - 1, n);
    }

    // If the right neighbor is smaller, move to the right half
    return findLocalMinima(arr, mid + 1, high, n);
}

int main() {
    int arr[] = {9, 6, 3, 14, 5, 7, 4};
    int n = sizeof(arr) / sizeof(arr[0]);
    int index = findLocalMinima(arr, 0, n - 1, n);
    cout << "Local minima found at index: " << index << ", value: " << arr[index] << endl;
    return 0;
}
