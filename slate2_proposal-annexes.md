
\newpage
Annexes
=======

A.1 Free and open source software
---------------------------------

The usage of the word "free" is misleading because it both means "freedom" and "zero price". The problem is that English, unlike other languages, does not have a common adjective that unambiguously refers to freedom. French for example has "libre" for "freedom" and "gratuit" for "free of charge".[@https://www.gnu.org/philosophy/categories.en.html]

In this context, the intended meaning was "freedom", as in "freedom of users".

### 2.3.1 Brief history

#### 1970s

Computers are built from scratch by research organizations and custom software has to be written to operate them. "Software was not yet standardized and was not considered to be a monetizable product."[@roads-and-bridges]

#### 1981[@roads-and-bridges]

IBM introduces the "IBM PC" or "Personal Computer". Industry adoption is high, winnowing out the competition and capturing half of the market share by 1986.[@23inroadsandbridges]

Standardized hardware brought along the opportunity to standardize software. IBM hires Microsoft to write the operating system for their PC and they deliver MS-DOS in the same year. Other companies follow suit.

Turning software into business proves lucrative, resulting in commercial licenses promoting the creation of proprietary products, preventing users from copying, modifying or redistributing software.

#### 1983

Concern rises among computer scientists "_about the closed and proprietary direction that software was taking_".[@roads-and-bridges] As a response, Richard Stallman launches GNU, a free operating system, also inadvertently laying the foundation for the "free software movement".[@https://www.gnu.org/gnu/initial-announcement.html]

#### 1985

Stallman founds the Free Software Foundation to support the objectives of the "free software movement".[@https://www.gnu.org/gnu/manifesto.html]

#### 1992

The growth of the World Wide Web gains momentum and becomes more widely available.

#### 1996

The commercialization of the web begins with great success and huge gains.

#### 1998

In a move unprecented at the time from a software company, Netscape releases the source code of its high market-share web browser. This event becomes the catalyst to a group of technologists, who have been advocating a more pragmatic approach to the Free Software Foundation's principles, to create the Open Source Initiative. The new organization's focus is to promulgate "_the practical benefits of free software_"[@roads-and-bridges] without "_the ideological and confrontational connotations of the term_"[@https://en.wikipedia.org/wiki/Open-source_software_movement]

### 2.3.2 Open source versus free software

#### 2.3.2.1 Common ground

Both **free[^footnote-word_free] software** and **open source software** do roughly mean the same:

  * According to the Free Software Foundation's summary, it means that "_users have the freedom to run, copy, distribute, study, change and improve the software_"[@https://www.gnu.org/philosophy/free-sw.en.html].

  * The Open Source Initiative defines it as "_software that can be freely accessed, used, changed, and shared (in modified or unmodified form) by anyone. Open source software is made by many people, and distributed under licenses that comply with the [Open Source Definition](https://opensource.org/osd-annotated)._"[@https://opensource.org/faq#osd]

See [Glossary](#glossary) for their formal definitions.

#### 2.3.2.2 Differences

"_Open source is a development methodology; free software is a social movement._"[@https://www.gnu.org/philosophy/open-source-misses-the-point.en.html] Although often discussed together, they are politically distinct: "free software" being more closely associated with ethics ("_essential respect for the users' freedom"[@https://www.gnu.org/philosophy/open-source-misses-the-point.en.html]) and "open source" with pragmatism (i.e., a practical, business-case approach to free software[@https://opensource.org/history]).

The groups' relationship between free and proprietary software is one of the most defining difference:

  * Members of the open source community are willing to coexist with the makers of proprietary software[@https://en.wikipedia.org/wiki/Open-source_software_movement,@https://opensource.org/faq#permissive] and feel that the issue of whether software is open source is a matter of practicality[@https://opensource.org/history]. One example is [tivoization](https://en.wikipedia.org/wiki/Tivoization).

  * In contrast, members of the free software community maintain the vision that all software is a part of freedom of speech and that proprietary software is unethical and unjust[@https://www.gnu.org/philosophy/open-source-misses-the-point.en.html,@https://www.gnu.org/proprietary/proprietary.en.html,@https://www.gnu.org/proprietary/proprietary-surveillance.en.html,@https://www.gnu.org/proprietary/proprietary-back-doors.en.html].

This differentiation is best reflected by the software licenses used: the open source community allows the use of licenses that permit developing proprietary (i.e., closed sourced) software. This is unacceptable to proponents of free software.

Therefore, on the practical side, every existing free software would qualify as open source because the Open Source Initiative allows the more restrictive (or permissive, depending on the perspective) free software licenses but not vice versa.

### 2.3.3 Introduction to licenses

#### Why software licenses are necessary

"_Licenses are important tools for setting specific terms on which software may be used, modified, or distributed_" and they "_can be used to facilitate access to software as well as restrict it_".[@https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3406002/] Because the legal default for original works is exclusive copyright, potential users may become discouraged to use a specific piece of code without a license to avoid future litigations as they do not know which limitations owners may want to enforce.[@https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3406002/] 

Open collaboration also requires legal ground rules to be layed down because "_without a license, everybody who contributes to the project also becomes an exclusive copyright holder of their work. That means nobody can use, copy, distribute, or modify their contributions – and that “nobody” includes the author as well._"[@github.com/github/opensource.guide]

Copyright holders therefore set formal permissions in the form of licenses, especially if they expect their code to be reused.

#### 2.3.3.1 Copyright

Copyright grants the creator of an original work exclusive but limited rights[^footnote-copyright_limits] for its use and distribution[@https://en.wikipedia.org/wiki/Copyright;@http://www.etymonline.com/word/copyright;@https://opensource.com/resources/what-is-copyleft] by default under the Berne Convention[@https://en.wikipedia.org/wiki/Berne_Convention;@https://en.wikipedia.org/wiki/Berne_Convention_Implementation_Act_of_1988]. Authors therefore have complete authority and they have to provide explicitly permit any actions that would involve the use of their work.

[^footnote-copyright_limits]: "_Copyright law does not protect the titles of books or movies, nor does it protect short phrases such as, “Make my day.” Copyright protection also doesn’t cover facts, ideas, or theories. These things are free for all to use without authorization._"[@https://fairuse.stanford.edu/overview/public-domain/welcome/]

#### 2.3.3.0 Public domain software

Some developers reject the necessity of software licenses altogether and therefore do not use licenses[@https://en.wikipedia.org/wiki/License-free_software] or put their work explicitly in the public domain[@http://cr.yp.to/distributors.html].

License-free software are usually avoided because it is not explicitly in the public domain and the absence of a license makes the software fully copyright protected according to the Berne convention.

Dedicating software to the public domain is somewhat better received. Works in the public domain are creative material that are not protected by copyright, trademark or patent laws and can be modified, distributed, or sold even without any attribution by anyone.[@https://en.wikipedia.org/wiki/Public-domain_software;@https://en.wikipedia.org/wiki/Public_domain;@https://fairuse.stanford.edu/overview/public-domain/welcome/] Legal ambiguities still exist however, especially when it comes to software, such as:

  * What is the legally accepted way to place software in the public domain?

    There are four common ways for works to end up in the public domain: the copyright has expired, forfeited, waived or inapplicable.[@https://en.wikipedia.org/wiki/Public_domain;@https://fairuse.stanford.edu/overview/public-domain/welcome/]

    Abandoning the copyright is the most pertinent in this case and there is a debate about what methods are legally accepted[@https://lists.opensource.org/pipermail/license-review/2012-March/001679.html;@http://cr.yp.to/distributors.html] or whether it can be done at all[^footnote-abandon_copyright].

[^footnote-abandon_copyright]: There is legal precedent to it, at least by the US Ninth Circuit: "_Abandonment of such rights, however, must be manifested by some overt act indicative of a purpose to surrender the rights and allow the public to copy._"[@1960hampton]

  * How can public domain software be re-used in proprietary software?

    Modifications to a public domain work may be protected by copyright[@https://fairuse.stanford.edu/overview/public-domain/trouble-spots/] if the modification is non-trivial (i.e., meets the applicable laws' originality and creativity requirements)[@https://copyleft.org/guide/comprehensive-gpl-guidech2.html#x5-50001.1;@http://www.publicdomainsherpa.com/10-misconceptions-about-the-public-domain.html#five] and this could be interpreted that only the modification itself can copyrighted[@http://www.publicdomainsherpa.com/10-misconceptions-about-the-public-domain.html#five].

    The meaning of "public domain" also depends on jurisdiction[@https://www.quora.com/When-you-create-a-proprietary-software-after-using-quite-a-few-open-source-software-projects-as-a-starting-point-how-is-this-legal;@https://en.wikipedia.org/wiki/Public_domain] and licenses are necessary that emulate the public domain, such as CC0[@https://wiki.creativecommons.org/wiki/CC0], Unilicense[@http://unlicense.org/] or WTFPL[@http://www.wtfpl.net/].

#### 2.3.3.0 Copyleft

The most exhaustive resource on this topic is the continuously updated Copyleft and the GNU General Public License: A Comprehensive Tutorial and Guide[@https://copyleft.org/guide/] but the following sections try to give a quick summary.

##### 2.3.3.0.1 History and rationale

Since the emergence of computer science, developing and sharing programs was entirely in the public domain, mostly in academia and software was not copyrightable.

In 1974, the US Commission on New Technological Uses of Copyrighted Works (CONTU) decided that "_computer programs, to the extent that they embody an author's original creation, are proper subject matter of copyright_"[@http://www.digital-law-online.info/CONTU/].

The Copyright Act of 1976[@https://www.law.cornell.edu/uscode/text/17/117] (and following legal precedents, such as Apple v. Franklin[@https://openjurist.org/714/f2d/1240/apple-computer-inc-v-franklin-computer-corporation]) "_clarified that the Copyright Act gave computer programs the copyright status of literary works_"[@https://en.wikipedia.org/wiki/Public-domain_software].

The Berne Convention Implementation Act of 1988 puts any original creative works under copyright after creation by default.

The legislation gave rise to the development of proprietary software and helped it become a lucrative business opportunity from the early 1980s, causing the decline of the academic public domain software ecosystem[@https://en.wikipedia.org/wiki/History_of_Unix].

Richard Stallman, himself an academic and alarmed by the growing trend, founds the GNU Project, and with that, the free software movement. He writes the first version of GNU General Public License in 1989 as a response, to encode public domain rights on software, relying "_on the enforceability of the copyright to be effective_"[@https://en.wikipedia.org/wiki/Public-domain_software].

##### 2.3.3.0.2 What is copyleft?

Also referred to as *reciprocal* or *protective* licensing. The derogatory adjectives "viral" or "infectious" are also used[@https://en.wikipedia.org/wiki/Viral_license]. (See [Controversies]).

It is a form of licensing that retains the author's exclusive copyrights for works but gives permission to recipients of the work to reproduce, change or distribute it, with the accompanying requirement that any resulting copies or adaptations are also bound by the same licensing agreement. "_In essence, copyleft grants freedom, but forbids others to forbid that freedom to anyone else along the distribution and modification chains._"[@https://copyleft.org/guide].(Hence the term "reciprocal".)

Copyleft software intentionally shares properties with public domain software and by requiring the same copyleft license downstream is an attempt to close one of its loopholes: "_any nontrivial modification made to the [public domain] work is fully copyrightable_", ergo "_over time, some entities will choose to proprietarize their modified versions_" with little "_incentive to contribute back to the commons_", until "_almost no interesting work is left in the public domain, because nearly all new work is done by proprietarization._"[@https://copyleft.org/guide].

"_Copyleft uses functional parts of the copyright system to achieve an unusual result (legal protection for free sharing)_"[@https://copyleft.org/guide/]: it modifies copyright law, which is usually employed to strengthen the rights of authors or publishers by prohibiting "_recipients from reproducing, adapting, or distributing copies of their work_"[@https://en.wikipedia.org/wiki/Copyleft], to strengthen instead the rights of users. This reversal is reflected in its name as a wordplay on "copyright".

The stipulation that the "_information necessary for reproducing and modifying the work must be made available to recipients of the binaries_"[@https://en.wikipedia.org/wiki/Copyleft] (i.e., source code) is added to prevent the creation of proprietary products[@https://www.gnu.org/copyleft/copyleft.html] and it is probably the most notable difference to public domain software because "_an executable program can be in the public domain but the source code is not available_"[@https://www.gnu.org/philosophy/categories.en.html].

The idea of copyleft can be also applied to works that are not software. These licenses are usually called share-alike (see Creative Commons[@https://creativecommons.org/].

##### 2.3.3.0.3 Types

###### Strong and weak copyleft

"_“Strong vs. weak” copyleft is not a dichotomy, it’s a spectrum._"[@https://copyleft.org/guide/] "_The strength of the copyleft governing a work is an expression of the extent that the copyleft provisions can be efficiently imposed on all kinds of derived[sic] works._"[@https://en.wikipedia.org/wiki/Copyleft]

The stronger the license, the more it will seek to ensure that the same license will cover every version of derivative works, making them subject to its requirements.[@https://copyleft.org/guide/] Practically this means that the corresponding source code has to be made available to licensees. The ideological goal is to ensure the propagations of the software freedoms for each user.

Usually larger end user programs, which cannot be used further as a component, opt in using such licenses to prevent turning them into proprietary products.[^footnote-strong_copyleft_abuse] The versions of the GNU General Public License (GNU GPL) are the most commonly cited examples for strong copyleft.

[^footnote-strong_copyleft_abuse]: This is not a rule though and strong copyleft licenses are known to be abused by the industry. See [Controversies].

GNU GPL version 3 with its system library exception is cited (see 9.3.3 in [@https://copyleft.org/guide/]) as an example to prove that the strength of a license is indeed a spectrum.

As the "copyleft" gets weaker, the license starts to introduce "trade offs" such as allowing cases of derivative works that are permitted to use another license and/or keeping parts of the source closed in order to foster wider adoption but still try to hold on to most of copyleft's principles.[@https://en.wikipedia.org/wiki/Copyleft;@https://copyleft.org/guide/]

The most well-known example for this seemingly counter-intuitive rationale is the history of the GNU Lesser General Public License (GNU LGPL) and "glibc", the GNU project's implementation of the C standard library. It was created to provide a common alternative to the world of proliferating proprietary implementations that had limited functionality, sometimes specific only to certain vendors. If it had used a stronger license (such as the GPL), any software created with it would have to be shipped with the same license, thus providing their source code would have been necessary to avoid violation of the license's terms. "_The de-facto standard for the C library on GNU/Linux would likely be not glibc_"[@https://copyleft.org/guide/], a free software, but probably the most popular proprietary one that allows developers to create proprietary software.

There are multiple ways to purposely weaken copyleft restrictions:

  * "The LGPL distinguishes between two classes of works: “works based on the library,” and “works that use the library” and it is generally used for the creation of software libraries.[^footnote-lgpl_terms]

  * The Mozilla Public License version 2.0 (MPL v2.0) is using a "file-level" copyleft instead[@https://www.mozilla.org/en-US/MPL/2.0/FAQ/] that "_treats the source code file as the boundary between MPL-licensed and proprietary parts, meaning that all or none of the code in a given source file falls under the MPL._"[@https://en.wikipedia.org/wiki/Mozilla_Public_License] It also allows sublicensing[@https://softwareengineering.stackexchange.com/questions/189633/what-sublicense-actually-means][^footnote-mpl_extra]

[^footnote-lgpl_terms]: The quoted terms are specific to LGPLv2 and has been superseded by LGPLv3. See Chapters 10 and 11 in [@https://copyleft.org/guide/].

[^footnote-mpl_extra]: Extra resources on when choosing MPL v2.0 could be beneficial to a project are [@https://christoph-conrads.name/why-i-chose-the-mozilla-public-license-2-0/;@https://julien.ponge.org/blog/mozilla-public-license-v2-a-good-middleground/].

###### Full and partial copyleft

TODO links!
This classification is used by some sources but there is no authoritative source for their definitions by any of the well-established entities (for example, organization such as the Free Software Foundation, Open Source Initiative, Mozilla Foundation, or licensing websites such as choosealicense.com, TLDR-legal).

---

Most of the definitions can be found in many places but they are

  * vague without examples, and they are exact or minimally modified copies of each other[@https://en.wikipedia.org/wiki/Copyleft;@https://books.google.com/books?id=WRAFJNMrSdkC&pg=PA34&lpg=PA34&dq=full+partial+copyleft&source=bl&ots=lg50hOJ0oe&sig=h8i3mjiEPmbazN7mV63v2z2tKs8&hl=en&sa=X&ved=0ahUKEwjWsLWf2ZHXAhVJ2GMKHVvCBK8Q6AEIfzAQ#v=onepage&q=full%20partial%20copyleft&f=false;@http://machines.plannedobsolescence.net/marxwiki/index.php?title=Copyleft#Full_and_partial_copyleft;@http://www.yourdictionary.com/copyleft;@https://wikivisually.com/wiki/Weak_copyleft;@http://encyclopedia2.thefreedictionary.com/Copyleft+licensing;@https://www.pcmag.com/encyclopedia/term/40363/copyleft]

  * indistinguishable in meaning from or bear close resemblance to weak/strong copyleft[@https://en.wikipedia.org/wiki/Copyleft;@https://fullmetallinux.wordpress.com/tag/copyleft/]

  * describing the difference between conventional and "file-level"[@https://www.mozilla.org/en-US/MPL/2.0/FAQ/] (or "per-file"[@https://www.gnu.org/licenses/license-list.en.html]) copyleft[@https://prezi.com/0sdn2cpssmyn/copyleft-prezi/;@https://www.academia.edu/9259737/Demystifying_Copyleft_Creative_Commons_and_Open_Access_Rights_a_little_]

    This makes the most sense but none of the sources provide explicit examples to this claim (such as CDDL or MPL as they would perfectly fit those descriptions).

    The Software Freedom Law Center's report comes closest in supporting this theory as it uses both "strong" and "partial" to describe CDDL's copyleft properties.

The adjective "full" is never used by any of the aforementioned entities to describe copyleft licenses[^footnote-osi_cat] and "partial" is used as a synonym to "weak" copyleft (with the exception mentioned in the last item above).[@http://oss-watch.ac.uk/resources/licensing-handout.pdf;@http://blog.docracy.com/post/51823372485/software-licensing-what-type-of-license-should-i/embed;@https://www.fsf.org/news/openoffice-apache-libreoffice;@https://books.google.com/books?id=isTBDAAAQBAJ&pg=PA276&lpg=PA276&dq=gnu+partial+copyleft&source=bl&ots=w4PESycpiK&sig=Hsb4A5DAlUVGMOyFoCJIA-8rmxk&hl=en&sa=X&ved=0ahUKEwjd_eWL5JHXAhUP-GMKHW6CCOEQ6AEIgwEwEA#v=onepage&q=gnu%20partial%20copyleft&f=false]

[^footnote-osi_cat]: The Open Source Initiative goes further because it does not even use "weak" or "strong" to categorize copyleft licenses.

The Free Software Foundation uses both "copyleft-weak" and "copyleft-partial" as explicit categories in its license description templates but only the latter is used[@https://directory.fsf.org/wiki/User:Jgay/license-categorization].

#### Licensing
##### Proprietary licenses

"_The primary purpose of a proprietary software license is to limit the use of software according to the rights owner's business strategy_"[@https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3406002/], generally distributed in binary form. They are typically very restrictive for end users as they disallow any action that is not specifically layed out in the license.

Examples of limitations:

  * deployment

    How many times can a software be installed?
    How many devices can it be installed?
    Are simultaneous installations allowed?

  * use

    What are the exact purposes that the software can be used for?
    Are other users allowed to use a specific installation?
    How can the functionality of the software be extended?

  * distribution

    What counts as (re-)distribution?
    Is it allowed at all?

  * derivative works

    What is a derivative work according to the copyright owner?
    Is it allowed to use parts or the entire software in derivative works?

##### 2.3.3.2 Open source licenses

Open source licenses are licenses that comply with the [Open Source Definition](https://opensource.org/osd) (i.e., they allow software to be freely used, modified, and shared), including non-copyleft licenses that allow proprietary derivative works[@https://opensource.org/faq#permissive]. (A reason why they are also called "permissive" licenses).

As the defintion of open source software is an extension of [the four essential freedoms of the Free Software Definition](https://www.gnu.org/philosophy/free-sw.html), all copyleft licenses are also open source licenses.

The Open Source Initiative maintains the list of approved licenses:
<https://opensource.org/licenses>

##### 2.3.3.3 Free software licenses

Free software licenses are licenses that comply with the [definition of free software](https://www.gnu.org/philosophy/free-sw.html). (TODO: glossary?) The Free Software Foundation's Licensing and Compliance Lab maintains an annotated and categorized list of licenses that can be found at <https://www.gnu.org/licenses/license-list.en.html>.

Free software tend to be using [copyleft](#glossary) licenses to keep propagating the same freedoms down the line but it is a misconception to think that all copyleft licenses are also automatically qualify as free software licenses (see [Sybase Open Watcom Public License version 1.0](https://www.gnu.org/licenses/license-list.en.html#Watcom)).

The most prominent examples are the versions of the GNU General Public License[^footnote-gpl_v3].

[^footnote-gpl_v3]: The latest version is the [GNU General Public License v3.0](https://www.gnu.org/licenses/gpl-3.0.en.html). For an extensive legal analysis is also available by the Software Freedom Law Center[@https://www.softwarefreedom.org/resources/2014/SFLC-Guide_to_GPL_Compliance_2d_ed.html] or see the de facto guide [@https://copyleft.org/guide/].

##### Controversial licensing practices
#### Compliance
##### compatibility
##### ?
#### 2.3.3.4 Choosing a license

Choosing a license depends on many factors, such as use cases (e.g., end user product, software module), adopting entities (e.g., company, group of hobby developers), project goals (e.g., commercial product, free or for fee services).[@https://blog.p2pfoundation.net/why-apache-defeated-the-gpl-license-developer-freedom-vs-user-freedom/2013/01/21,@https://softwareengineering.stackexchange.com/questions/107883/agpl-what-you-can-do-and-what-you-cant,@https://news.ycombinator.com/item?id=1273231,@roads-and-bridges]

### 2.3.4 Factors to consider before adoption

  * **Cost**

    Proprietary software is always more expensive because a company has to pay for development, distribution, support, legal fees etc.

    On the contrary, open source code can be obtained free of charge but all sources agree that there are hidden costs (if not about their extent).[@https://www.americanexpress.com/us/small-business/openforum/articles/the-open-source-conundrum-3-benefits-and-drawbacks-to-consider/;@https://jaxenter.com/think-open-source-software-free-think-131436.html;@https://crowdsourcedtesting.com/resources/pros-cons-open-source-software/;@http://thevarguy.com/open-source-application-software-companies/reasons-organizations-opt-not-use-open-source-software;@https://www.americanexpress.com/us/small-business/openforum/articles/the-open-source-conundrum-3-benefits-and-drawbacks-to-consider/;@http://entrepreneurhandbook.co.uk/open-source-software/;@https://crowdsourcedtesting.com/resources/pros-cons-open-source-software/;@roads-and-bridges,@osmovement] and the next items expand on the nature of these. Their categorization into pros and cons is not straightforward because it depends on the scope of the adopting organization and the parties involved making their case.

  * **Risk of abandonment of dependent projects.**

    The argument stems from the fear of the decentralized open source workflow and that project governance is unclear in many cases.

    On the other hand this fear is also valid regarding proprietary software: companies phase out older products or functionality (sometimes without any notice) regardless of users relying on them (e.g., subsequent iterations of Microsoft products routinely defy assumptions based on previous versions) and even profiting from offering additional transitional support.

  * **Support and ongoing maintenance**

    Commercial proprietary products are traditionally shipped with guaranteed support whereas open source is perceived to lack this level of care[@http://thevarguy.com/open-source-application-software-companies/reasons-organizations-opt-not-use-open-source-software]. This may be due to the fact that it is not stated explicitly in every project but is an intrinsic part of open source culture:

    * documentation is kept up to date

    * communities around a project have mailing lists, chat rooms, meet-ups set up (even regular office hours specified![@https://make.wordpress.org/community/handbook/wordcamp-organizer/planning-details/gpl-primer/]

    * sites dedicated to answering questions of almost any nature, such as Stackoverflow or Quora

    * issues and feature requests can be directly opened on the project's source code repository (e.g., on Github)

    * as a last resort, the source code is always available

    Open source companies also offer commercial support as part of their business model.

   Commercial support for proprietary software on the other hand can be so poor that another company needs to be hired for deployment and for ongoing operations. The worst case scenario is that local staff takes up the mantle even though they had no role in development and have little ability to do anything else other than coming up with workarounds by trial and error as the implementation details are not known.[@osmovement]

    This brings up the issue of control:

  * **Control**

    Proprietary vendors have iron grip over the software's functionality and future evolution. Monopolies eliminate any upstart innovators, effectively locking the organizations into a platform with the ability to demand any price.

    Open source's alluring promise is to return control.
    over the tools one would like to use and how one would like to use them.

    Examples to the former are alternatives to proprietary software such as
    Control over the choice of tools one would like to use:

      * OpenOffice instead of Microsoft Office

      * Linux, BSD or other open source operating systems instead of Microsoft Windows or Apple Mac OS X[^footnote-macosx_open]

      * FreeSWITCH instead of Avaya IP Office

    Control over how one would like to use these tools:

      * Restrictions of proprietary software licenses are able to limit any aspect of a program (such as JAWS, Raiser's Edge, EyeCare, Microsoft Office): the number of times a software can be installed, the number of computers it can be present simultaneously, the number of database records, the date until it can be used and so on.

        Alternatives, such as NVDA, CiviCRM, OpenERM, OpenOffice etc. do not have these restrictions.

      * Avaya IP Office phone system only allows certain functionality in combination with specific hardware (and even then it is not guaranteed).

        FreeSWITCH may be compiled on any commodity hardware and can be extended programmatically or by community modules.

    Control over one's own data because by the lack of regulations, users' have little authority over what should happen to their voluntarily supplied information to large corporations[@https://www.economist.com/news/leaders/21721656-data-economy-demands-new-approach-antitrust-rules-worlds-most-valuable-resource]. Open Stack is one solution to create a private or public cloud on any available hardware.

[^footnote-macosx_open]: Even though Apple recently open sourced the kernel of Mac OS X but it is only responsible for booting up the computer - all the useful programs are still proprietary and are not included[@https://www.techrepublic.com/article/why-apple-open-sourcing-mac-os-x-isnt-terribly-exciting/]

  * **Standards and tools**

    Ever since the business opportunity of selling software has been recognized, companies have been creating programs to solve a specific problem (networking, data management, etc.) with the intent of successful commercial distribution. Many times the problem domains have been complex enough to develop a proprietary standard solution and patent it, leading the way to reinvent the wheel over and over. Overall secrecy made it difficult to prove the superiority of one product over the other and typically the corporation with the most resources and/or better marketing campaign prevailed.

    Adopting organizations still require long periods of deliberation before purchasing any proprietary software suite because:

    * The rigidness of the tools would require adjusting organizational processes and workflows (i.e., serving the tool instead of the other way around)

    * It would lock them in in the long haul. Reasons include:

        * information is stored in a proprietary format

        * no interoperation with other vendor's products

        * accumulated experience would not translate to other similar solutions requiring re-training and/or new hires

    With the emergence of the free and the open source movement large-scale collaboration on *open standards* became the norm. Proprietary software could still be built upon them but many went down the open source path. Of course this led to the proliferation of tools but now one had a choice even if in the end a proprietary product ended up being use. Open standards also incentivized corporations to get involved as more and more customers started to trust the new process of laying down the foundations of a new technology in the open.

  * **Qualified labor**

    Proprietary software usually has one setup for each use case (because many times they are tied to a specific proprietary hardware) that makes life easier but this ease comes with the aforementioned costs. Vendors usually sell trainings and certifications for individuals and/or they provide support services to help operations. Such specialization comes with high prices and limits the mobility of the workforce (i.e., seek opportunitites only at companies with the same equipment or setup).

    The learning curve of open source is steeper but becoming versed in its ways may yield many advantages:

      * Individuals get a reusable set of skills and a more holistic view of how principles from multiple fields can be tied together.

        Specialization to proprietary systems is easier using this path because companies use their own obfuscated terminology based on marketing buzzwords whereas the underlying principles have their standard terminology rooted in (academic) research. Open standards used the latter as clarity is crucial in wide-spread adoption.

      * Organizations lay down a foundation for future flexibility and continuous improvement.

        Open source has a vibrant community based around popular and well documented programming languages and frameworks with their own support support networks sharing the same infrastructure (e.g., Github, Stackoverflow, Slack). Switches between *technology stacks* are common and seamless because the underlying tools are the same and/or based on similar principles.

        Adopted tools can also be further specialized/improved and these modifications can be contributed back to the larger community.

      * Wide-spread availability promotes easy entry for anyone interested

      * Most people working on open source projects are characterized mostly by enthusiasm[@https://ocw.mit.edu/courses/sloan-school-of-management/15-352-managing-innovation-emerging-trends-spring-2005/readings/lakhaniwolf.pdf]

  * **Security**

    Proponents of open source believe in [Linus' Law](https://en.wikipedia.org/wiki/Linus%27s_Law)[@bazaar]: open source project are more widely available to the publicand more eyes mean higher chances to discover a (security) bug.

   Although this statement has not been proved by any major research and it relies on questionable assumptions.[@http://www.zdnet.com/article/six-open-source-security-myths-debunked-and-eight-real-challenges-to-consider/] The most widely publicized open source vulnerability was the OpenSSL Heartbleed bug[@http://heartbleed.com/] but the causes leading up to it are more complex than a simple oversight.[^footnote-heartbleed]. Security issues tend to be disclosed almost as soon as they are discovered though, as opposed to proprietary bugs.

[^footnote-heartbleed]: The report titled "Roads and Bridges: The Unseen Labor Behind Our Digital Infrastructure"[@roads-and-bridges] written by Nadia Eghbal for the [Ford Foundation](http://www.fordfoundation.org)[^footnote-cc_license] gives an extensive treatment of the issue and open source infrastructure in general. (See chapters "Introduction" and "The hidden costs of ignoring infrastructure".)

    Opponents argue that "proprietary programs whose code is closed cannot be as easily inspected by malicious hackers who are looking for security holes to exploit"[@http://thevarguy.com/open-source-application-software-companies/reasons-organizations-opt-not-use-open-source-software].

    Proprietary software is most often tied to business interests and therefore withhold disclosure for certain period of time or entirely until revealed by a leak. Examples include the Equifax breach[@https://www.wired.com/story/equifax-breach-no-excuse/], Yahoo breach[@https://techcrunch.com/2017/10/03/yahoo-says-all-3b-accounts-were-impacted-by-2013-breach-not-1b-as-thought/] or a Microsoft breach that remained undisclosed since 2013[@https://ca.reuters.com/article/technologyNews/idCAKBN1CM0D0-OCATC]. The exploits could have been easily prevented because the open source projects, that the proprietary solutions were building upon, had their security holes already fixed but these patches haven't been applied due to neglect.[@https://jaxenter.com/think-open-source-software-free-think-131436.html] Aside from business misconducts, the "United States National Institute of Standards and Technology (NIST) specifically recommends against using closed source as a way to secure the software (i.e. “security through obscurity”)"[@https://www.efrontlearning.com/blog/2012/04/open-source-and-the-security-through-obscurity-fallacy.html], and they state, “system security should not depend on the secrecy of the implementation or its components” [@https://csrc.nist.gov/publications/detail/sp/800-123/final].

    A recent (10/16/2017) flaw in the WPA2 protocol[@https://www.krackattacks.com/] (a protocol that secures all modern protected Wi-Fi networks) proves that security bugs sometimes stem from accepted industry standards therefore any correct implementation would be affected, regardless of being an open source or a proprietary product.

  * **Compliance requirements**

    Software compliance means to keep track of all the copyright notices and licenses, and oblige to their requirements. Compliance tracking is also important to document the software supply chain (e.g. to be able to produce a Bill of Materials on request) and to respond quickly to a newly disclosed security vulnerability (i.e., to know which parts are affected, if any).

    From a software development standpoint, large corporations have advantage as they usually own all of the source code. Even if they incorporate open source projects in their closed source product(s), they have the legal apparatus to tip the scale to their favour should it come to a legal dispute over license ambiguities. Therefore in the case of proprietary software, the burden of compliance falls to the users, especially if the products are going to be used in a commercial setting.

    With open source software the users are the clear winners because they have complete freedom on how to use the products and they only have to satisfy license obligations if they are planning on commercial re-distribution of the (modified) works or if they would like to create a proprietary product from open source projects.[^footnote-proprietary_opensource]

[^footnote-proprietary_opensource]: Although if they steer clear of strong copylefted code than their situation becomes magnitudes easier.

    Building on open source code on the other becomes more complex as each included project may have different (or even multiple) licenses. Fortunately, this requirement has become more and more a standardized and automated process with the lead of large open source non-profits such as the Linux Foundation or the Open Source Initiative.[@https://www.linuxfoundation.org/blog/why-companies-that-use-open-source-need-a-compliance-program/] One example is the Software Composition Analysis methodology[@https://blog.blackducksoftware.com/software-composition-analysis-compatible-agile-devops].

### 2.3.5 Commercial applicability
#### controversies

#### 2.3.5.1 Commercial versus proprietary software

It is worth emphasizing:

>“Commercial” and “proprietary” are not the same! Commercial software is software developed by a business as part of its business. Most commercial software is proprietary, but there is commercial free software, and there is noncommercial nonfree software.
>
>For example, GNU Ada[^footnote-ada_link] is developed by a company. It is always distributed under the terms of the GNU GPL, and every copy is free software; but its developers sell support contracts. When their salesmen speak to prospective customers, sometimes the customers say, “We would feel safer with a commercial compiler.” The salesmen reply, “GNU Ada is a commercial compiler; it happens to be free software.”[@GNU's "Categories of free and nonfree software"  https://www.gnu.org/philosophy/categories.en.html#commercialSoftware]

[^footnote-ada_link]: https://en.wikipedia.org/wiki/GNAT

#### 2.3.5.2 Free/open source software versus commercial software

Commercial software is not the antonym of free and open source software, proprietary software is. Misunderstandings stem from conflicting uses of the adjectives *commercial* and *proprietary*.[@http://peerproduction.net/issues/issue-1/peer-reviewed-papers/why-free-software-is-not-the-antonym-of-commercial-software/]

Software licensed under an open source (or even under a more strict free software) license can be sold for a price or licensed for a fee just like any other product.[@https://blog.codecentric.de/en/2012/05/using-gpl-licensed-components-in-proprietary-projects/,@https://www.gnu.org/licenses/gpl-faq#DoesTheGPLAllowMoney,]

#### 2.3.5.3 Business models for open source software

##### 2.3.5.2.3 Controversies

It can be especially hard if one would like to choose an open source license for a commercial project as some of them are historically abused for unethical business practices[@http://www.dr-chuck.com/csev-blog/2014/09/how-to-achieve-vendor-lock-in-with-a-legit-open-source-license-affero-gpl/;@http://www.davewentzel.com/content/open-source-licensing] and some have pejorative connotations associated with them by negative campaigns at the time when open source practices where perceived as a threat by corporations (e.g., adjectives "viral" and "infectious" used for copyleft licenses[@https://en.wikipedia.org/wiki/Viral_license]).

A.1 Comparison of CRM implementation approaches
-----------------------------------------------

A.2 Arguments against using Salesforce
--------------------------------------

A.3 Microservices
---------------------------

\newpage
References
==========

