import java.util.Scanner;

public class RecursiveLinearSearch {
    
    // Recursive method to perform linear search
    public static int linearSearch(int[] arr, int target, int index) {
        // Base case: if index is beyond array length, target not found
        if (index >= arr.length) {
            return -1;
        }
        // If target is found at the current index, return index
        if (arr[index] == target) {
            return index;
        }
        // Recursive call to search in the rest of the array
        return linearSearch(arr, target, index + 1);
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Taking array size input from the user
        System.out.print("Enter the size of the array: ");
        int size = scanner.nextInt();
        
        int[] arr = new int[size];
        
        // Taking array elements input from the user
        System.out.println("Enter the elements of the array:");
        for (int i = 0; i < size; i++) {
            arr[i] = scanner.nextInt();
        }
        
        // Taking target value input from the user
        System.out.print("Enter the target value to search: ");
        int target = scanner.nextInt();
        
        // Perform linear search
        int result = linearSearch(arr, target, 0);
        
        // Display the result
        if (result == -1) {
            System.out.println("Target value " + target + " not found in the array.");
        } else {
            System.out.println("Target value " + target + " found at index " + result + ".");
        }
        
        scanner.close();
    }
}



import java.util.Scanner;

public class RecursiveMaxMin {

    // Recursive method to find the maximum value in the array
    public static int findMax(int[] arr, int index, int max) {
        // Base case: if index is beyond array length, return the max found
        if (index >= arr.length) {
            return max;
        }
        // Update max if the current element is greater
        if (arr[index] > max) {
            max = arr[index];
        }
        // Recursive call to find max in the rest of the array
        return findMax(arr, index + 1, max);
    }

    // Recursive method to find the minimum value in the array
    public static int findMin(int[] arr, int index, int min) {
        // Base case: if index is beyond array length, return the min found
        if (index >= arr.length) {
            return min;
        }
        // Update min if the current element is smaller
        if (arr[index] < min) {
            min = arr[index];
        }
        // Recursive call to find min in the rest of the array
        return findMin(arr, index + 1, min);
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Taking array size input from the user
        System.out.print("Enter the size of the array: ");
        int size = scanner.nextInt();
        
        int[] arr = new int[size];
        
        // Taking array elements input from the user
        System.out.println("Enter the elements of the array:");
        for (int i = 0; i < size; i++) {
            arr[i] = scanner.nextInt();
        }
        
        // Finding max and min values in the array
        int max = findMax(arr, 0, arr[0]);
        int min = findMin(arr, 0, arr[0]);
        
        // Display the max and min values
        System.out.println("Maximum value in the array: " + max);
        System.out.println("Minimum value in the array: " + min);
        
        scanner.close();
    }
}
import java.util.Scanner;

public class RecursiveBubbleSort {

    // Recursive method to perform bubble sort
    public static void bubbleSort(int[] arr, int n) {
        // Base case: if array size is 1, it is already sorted
        if (n == 1) {
            return;
        }
        
        // One pass of bubble sort. After this pass, the largest element is moved to the end.
        for (int i = 0; i < n - 1; i++) {
            if (arr[i] > arr[i + 1]) {
                // Swap arr[i] and arr[i + 1]
                int temp = arr[i];
                arr[i] = arr[i + 1];
                arr[i + 1] = temp;
            }
        }
        
        // Largest element is fixed, recur for remaining array
        bubbleSort(arr, n - 1);
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Taking array size input from the user
        System.out.print("Enter the size of the array: ");
        int size = scanner.nextInt();
        
        int[] arr = new int[size];
        
        // Taking array elements input from the user
        System.out.println("Enter the elements of the array:");
        for (int i = 0; i < size; i++) {
            arr[i] = scanner.nextInt();
        }
        
        // Performing bubble sort
        bubbleSort(arr, arr.length);
        
        // Display the sorted array
        System.out.println("Sorted array:");
        for (int i = 0; i < size; i++) {
            System.out.print(arr[i] + " ");
        }
        System.out.println();
        
        scanner.close();
    }
}
import java.util.Scanner;

public class RecursiveSelectionSort {

