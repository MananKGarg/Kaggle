## Lists

primes = [2, 3, ,5 ,7]
planets = ['Mercury', 'Venus', 'Earth', 'Mars', 'Jupiter', 'Saturn', 'Uranus', 'Neptune']

--> We can make a list of lists
 
    hands = [
              ['j', 'q', 'k'],
              ['2', '2', '2'],
              ['6', 'a', 'k']
      
                 ]

--> list can contain different types of variables

    my_list = [ 32, 'raindrops on roses', help]
    
1. Indexing    

Python follows 0 based indexing

               planets[0] - 'Mercury'
               planets[1] - 'Venus'
               planets[-1] - 'Neptune'
               planets[-2] - 'Uranus'
               planets[0:3]- ['Mercury' 'Venus' 'Earth']
               planets[:3] - ['Mercury' 'Venus' 'Earth']
               planets[5:] - [Saturn, Uranus, neptune]
               planets[1:-1] - [Venus', 'Earth', 'Mars', 'Jupiter', 'Saturn', 'Uranus', 'Neptune']
               planets[-3:] - [Saturn, Uranus, neptune]
             
2. Changing Lists

We can modify elements in a list

for example planets[0] = malacandra     changes the value of planets[0] from mercury to malacandra

3. List Functions
 
  1. len 
         Gives the length of the list
         len(planets)   output = 8
  2. sorted
         returns sorted version of list - sorts strings in alphabetical order
  3. sum - sums numbers
         sum(primes) = 17
  4. max - max(primes) = 7
  
Objects -  Everything in python is an object
           In short, objects carry something around them. We acces that by using python's dot syntax
           
           For example - numbers carry associated variable called imag to give imaginary part 
            
           x = 12
           print(x.imag)
           
           output = 0
             
           c= 12 + 3j
           print(c.imag)
           
           output = 3.0
        
   Things that objects carry around can also include functions.A function attached to an object is called a method. Non          function things such as imag are called attributes.
   
   example for numbers we have amethod called bit_length - it tells number of characters in binary form of that number
   
           x = 76
           x.bit_length()
           
           >>> 7 
           
5. List Methods
   
   1. append - adds one element at the end of list
       
               planets.append('Pluto') #adds pluto in the end
               
               help(list.append)
                  
                  append(...) method of builtins.list instance
                          L.append(object) -> None -- append object to end
                          
none part tells us that list.append does not return anything

   2. pop - list.pop() removes last element of a list
   
   3. searching list - we can get index of an element by using list.index()
   
   4. in - to determine whether an element exists in list or not
       
           "Earth" in planets   output - True
           
           "isbvcihsb" in planets    output - False
           
           
Tuples

Same as lists but cannot be modified  

tuples are often used for functions that have multiple return values.

for example as_integer_ratio() method of float objects returns numerators and denominators in the form of a tuple

         x = 0.125
         x.as_integer_ratio()
         
         output - (1,8)
         
These multiple return values can be individually assigned as follows

        numerator, denominator = x.as_integer_ratio()
        print(numerator/denominator)
        
        Output - 0.125
        
Python swap trick
         
        a = 1
        b = 0
        
        a, b = b, a
        print(a,b)
        
        output - 0, 1
        
        
   
                          
   


      
               




















