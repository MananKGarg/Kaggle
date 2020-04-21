## Booleans and Conditionals
---

bool - True or False

                      x = True
                      print(x)
                      print(type(x))
                      
                      Output
                      
                      True
                      <class 'bool'>
                      
                      
We get boolean values from operators

                    a==b, a!=b, a>b, a<b, a<=b,a>=b
                    
                    def can_run_against_PM_Modi(age):
                    """Can someone of given age run for PM"""
                    
                    return age >=50
                    
                    print(can_run_against_PM_Modi(23))
                    print("\n")
                    print(can_run_against_PM_Modi(57))
      
                    Output
                    
                    False
                    True
                    
>>> 3.0 == 3
   True
   
>>> '3' == 3
    False
    
---> Program to check odd number
    
                  def is_odd(n):
                      return(n%2 == 1)
                      
                  print("Is 100 odd?", is_odd(100))
                  print("\n")
                  print("Is 5 odd", is_odd(5))
                  
--->  def can_run_for_president(age, is_natural_born):                  
                    
          return is_natural_born and (age >= 50)
          
      print(can_run_for_president(19, True))
      print(can_run_for_president(55, False))
      print(can_run_for_president(57, True))
      
      Output
      
      False
      False
      True
      
---> If - else

         def inspect(x):
             if x==0:
                 print(x, "is zero")
              
             elif x > 0:
                 print(x, "is positive")
                 
             elif x < 0:
                 print(x, "is negative")
                 
             else:
                 print(x, "is unlike anything")
                 
         inspect(0)
         inspect(-15)
         inspect(23)
         
---> Boolean conversion

    print(bool(1))  # all numbers are treated as true except 0
    print(bool(0)) 
    print(bool"anything") # all strings are treated as true except empty string
    print(bool(" ")) # Generally empty lists, sequences, strings are 'falsey' and the rest 'truthy'
    
    Output
    
    True
    False
    True
    False
    
---> We can use non boolean objects in if conditions and other places where a boolean would be expected. Python will 
     implicitly treat them as their corresponding boolean value
     
     if 0:
         print(0)
     elif "spam":
         print("spam")
         
     output
     
     spam
     
---> def quiz_message(grade):
         if grade < 50:
             outcome = 'failed'
         else:
             outcome = 'passed'
         print('You', outcome, 'the quiz with a grade of', grade)
         
     quiz_message(80)
     
     Output - You passed the quiz with a grade of 80
     
     ---> Python has a single line code for such cases
     
     def quiz_message(grade):
         outcome = 'failed' if grade < 50 else 'passed'  # ternary operator 
         print('You', outcome, 'the quiz with a grade of', grade)
         
     quiz_message(45)
     
     Output - You failed the quiz with a grade of 45
     
      
      
      
      
      
      
      
      
