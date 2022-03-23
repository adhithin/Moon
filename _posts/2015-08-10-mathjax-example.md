---
layout: post
title: Week Two (2) 
date: 2022-03-28
excerpt: "Calculator Code, with Stacks, Reverse Polish Notation, and Tokens."
tags:
comments: true
---

## Week 2 Code 

Below are some coding snippets. 

<div markdown="0"><a href="https://adhithin.github.io/posts/" class="btn btn-info"> Click to Go Back</a></div>

## Reverse Polish Notation to Result 

      private void rpnToResult()
    {

        Stack stack = new Stack();


        for (String token : this.reverse_polish)
        {

            if (!isOperator(token))
            {
                stack.push(token);
            }
            else
            {

                Double operand1 = Double.valueOf( (String)stack.pop() );
                Double operand0 = Double.valueOf( (String)stack.pop() );


                Double result;
                switch (token) {
                    case "+":
                        result = operand0 + operand1;
                        break;
                    case "-":
                        result = operand0 - operand1;
                        break;
                    case "*":
                        result = operand0 * operand1;
                        break;
                    case "/":
                        result = operand0 / operand1;
                        break;
                    case "%":
                        result = operand0 % operand1;
                        break;
                    case "^": //this is for power
                        result = Math.pow(operand0, operand1);
                        break;
                    case "?": //this is for sqrt
                        result = Math.sqrt(operand0);
                        break;
                    default:
                        result = 0.0;
                }


                stack.push( String.valueOf( result ));
            }
        }

        this.result = Double.valueOf((String)stack.pop());
    }

## Power 
     // add the same, but for power in the driver 
        System.out.println();

        Calculator squareMath = new Calculator("3 ^ 2");
        System.out.println("squareMath\n" + squareMath);
        
        // in the operators with precedence 
        OPERATORS.put("^", 3);
        
        //the case 
        case "^": // power
        
        //other case, using java.lang.Math; 
         case "^": //this is for power
            result = Math.pow(operand0, operand1);
            break;

## Extra Credit: Square Root 

    // add the same, but for square root in the driver 
        System.out.println();

        Calculator squarerootMath = new Calculator("9 ? 0");
        System.out.println("squarerootMath\n" + squarerootMath);
        
         // in the operators with precedence 
        OPERATORS.put("?", 3);
        
        //the case 
        case "?": // sqrt
        
        //other case, using java.lang.Math; 
         case "?": //this is for sqrt
            result = Math.sqrt(operand0);
            break;




