## Functions
---

1. help() function - find what a function does<br/>
                   - print takes sep as an argument, for example print("hello", "world", sep='>')
                   
2. defining our own functions - def

                   
                   
                   def least_difference(a,b,c):
                       diff1 = abs(a-b)
                       diff2 = abs(b-c)
                       diff3 = abs(c-a)
                       return min(diff1,diff2,diff3)
                       
We can write a docstring so that we know what the function does if help is called

                 def least_difference(a,b,c):
                     """ Return the smallest difference among a,b,c
                     
                         >>> least_difference(1,5,-5)
                         4
                         """
                       diff1 = abs(a-b)
                       diff2 = abs(b-c)
                       diff3 = abs(c-a)
                       return min(diff1,diff2,diff3)
                       
Some functions do not have return in the end, so they are pintless on their own but they may be useful for their side effects. for exmaple help() function.

3. Default arguments - sep is an optional argument for print. By default it is single white space.

We can add optional arguments with default values to functions we define

                         def greet(who = "manan"):
                             print("Hello", who)
                             
                         greet()
                         greet("Manan")
                         
Output 
                            
Hello, manan
Hello, Manan

4. Functions applied to functions - We can supply functions as arguments to other functions

                          def mult_by_five(x):
                              return 5*x
                              
                          def call(fn,arg):
                              """ Call fn on arg"""
                              
                              return fn(arg)
                          
                          def double_call(fn,arg):
                              return fn(fn(arg))
                              
                          print(
                              call(mult_by_five, 2),
                              double_call(mult_by_five, 3),
                              sep='\n'
                                                       
                          
                          )    
                       
Output

10
75


5. A good example 
   
By default, max returns the largest of its arguments. But if we pass in a function using the optional key argument, it returns the argument x that maximizes key(x) (aka the 'argmax')

                        def mod_5(x)
                            """ Return the remainder of x after dividing by 5"""
                            return x % 5
                            
                        print(
                              "Which number is biggest?",
                              max(100,51,14),
                              "Which number is biggest modulo 5?",
                              max(100, 51, 14, key = mod_5), sep = "\n"
                              
                        
                        )
                        
                        
                        
                            
                         

















