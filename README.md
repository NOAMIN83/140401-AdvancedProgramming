#include <iostream>
using namespace std;

int recursiveBinarySearch(int arr[], int left, int right, int target) {
    if (left > right) return -1;

    int mid = (left + right) / 2;

    if (arr[mid] == target)
        return mid;
    else if (arr[mid] > target)
        return recursiveBinarySearch(arr, left, mid - 1, target);
    else
        return recursiveBinarySearch(arr, mid + 1, right, target);
}

int main() {
    int arr[] = {1, 3, 5, 7, 9};
    int n = 5, target = 7;

    int result = recursiveBinarySearch(arr, 0, n-1, target);

    if (result != -1)
        cout << "Found at index: " << result;
    else
        cout << "Not found";

    return 0;
}
