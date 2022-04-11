---
layout: post
title:  "Week Three (3)"
date:   2022-04-04
excerpt: "Sorting with Bubble Sort, Merge Sort, Insert Sort, and Select Sort."
tag:

comments: true
---

## Week 3 (Three) Overview 

 <a href="#topic"> Description of Code </a> |  <a href="#codeanalysis" > Code Analysis </a>  | <a href="#code"> Code Snippets </a>



<div> <a href="https://adhithin.github.io//posts/" class="btn btn-info"> Click to Go Back </a></div>

## <div> <a id="topic">  What is Big O Notation? What are the sort implementations? </a></div>

### Big O Notation

Big O notation is "mathematical notation that describes the limiting behavior of a function when the argument tends towards a particular value or infinity". It helps us determine the efficiency of a program. It's often used in math, but can be used in coding when we have to work and figure out the efficiency of certian algorithms and programs. 

### Bubble 

Bubble Sort is a sort where we check two elements in an Array at a time. We look at the first two elements, and if the first element is bigger than the other, we swap them. If not, we do not swap them. This keeps iterating throughout the Array until the Array is sorted in order. 

### Insertion 

Insertion Sort creates the array by inserting the element by order. It inserts one element at a time into the Array, while sorting the Array.

### Merge 

Merge Sort is when we sort by merging and dividing. We split the Array into two's, and sort that way in pairs. 

### Select 

Select Sort selects elements in the list and orders them by pair, and then within the pair. 




## <div> <a id="codeanalysis"> Code Analysis </a></div> 

### Graph 

#### Graph of efficiency for bubble sort: 
<img width="1332" alt="Screen Shot 2022-04-06 at 9 12 58 AM" src="https://user-images.githubusercontent.com/71796291/162019940-337df17d-d2cd-43b8-a01d-4b6e58f8e50d.png">

#### Graph of efficiency for merge sort: 
<img width="1413" alt="Screen Shot 2022-04-06 at 9 16 20 AM" src="https://user-images.githubusercontent.com/71796291/162020557-f08eb0d4-450b-4fd0-ab07-862cd1f19488.png">

#### Graph of efficiency for select sort: 
<img width="1341" alt="Screen Shot 2022-04-06 at 9 15 12 AM" src="https://user-images.githubusercontent.com/71796291/162020376-7dc971c4-880d-4e28-83b9-de7f432304e5.png">

#### Graph of efficiency for insertion sort: 
<img width="1311" alt="Screen Shot 2022-04-06 at 9 17 42 AM" src="https://user-images.githubusercontent.com/71796291/162020836-6365a255-a99a-4ad9-9840-86c3efcede2a.png">

### Data Table 

| Sort      | Speed |
| ----------- | ----------- |
| Bubble     |   0.000149  |
| Merge   | 0.000004       |
| Insertion   | 0.000002       |
| Select   | 0.000023      |

### Analysis 

The most efficient sort program was the Insertion Sort. The time that it took the bubble sort algorithm to sort the given list was 0.000149. The time that it took the insertion algorithm was 0.000002, and it took the Merge sort 0.000004. The select sort took 0.000023. Out of these, the fastest was the insertion sort. This indicates that the insertion sort was the most fastest, and thus in our definition, the most efficient program to sort through the list. 

##  <div> <a id="code"> Coding Snippets </a></div> 

### Bubble Sort 

        public ArrayList<Integer> bubbleSort (ArrayList<Integer> arr) {
       for (int i = 0; i < arr.size() - 1; i++) {
           for (int j = arr.size() - 1; j > i; j--) {
               if (arr.get(j - 1) > arr.get(j)) {
                   //Swap
                   int tmp = arr.get(j - 1);
                   arr.set(j -1, arr.get(j));
                   arr.set(j, tmp);
               }
           }
       }

       return arr;
   }

### Insertion Sort 

     public ArrayList<Integer> insertSort(){

        Instant begin = Instant.now();    // time capture -- end

        for(int i=1;i<data.size();i++){


            int key = data.get(i);

            for(int j= i-1;j>=0;j--){
                if(key < data.get(j)){
                    // Shifting Each Element to its right as key is less than the existing element at current index
                    data.set(j+1,data.get(j));

                    // Special case scenario when all elements are less than key, so placing key value at 0th Position
                    if(j==0){
                        data.set(0, key);
                    }
                }

                else {
                    // Putting Key value after element at current index as Key value is no more less than the existing element at current index
                    data.set(j+1,key);
                    break; // You need to break the loop to save un necessary iteration
                }

            }

            for (Integer x : data){
                System.out.print(x);
            }

        }

### Merge Sort  

    public ArrayList<Integer> merge() {
            //Below is the mergedarray that will be sorted array Array[i-midIndex] , Array[(midIndex+1)-endIndex]
            ArrayList<Integer> mergedSortedArray = new ArrayList<Integer>();

            Instant s1 = Instant.now();    // time capture -- end

            int leftIndex = data.get(0);
            int rightIndex = data.get(data.size() - 1);
            int midIndex = data.size()/2;
            int endIndex = data.size() - 1;
            int startIndex = 0;

            while (leftIndex <= midIndex && rightIndex <= endIndex) {
                if (data.get(leftIndex) <= data.get(rightIndex)) {
                    mergedSortedArray.add(data.get(leftIndex));
                    leftIndex++;
                } else {
                    mergedSortedArray.add(data.get(rightIndex));
                    rightIndex++;
                }
            }

            //Either of below while loop will execute
            while (leftIndex <= midIndex) {
                mergedSortedArray.add(data.get(leftIndex));
                leftIndex++;
            }

            while (rightIndex <= endIndex) {
                mergedSortedArray.add(data.get(rightIndex));
                rightIndex++;
            }

            int i = 0;
            int j = startIndex;
            //Setting sorted array to original one
            while (i < mergedSortedArray.size()) {
                data.set(j, mergedSortedArray.get(i++));
                j++;
            }

            Instant e1 = Instant.now();    // time capture -- end

            this.mergeTime = Duration.between(s1, e1);

            this.data = mergedSortedArray;



            return data;
        }


### Select Sort


    public ArrayList<Integer> selectSort(){

        Instant b = Instant.now();  // starting the time

        for (int i = 0; i < data.size(); i++) {
            // find position of smallest num between (i + 1)th element and last element
            int pos = i;
            for (int j = i; j < data.size(); j++) {
                if (data.get(j) < data.get(pos))
                    pos = j;
            }
            // Swap min (smallest num) to current position on array
            int min = data.get(pos);
            data.set(pos, data.get(i));
            data.set(i, min);
        }



