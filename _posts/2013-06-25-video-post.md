---
layout: post
title:  "Week 0"
date:   2022-03-09
excerpt: "Matrix, Menu, & IntByReference"
tag:

comments: true
---

## Week 0 Code 

Below are some coding snippets. 

<div markdown="0"><a href="https://adhithin.github.io/posts/" class="btn btn-info"> Click to Go Back</a></div>

## Matrix 

        for (int j = 0; j < matrix[x].length; j++){ // this is the line that doesn't go through the matrix that doesn't have everything
           // nested for loops, this second one is the width of the matrix

            if (matrix[i][j] == -1){
                System.out.print("  ");
            }

            else if (matrix[i][j] > 9){
                String n = Integer.toHexString(matrix[i][j]);
                System.out.print(n);
                System.out.print(" ");
            }

            else {
                System.out.print(matrix[i][j]);
                System.out.print(" ");
            }


        }
        System.out.println("");
        x++;
    }

## Menu 

## IntByReference 

    public IntByReference(int n){
    this.value = n;
    }

    public IntByReference swapToLowHighOrder(IntByReference x){
    

     IntByReference temp = new IntByReference (value);

    if (x.value < value){

        temp.value = value;
        value = x.value;
        x.value = temp.value;

    }

    else {

        return x;
    }


    return x;

}