    // Recursive method to perform selection sort
    public static void selectionSort(int[] arr, int startIndex) {
        // Base case: if startIndex is at the end of the array, sorting is complete
        if (startIndex >= arr.length - 1) {
            return;
        }
        
        // Find the index of the minimum element in the remaining unsorted array
        int minIndex = startIndex;
        for (int i = startIndex + 1; i < arr.length; i++) {
            if (arr[i] < arr[minIndex]) {
                minIndex = i;
            }
        }
        
        // Swap the found minimum element with the first element of the unsorted part
        int temp = arr[minIndex];
        arr[minIndex] = arr[startIndex];
        arr[startIndex] = temp;
        
        // Recursive call to sort the remaining unsorted array
        selectionSort(arr, startIndex + 1);
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Taking array size input from the user
        System.out.print("Enter the size of the array: ");
        int size = scanner.nextInt();
        
        int[] arr = new int[size];
        
        // Taking array elements input from the user
        System.out.println("Enter the elements of the array:");
        for (int i = 0; i < size; i++) {
            arr[i] = scanner.nextInt();
        }
        
        // Performing selection sort
        selectionSort(arr, 0);
        
        // Display the sorted array
        System.out.println("Sorted array:");
        for (int i = 0; i < size; i++) {
            System.out.print(arr[i] + " ");
        }
        System.out.println();
        
        scanner.close();
    }
}
import java.util.Scanner;
import java.util.Arrays;

public class RecursiveBinarySearch {

    // Recursive method to perform binary search
    public static int binarySearch(int[] arr, int target, int low, int high) {
        // Base case: if low index exceeds high, target not found
        if (low > high) {
            return -1;
        }
        
        // Find the middle index
        int mid = low + (high - low) / 2;
        
        // If target is found at mid, return mid
        if (arr[mid] == target) {
            return mid;
        }
        
        // If target is less than mid element, search in the left half
        if (arr[mid] > target) {
            return binarySearch(arr, target, low, mid - 1);
        }
        
        // If target is greater than mid element, search in the right half
        return binarySearch(arr, target, mid + 1, high);
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Taking array size input from the user
        System.out.print("Enter the size of the array: ");
        int size = scanner.nextInt();
        
        int[] arr = new int[size];
        
        // Taking array elements input from the user
        System.out.println("Enter the elements of the array:");
        for (int i = 0; i < size; i++) {
            arr[i] = scanner.nextInt();
        }
        
        // Taking target value input from the user
        System.out.print("Enter the target value to search: ");
        int target = scanner.nextInt();
        
        // Sorting the array
        Arrays.sort(arr);
        
        // Perform binary search
        int result = binarySearch(arr, target, 0, arr.length - 1);
        
        // Display the result
        if (result == -1) {
            System.out.println("Target value " + target + " not found in the array.");
        } else {
            System.out.println("Target value " + target + " found at index " + result + ".");
        }
        
        scanner.close();
    }
}
import java.util.*;
class Fib{
  static int fib(int n){
    if(n==0){
      return 15;
    }
    if(n==1){
      return 23;
    }
    return fib(n-1)+fib(n-2);
  }
  public static void main(String args[]){
    Scanner sc = new Scanner(System.in);
    System.out.println("Enter n :");
    int n = sc.nextInt();
    for(int i=0;i<n;i++){
      System.out.println(fib(i)+" ");
    }
  }
}
import java.util.*;
import java.io.*;
class QuickSort{
  static int max=5000;
  void quick(int arr[],int l,int h){
    int s;
    if(l<h){
      s = partition(arr,l,h);
      quick(arr,l,s-1);
      quick(arr,s+1,h);
    }
  }
  int partition(int arr[],int l,int h){
    int p,i,j,temp;
    p = arr[l];
    i = l+1;
    j = h;
    while(l<h){
      while(arr[i]<p && i<h){
        i++;
      }
      while(arr[j]>p){
        j--;
      }
      if(i<j){
        temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
      }
      else{
        temp = arr[l];
        arr[l] = arr[j];
        arr[j] = temp;
        return j;
      }
    }
    return j;
  }
  public static void main(String[] args) {
    Scanner sc = new Scanner(System.in);
    System.out.println("Enter number of ele: ");
    int n = sc.nextInt();
    Random gen = new Random();
    int arr[] = new int[max];
    for(int i=0;i<n;i++){
      arr[i] = gen.nextInt(1000);
    }
    System.out.println("Random ele: ");
    for(int i=0;i<n;i++){
      System.out.print(arr[i]+" ");
    }
    System.out.println();
    long start = System.nanoTime();
    QuickSort qs = new QuickSort();
    qs.quick(arr,0,n-1);
    long stop = System.nanoTime();
    System.out.println("array after sorting: ");
    for(int i=0;i<n;i++){
        System.out.print(arr[i]+" ");
    }
    System.out.println("Time taken: "+(stop-start));

  }

}
import java.util.*;
class flyods{
  public static void main(String[] args) {
    Scanner sc = new Scanner(System.in);
    System.out.println("Enter the number of ele: ");
    int n =sc.nextInt();
    System.out.println("Enter the adj matrxi: ");
    int adj[][] = new int[10][10];
    for(int i=1;i<=n;i++){
      for(int j=1;j<=n;j++){
        adj[i][j] = sc.nextInt();
      }
    }
    flyod(adj,n);
    System.out.println("the all pair shoretst path is: ");
    for(int i=1;i<=n;i++){
      for(int j=1;j<=n;j++){
        System.out.print(adj[i][j]+" ");
      }
      System.out.println();
    }
  }
  static void flyod(int arr[][],int n){
    for(int k=1;k<=n;k++){
      for(int i=1;i<=n;i++){
        for(int j=1;j<=n;j++){
          arr[i][j] = min(arr[i][j],(arr[i][k]+arr[k][j]));
        }
      }
    }
  }
  static int min(int a,int b){
    if(a<b){
      return a;
    }
    return b;
  }
}
import java.util.*;

