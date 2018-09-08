---
layout: post
title: "JSON Web Tokens and SwiftyJWT"
date: 2018-09-08
---

If you're looking for an easy way to authenticate REST API requests, you'd be in good stead to look at JSON Web Tokens \([jwt.io](https://jwt.io)\). They are simple and well-supported on many languages and platforms. 

They work like this: each URL you want to authenticate has a token added to it which contains

1. A JSON dictionary or array containing parameters.
2. A metadata dictionary containing expiration date, issue date, and other info.
3. An encrypted hash of the parameters + metadata. 

You use the hash to verify that the other two sections haven't been changed in transit. If it matches, you can be assured of the integrity of the data. 

The beauty of this process is that you can encrypt the hash using public-private key pairs. You keep the private key secured on your server and push the public key into your iOS, Android, and Web apps. Then the apps can verify that any link they got matches what the server sent. If you have a secure way to get another private key into your clients, then they can encrypt JWT for the server to verify too. 

I don't know about you, but I've "invented" several ways to do this over the years before I discovered JWT. Now I'm done making up crazy verification methods and can use the standard. Woot!

If you do decide to use JWT in your apps, I'd like to recommend SwiftyJWT \([Cocoapods link](https://cocoapods.org/pods/SwiftyJWT)\). It's clean, easy, and I just fixed a bug in it so it can now handle both HMAC (symmetric keys) and RSA (asymmetric keys) algorithms for the hash. Using RSA + SwiftyJWT, I'm much less worried about people hacking my API now. 

Stay safe!