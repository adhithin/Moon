---
layout: post
title: "Week One (1)"
date: 2022-03-17
excerpt: "LinkedLists, Queues, and Stacks."
tags: [sample post, images, test]
comments: true
---

## Week 1 Code 

|  <a href="#topic" class="btn btn-info"> Description of Code </a> |  <a href="#code" class="btn btn-info"> Code Snippets </a> | 



## <div> <a id="topic">  Description Of Code + Key Learnings </a></div>

### Key Learnings: 

#### A stack is like a stack of plates. When you add, it adds to the top, and when you take an object away from the stack, it takes it from the top. 

#### A linked list is a list of objects linked to each other in a queue. 

## <div> <a id="code"> Code Snippets </a></div>

### LinkedList Stack 

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


### LinkedList Combine 

 

       for (Object a : words){
            qMix.add(1, a);

        }

        for (Object x : numbers) {
            qMix.add(1, x);

        }


### LinkedList Queue

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



