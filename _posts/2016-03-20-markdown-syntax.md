---
layout: post
title:  "Week 0"
date:   2022-03-09
excerpt: "Matrix, Menu, & IntByReference"
tag:
- markdown 
- syntax
- sample
- test
- jekyll
comments: true
---

## HTML Elements

Below is our coding exercepts 

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

## Tables

|Code Link| Commits |  Score  |
|:--------|:-------:|--------:|
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
|----
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
|=====
| Foot1   | Foot2   | Foot3
{: rules="groups"}



## Buttons

Make any link standout more when applying the `.btn` class.

{% highlight html %}
<a href="#" class="btn btn-success">Success Button</a>
{% endhighlight %}

<div markdown="0"><a href="#" class="btn">Primary Button</a></div>
<div markdown="0"><a href="#" class="btn btn-success">Success Button</a></div>
<div markdown="0"><a href="#" class="btn btn-warning">Warning Button</a></div>
<div markdown="0"><a href="#" class="btn btn-danger">Danger Button</a></div>
<div markdown="0"><a href="#" class="btn btn-info">Info Button</a></div>

