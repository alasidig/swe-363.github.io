---
title: "Introduction"
date: 2024-01-10T11:26:19+03:00
draft: false
summary: Introduction to Web engineering and Development.
weight: 2
tags: [Networking, IP, DNS]
toc: true # Show table of contents? true/false
type: docs # Do not modify.
menu:
  swe363:
    intro:
      name: Introduction
      weight: 4
---

# Demystifying the Web: Your Journey into Web Development and Engineering

**Welcome aboard, future web architects!** This module lays the foundation for your exciting journey into the world of web development and engineering. Buckle up as we explore the intricate tapestry of the web, unraveling its purpose, technology, and underlying principles.

## The Web: An Ocean of Information

Before we dive deep, let's define our playground. The **web** isn't just a collection of websites; it's a vast, interconnected network of documents and resources, accessible through `hyperlinks` and accessed using web `browsers`. It's a living breathing entity, constantly evolving, and serving its primary purpose: connecting people and information.

**Imagine an endless library with shelves upon shelves of information, connected by magical threads you can click to explore further - that's the web!**

### Web vs. Internet: Not Identical Twins

Don't confuse the web with its underlying infrastructure, the **internet**. The internet is the network of networks, the cables and _**protocols**_ that allow communication between computers worldwide. Think of it as the highways and traffic lights, while the web is the vibrant city built upon them.

### Web Servers, Browsers, and Hyperlinks: The Web's Symphony

Now, meet the key players behind the scenes:

- **Web servers:** These tireless workhorses store and deliver website content upon request. Imagine them as libraries housing millions of books, ready to be dispatched to eager readers.
- **Web browsers:** These are your windows to the web, interpreting and displaying the information delivered by web servers. It's like your personal reading device, transforming bytes into beautiful, interactive experiences.
- **Hyperlinks:** These are the web's magic connectors, weaving pages together. They're the clickable pathways that let you navigate from one corner of the web to another, seamlessly and with a single click.

  | Browser                                                                                      | Server                                                    |
  | -------------------------------------------------------------------------------------------- | --------------------------------------------------------- |
  | ![Browser translate the code](../browser.webp) _The browser translate the code of a webpage_ | ![server](../hosting.gif) _The server store/run the code_ |

## How the Internet Makes the Web Dance