public class BellmanFord {
    static class Edge {
        int source, destination, weight;
    }
    static void bellmanFord(int V, int E, Edge[] edges, int src) {
        int[] dist = new int[V];
        for (int i = 0; i < V; i++)
            dist[i] = Integer.MAX_VALUE;
        dist[src] = 0;

        for (int i = 1; i < V; i++) {
            for (Edge e : edges) {
                int u = e.source;
                int v = e.destination;
                int w = e.weight;
                if (dist[u] != Integer.MAX_VALUE && dist[u] + w < dist[v])
                    dist[v] = dist[u] + w;
            }
        }     
        for (Edge e : edges) {
            int u = e.source;
            int v = e.destination;
            int w = e.weight;
            if (dist[u] != Integer.MAX_VALUE && dist[u] + w < dist[v])
                System.out.println("Graph contains negative weight cycle");
        }   
        for (int i = 0; i < V; i++)
            System.out.println("Distance from source " + src + " to vertex " + i + " is " + dist[i]);
    }
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Enter the number of vertices:");
        int V = scanner.nextInt();

        System.out.println("Enter the number of edges:");
        int E = scanner.nextInt();

        Edge[] edges = new Edge[E];

        System.out.println("Enter the source, destination, and weight of each edge:");
        for (int i = 0; i < E; i++) {
            edges[i] = new Edge();
            edges[i].source = scanner.nextInt();
            edges[i].destination = scanner.nextInt();
            edges[i].weight = scanner.nextInt();
        }
        System.out.println("Enter the source vertex:");
        int src = scanner.nextInt();
        bellmanFord(V, E, edges, src);
    }
}
import java.util.*;
import java.io.*;
class MergeSort{
  static int max=5000;
  void mergesort(int arr[],int l,int h){
    int mid;
    if(l<h){
      mid = (l+h)/2;
      mergesort(arr,l,mid);
      mergesort(arr,mid+1,h);
      merge(arr,l,mid,h);
    }
  }
  void merge(int arr[],int l,int mid,int h){
    int i,j,k;
    i = l;
    j = mid+1;
    k = l;
    int t[] = new int[max];
    while(i<=mid && j<=h){
      if(arr[i]<=arr[j]){
        t[k++] = arr[i++];
      }
      else{
        t[k++] = arr[j++];
      }
    }
    while(i<=mid){
      t[k++] = arr[i++];
    }
    while(j<=h){
      t[k++] = arr[j++];
    }
    for(i=l;i<=h;i++){
      arr[i] = t[i];
    }

  }
  public static void main(String[] args) {
    Scanner sc = new Scanner(System.in);
    System.out.println("Enter number of ele: ");
    int n = sc.nextInt();
    Random gen = new Random();
    int arr[] = new int[max];
    for(int i=0;i<n;i++){
      arr[i] = gen.nextInt(1000);
    }
    System.out.println("Random ele: ");
    for(int i=0;i<n;i++){
      System.out.print(arr[i]+" ");
    }
    System.out.println();
    long start = System.nanoTime();
    MergeSort qs = new MergeSort();
    qs.mergesort(arr,0,n-1);
    long stop = System.nanoTime();
    System.out.println("array after sorting: ");
    for(int i=0;i<n;i++){
        System.out.print(arr[i]+" ");
    }
    System.out.println("Time taken: "+(stop-start));
  }
}
import java.util.*;
import java.io.*;
class Kruskals{
  public static void main(String args[]){
    Scanner sc = new Scanner(System.in);
    int cost[][] = new int[10][10];
    int mincost = 0;
    int i,j,n;
    System.out.println("Enter the number of nodes : ");
    n = sc.nextInt();
    System.out.println("Enter the adj matrix : ");
    for(i=1;i<=n;i++){
      for(j=1;j<=n;j++){
        cost[i][j] = sc.nextInt();
      }
    }
    mincost = kruskals(n,mincost,cost);
    System.out.println("the min cost of st is : " + mincost);
    
  }
  static int kruskals(int n,int mincost,int cost[][]){
    int ne=1,a=0,b=0,u=0,v=0,min;
    int parent[] = new int[10];
    while(ne<n){
      min=999;
      for(int i=1;i<=n;i++){
        for(int j=1;j<=n;j++){
          if(cost[i][j]<min){
            min =cost[i][j];
            a=u=i;
            b=v=j;
          }
        }
      }
      if(parent[u]>0){
        u = parent[u];
      }
      if(parent[v]>0){
        v = parent[v];
      }
      if(u!=v){
        System.out.println((ne++)+" min edge is: (" + a +"->"+b+") and its cost is : " + min);
        mincost+=min;
        parent[v] = u;
      }
      cost[a][b] = cost[b][a] = 999;
    }
    return mincost;
  }
}
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Main.java to edit this template
 */

