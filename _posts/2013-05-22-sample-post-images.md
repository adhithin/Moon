---
layout: post
title: "Week One (1)"
date: 2022-03-17
excerpt: "LinkedLists, Queues, and Stacks."
tags: [sample post, images, test]
comments: true
---

## Week 1 Code 

Below are some coding snippets. 

<div markdown="0"><a href="https://adhithin.github.io/posts/" class="btn btn-info"> Click to Go Back</a></div>

## LinkedList Stack 

        public void emptyStack()
    {
        if (DEBUG) ConsoleMethods.println("Delete " + title);
        while (this.stack.peek() != null) {
            T data = this.stack.pop();
            if (DEBUG) ConsoleMethods.println("Pop: " + data + " " + stack);
            System.out.println(stack);  // printing the stack for challenge
        }
        if (DEBUG) ConsoleMethods.println();
        System.out.println(stack); // printing the stack for challenge
    }


## LinkedList Combine 

 

       for (Object a : words){
            qMix.add(1, a);

        }

        for (Object x : numbers) {
            qMix.add(1, x);

        }


## LinkedList Queue

     public T delete() {
        T data = this.queue.delete();
        this.count--;
        if (DEBUG) {
            System.out.println("Dequeued data: " + data);
            printQueue();
        }
        printQueue(); // printing the linkedlist for challenge
        return data;
    }



