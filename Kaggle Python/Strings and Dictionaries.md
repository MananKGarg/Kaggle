## Strings and Dictionaries

          'Pluto's a planet' - error with this string because confuion with single quotes.

Solve this by using backslash
 
          'Pluto\'s a planet' 
          
\n - new line

triple quotes ensure that enter command is executed without using \n.

          triplequoted_hello = """hello
                               world"""
                               
          >>> hello
              world
        
The print() function automatically adds a newline character unless we specify a value for the keyword argument end other than the default value of '\n':          

      print("hello")
      print("world")
      print("hello", end='')
      print("pluto", end='').
      
      hello
      world
      hellopluto
      
Strings can be thought of as sequences of characters. Almost everything we've seen that we can do to a list, we can also do to a string.

      #Indexing
      planet = 'Pluto'
      planet[0]
      
      'P'
      
      # Slicing
      planet[-3:]
      
      'uto'
                                 
      len(planet) = 5     #Number of characters in Pluto
      
      
      #Yes, we can even loop over them
      [char+'! ' for char in planet]
      ['P! ', 'l! ', 'u! ', 't! ', 'o! ']
      
 ###Strings are immutable     

1. Methods in strings

   1. .upper() - makes all capital
                  
                  name = 'Pluto is a planet'
                  name.upper()
                  
                  >>> 'PLUTO IS A PLANET'
                  
   2. .lower() - makes all lowercase
   
                  name.lower()
                  
                  >>> 'pluto is a planet'
                  
   3. .index() - gives first index of a substring
               
                  name.index('plan')
                  
                  >>> 11
   
   4. startswith() - The startswith() method returns a boolean.

                   It returns True if the string starts with the specified prefix.
                   It returns False if the string doesn't start with the specified prefix.    
                   
   5. split() - str.split() turns a string in a list of strings breaking on whitepaces by default
   
                   words = planet.split()
                   words
                   
                   ['Pluto', 'is', 'a', 'planet!']
                   
      Sometimes we have to split through something other than whitespace
      
                   datestr = '1956-01-31'
                   year, month, day = datestr.split('-')
                   
 6. str.join() - takes us in the other direction, sewing a list of strings up into one long string, using the string it was                    called on as a separator.      
 
                   '/'.join([month, day, year])
                   '01/31/1956'
                   
7. format() -     
                   
                   positon = 9
                   planet = pluto 
                   
                   "{}, you'll always be the {}th planet to me.".format(planet, position)
                   
                   output 
                   
                   "Pluto, you'll always be the 9th planet to me."
                   
                   
                   pluto_mass = 1.303 * 10**22
                   earth_mass = 5.9722 * 10**24
                   population = 52910390
                   #2 decimal points   3 decimal points, format as percent     separate with commas
                   "{} weighs about {:.2} kilograms ({:.3%} of Earth's mass). It is home to {:,} Plutonians.".format(
                   planet, pluto_mass, pluto_mass / earth_mass, population,
                   )
                   
                   "Pluto weighs about 1.3e+22 kilograms (0.218% of Earth's mass). It is home to 52,910,390 Plutonians."
                   
                   
                   # Referring to format() arguments by index, starting from 0
                   s = """Pluto's a {0}.
                   No, it's a {1}.
                   {0}!
                   {1}!""".format('planet', 'dwarf planet')
                   print(s)
                   
                   
Dictionaries - Built in python data structure for mapping keys to values.

                  numbers = { 'one':1, 'two':2, 'three':3 }
                  
                  Here 'one','two', 'three' are keys and 1, 2, 3 are values assigned
                  
Values are accessed via square bracket syntax similar to indexing into lists and strings.

                  numbers['one']
                  1

We can add another key 
                     
                  numbers['eleven'] = 11
                  numbers
                  
                  {'one': 1, 'two': 2, 'three': 3, 'eleven': 11}
                  
Change value associated with an existing key

                  numbers['one'] = 'Pluto'
                  numbers
                  
                  {'one': 'Pluto', 'two': 2, 'three': 3, 'eleven': 11}
                  
                  
Python has dictionary comprehensions with a syntax similar to the list comprehensions we saw in the previous tutorial.                  
                  
                  planets = ['Mercury', 'Venus', 'Earth', 'Mars', 'Jupiter', 'Saturn', 'Uranus', 'Neptune']
                  planet_to_initial = {planet: planet[0] for planet in planets}
                  planet_to_initial
                  {'Mercury': 'M',
                  'Venus': 'V',
                  'Earth': 'E',
                  'Mars': 'M',
                 'Jupiter': 'J',
                  'Saturn': 'S',
                 'Uranus': 'U',
                 'Neptune': 'N'}
                 
 8. in operator tells whether something is a key in a dictionary
            
                 'Saturn' in planet_to_initial
                 True
                 
                 'beetel' in planet_to_initial
                 False
## A for loop over a dictionary will loop over it's keys

                  for k in numbers:
                      print("{} = {}".format(k, numbers[k]))
                      
                  output
                  
                  one = Pluto
                  two = 2
                  three = 3
                  eleven = 11
                  
 We can access a collection of all the keys or all the values with dict.keys() and dict.values(), respectively.
 
                  # Get all the initials, sort them alphabetically, and put them in a space-separated string.
                  ' '.join(sorted(planet_to_initial.values()))
                  'E J M M N S U V'
                  
 dict.items()
 
                  
                  
                  
                  
                  
                  
                  
                  
                  
                  
                  
                  
                  
                  
                  






















