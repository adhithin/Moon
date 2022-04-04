---
layout: post
title:  "Week Three (3)"
date:   2022-04-04
excerpt: "Sorts"
tag:

comments: true
---

## Week 3 (Three) Code 

Below are some coding snippets. 

<div markdown="0"><a href="https://adhithin.github.io/posts/" class="btn btn-info"> Click to Go Back</a></div>

## Reflection 

I struggled with the first understanding, but then I ended up understanding, and I coded

## Bubble Sort 

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

## Insertion Sort 

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

## Merge Sort  

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


## Select Sort


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



