# Binary-Search
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;
int binarySearch(const vector<int>& arr, int target) {// Binary Search Function
    int left = 0, right = arr.size() - 1;
    while (left <= right) {
        int mid = left + (right - left) / 2;
        if (arr[mid] == target)
            return mid;  // Found
        else if (arr[mid] < target)
            left = mid + 1;
        else
            right = mid - 1;
    }
    return -1; } // Not found
int main() {
    srand(time(0));
    int N;
    cout << "Enter the number of random elements (N): ";
    cin >> N;
    vector<int> data(N);
    cout << "Random numbers generated:\n";
    for (int i = 0; i < N; ++i) {
        data[i] = rand() % 100;  // Random number between 0 and 99
        cout << data[i] << " ";}
    // Sorting
    sort(data.begin(), data.end());
    cout << "\nSorted array in ascending order:\n";
    for (int num : data)
        cout << num << " ";
    // Search input
    int key;
    cout << "\n\nEnter element to search using Binary Search: ";
    cin >> key;
    int result = binarySearch(data, key);
    if (result != -1)
        cout << "Element " << key << " found at index " << result << " (0-based index).\n";
    else
        cout << "Element " << key << " not found in the array.\n";
    return 0;
}