package knapsackgreedy;
import java.util.Scanner;

public class KnapsackGreedy {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Taking the number of items as input
        System.out.print("Enter the number of items: ");
        int n = scanner.nextInt();

        int[] weights = new int[n];
        int[] profits = new int[n];
        double[] ratio = new double[n];

        // Taking weights of the items as input
        System.out.println("Enter the weights of the items:");
        for (int i = 0; i < n; i++) {
            weights[i] = scanner.nextInt();
        }

        // Taking profits of the items as input
        System.out.println("Enter the profits of the items:");
        for (int i = 0; i < n; i++) {
            profits[i] = scanner.nextInt();
        }

        // Taking the capacity of the knapsack as input
        System.out.print("Enter the capacity of the knapsack: ");
        int capacity = scanner.nextInt();

        // Calculate profit to weight ratio
        for (int i = 0; i < n; i++) {
            ratio[i] = (double) profits[i] / weights[i];
        }

        // Sort items by ratio in descending order using selection sort
        for (int i = 0; i < n - 1; i++) {
            int maxIndex = i;
            for (int j = i + 1; j < n; j++) {
                if (ratio[j] > ratio[maxIndex]) {
                    maxIndex = j;
                }
            }
            // Swap the ratios
            double tempRatio = ratio[maxIndex];
            ratio[maxIndex] = ratio[i];
            ratio[i] = tempRatio;

            // Swap the weights
            int tempWeight = weights[maxIndex];
            weights[maxIndex] = weights[i];
            weights[i] = tempWeight;

            // Swap the profits
            int tempProfit = profits[maxIndex];
            profits[maxIndex] = profits[i];
            profits[i] = tempProfit;
        }

        double totalProfit = 0.0;
        int remainingCapacity = capacity;

        // Fill the knapsack with the highest profit/weight ratio items
        for (int i = 0; i < n; i++) {
            if (weights[i] <= remainingCapacity) {
                remainingCapacity -= weights[i];
                totalProfit += profits[i];
            } else {
                totalProfit += ratio[i] * remainingCapacity;
                break;
            }
        }

        System.out.println("Maximum profit: " + totalProfit);

        scanner.close();
    }
}
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Main.java to edit this template
 */
package subsetsum;
import java.util.Scanner;

public class SubsetSum {

