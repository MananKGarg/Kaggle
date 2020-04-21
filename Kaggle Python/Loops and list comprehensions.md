## Loops and List Comprehensions

1. For loop

       multiplicands = [2, 2, 2, 3, 5, 6]
       product = 1
       for mult in multiplicands:
           product = product*mult
       product
       
       output  = 360
       
       
s = 'steganograpHy is the practicE of conceaLing a file, message, image, or video within another fiLe, message, image, Or video.'
msg = ''
 #print all the uppercase letters in s, one at a time
 
 for char in s:
    if char.isupper():
        print(char, end=' ')
        
        
range returns a sequence of numbers
      
         for i in range(5): #range starts from 0
            print("Doing important work. i =", i)
            
2. While loop 

         i =0 
         while i < 10:
            print(i, endd = ' ')
            i+=1
            
3. List comprehensions

        squares = [n**2 for n in range(10)]
        squares 
        
        output - [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
        
        
        
        short_planets = [planet for planet in planets if len(planet) < 6]
        short_planets
        
        output - ['Venus', 'Earth', 'Mars']  
        
str.upper() returns all caps version of a string

        loud_short_planets = [planet.upper() + 'i' for planet in planets if len(planet) < 6]
        loud_short_planets
        
        output
        
        ['VENUS!', 'EARTH!', 'MARS!']
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
