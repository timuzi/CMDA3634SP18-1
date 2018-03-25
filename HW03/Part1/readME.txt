Part 1
In the HW03 folder you will find two folders, Part1 and Part2. This section concerns the contents of the Part1 folder.
Setting up an ElGamal Cryptographic System: Recall that in the description of the ElGamal cryp- tographic system in Homework 1 we considered three different people, Alice, Bob, and Eve. In the system, Alice sets up an ElGamal cryptographic system and shares her public-key which consists of the prime number p, generator g, and number h. She also secretly selects a number x, keeping this number private. Using the public-key, Bob is able to send messages that only Alice can read by encrypting his messages m using p, g, and h in such a way that only Alice is able to decrypt the resulting cyphertext.
Let us consider a single program which can emulate this process. In the source file main.c we have begun a program which must be run with MPI using at least 2 ranks. We will label rank 0 as Alice and rank 1 as Bob.
Q1.1(5 points) The program should begin with Alice setting up her ElGamal cryptographic system. Since this the same process each time, we have added the function setupElGamal in the functions.c file. Write this function so it calculates and returns the necessary values for an ElGamal cryptographic system.
Q1.2(5 points) Alter the main function so that only Alice inputs a bit length from the user and sets up an ElGamal cryptographic system.
Q1.3(5 points) Use MPI to broadcast the values which are part of Alice’s public-key to all MPI processes.
Encryption and Decryption: Once the ElGamal system is set up, the crucial steps that remain are the encryption and decryption functions. The main function currently creates an array of Nmessages=5 messages, encrypts and then decrypts them, outputting their values along the way.
Q2.1(10 points) In the file functions.c we have begun implementing the ElGamalEncrypt function. Use the description of the ElGamal encryption process from Homework 1 to complete this function.
Q2.2(10 points) In the file functions.c we have begun implementing the ElGamalDecrypt function. Use
2
the description of the ElGamal decryption process from Homework 1 to complete this function.
Q2.3(15 points) Alter the main function so that only Bob populates the message array and encrypts it. After encryption, use MPI to send the encrypted messages to Alice. Alice should then receive the messages and decrypt them. Run your program and confirm that Alice obtains Bob’s original messages after decryption.
