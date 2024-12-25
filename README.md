# Heap-Sort-algorithm
Heap-Sort algorithm With C++ 

Part (a) - Heapsort Algorithm (C++)
Algorithm in Pseudocode:
function heapify(arr, n, i):
    largest = i  // Initialize largest as root
    left = 2 * i + 1  // Left child
    right = 2 * i + 2  // Right child
    if left < n and arr[left] > arr[largest]:
        largest = left
    if right < n and arr[right] > arr[largest]:
        largest = right
    if largest != i:
        swap(arr[i], arr[largest])
        heapify(arr, n, largest)

function buildMaxHeap(arr, n):
    for i = n / 2 - 1 down to 0:
        heapify(arr, n, i)

function heapSort(arr):
    n = length(arr)  
    buildMaxHeap(arr, n)
    for i = n - 1 down to 1:
        swap(arr[0], arr[i])
        heapify(arr, i, 0)


        Part (b) - Algorithm Analysis
Time Complexity:
1.Building the Max-Heap:
The heapify function runs in O(log n) time for each node. Since it is called for each non-leaf node (about n/2 nodes), the total time complexity to build the max-heap is O(n).
Sorting:
After building the max-heap, the root of the heap (which is the largest element) is swapped with the last element of the heap. This process is repeated for n-1 elements, and after each swap, the heap size is reduced by one. The heapify function is called each time, which takes O(log n) time for each of the n-1 iterations.
Hence, the time complexity of the sorting phase is O(n log n).
Overall, the time complexity of Heapsort is O(n log n) for both the heap construction and the sorting phase.

Space Complexity:
Heapsort is an in-place sorting algorithm, meaning it does not require extra space for another array. The space complexity is O(1), as it only requires a constant amount of extra space for variables and the recursive call stack during heapify.
Stability:
Heapsort is not a stable sort, meaning it might not preserve the relative order of equal elements. During the heapify process, equal elements might be swapped, which could change their order.

