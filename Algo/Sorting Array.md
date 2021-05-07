#### Bubble
https://www.geeksforgeeks.org/comparison-among-bubble-sort-selection-sort-and-insertion-sort/
repeatedly compares and swaps(if needed) adjacent elements in every pass. In **i-th pass** of Bubble Sort (ascending order), **last (i-1) elements are already sorted**,

**Optimaized Algo**
```js
**BubbleSort (Arr, N)** // Arr is an array of size N.
{
    For ( I:= 1 to (N-1) ) // N elements => (N-1) pass
    {
    // Swap adjacent elements of Arr\[1:(N-I)\]such that
    // largest among { Arr\[1\], Arr\[2\], ..., Arr\[N-I\] } reaches to Arr\[N-I\]
        noSwap = true; // Check occurrence of swapping in inner loop
        For ( J:= 1 to  (N-I) ) // Execute the pass
        {
            If ( Arr \[J\] > Arr\[J+1\] )
            { 
                Swap( Arr\[j\], Arr\[J+1\] );
                noSwap = false;
            }
        }
        If (noSwap) // exit the loop
            break;
    }
}
```

**Time Complexity**:   

-   **Best Case** Sorted array as input. Or almost all elements are in proper place. \[ **O(N)** \]. **O(1)** swaps.
-   **Worst Case**: Reversely sorted / Very few elements are in proper place. \[ **O(N2)** \] . **O(N2)** swaps.
-   **Average Case**: \[ **O(N2)** \] . **O(N2)** swaps.

**Space Complexity**: A temporary variable is used in swapping \[ auxiliary, **O(1)** \]. Hence it is In-Place sort.

#### Insertion

#### Selection

#### Merge
``` js
**MergeSort(arr\[\], l,  r)**
If r > l
     **1\.** Find the middle point to divide the array into two halves:  
             middle m = l+ (r-l)/2
    **2.** Call mergeSort for first half:   
             Call mergeSort(arr, l, m)
     **3.** Call mergeSort for second half:
             Call mergeSort(arr, m+1, r)
     **4\.** Merge the two halves sorted in step 2 and 3:
             Call merge(arr, l, m, r)
```

![Merge-Sort-Tutorial](https://media.geeksforgeeks.org/wp-content/cdn-uploads/Merge-Sort-Tutorial.png)


#### Quick
![quicksort](https://www.geeksforgeeks.org/wp-content/uploads/gq/2014/01/QuickSort2.png)