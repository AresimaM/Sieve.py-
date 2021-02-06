# Sieve.py-
#Using the Sieve of Eratosthenes algorithm, prints out all prime numbers of given integer by #user 
#def makeSieve(): returns True/False Boolean Values for Prime Index  
def makeSieve(n):
    m = 2
    p = [False, False]
    for i in range(n-1):  
      p.append(True)   
    while (m**2) <= n:
      for j in range(m**2,n+1,m):
        p[j] = False
      m +=1
      while not p[m]: #not necessary 
        m +=1
    return p
    #print(p) 
#end makeSieve

#getPrimes: returns prime numbers after calling makeSieve() 
def getPrimes(n):
    P = []
    K = makeSieve(n)
    for i in range(2, n+1):
      if K[i] == True:  #truthy falsey 
        P.append(i)

    #print(P)
    return P
#end getPrimes



#--main program-------------------------

if __name__=='__main__': 
  print()
  #prompt user for positive vallues only
  n = int(input('Enter a positive integer: '))
  while n <= 0:
    n = int(input('Please enter a positive integer: ')) 
 
  print()
  G = getPrimes(n)
  print("There are", len(G), "prime numbers less than or equal to", str(n)+":")
  
  #print without brackets and only in 10 lines
  for i in range(0, len(G)):
   if i%10 == 0:      #i here refers to the index
      print()
   print(G[i], end = ' ')
   #end for
  print()
  print()
   

