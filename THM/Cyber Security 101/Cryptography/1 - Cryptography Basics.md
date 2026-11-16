
# Plaintext to Ciphertext

- We begin with the plaintext we want to encrypt
- The plaintext is the readable data
- The plaintext is passed through the encryption function along with a proper key; the encryption function returns a ciphertext
- The encryption function is part of the cipher; a cipher is an algorithm to convert a plaintext into a ciphertext and vice versa


![[Pasted image 20261116092753.png|700]]


- To recover the plaintext, we must pass the ciphertext along with the proper key via the decryption function, which would give us the original plaintext


![[Pasted image 20261116092928.png]]


- **Plaintext** is the original, readable message or data before it's encrypted; It can be a document, an image, a multimedia file, or any other binary data
- **Ciphertext** is the scrambled, unreadable version of the message after encryption; Ideally, we cannot get any information about the original plaintext except its approximate size
- **Cipher** is an algorithm or method to convert plaintext into ciphertext and back again
- **Key** is a string of bits the cipher uses to encrypt or decrypt data
- **Encryption** is the process of converting plaintext into ciphertext using a cipher and a key
- **Decryption** is the reverse process of encryption, converting ciphertext back into a plaintext using a cipher key
