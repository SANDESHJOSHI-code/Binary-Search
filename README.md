#include <iostream>
#include <algorithm>  // For sort()
using namespace std;
int binarySearch(int arr[], int size, int target) {
    int left = 0, right = size - 1;
    while (left <= right) {
        int mid = left + (right - left) / 2;
        if (arr[mid] == target)
            return mid;  // Found
        else if (arr[mid] < target)
            left = mid + 1;
        else
            right = mid - 1;
    }
    return -1;  // Not found
}
int main() {
    int arr[] = {21, 4, 18, 9, 11, 42, 16};
    int size = sizeof(arr) / sizeof(arr[0]);
    int target = 18;
    // Sort the array before binary search
    sort(arr, arr + size);
    cout << "Sorted array: ";
    for (int i = 0; i < size; ++i)
    cout << arr[i] << " ";
    cout << endl;
    int result = binarySearch(arr, size, target);
    if (result != -1)
        cout << "Element " << target << " found at index " << result << "." << endl;
    else
        cout << "Element " << target << " not found in the array." << endl;
    return 0;
}
