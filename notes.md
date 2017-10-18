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

open source - pros and cons
===========================

http://www.fordfoundation.org/media/2976/roads-and-bridges-the-unseen-labor-behind-our-digital-infrastructure.pdf

page 33 - 3x
mostly pros but the whole document is about hidden costs of open source


http://thevarguy.com/open-source-application-software-companies/reasons-organizations-opt-not-use-open-source-software

CONS

  * Open Source Isn't Free:
    you need either in-house expertise to deploy open source, or to contract with an organization that can provide that expertise. Both approaches are going to cost money.

    COUNTERARGUMENT: don't give people food but teach them how to fish and hunt. The above downside of open source software is just as true to proprietary software but the costs are higher (product AND support fees), learned in-house expertise is usually barely transferable to other software or fields because of highly specialized or distorted terminology and non-standard and/or obfuscated/obscured architectural design choices. e.g., salesforce administrators would be confused with another CRM where standard terms are used, or windows admins moving to open source operating systems where updates and installations are handled in a different way (but almost uniform among themselves)

    Another solution is education and the organization that embraces the notion that coding (or hacking) is going to be a common required skill, will therefore planning to stabilize its future in the long run.

  * compliance requirements
    That said, the fact that open source software in its raw form usually comes with no warranty or other official guarantee can make it more difficult to use in a business environment where compliance is a must. Plus, things can get complicated when your software stack includes dozens or hundreds of different pieces of open source code, all licensed in varying ways.

    The easy solution is to purchase open source software from a company that guarantees the whole product, like Red Hat or Suse. But that might undercut the attractiveness of open source in the first place for some organizations, especially ones that want it free. So there is always going to be a tradeoff in this respect.

    COUNTERARGUMENT:

    * Yes, are multiple free software and open source licenses and developers have to make sure that every component is compliant with the projects aim (and therefore, with its license). With open source developers cannot stick their head in the sand and have to be aware the implications of their contribution. Just as you cannot develop a software for a specific purpose without getting intimate with domain that product is for. It is just like basic maintenance of your car: unless you have a driver, you have to know the very basics of the car maintenance (what type of fuel to use (gas or diesel, octane etc), replace a tire).

   On the other hand, the end users have more freedom than using a proprietary software because

      1. no one reads the small print that has been the base of many legal battle

      2. the legal burden of understanding all the restrictions that the software may not be used and enforce these requiremeents on the staff.

        With FLOSS, the users are free, they can even alter the end product and suggest those changes back to the development team, who already worked out the details how the components can be compliant.

      3. Owners of proprietary products prefer to use terms that have no legal bindings (intellectual property, rights (see stallman)) to scare into compliance.

    * Confusion about the multiple meanings of the word 'free'. Free software does not mean that it is gratis. (e.g., rhel and sles are both commercial products but there source code is freely available)


  * defunct projects

    When you purchase commercial software, it usually comes with a guarantee of official support from the developers for a fixed period of time. Open source software that you acquire for free often does not.

    This is not universally true, of course. For example, Canonical guarantees support for LTS releases of Ubuntu for extended periods of time even though Ubuntu is free. Plus, it's not a completely sure thing that any support guarantees you get from commercial software will be honored. A company could always go out of business, just as an open source project could go defunct.

    Still, fewer open source products come with support or other longevity guarantees, and it is easier for a user to imagine a volunteer open source project going belly-up than a commercial software company. This, too, is a downside for people considering open source.

    COUNTERARGUMENT: The core principle of the open source model is that you are responsible to your project and it should be handed off to a successor. Companies using FLOSS tools are also contributing back to communities and oftentimes take over maintenance of open source projects that became orphan for multiple reasons: to support the community by giving back and the more practical reason because they rely on that product.

    This part also boils down to education and fostering the local or "close" (ie online) technical community and aspirations.


  * security

    Security is a touchy issue for open source fans. On the one hand, the Eric Raymond mantra (which he calls "Linus' Law," even though Raymond invented the term, not Linus Torvalds) that "given enough eyeballs, all bugs are shallow" suggests that open code should be more secure because a lot of people can review it, which makes it easier to find security flaws.

    On the other hand, there is the argument that proprietary programs whose code is closed cannot be as easily inspected by malicious hackers who are looking for security holes to exploit. In other words, closed-source software has the advantage of security by obscurity.

    Deciding which development model, open or closed, is best for security is an argument that will never be won. There have been some embarrassing security fiascos for the open source community, like Heartbleed. But there have been plenty of similar ones for Windows, iOS and innumerable other closed-source platforms. (Blaster, anyone?)

    For people considering whether to use open source, however, the evidence here is not what matters. Instead, the simple fact that proprietary software companies can make certain arguments to claim their code is more secure can sway users away from open source, regardless of the actual reality.

    COUNTERARGUMENT: No single software is perfect. (not even hello world - it has side effects). A further addendum to Linus' Law is that it is easier to disclose vulnerabilities and they are easier to hide, prompting for immediate action (heartbleed). Whereas vulnerabilities exist to proprietary software as well that won't be disclosed to the public if it has been discovered internally (equifax) because of business interestests.

    Security through obscurity (i.e., closed source software) is not a silver bullet either and usually protects business interests only. Because these products are used by people and do not exist in vacuum. If there is interaction, it can be reverse-engineered. Once the vulnerability is disclosed a small team has to scramble to fix it. (NIST  https://csrc.nist.gov/publications/detail/sp/800-123/final)

http://www.thewhir.com/blog/why-releasing-open-source-software-is-good-for-your-company

PROS

  * recruitment

    Open source developers are flexible and goal-oriented polyglots, well versed in multiple programmming paradigm to get the job done. The knowledge is also out it in the open to learn from.

  * faster and more diverse feedback

  * contributing to the community

    just as the project is using open source projects, whenever our development generates tools that can be used by the greater public, those can be shared as well. It is also free advertising and generates attention

