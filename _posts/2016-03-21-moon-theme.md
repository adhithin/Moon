---
layout: post
title: Search Insert Position
date: 2022-03-28
excerpt: "Solving the Search Insert Position Coding challenge on LeetCode."
tags:
comments: true
---

## Overview 

## Takeaways 

## Code 

Below is the method for the search insert position algorithm: 

<div markdown="0"><a href="https://adhithin.github.io/posts/" class="btn btn-info"> Click to Go Back </a></div>


   
      class Solution {
    
    public int index; 
    public int searchInsert(int[] nums, int target) {
        
        // for each number in the nums array
        for (int i = 0; i < nums.length; i++){
            
            // if the element equal target 
            if (nums[i] == target){
                
                // index i is going to be returned 
                this.index = i; 
            }
            
            // else if target is greater than the last element
            else if (target > nums[nums.length -1]){
                
                // index is the length of the array plus 1 
                this.index = nums.length; 
                
            }  
            
        
            // if the element is between this and the next 
            else if (nums[i] < target && nums[i+1] > target){
                
                // index i + 1 is returned 
                this.index = i + 1;   
            }
            
    
        
            // else
            else {
                // the index is the index from earlier  
                this.index = index; 
            }
            
            // index 
            this.index = index; 
     
        }
        
        return index; 
    }
}


