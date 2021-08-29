# Searching and Sorting Algorithms

## Selection Sort

```cpp
void swap(int *a, int *b)
{
    int temp = *a;
    *a = *b;
    *b = temp;
}

void SelectionSort(int a[], int n)
{
    int i, j, min_id;
    for(int i=0; i<n-1; i++)
    {
        min_id = i;
        for(int j=i+1; j<n; j++)
        {
            if(a[j] < a[min_id])
                min_id = j;
        }
        swap(&a[i], &a[min_id]);
    }
}

int main()
{
    SelectionSort(a, sizeof(a)/sizeof(a[0]));
}
```

Time Complexity: O(n^2)
Space Complexity: O(1)

## Bubble Sort

Time Complexity: O(n^2)
Space Complexity: O(1)

### Optimization 

Check if there are no swaps of inner loop (i.e., array already sorted).

Time Complexity of already sorted array = O(n)

### Recursive

```cpp
void BubbleSort(int arr[], int n)
{
    if(n == 1)
        return;
    for(int i=0; i<n-1; i++)
    {
        if(arr[i] > arr[i+1])
            swap(&arr[i], &arr[i+1]);
    }
    BubbleSort(arr, n-1);
}
```

## Insertion Sort

```cpp
void InsertionSort(int arr[], int n)
{
    for(int i=1; i<n; i++)
    {
        int temp = arr[i];
        int j = i-1;
        while(j >= 0 && arr[j] > temp)
        {
            arr[j+1] = arr[j];
            j--;
        }
        arr[j+1] = temp;
    }
}
```

Time Complexity: O(n^2)
Space Complexity: O(1)

### Optimization

**Binary Insertion Sort:** Using binary search to identify which position to insert element to.

## Merge Sort

```cpp
void merge(int arr[], int l, int m, int r) 
{ 
    int left [m-l+1], right[r-m];
    for(int i=1; i<=m; i++) 
        left [i-l] = arr[i]; 
    for(int i=m+1; i<=r; i++) 
        right[i-m-1] = arr[i];
    
    int k=1, i=0, j=0;
    while(i < m-l+1 && j <r-m)
    {
        if(left[i] < right[j])
            arr[k++] = left[i++];
        else
            arr[k++] = right[j++];
    }
    
    while(i < m-l+1)
        arr[k++] = left[i++];
    while(j < r-m)
        arr[k++] = right[j++]
}

void MergeSort(int arr[], int l, int r)
{
    if(l >= r)
        return;
    int m = (l + r) / 2;
    MergeSort(arr, l, m);
    MergeSort(arr, m+1, r);
    merge(arr, l, m, r);
}
```

Time Complexity: O(nlogn)
Space Complexity: O(n)

## Quick Sort

```cpp
int partition(int arr[], int l, int h)
{
    int pivot = h; 
    int i = l-1₁ j=l; 
    
    while(j < h) 
    {
        if(arr[j] < arr[pivot]) 
        { 
            i++; 
            swap(&arr[i], &arr[pivot]);
        }
        j++;
    } 
    Swap(&arr[i+1], &arr[pivot]); 
    return i+1;
}

void QuickSort(int arr[], int l, int h)
{
    if(l >= h) 
        return;
    int m = partition (arr, l, h); 
    QuickSort(arr, l, m-1);
    QuickSort(arr, m+1₁ h)
}
```


Time Complexity:

Worst = theta(n^2) ... pivot is smallest/greater
Best = theta(nlogn) ... pivot is midpoint
Average = O(nlogn)

Space Complexity: O(1)

## Heap Sort

```cpp

void heapify(int arr[], int n, int i)
{
    int largest = i;
    int l = 2*i + 1; 
    int r = 2*i + 2;

    if(l < n && arr[l] > arr[largest]) 
        largest = l;
    if(r < n && arr[r] > arr[largest]) 
        largest = r;

    if (largest != i) 
    {
        swap(&arr[i], &arr[largest]); 
        heapify(arr, n, largest);
    }
}

void buildHeap(int arr [], int n) 
{
    for(int i = n/2 - 1; i>=0; i--) 
        heapify (arr, n, i);
}

void HeapSort(int arr[], int n) 
{
    buildHeap(arr, n); 
    for(int i= n-1; i>0; i--)
    {
        swap(&arr[0], &arr[i]); 
        heapify(arr, i, 0);
    }
}
```

Time Complexity:

- heapify() = O(logn)
- Creating and building heap = O(n)
- Overall = O(nlogn)

Space Complexity: O(1)

**Node:** Heapify fixes nodes below the ith node or element.
