class Solution:
    # Function to rotate an array by d elements in counter-clockwise direction.
    def rotateArr(self, arr, d):
        n = len(arr)
        # Handle cases where d > n
        d %= n
        
        # Helper function to reverse a portion of the array in place
        def reverse(start, end):
            while start < end:
                arr[start], arr[end] = arr[end], arr[start]
                start += 1
                end -= 1
        
        # Step 1: Reverse the first d elements
        reverse(0, d - 1)
        
        # Step 2: Reverse the rest of the array
        reverse(d, n - 1)
        
        # Step 3: Reverse the entire array
        reverse(0, n - 1)
