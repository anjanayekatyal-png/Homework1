# Homework1
Homework#1 W1 D2 jan26-27
package com.example.arrays;

/*
 * This class has a method to merge two sorted arrays.
 * Both input arrays are already sorted in increasing order.
 * The result will also be sorted.
 */
public class SortedArrayMerger {

    /*
     * This method takes two sorted arrays and returns
     * one new sorted array.
     */
    public static int[] mergeSorted(int[] a, int[] b) {

        // Create a new array large enough to hold both arrays
        int[] result = new int[a.length + b.length];

        // i is used to go through array a
        int i = 0;

        // j is used to go through array b
        int j = 0;

        // k is used to fill the result array
        int k = 0;

        /*
         * Compare elements from both arrays.
         * Put the smaller value into result.
         */
        while (i < a.length && j < b.length) {
            if (a[i] <= b[j]) {
                result[k] = a[i];
                i++;   // move to next element in array a
            } else {
                result[k] = b[j];
                j++;   // move to next element in array b
            }
            k++;       // move to next position in result
        }

        /*
         * If array a still has elements left,
         * copy them into result.
         */
        while (i < a.length) {
            result[k] = a[i];
            i++;
            k++;
        }

        /*
         * If array b still has elements left,
         * copy them into result.
         */
        while (j < b.length) {
            result[k] = b[j];
            j++;
            k++;
        }

        // Return the merged sorted array
        return result;
    }
}