    // Main method to drive the program
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Input: Number of elements
        System.out.print("Enter the number of elements: ");
        int n = scanner.nextInt();

        int[] set = new int[n];

        // Input: Elements of the set
        System.out.println("Enter the elements of the set:");
        for (int i = 0; i < n; i++) {
            set[i] = scanner.nextInt();
        }

        // Input: Target sum
        System.out.print("Enter the target sum: ");
        int target = scanner.nextInt();

        scanner.close();

        // Array to store the current subset
        int[] subset = new int[n];
        
        // Find and print subsets that sum to the target
        findSubsets(set, n, 0, subset, 0, target);
    }

    // Function to find subsets that sum to the target
    public static void findSubsets(int[] set, int n, int index, int[] subset, int subsetSize, int target) {
        // If target is 0, we found a subset
        if (target == 0) {
            printSubset(subset, subsetSize);
            return;
        }

        // If target is less than 0 or no more elements to process, return
        if (target < 0 || index == n) {
            return;
        }

        // Include the current element in the subset
        subset[subsetSize] = set[index];
        findSubsets(set, n, index + 1, subset, subsetSize + 1, target - set[index]);

        // Exclude the current element from the subset (backtrack)
        findSubsets(set, n, index + 1, subset, subsetSize, target);
    }

    // Function to print the subset
    public static void printSubset(int[] subset, int subsetSize) {
        System.out.print("Subset: ");
        for (int i = 0; i < subsetSize; i++) {
            System.out.print(subset[i] + " ");
        }
        System.out.println();
    }
}
package primalgorithm;
import java.util.Scanner;

public class PrimAlgorithm {

    public static int prim(int[][] c, int n, int s) {
        int[] v = new int[10];       // Array to track visited vertices
        int[] ver = new int[10];     // Array to store the vertices of the MST
        int[] d = new int[10];       // Array to store the minimum weights
        int sum = 0, min, u = 0;

        for (int i = 1; i <= n; i++) {
            ver[i] = s;
            d[i] = c[s][i];
            v[i] = 0;
        }
        v[s] = 1;

        for (int i = 1; i <= n - 1; i++) {
            min = Integer.MAX_VALUE;
            for (int j = 1; j <= n; j++) {
                if (v[j] == 0 && d[j] < min) {
                    min = d[j];
                    u = j;
                }
            }
            v[u] = 1;
            sum += d[u];
            System.out.println(ver[u] + " -> " + u + " sum=" + sum);
            for (int j = 1; j <= n; j++) {
                if (v[j] == 0 && c[u][j] < d[j]) {
                    d[j] = c[u][j];
                    ver[j] = u;
                }
            }
        }
        return sum;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int[][] c = new int[10][10];
        int n, s;

        System.out.print("Enter the number of vertices: ");
        n = scanner.nextInt();

        System.out.println("Enter the graph data (adjacency matrix): ");
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= n; j++) {
                c[i][j] = scanner.nextInt();
                if (c[i][j] == 0) {
                    c[i][j] = 999; // Assuming 999 is used as the representation of infinity
                }
            }
        }

        System.out.print("Enter the source node: ");
        s = scanner.nextInt();

        //int res = prim(c, n, s);
        System.out.println("Cost = " + prim(c, n, s));
        scanner.close();
    }
}


war
package floyds;
import java.util.*;
class Floyds
{
  public static void main(String[] args) 
  {
      Scanner sc=new Scanner(System.in);
      System.out.println("Enter n");
      int n=sc.nextInt();
      System.out.println("Enter matrix");
      int[][] arr=new int[20][20];
      for(int i=0;i<n;i++)
      {
          for(int j=0;j<n;j++)
          {
              arr[i][j]=sc.nextInt();
          }
      }
      fd(arr,n);
      System.out.println("SSSP");
      for(int i=0;i<n;i++)
      {
          for(int j=0;j<n;j++)
          {
              System.out.print(arr[i][j]+" ");
          }
          System.out.println(" ");
      }
  }
  public static void fd(int arr[][],int n)
  {
      for(int k=0;k<n;k++)
      {
          for(int i=0;i<n;i++)
          {
              for(int j=0;j<n;j++)
              {
                  if(arr[i][j]==0 && arr[i][k]==1 && arr[k][j]==1){
                        arr[i][j]=1;
                  }
              }
          }
      }
  }
}
