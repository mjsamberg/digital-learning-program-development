---
layout: page
title: "A (Very Abbreviated) History of the Web"
course: "webdev"
unit: 1
---
The story of the Internet begins in 1966 with the launch of ARPANET. Over the next decade, the US government and universities worked to establish a network to send messages back and forth between computers. Over the next 30-ish years, the foundations for the Internet grew from this effort.

Read: [How the Internet was born: from the ARPANET to the Internet](https://theconversation.com/how-the-internet-was-born-from-the-arpanet-to-the-internet-68072)

The technologies that grew from ARPANET are still in use today. The two original protocols that grew from ARPANET are called **Transmission Control Protocol** (TCP) and the **Internet Protocol** (IP), referred to collectively as **TCP/IP**. The TCP protocol breaks up data to be sent over the Internet into individual chunks (called packets) and adds information to the packet that describes where the packet needs to go and how to put the packets back together in the event they arrive out of order. TCP is also smart enough to be able to figure out of a packet was lost or damaged (in the olden days, for example, when someone picked up a phone receiver and started dialing) and to inform the sender to retransmit a packet and acknowledge receipt of a packet. IP assigns a unique identifier to each device on the Internet (known as an IP address). The IP address allows computers on the Internet to find each other, and allows the Internet to know how to route the TCP packets from the source to the destination.

Building on these blocks, services began to emerge throughout the 70s and 80s. Email was among the first services to emerge, followed by [Usenet - a bulletin board service](https://en.wikipedia.org/wiki/Usenet). Usenet is what people are typically thinking about when they're thinking about the "old school Internet" - largely text-based discussion forums and navigation via keyboard and text-based interfaces. As graphical user interfaces (GUIs) became more popular, services like [CompuServe](https://en.wikipedia.org/wiki/CompuServe) (foudned 1969) and [Prodigy](https://en.wikipedia.org/wiki/Prodigy_(online_service)) (founded 1984) took this further and wrapped Usenet in more consumer-focused services. [America Online](https://en.wikipedia.org/wiki/AOL) (founded 1983) became among the most popular of these services, being among the first to offer a mouse-based GUI, a free trial, local dial-in telephone numbers (because at this time, you had to make a [phone call to the Internet](https://www.youtube.com/watch?v=D1UY7eDRXrs) using a device called a [modem](https://en.wikipedia.org/wiki/Dial-up_Internet_access)). While Usenet and email worked across services, CompuServe, Prodigy, and AOL were insular, each with their own service offerings and companies having to establish their own storefronts on each ISP. In the early 90s, a new service called [Gopher](https://en.wikipedia.org/wiki/Gopher_(protocol)) allowed for some file sharing capabilities.

## From the Internet to the Web

The web itself emerged in 1990, created by British scientist [Tim Berners-Lee at CERN](https://home.cern/science/computing/birth-web/short-history-web). Berners-Lee created the hypertext project, where specially annotated text (web pages) could be viewed over a tool called a browser. The hypertext markup language (HTML) was created to instruct browsers as to how text and images should be rendered on the screen. Eventually, the National Center for Supercomputing Applications at the University of Illinois at Urbana-Champaign created the first mainstream browser, [NCSA Mosaic](https://en.wikipedia.org/wiki/Mosaic_(web_browser)). Mosaic was popular for a while, eventually losing ground to a new company that leveraged web standards called Netscape Navigator. Netscape is the precursor to the Firefox browser. Microsoft also released their own browser with Windows 95 (Microsoft Internet Explorer) and Apple released Safari with Mac OS X in 2003. The latecomer to the game, Google Chrome, was released in 2008 and became popular through support for a wider array of web standards, speed, and compatibility with Google services. [Watch: Browser share over time from 1997-2019.](https://www.reddit.com/r/dataisbeautiful/comments/cxuah9/usage_share_of_internet_browsers_1996_2019_oc/)

HTML is an open standard - anyone can write HTML code without paying licensing fees, and anyone may submit requests for updates. The [World Wide Web Consortium (w3c)](https://www.w3.org) is the standards body responsible for developing web standards, including HTML, Java Script, and other related standards. They also manage the HTTP protocol. HTTP stands for **HyperText Transfer Protocol** and is the protocol used to send webpage data from a web server to your machine as well as send data back to web servers when you click a link or submit a form. Designed for a time when Internet connections were unreliable, HTTP is a *stateless* protocol, meaning each request is executed independently as if it's the only request a user has ever made to access a web page. HTTP does not remember that a client has visited it before, nor how many times. Interactive webpages that we now enjoy employ a series of tools to mimic interactivity (requests that are invisible to the user that rewrite parts of web pages on your local machine, tokens that identify you to severs, etc.). We will explore these techniques in this course, but the foundational technology itself remains stateless.

Over the time after HTML, tools like Cascading Stylesheets (CSS) allow for sites to be more easily and consistently styled and JavaScript allows for some interactivity on a web page and for the development of web applications. 

## Open Source Foundations

While much of what's on the Internet is proprietary information, the proliferation of the Internet has been enabled through [open source](https://opensource.com/resources/what-open-source) technologies. Open Source technology allows developers to relinquish some of their copyright controls so that other people may use and adapt the software for other purposes. The original creator assigns a license to the work which describes what anyone wishing to use a software package may do with it (see: [Choose a License](https://choosealicense.com)). For example, some software is licensed under the GNU Public License which means that anyone can take the software and use it for commercial purposes, distribute and modify; but they must disclose their source and license the derivative work under this same license. Different licenses have different sets of permissions. Much of the Internet is completely Open Source - Chrome is built on an Open Source tool called Chromium and Safari is built on a tool called WebKit. Apache is the most popular web server and is also open source.
Read: [Wired Guide to Open Source](https://www.wired.com/story/wired-guide-open-source-software/)

Many Open Source software packages also allow anyone to make changes and have them included for anyone to use. A change control board typically reviews these changes for accuracy before including them in the software for everyone else to also benefit from. In his book, [http://www.catb.org/~esr/writings/cathedral-bazaar/cathedral-bazaar/index.html](The Cathedral and the Bazaar), Eric Raymond described the advantages of this approach including how "given enough eyeballs, all bugs are shallow".

Nearly all open source software is available for free and allows for tinkering, modification, and experimentation. This allows the user base to have access to these tools, learn and use them, improve them, and share them. All of the tools used in this course are open source. Moodle is an open source product that anyone can download and install for free, as well as create new plugins for. This textbook is created using an open source tool called Jekyll using a stylesheet framework called Bootstrap, and developed in Visual Studio Code. We will learn about many of these tools this semester. 
