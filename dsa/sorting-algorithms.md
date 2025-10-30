### Selection Sort

Selection Sort is a comparison-based sorting algorithm. It sorts an array by repeatedly selecting the smallest (or largest) element from the unsorted portion and swapping it with the first unsorted element. This process continues until the entire array is sorted.

- First we find the smallest element and swap it with the first element. This way we get the smallest element at its correct position.
- Then we find the smallest among remaining elements (or second smallest) and swap it with the second element.
- We keep doing this until we get all elements moved to correct position

Best, worst and average `time complexity` for selection sort is **O(n<sup>2</sup>)**.

#### Algorithm

```cpp
// 0 - n-1
for(int i =0; i<arr.size()-1;i++){
    minIndex = i;
    // i+1 - n-2
     for(int j = i + 1; j < arr.size(); j++){
        if(arr[j] < arr[i]){
            minIndex = j;
        }
    }

    swap(arr[minIndex], arr[i]);
}
```

---

### Bubble Sort

Bubble Sort is the simplest sorting algorithm that works by repeatedly swapping the adjacent elements if they are in the wrong order. This algorithm is not suitable for large data sets as its average and worst-case time complexity are quite high.

- We sort the array using multiple passes. After the first pass, the maximum element goes to end (its correct position). Same way, after second pass, the second largest element goes to second last position and so on.
- In every pass, we process only those elements that have already not moved to correct position. After k passes, the largest k elements must have been moved to the last k positions.
- In a pass, we consider remaining elements and compare all adjacent and swap if larger element is before a smaller element. If we keep doing this, we get the largest (among the remaining elements) at its correct position.

We can further optimize this sort technique by tracking that at any point did swap happen, i.e if at any point we find that the array or subarray which we are looping through has all sorted elements then there is no point in continuing because all elements are already sorted now. In that case we improved time complexity.

Worst and average `time complexity` for bubble sort is **O(n<sup>2</sup>)**.

Best `time complexity` for bubble sort is **O(n)**.

#### Algorithm

```cpp
// n-1 - 1
for(int i = arr.size()-1; i >= 1; i--){
    bool didSwap = false;
    // 0 - i-1
    for(int j = 0; j < i; j++){
        if(arr[j]>arr[j+1]){
            swap(arr[j], arr[j+1]);
            didSwap = true;
        }
    }

    //checking if swap condition happended or not in current subarray
    // i.e if all elements are already sorted teh swap did not happen
    if(!didSwap){
        break;
    }
}
```

---

### Insertion Sort

Insertion sort is a simple sorting algorithm that works by iteratively inserting each element of an unsorted list into its correct position in a sorted portion of the list.

- We start with the second element of the array as the first element is assumed to be sorted.
- Compare the second element with the first element if the second element is smaller then swap them.
- Move to the third element, compare it with the first two elements, and put it in its correct position
- Repeat until the entire array is sorted.

Worst and average `time complexity` for insertion sort is **O(n<sup>2</sup>)**.

Best `time complexity` for insertion sort is **O(n)**.

#### Algorithm

```cpp
// 0 - n-1
for(int i = 0; i < arr.size(); i++){
    j = i;
    while(j>0 && arr[j-1]>arr[j]){
        swap(arr[j-1], arr[j]);
        j--;
    }
}
```

---

### Merge Sort

Merge sort is a popular sorting algorithm known for its efficiency and stability. It follows the Divide and Conquer approach. It works by recursively dividing the input array into two halves, recursively sorting the two halves and finally merging them back together to obtain the sorted array.

Here's a step-by-step explanation of how merge sort works:

- **Divide**: Divide the list or array recursively into two halves until it can no more be divided.
- **Conquer**: Each subarray is sorted individually using the merge sort algorithm.
- **Merge**: The sorted subarrays are merged back together in sorted order. The process continues until all elements from both subarrays have been merged.

Best, worst and average `time complexity` for selection sort is **O(nlog(n))**.

Worst case `space complexity` of merge sort is **O(n)**. As we are taking an extra array to merge.

#### Algorithm

```cpp
// intially low is at index 0 and high at last index of parent array
void mergeSort(vector<int> &arr, int low, int high){
    //base case
    if(low>=high){
        return;
    }

    //recursively call mergeSort function
    int mid = (low + high)/2;
    mergeSort(arr, low, mid);
    mergeSort(arr, mid+1, high);

    //function to merge the elements in sorted order
    merge(arr, low, mid, high);
}

void merge(vector<int> &arr, int low, int mid, int high){
    // two pointer apporach to sort the array divided in two halves into one
    int left = low;
    int right = mid+1;

    //temporary array
    vector<int> temp;

    while(left<=mid && right<=high){
        if(arr[left]<=arr[right]){
            temp.push_back(arr[left]);
            left++;
        }else{
            temp.push_back(arr[right]);
            right++;
        }
    }

    //push remaning elements if any left
    while(left<=mid){
        temp.push_back(a[left]);
        left++;
    }

    //push remaning elements if any left
    while(right<=high){
        temp.push_back(a[right]);
        right++;
    }

    //update the original array with orted section/subarray
    for(int i = low; i <= high; i++){
        arr[i]=tem[i-low];
    }
}
```
