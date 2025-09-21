---
layout: post
title: "IND-CPA Security"
date: 2025-09-21 12:00:00 -0400
categories: cryptography
tags: [Fall2025, notes]
---

### IND-CPA Security

I had taken two Number Theory classes in undergrad which formed a good mathematical foundation for understanding encryption protocols. Something new I learned in the first week of Applied Cryptography class was the idea of **IND-CPA** (Indistinguishability under Chosen-Plaintext Attacks).

***

### Min

**IND-CPA** is a game to define security. Put simply, if you choose a pair of plaintexts and receive a ciphertext, are you able to deduce which plaintext was used?

***

### Max

Here are some interesting examples of **IND-CPA** in action:

A plaintext with a starting bit leaked is **trivially distinguishable**. An attacker can send a message with either a 0 or a 1 as the first bit. Based on the returned ciphertext, they can deduce which plaintext was used, thus breaking the security.

An interesting result is that the **one-time pad** can be attacked under this framework. By properties of XOR, the oracle will return the secret key when a zero-string is given as the message. While the one-time pad is often used as an example of an **information-theoretically secure cryptosystem**, this security only holds under definitions weaker than CPA security. This is because, under the formal definition of CPA security, the encryption oracle has no state. This vulnerability may not be applicable to all practical implementations—the one-time pad can still be made secure if key reuse is avoided (hence the name "one-time" pad).

***

### Lee

This is a new way of thinking for me. I like how there is still a mathematical bound to define security, but it uses abstraction to only consider how a key could be leaked through plaintext combinations.