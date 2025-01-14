---
title: "Internet connection super heroes TCP and UDP"
seoTitle: "TCP vs UDP "
datePublished: Mon Jan 13 2025 17:53:15 GMT+0000 (Coordinated Universal Time)
cuid: cm5vceaoc000g09mn5d64436f
slug: internet-connection-super-heroes-tcp-and-udp
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1736790743443/5a421c7e-9716-48dd-9ecc-4a79c0d8f077.webp
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1736790748124/6ee1a456-31de-45bb-897c-28902e5c1725.webp
tags: web-development, internet, tcp, udp, chaicode, chaicohort

---

## **TCP (Transmission Control Protocol)**

### Characteristics:

* **Connection Oriented:** It establishes a connection between client (browser) and server via a process called 3-Way hand shake
    

**3-way hand shake:** it is a process of connection between server and client (browser) .

it happens like this:-

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1736788201357/d36138b9-000e-4b6e-b413-37d8662e8309.png align="center")

First browser send sync-1 then server sends sync 200 and acknowledge-1 in response then browser sends acknowledge 200 in return and connection is established or in simple see this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1736788348646/0bb29491-1f91-4f81-ad36-90851ce3a4bf.png align="center")

first Browser calls and says hello then server says hi, i can you hear me then browser says yes, i can hear you then they share data to each other

* **Reliable**: it’s ensures that every packet of your data go to the server or client without losing any thing
    
* **Ordered:** Data packets are reassembled in the correct order.
    
* **Flow Control:** Uses mechanisms to prevent overwhelming the receiver.
    
* **Slower Speed:** The reliability mechanisms add overhead, making TCP slower compared to UDP.
    
* **Heavyweight:** More complex due to connection management and reliability features.
    

### Use Cases :

* Applications requiring speed and low latency, tolerating some data loss:
    
    * Online gaming
        
    * Streaming services (video/audio)
        
    * Voice over IP (VoIP)
        
    

## UDP (User Datagram Protocol):

### Characteristics:

* No Connection needed
    
* Tt’s sends data directly to then server
    
* It does not care about correnct order
    
* It can lose data midway
    

### Use Cases:

* Video Call
    
* Real time data
    

## Difference b/w UDP and TCP

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1736789857414/c1de0fe3-1134-4f8a-89c1-f2816cc5b7b1.png align="center")

## Real-World Examples

### Let's make this super practical:

1. **Netflix:** Initially uses **TCP** to load your video, then switches to **UDP** for streaming. Why? Because it's better to have a slightly pixelated frame than to pause your show waiting for perfect quality.
    
2. **WhatsApp Call:** Uses **UDP** because who wants to wait for lost packets in a live conversation? A tiny glitch is better than awkward delays.
    
3. **Downloading a Game:** Strictly **TCP** territory. You can't have missing pieces in your game files!
    

## Why Do We Need Both?

It's all about the right tool for the right job. **TCP** is like taking the safe but slower mountain road, while **UDP** is like the fast but bumpy highway. Neither is "better" - they just serve different purposes.

## Conclusion

Understanding TCP and UDP both is crucial for developers so they can use one of them in their particular need some times we need both it all depends on our need

now next time when you watch a live cricket show you will know TCP is working under the hood and when you talk to some body on video call you will know that UDP is doing it’s job