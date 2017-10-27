commercial vs open source / free
================================

http://peerproduction.net/issues/issue-1/peer-reviewed-papers/why-free-software-is-not-the-antonym-of-commercial-software/
NOTE: free and open source software is not an antonym of commercial software (proprietary is)

In other words, for this developer all the software covered by the GPL should be considered as a specific form of commercial software, to the extent that developers are entitled by the license to distribute copies of the software asking for a payment. This definition (FLOSS as commercial software), states the developer, is also supported by concrete examples such as the GNU/Linux commercial distributions.

NOTE: so you can sell it but you have to provide the source code and the buyer (or licensee) can further distribute the product with the same license (and its restrictions). The next quote further emphasizes that free/open source is not against commercial use:

Open Design Alliance members have created the following free utilities, based on the OpenDWG Libraries, for your unrestricted, non-commercial use. Please note that inclusion of any utility in a commercial product does require commercial licensing [14]
This post clarifies to GRASS developers that it is not possible for them to use the OpenDWG Library together with GRASS, due to the clear commercial nature of GRASS granted by the terms of the GPL (for instance by the term 1 ). Indeed, the OpenDWG source code can be freely used, as it is clearly stated above, but only for non-commercial purposes. Therefore we have an opposition between FLOSS and non-commercial software and not between FLOSS and commercial software.


Lessons for creating good open source software[edit]
====================================================

@bazaar
Raymond points to 19 "lessons" learned from various software development efforts, each describing attributes associated with good practice in open source software development:[3]
Every good work of software starts by scratching a developer's personal itch.
Good programmers know what to write. Great ones know what to rewrite (and reuse).
Plan to throw one [version] away; you will, anyhow. (Copied from Frederick Brooks' The Mythical Man-Month)
If you have the right attitude, interesting problems will find you.
When you lose interest in a program, your last duty to it is to hand it off to a competent successor.
Treating your users as co-developers is your least-hassle route to rapid code improvement and effective debugging.
Release early. Release often. And listen to your customers.
Given a large enough beta-tester and co-developer base, almost every problem will be characterized quickly and the fix obvious to someone.
Smart data structures and dumb code works a lot better than the other way around.
If you treat your beta-testers as if they're your most valuable resource, they will respond by becoming your most valuable resource.
The next best thing to having good ideas is recognizing good ideas from your users. Sometimes the latter is better.
Often, the most striking and innovative solutions come from realizing that your concept of the problem was wrong.
Perfection (in design) is achieved not when there is nothing more to add, but rather when there is nothing more to take away. (Attributed to Antoine de Saint-Exupéry)
Any tool should be useful in the expected way, but a truly great tool lends itself to uses you never expected.
When writing gateway software of any kind, take pains to disturb the data stream as little as possible—and never throw away information unless the recipient forces you to!
When your language is nowhere near Turing-complete, syntactic sugar can be your friend.
A security system is only as secure as its secret. Beware of pseudo-secrets.
To solve an interesting problem, start by finding a problem that is interesting to you.
Provided the development coordinator has a communications medium at least as good as the Internet, and knows how to lead without coercion, many heads are inevitably better than one.


# controversies, copyleft shakedowns, bait and switch etc

## https://copyleft.org/guide/ (chapter 10)

NOTE: Even FSF realized where it would lead if everything would be licensed under a strong copyleft:

10.1 The First LGPL’d Program
(if glibc would be distributed under the GPL, all derivative works would have to be licensed under GPL) [...] At first glance, such an outcome seems like a windfall for Free Software advocates, since it stops all proprietary software development on GNU/Linux systems. However, the outcome is a bit more subtle. In a world where many C libraries already exist, many of which could easily be ported to GNU/Linux, a GPL’d glibc would be unlikely to succeed. Proprietary vendors would see the excellent opportunity to license their C libraries to anyone who wished to write proprietary software for GNU/Linux systems. The de-facto standard for the C library on GNU/Linux would likely be not glibc, but the most popular proprietary one.
