---
title: "Secure Shell"
categories:
  - Blog
tags:
  - Networking theory
  - basics
  - remote shell
---

SSH, or secure shell, is a remote administration protocol that lets users, wherever they are, spawn a remote shell to work on their servers.

SSH  manages authentication of remote users and serves as an intermediary by relaying the user's input to the server and the output from the server to the user.

SSH was born as a replacement for unencrypted telnet, it uses encryption techniques to encrypt both credentials and data flow.

<h2>Usage</h2>

To start a ssh session you have to provide both a user and a host

> ssh {user}@{host}

{user} is the user account you want to log in, {host} is the ip or hostname of the device you are trying to log into.

After the initial handshake you will be prompted for a password.

If the combination of User, password and host is correct you will be presented a shell. 

<h2>What do you mean with encryption?</h2>

The main advantage of SSH over telnet lies on the encryption of data streams. Assuring the secure transfer of information between client and host.

SSH implements three types of encryption:

<ul>
<li>Symmetric</li>
<li>Asymmetric</li>
<li>Hashing</li>
</ul>

<h3>Symmetric encryption</h3>

Symmetric encryption is a form of encryption in which a secret key is used for both encryption and decryption of a message
Anyone with the key can decrypt the message being transferred

Often called shared key. 

Usually there is only one key that is used, or sometimes a key pair where one key can be easily computed from the other.

Symmetric keys are used to encrypt all communication during an SSH session. Both the client and the server derive the secret key using an agreed method, and the resulting key is never revealed to third parties. 

What makes this algorithm particularly secure is the fact that the key is never transmitted between the client and the host. Instead, the two computers share public data and then manipulate it to independently calculate the secret key. Even if another machine captures the publicly shared data, it will not be able to calculate a key since the key exchange algorithm is not known.

<h3>Asymmetric encryption</h3>

Unlike symmetric encryption, asymmetric encryption uses two separate keys for encryption and decryption. These two keys are known as the public key (public key) and the private key (private key). Together, these keys form the public-private key pair

The public key, as the name suggests, is openly distributed and shared with all parties. While it is closely tied to the private key in terms of functionality, the private key cannot be mathematically calculated from the public key. The relationship between the two keys is highly complex: a message encrypted by the public key of a machine can only be decrypted by the same private key of the machine. This one-way relationship means that the public key cannot decrypt its own messages or decrypt anything encrypted by the private key.

The private key must remain private, that is, for the connection to be secure, no third party must know it.

<h3>Hashing</h3>

One-way hash functions differ from the previous two forms of encryption in that they are never meant to be decrypted. They generate a unique value of a fixed length for each input that does not show a clear trend that can be exploited. This makes them practically impossible to reverse.

It is easy to generate a cryptographic hash of a given input, but impossible to generate the hash input. This means that if a client has the correct input, they can generate the cryptographic hash and compare its value to see if they have the correct input.

<h2>How does it work?</h2>

There are two stages to establishing a connection: first, both systems must agree on encryption standards to protect future communications, and second, the user must authenticate. If the credentials match, the user is granted access.

<h2>Session encryption negotiation</h2>

When a client tries to connect to the server via TCP, the server presents the encryption protocols and the respective versions that it supports. 

If the client has a similar protocol and version pair, an agreement is reached and the connection is initiated with the accepted protocol. The server also uses an asymmetric public key that the client can use to verify the authenticity of the host.

Once this is established, the two parties use what is known as the <b>Diffie-Hellman Key Exchange Algorithm</b> to create a symmetric key. 

This algorithm allows both the client and the server to arrive at a shared encryption key that will be used from now on to encrypt the entire communication session.

Here is how the algorithm works on a very basic level:

<ol>
<li>Both the client and the server agree on a very large prime number, which of course has no factor in common. This prime number value is also known as the seed value.</li>

<li>The two parties then agree on a common encryption mechanism to generate another set of values ​​by manipulating the seed values ​​in a specific algorithmic way.
These mechanisms, also known as cipher generators, perform large operations on the seed. </li>

<li> Both parties independently generate another prime number. This is used as a secret private key for the interaction</li>

<li>This newly generated private key, with the shared number and encryption algorithm (for example, AES), is used to calculate a public key that is distributed to the other computer</li>

<li>The parties then use their personal private key, the other machine's shared public key, and the original prime number to create a final shared key. This key is calculated independently by both computers, but will create the same encryption key on both sides.</li>

<li>Now that both parties have a shared key, they can symmetrically encrypt the entire SSH session. The same key can be used to encrypt and decrypt messages .</li>

</ol>

Now that the symmetrically secure encrypted session has been established, the user must be authenticated.

