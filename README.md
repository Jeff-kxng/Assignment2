Details implementing AES encryption and decryption in both CBC mode and CTR mode : 
1. AES in CBC Mode (Cipher Block Chaining):
   - In CBC mode, each plaintext block is XORed with the previous ciphertext block before encryption.
   - The initial block (IV) is XORed with the first plaintext block.
   - Padding (such as PKCS5) ensures that the plaintext length is a multiple of the block size (16 bytes for AES).
   - The ciphertext is formed by encrypting each modified plaintext block.
   - For decryption, the process is reversed: each ciphertext block is decrypted and XORed with the previous ciphertext block.
   - The IV is used for the first block.
   - The final step is to remove any padding.
2. AES in CTR Mode (Counter Mode):
   In CTR mode:
   - A counter (starting from the IV) is encrypted to produce a keystream.
   - The keystream is XORed with the plaintext to produce the ciphertext.
   - The counter is incremented for each block.
   - CTR mode doesn’t require padding.
   - For decryption, the same keystream is generated, and XORing it with the ciphertext yields the plaintext.
3. Implementation Tips:
   -While you can use existing crypto libraries (such as PyCrypto or Crypto++), consider implementing CBC and CTR modes yourself for a better learning experience.
