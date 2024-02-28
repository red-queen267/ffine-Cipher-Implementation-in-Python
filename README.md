# ffine-Cipher-Implementation-in-Python
Implement the Affine Cipher in Python, a substitution cipher algorithm that employs algebraic operations modulo the alphabet size


string="ABCDEFGHIJKLMNOPQRSTUVWXYZ" #this string has all the alphabet saved with the index to help encrypting and decrypting

a=int(input("Key a: "))
b=int(input("Key b: "))
s=input("Enter a string: ")


def encrypt():# this is a function that will encrypt the givien text
    global erypt # golable variable so it can be accessed outside the function
    
    erypt=""
    
    for i in s:# a loop that goes through the given string
        
        for j in string:# a loop that goes through the alphabet
            
            if i==j:
                
                idx=string.index(j)
                new_idx=((a*idx)+b)%26# the formula to give the new letter index
                erypt=erypt+string[new_idx]
  
    print('The Encrypted Text: ',erypt)
                
        
       
def decrypt(cp): # this is a function that will encrypt the givien text 
    drypt=""
    
    for i in cp:# a loop that goes through the encrypted string
        
        for j in string:# a loop that goes through the alphabet
            
            if i==j:
                
                idx=string.index(j)
                for k in range(0,26):
                    
                    if (k*a)%26==1:#a loop where we try to get the value of a^-1(inverse of a)
                        
                        n=k
                        break
                    
                new_idx=n*(idx-b)%26# the formula to give the new letter index
                drypt=drypt+string[new_idx]
                
    print('The Decrypted Text: ',drypt)

encrypt()
decrypt(erypt)
