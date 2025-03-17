a dynamic array that stores collection of elements same type in contiguous memory. It has the ability to resize itself automatically when an element is inserted or deleted.
[Vector in C++ STL - GeeksforGeeks](https://www.geeksforgeeks.org/vector-in-cpp-stl/)

```
int main() {

    // Creating a vector of 5 elements from
    // initializer list
    vector<int> v1 = {1, 4, 2, 3, 5};

    // Creating a vector of 5 elements with
    // default value
    vector<int> v2(5, 9);

    printVector(v1);
    printVector(v2);
    return 0;
}
```

