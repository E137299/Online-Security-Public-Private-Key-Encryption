# Public and Private Key Encryption

[Useful Video Tutorial](https://youtu.be/j2NBya6ADSY)

[ASCII Table](http://sticksandstones.kstrom.com/appen.html)

[Google Sheet](https://docs.google.com/spreadsheets/d/1JSxuIxQq5_de-KWqW_ZZg7EQ7a8wUsuKoiulczy6euY/edit?usp=sharing) - Share your public keys on the Google Sheet. I will use your public keys to encypt a message and I'll leave it on the sheet for you to decrypt.

### Key:
- **p,q** = 	Prime numbers
- **N** = 	Key
- **T** = 	Euler Totient
- **e** = 	Public key
- **d** = 	Private key
- **v** = 	Index value for letter to be encrypted
- **enc** =	Encrypted value(integer)
- **dec** = 	Decrypted value(integer)

### Steps of Encryption:
1. Pick two prime numbers (**p,q**)
2. Let **N = p * q**
3. Let **T = (p-1)*(q-1)**
4. Choose **e** and **d** so that **(e*d) % T =1**
   - **e** must be less than **T**
   - **e** must be coprime with **T** and **N**
5. Publish **N** and **e** for everyone to see.
6. Keep **d** secret.
7. **enc = (v^e) % N**

### Steps of Decryption:
1. **dec = (enc^d)%N**
  

### Functions To Be Written:
- **calculate_N(p,q)**:
	- Input: prime number, prime number
	- Output: N value
- **calculate_T(p,q)**:
    - Input: prime number, prime number
	- Output: T value
- **pick_e_d(p,q)**:
    - Input: prime number, prime number
	- Output: e, d
- **encrypt(n, e, letter)**:
	- Input: key, public key, letter to be encrypted
    - Output: encrypted letter
- **encrypt_message(n, e, message)**:
	- Input: public key, number, string with a secret message
    - Output: a list of containing integer values for each encrypted letter
- **decrypt(n, d, enc)**:
	- Input: key, private key, encrypted letter
    - Output: letter in message
- **decrypt_message(n,d,list)**:
	- Input: prime number, prime number, list of containing integer values for each encrypted letter
    - Output: the decrypted message
  
### Helpful Function:
* **ord(character)**
	* returns the ascii number for a letter/character
* **chr(ascii number)**
	* returns the letter/character associated to an integer
```python
# Returns a list of all the prime numbers from 2 to n
def primes_less_than(n):
	all_primes=[]
	prime = [True for i in range(n + 1)]
	p = 2
	while (p * p <= n):
		if (prime[p] == True):
			for i in range(p ** 2, n + 1, p):
				prime[i] = False
		p += 1
	prime[0]= False
	prime[1]= False
	# Print all prime numbers
	for p in range(n + 1):
		if prime[p]:
			all_primes.append(p)
	return all_primes
	
# These two functions will help determine if two numbers are coprimes #
# Returns the greatest common denominator for two numbers
 def gcd(p,q):
    while q != 0:
        p, q = q, p%q
    return p

# Determines if two numbers are coprime. Returns True or False
def is_coprime(x, y):
    return gcd(x, y) == 1
 ```
