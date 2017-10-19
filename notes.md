commercial vs open source / free
================================

https://blog.codecentric.de/en/2012/05/using-gpl-licensed-components-in-proprietary-projects/

 The two most frequently found myths are:

 You cannot ask for license fees.
 The source code of the project must be published.
 If these claims were true, GPL-licensed software would indeed be unsuitable for proprietary projects. But they aren’t. So, let’s have a closer look and see what the situation is really like.

 The GPL does not contain any passage stating that license fees can not be asked for. The GPL faq list states explicitly that one can ask for license fees for software under the GPL (see, e.g., here).

 Neither does the GPL state that the source code has to be made public. It is the licensees and only the licensees who must be granted assess to the source code. And the licensor decides who his licensees are. The fact that a GPL-licensed component is publicly available, e.g., over the internet, does in no ways mean that a project building on this component must also be publicly available.


 “Ordinary” Client Projects
 An “ordinary” client project is a project where a software company develops an application for one particular client or a particular small set of clients, usually on demand of the client. Even in these projects, the use of GPL-licensed components can be feasible. Actually, the requirement to hand over the source code of the project to the client is not really a big restriction because contracts regularly contain clauses by which the source code is handed over anyway. Since the client pays for the development of the software he has the right to receive all artefacts of the development including the source.

 NOTE this clearly wasn't the case with slate...

 The issue that is more relevant here is that the client also receives the right to re-distribute the software including the option to ask for fees. So an important question here is whether or not the client may have an interest in re-distributing the software. Let’s consider two examples. Suppose your company developed an application which is not only useful for the client but also for many companies in the industrial sector of client. An example may be an application managing end customer data like addresses and payment management. Such a system is not particular specific to your client. He may thus have an interest in re-selling the application to his competitors. The GPL provides him the freedom to do so.

Suppose the application you create for your client is a software model of the core process of the client’s business model. The application models the key properties that sets the client ahead of his competitors. In the automotive industry, to give an example, this may be car configurator that directly interacts with order systems and production lines. The application is essential to the economic success of your client and constitutes one of his core values. In such a situation, the client has almost no reason at all to re-distribute the application. Thus, though the client is granted certain rights under the GPL, you can be quite sure the client has no interest in actually putting these rights to use. It is therefore a valid option to use GPL-licensed components in such projects.

NOTE: in our case re-distribution is a boon because we are a non profit and do not treat other agencies as competition. What about attribution? there you go:

https://opensource.stackexchange.com/questions/4971/what-are-the-attribution-requirements-of-the-agpl-license

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

