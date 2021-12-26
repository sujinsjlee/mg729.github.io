---
layout: post
title: IP address and Gateway, DNS, subnet
description: "Understanding about IP address and Gateway, DNS, subnet"
modified: 2021-12-26
tags: [Network]
categories: [Network]
---

> **IP(*Internet + Protocol*) Address**  

   - Internet means inter + network as the name suggests
   - Several small networks are connected to form a large network
   - When computers are physically connected using an ethernet cable, it becomes a small network.
   - This is called **LAN** (*Local Area Network*)
   - LAN + LAN ==> Internet
   - Protocols on control, connection or communication and data transfer between computers on the Internet
   - an address of a computer

> **Gateway**  


  - LAN connects to the external network through a computer acting as an entrance --> that computer is a gateway
  - *Gateway*: A network point that serves as an entrance to another network.

> **DNS**  


  - DNS emerged in order for devices to recognize each other in computer networks and because it is impossible to memorize IP addresses one by one
  - *DNS*: Converts human-readable domain names into numeric identification numbers to find the address of a specific computer
> **subnet**  


<!--- 서브넷을 보면 255와 0으로 구성이 되어 있다. 네트워크 부분은 255로, 호스트 부분은 0으로 지정해서 IP주소의 어디까지가 네트워크 주소이고 어디부터가 호스트 주소인지 알 수 있다.

  - 예를 들어, subnet이 255.255.0.0 이고 IP 주소가 1.2.3.4 라면, 1.2 까지가 네트워크 주소이고 3.4는 호스트 주소가 된다. 다시 예를 들어 subnet이 255.255.255.0 이고 IP 주소가 1.2.3.4라면 1.2.3까지가 네트워크 주소이고 마지막 4가 호스트 주소가 되는 것이다. 

  - 그렇다면 네트워크 부분과 호스트 부분은 정확히 어떠한 것을 정의하는 것일까? 
    - 네트워크 부분은 통신을 위해서 데이터를 전송하였을 때 라우터를 거치지 않고 전송이 가능한 영역이라는 뜻이다. 호스트 부분은 각각의 PC를 말하는 것이다.
  - 예시를 보면 조금 이해가 빠를 것이다. 호스트 3개가 있다고 치자. 
  - 호스트 a의 IP는 210.170.1.1, 호스트 b의 IP는 210.170.1.2, 호스트 c의 IP는 210.170.2.1이라고 하자.

  - 만일 이 호스트들의 써브넷마스크가 255.255.255.0이라고 하면 네트워크 주소 부분이 세번째 부분까지 된다. 따라서 210.170.1.까지 같은 a와 b는 같은 네트워크로 직통연결이 가능하다.

  - 만약 써브넷마스크가 255.255.0.0이라면 a,b,c 모두 같은 네트워크가 되어 직통연결이 가능한 것이다.-->

  - Abbreviation for subnetwork
    - A network that belongs to an organization but can be recognized as a separate network

  - If you look at the subnet, it is composed of 255 and 0. 
  - By designating the network part as 255 and the host part as 0, you can know where the IP address is from the network address and from where the host address is.

    - For example, if subnet is `255.255.0.0` and IP address is `1.2.3.4`, up to `1.2` are network addresses and `3.4` are host addresses. Again, for example, if the subnet is `255.255.255.0` and the IP address is `1.2.3.4`, then `1.2.3` is the network address and the last `4` is the host address.

    - So, what exactly do the network part and the host part define?
      - The network part means the area where data can be transmitted without going through a router when data is transmitted for communication. 
      - The host part refers to each PC.
    - It will be easier to understand if you look at an example. Let's say you have 3 hosts.
    - Assume that the IP of host a is `210.170.1.1`, the IP of host b is `210.170.1.2`, and the IP of host c is `210.170.2.1`.

    - If the subnet mask of these hosts is `255.255.255.0`, the network address part is up to the third part. Therefore, up to `210.170.1.`, the same a and b can be directly connected to the same network.

    - If the subnet mask is `255.255.0.0`, a, b, and c all become the same network and direct connection is possible.
