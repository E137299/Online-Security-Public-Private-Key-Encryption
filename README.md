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
  
### Helpful Functions:
* **ord(character)**
	* returns the unicode number for a letter/character
* **chr(ascii number)**
	* returns the character that represents the specified unicode.

### Provided Functions
* **primes_less_than(n)**
	* returns a list of primes from 2 to n
* **gcd(p,q)**
	* returns the greatest common denominator of the two parameters
* **Is_coprime(x,y)**
	* Determines if two numbers are coprime. Returns True or False
