
// Name: Melissa Guevara Hernandez
// Course: CISC 192 - C++ Programming
// Date: 11/02/2025
// Assignment: Non-Duplicated Integer Array Operations

```cpp
#include <iostream>
#include <array>

int main() {
    const int N = 5;
    std::array<int, N> nums{};

    std::cout << "Enter " << N << " unique integers:\n";
    for (int i = 0; i < N; ++i) {
        int value;
        bool duplicate;
        do {
            duplicate = false;
            std::cout << "Element " << i + 1 << ": ";
            std::cin >> value;

            // check duplicates
            for (int j = 0; j < i; ++j) {
                if (nums[j] == value) {
                    std::cout << "Duplicate found! Enter a different number.\n";
                    duplicate = true;
                    break;
                }
            }
        } while (duplicate);
        nums[i] = value;
    }

    std::cout << "\nChoose an operation:\n";
    std::cout << "1. Sort Ascending\n";
    std::cout << "2. Sort Descending\n";
    std::cout << "3. Find Maximum\n";
    std::cout << "Enter your choice: ";
    int choice;
    std::cin >> choice;

    switch (choice) {
    case 1: {
        // bubble sort ascending
        for (int i = 0; i < N - 1; ++i) {
            for (int j = 0; j < N - 1 - i; ++j) {
                if (nums[j] > nums[j + 1]) {
                    int temp = nums[j];
                    nums[j] = nums[j + 1];
                    nums[j + 1] = temp;
                }
            }
        }
        std::cout << "\nArray sorted in ascending order:\n";
        for (int x : nums) std::cout << x << " ";
        std::cout << "\n";
        break;
    }
    case 2: {
        // bubble sort descending
        for (int i = 0; i < N - 1; ++i) {
            for (int j = 0; j < N - 1 - i; ++j) {
                if (nums[j] < nums[j + 1]) {
                    int temp = nums[j];
                    nums[j] = nums[j + 1];
                    nums[j + 1] = temp;
                }
            }
        }
        std::cout << "\nArray sorted in descending order:\n";
        for (int x : nums) std::cout << x << " ";
        std::cout << "\n";
        break;
    }
    case 3: {
        int maxVal = nums[0];
        for (int i = 1; i < N; ++i) {
            if (nums[i] > maxVal) maxVal = nums[i];
        }
        std::cout << "\nMaximum value: " << maxVal << "\n";
        break;
    }
    default:
        std::cout << "Invalid choice.\n";
    }

    return 0;
}
```
