# Affine-Cipher-Implementation-in-Python
Implement the Affine Cipher in Python, a substitution cipher algorithm that employs algebraic operations modulo the alphabet size

# This string has all the alphabet saved with the index to help encrypting and decrypting
 
    alpha="ABCDEFGHIJKLMNOPQRSTUVWXYZ"
    keya=int(input("Key a: "))
    keyb=int(input("Key b: "))
    plain=input("Enter a string: ")

# This is a function that will encrypt the givien text

    def encrypt():
        global cipher # golable variable so it can be accessed outside the function
    
    cipher=""
    
    for i in plain:# a loop that goes through the given string
        
        for j in alpha:# a loop that goes through the alphabet
            
            if i==j:
                
                idx=alpha.index(j)
                new_idx=((keya*idx)+keyb)%26# the formula to give the new letter index
                cipher=cipher+alpha[new_idx]
  
    return cipher
                       
# This is a function that will encrypt the givien text
    
    def decrypt(cp):
       drypt=""
    
    for i in cp:# a loop that goes through the encrypted string
        
        for j in alpha:# a loop that goes through the alphabet
            
            if i==j:
                
                idx=alpha.index(j)
                for k in range(0,26):
                    
                    if (k*keya)%26==1:#a loop where we try to get the value of a^-1(inverse of a)
                        
                        inv_a=k
                        break
                    
                new_idx=inv_a*(idx-keyb)%26# the formula to give the new letter index
                drypt=drypt+alpha[new_idx]
    print('The Encrypted Text: ', cipher)
                
    return drypt
    
# Calling the functions

    print('The Decrypted Text:',decrypt(encrypt()))