Let's peek under the hood and witness the internet's magic trick: data transmission. It all starts with your request, which travels through the internet as tiny **packets**, carrying unique identifiers like {{< appr title="An Internet Protocol address (IP address) is a numerical label such as 192.0.2.1 that is assigned to a device connected to a computer network that uses the Internet Protocol for communication. IP addresses serve two main functions: network interface identification, and location addressing." >}}
**IP Address**
{{< /appr >}} and **sequence numbers**. Think of them as numbered mail packages finding their way through complex sorting centers, guided by **DNS** (the internet's phonebook) and clever algorithms choosing the **best route**. Every packet's safe arrival is confirmed with an **acknowledgement**, ensuring smooth delivery of information.
![Packet Switching](../intro_packet.png)

{{< detailsumary title="1. Packets: " >}}
In data networking, a packet is a small segment of a larger message. Data sent over computer networks, such as the Internet, is divided into packets. These packets are then recombined by the computer or device that receives them. Each packet contains both the data being transmitted and information about the data, such as the source and destination addresses, the sequence number, and the size of the packet.
{{< /detailsumary >}}
{{< detailsumary title="2. IP Addresses: " >}}
An Internet Protocol address (IP address) is a numerical label such as 192.0.2.1 that is assigned to a device connected to a computer network that uses the Internet Protocol for communication. IP addresses serve two main functions: network interface identification, and location addressing.
{{< /detailsumary >}}
{{< detailsumary title="3. Sequence Numbers: " >}}
TCP (Transmission Control Protocol) uses a sequence number to identify each byte of data. The sequence number identifies the order of the bytes sent from each computer so that the data can be reconstructed in order, regardless of any out-of-order delivery that may occur.
{{< /detailsumary >}}
{{< detailsumary title="4. DNS (Domain Name System): " >}}
The Domain Name System (DNS) is the phonebook of the Internet. Humans access information online through domain names, like nytimes.com or espn.com. Web browsers interact through Internet Protocol (IP) addresses. DNS translates domain names to IP addresses so browsers can load Internet resources.
{{< /detailsumary >}}
{{< detailsumary title="5. Best Route: " >}}
The best path is selected by a routing protocol based on the value or metric it uses to determine the distance to reach a network. A metric is the quantitative value used to measure the distance to a given network. The best path to a network is the path with the lowest metric.
{{< /detailsumary >}}
{{< detailsumary title="6. Acknowledgement: " >}}
In data networking, telecommunications, and computer buses, an acknowledgment (ACK) is a signal that is passed between communicating processes, computers, or devices to signify acknowledgment, or receipt of message, as part of a communications protocol.
{{< /detailsumary >}}

#### 💻 Practice Zone

- [Use this website for DNS lookup https://mxtoolbox.com/DNSLookup.aspx](https://mxtoolbox.com/DNSLookup.aspx)
- Run the following commands from the command prompt:

```shell {linenos=table,linenostart=1}
ipconfig # to find the ip address of the machine
nslookup google.com # to do DNS query to get the IP of the domain
```

### Behind the Scenes: The Journey of a Web Page

**Let's follow the path of a web page from the moment you type a URL to the instant it appears on your screen. It's a fascinating journey involving multiple actors and a precise choreography of steps.**

**1. User Initiates the Journey:**

- You enter a URL (like "[www.example.com](https://www.example.com)") into the browser's address bar.

**2. DNS Lookup: Finding the Address:**

- The browser contacts a DNS (Domain Name System) server, the internet's phonebook, to translate the human-readable URL into a numerical IP address that computers understand.

**3. Browser Sends a Request:**

- The browser crafts a well-formatted HTTP request message, containing the URL, browser information, and other relevant details. It sends this message across the internet, aiming for the server at the specified IP address.

**4. Server Receives and Responds:**

- The web server, constantly listening for incoming requests, receives the message. It locates the requested web page files on its storage and packages them into a response message.

**5. Packet Delivery: The Journey Home:**

- The server sends the response message back to the browser, broken down into smaller packets of data. These packets travel through various routers and networks, finding the optimal path to reach the user's device.

**6. Browser Reassembles and Renders:**

- The browser receives the packets, reassembles them into the complete web page, and begins rendering it on the screen. This involves interpreting HTML, CSS, and JavaScript code to create the visual layout and interactive elements.

**7. Fetching Additional Resources:**

- The browser doesn't stop there! It also fetches any linked CSS stylesheets to apply styling and visual formatting to the page content.
- It also fetches JavaScript files, which add dynamic behavior and interactive features to the page, enhancing user experience.

**8. Page Fully Displayed:**

- Once all resources are received and rendered, the web page appears in its full glory, ready for user interaction. This entire process usually happens within a few seconds, making the web feel seamless and responsive.

#### 💻 Practice Zone

Use the browser inspector and navigate to the networking tap to view network requests.

### Under the Hood: Protocols Powering the Web

While we've explored the user-facing journey of accessing a web page, a complex network of protocols operates behind the scenes, ensuring smooth communication and data exchange. Let's peek into some of the most important protocols for web development:

**1. HTTP (Hypertext Transfer Protocol):** The very language of the web! HTTP governs communication between browsers and servers. It dictates how requests are formatted, how responses are sent, and the overall flow of information. Every click, every image download, every interaction on a website relies on HTTP.

**2. HTTPS (Hypertext Transfer Protocol Secure):** Adding a layer of security to HTTP, HTTPS encrypts communication between browsers and servers using SSL/TLS protocols. This protects sensitive information like login credentials and financial data from eavesdropping and manipulation. In today's online world, using HTTPS is essential for building trust and ensuring user privacy.

**3. TCP/IP (Transmission Control Protocol/Internet Protocol):** These two protocols form the backbone of internet communication. TCP ensures reliable data delivery by breaking down information into packets, sequencing them, and requesting retransmission if any are lost. IP, on the other hand, routes these packets through the internet maze, using unique IP addresses to identify devices and networks.

**4. DNS (Domain Name System):** Remember the internet's phonebook? That's DNS! It translates human-readable domain names like "[www.example.com](https://www.example.com): [https://www.example.com](https://www.example.com)" into numerical IP addresses that computers understand. This simplifies the user experience and allows us to remember names instead of complex numbers.

**5. FTP (File Transfer Protocol):** This protocol facilitates the transfer of files between computers on the internet. Often used by developers to upload website files to web servers, FTP ensures reliable and efficient file transfer with features like progress tracking and error recovery.

**6. REST (REpresentational State Transfer):** A popular architectural style for designing web APIs (Application Programming Interfaces), REST relies on HTTP requests and responses to exchange data between applications. Its simplicity, scalability, and widespread adoption make it a favorite for building modern web services.

**7. GraphQL:** An alternative to REST, GraphQL allows clients (frontends) to specify exactly the data they need from an API. This can lead to more efficient data transfer and less server load compared to fetching everything with REST.

These are just a few of the crucial protocols powering the web. Understanding their roles and functions equips you as a web developer to navigate the complex technological landscape, build efficient and secure web applications, and contribute to the ever-evolving digital world.

### Web Browsers: Compatibility Chameleons

Remember, not all browsers are created equal. Different versions and capabilities can lead to inconsistencies in how websites appear and function. This is the challenge of **web browser compatibility**. As developers, we must strive to make our creations adaptable, chameleon-like, adjusting to the diverse landscape of browsers our users inhabit.

#### 💻 Practice Zone

Here is a useful website to check the support of features in different browsers [https://caniuse.com/](https://caniuse.com/?search=container)

## Static vs. Dynamic Websites: Two Flavors of the Web Cake

Imagine a website as a bakery. **Static websites** are like pre-baked cookies, delicious and fixed in form. They offer stability and simplicity, perfect for informational portals or personal portfolios. On the other hand, **dynamic websites** are like freshly baked cakes, responsive and ever-changing. They use scripting languages and databases to personalize experiences and interact with users, making them ideal for e-commerce platforms or social media.
![Static vs dynamic](../static.jpg)

### Web 2.0 and Web 3.0: Evolution of the Web's DNA

The web is constantly evolving, and we've witnessed two major leaps:

- **Web 2.0:** Remember MySpace and Facebook? They ushered in an era of user-generated content and social interaction, turning the web from a one-way street to a bustling marketplace of ideas.
- **Web 3.0:** Prepare for the "semantic web," where AI and machine learning personalize your experience even further. Imagine websites that understand your context and preferences, anticipating your needs before you even express them.

![Web Evolution](../web_evolution.webp)

## Frontend and Backend: Teamwork Makes the Dream Work

Developing a website is like building a house. The **frontend** is the beautiful facade, the part users see and interact with. It's made of HTML, CSS, and JavaScript, the bricks and mortar of visual design and interactivity. Think of it as the paint, windows, and doors that make the house inviting and functional.

<!-- [Image of a beautiful house showcasing its exterior design and elements] -->

On the other hand, the **backend** is the powerhouse engine and data storage, hidden behind the scenes but crucial for the house to function. Languages like Python and Java come into play here, ensuring smooth data processing, secure information handling, and efficient database management. It's like the foundation, plumbing, and electrical wiring that keep the house standing and everything running smoothly.

**Think of it this way:** When you enter a website, you see the buttons, pictures, and text – that's the frontend. But when you click a button, log in, or make a purchase, the backend machinery kicks in, processing your request, retrieving data from the database, and sending it back to the frontend to update what you see on your screen.

### The two sides work together seamlessly:

- **Frontend developers** are the architects and interior designers, building the visible structure and user experience.
- **Backend developers** are the engineers and plumbers, ensuring the underlying systems are secure, efficient, and performant.

**Both are essential for a successful website, just like both the facade and the foundation are crucial for a strong house.**
![Scripting](../intro_scripting.png)

# Web Engineering

## Web Project Lifecycle: From Dream to Reality

Every amazing website starts as a seed of an idea. The **web project lifecycle** takes that seed and nurtures it into a flourishing digital garden. It involves meticulous **requirements gathering,** creating blueprints like **wireframes,** and then employing development methodologies like the **agile process** to break down tasks into manageable sprints. Finally, we employ the **multi-tier architecture,** the three-layered cake of browser, web server, and database, to bring the website to life in a secure and efficient manner.

<!-- [Image depicting the web project lifecycle as a plant growing from a seed, with stages like requirements gathering, wireframing, agile development, and multi-tier architecture represented as steps in the growth process] -->

### Here's a closer look at the phases:

- **Requirements Gathering:** This is where we understand the client's vision, target audience, and website goals. It's like talking to the homeowner to understand their needs and desired outcome for the house.
- **Wireframing:** This is creating a rough sketch of the website's layout and functionality. It's like drawing the floor plan of the house before construction begins.
- **Agile Development:** This is a flexible approach where we break down the project into small, iterative tasks and work in short sprints. It's like building the house room by room, constantly testing and refining as we go.
- **Multi-Tier Architecture:** This is the layered structure of the website, with the browser at the top interacting with the web server, which in turn communicates with the database. It's like the different floors of the house, each with its own purpose and connected through stairs and hallways.

By following this lifecycle, we ensure that websites are built efficiently, meet user needs, and are adaptable to future changes.

**This is just a glimpse into the exciting world of web development and engineering. Get ready to delve deeper, explore new technologies, and unleash your creativity to build beautiful, functional, and impactful websites!**
