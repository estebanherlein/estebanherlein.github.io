---
title: "Encryption"
categories:
  - Blog
tags:
  - Cibersecurity
---

Encryption is when you change data with a special encoding process so that the data becomes unrecognizable (it's encrypted). You can then apply a special decoding process and you will get the original data back. By keeping the decoding process a secret, nobody else can recover the original data from the encrypted data.

A very basic form of encryption is ROT-13. It replace all letters of a message with the letter that comes 13 slots later in the alphabet. A becomes N, B becomes O, etc. since the alphabet has 26 letters, if you apply ROT-13 two times you get the original letter back. So in the case of ROT-13, the decryption process is exactly the same as the encryption process.

This method is not a secret either, so it isn't really used to protect private messages. Mostly it's used to hide spoilers: the text looks like rubbish until you decode it, but it's easy to decode when you want to know what it actually says.

There are too many encryption processes to describe them all here. One notable system is one with a private key and a public key. The principle is that there are two processes that decode each other (if you encode with the private key, you can decode with the public key and vice-versa). Your private key is kept private, but you can give your public key to everybody. This allows two things: people can encrypt messages with your public key so that you'll be the only one able to decode them, and you are able to "sign" message by encrypting them with your private key. As your public key can decode the message, everyone will know it was encoded with your private key so it can only come from you.

This is also called asymetric cryptography, as the decoding key is not merely the encoding key in reverse. They are complex mathematical operations that are not symmetrical. If you want to know how private and public keys are implemented precisely, do a search for "public key" here on ELI5.

About some of the terms you wanted explained:

<ul>
<li><strong>AES:</strong> Advanced Encryption Standard. It's a specific way to encode things, based on an encryption key. If you know that something is encoded in AES, you know precisely what to do with the key and the encrypted data so that you get the original data back.</li>

<li><strong>AES uses symmetrical encryption:</strong> the encoding and decoding keys are the same, so they must remain secret. You can only encrypt messages for someone who knows the key, or simply for yourself, to store data in a protected form so that nobody else can read it.</li>

<li><strong>SSL:</strong> Secure Socket Layer. This is a protocol that encrypts the data between your browser and the website you're visiting. When you use an address that starts with https (the S stands for secure), your browser uses SSL to connect to that address.<br><br>

SSL uses asymetric cryptography. This is appropriate, because your browser and the website don't know each other, so they can't arrange to choose a common key beforehand. With asymetric encryption they can exchange public keys (no need to hide them) and then they'll be able to encode something for the other to decode.</li>

<li><strong>256-bit:</strong> There are people who will want to decrypt your message without the decryption key. If you use too simple an encryption (like if you simply replace each letter with another), it'll be too easy for them to decode it. So you want to make it complicated. One way to make it complicated is to use a very big key.<br><br>

Now a computer uses bits to store information. A bit can either be 0 or 1. Imagine that your decryption key is one bit long: it can only be 0 or 1. Someone who wants to decode your message only needs to try two possibilities. Not very secure, is it? If you use two bits, there are 4 possible values: in binary 00, 01, 10 and 11 (or in decimal 0, 1, 2, 3). If you use three bits, there are 8 possible values: 000, 001, 010, 011, 100, 101, 110 and 111. Each time you add a bit, you double the amount of possible keys, and make it that much harder for someone to try them all.<br><br>

256-bit encryption simply means that there are 2256 possible keys. That's a hundred thousand billion billion billion billion billion billion billion billion possible keys. Good luck trying them all.</li>

</ul>