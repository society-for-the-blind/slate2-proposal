TODO: add licenses to bibliography (addendum or note in biblatex?)
\newpage
Executive Summary
====================

[Main goal](#maingoal)
--------------------------

Develop a constituent relationship and service program management system that is tailored to fit the needs of blindness organizations.

[Activity plan](#activity)
------------------------------

**Activities/Tasks**                                    **Responsibility**       **Start**      **End**
------------------------------------------------------- ---------------------- -----------   ----------
0 [Build local development environment](#env510)        Attila Gulyas          11/1/2017     12/15/2017
1 [Plan agency-wide schema](#plan511)                   Attila Gulyas          11/1/2017     2/15/2018
2 [Develop subsystem for educational](#dev512)          Attila Gulyas          11/1/2017     6/15/2018
  [services departments](#dev512)
3 [Prepare to move to the Cloud](#prep513)              Attila Gulyas          12/15/2017    2/1/2019
4 [Focus on Resource Development](#resdev514)           Attila Gulyas           6/15/2018    12/15/2018
5 Retail services                                       Attila Gulyas           2019
6 Low Vision clinic                                     Attila Gulyas           2019

[Budget](#bdgt)
---------------------

**Activity**                                               **From**    **From**    **Cost**
------------------------------------------------------- ----------- ----------- -----------
**3 [Prepare to move to the Cloud](#prep513)**          12/15/2017     2/1/2019
\
3.1 [Replicate local development](#local5131)           12/15/2017     3/1/2018  [$40.04](https://cloud.google.com/products/calculator/#id=3a39d0d1-67c0-467e-82c0-ff1b48545b88)
    [environment in the Cloud](#local5131)
3.2 [Experiment with collaboration between](#exp5133)    3/1/2018      4/15/2018 [$35.42](https://cloud.google.com/products/calculator/#id=c77898a4-c560-4639-91ed-dc4d63696d4d)
    [local and remote subsystems](#exp5133)
3.3 [Deploy stable educational](#dummy5132)              4/15/2018     9/20/2018 [$519.93](https://cloud.google.com/products/calculator/#id=92c04925-6eb6-4373-9399-1c38050ad23f)
    [subsystems for testing](#dummy5132)
3.4 [Put data-processing subsystems into](#proc5134)     6/15/2018     10/1/2018 [$35.97](https://cloud.google.com/products/calculator/#id=92c04925-6eb6-4373-9399-1c38050ad23f)[^footnote-price]
    [production](#proc5134)
\
**Total**                                                                        **$631.36**
\
**Ongoing costs at full capability**                     10/1/2018               **[$3117.06](https://cloud.google.com/products/calculator/#id=3c01e636-6ae5-4585-8ae7-cd41e33bec7d)**
(see [_Notes_](#budgetnotes))
-------------------------------------------------------------------------------

[Long-term vision](#vision)
-------------------------------

Put Society for the Blind on the information technology map as a hub for knowledge exchange that nurtures the local tech community without any barriers and bias.

[Reporting](#report)
------------------------

Weekly reports on current progress, challenges and amount of time spent on specific activity or task.

1. Terminology
==============

**subsystem**
: The _constituent relationship and service program management system_ proposed in this paper is a collection of subsystems collaborating with each other to provide services for organizational programs and departments. Each subsystem is a software with a specific purpose that contributes to the overall functionality of the system. An example would be a subsystem for volunteer management.

---

**commercial software**
: "A program is commercial if it is developed as a business activity. A commercial program can be free or nonfree, depending on its manner of distribution. Likewise, a program developed by a school or an individual can be free or nonfree, depending on its manner of distribution. The two questions—what sort of entity developed the program and what freedom its users have—are independent."[@gnu-words]

---

**proprietary software**
: A usually commercial software[^footnote-noncommercial-proprietary] with a closed source code (i.e., made unavailable for the users). Proprietary licenses are most often associated with proprietary programs that further restrict user interaction, such as the prohibition to distribute or use outside the prescribed scope (e.g., install on multiple computers, lend it to a friend etc.).

[^footnote-noncommercial-proprietary]: Most commercial software is proprietary, but is noncommercial nonfree software.[@https://www.gnu.org/philosophy/categories.en.html] [Winamp](https://en.wikipedia.org/wiki/Winamp), the popular audio player on Windows, is one example.

  Free software proponents also refer to these as *nonfree* software[@gnu-words].

\newpage
2 Context
=========

2.1 Disambiguation of database-related concepts and terms
---------------------------------------------------------

An agency-wide timesheet, represented as Microsoft Excel spreadsheet, will be used as an example to demonstrate database-related concepts.

\scriptsize
_Caveat_: Microsoft Excel is only a spreadsheet application (i.e., record-keeping software) not a DBMS but its functionality bears close resemblance to the way database-management systems structure their data to draw parallels between them.[^footnote-why_excel_is_not_a_dbms]
\normalsize

[^footnote-why_excel_is_not_a_dbms]: It would be possible to use Microsoft Excel as a DBMS but because neither integrity nor consistency is enforced on data and their relations, these would have to be maintained manually, defeating the purpose of database-management systems.

------------------------------------------------------------------------

**database**[@wiki-database]
: A database is an organized collection of data.

------------------------------------------------------------------------

For example, a spreadsheet with multiple tabs for each filled out timesheet belonging to an employee for a specific month.

The word "database" is mostly used as a shorthand for "database-management system" or "database schema" though and sometimes even incorrectly for software that employs a database-management system to store application data in one or more databases.

------------------------------------------------------------------------

**database-management system (DBMS)**[@wiki-database;@techtarget-database]
:   A database management system (DBMS) is software for creating and managing databases. The DBMS provides users and programmers with a systematic way to create, retrieve, update, manage and analyze data.

    \scriptsize Figure 1. The role of a DBMS in a generic application from data to end users \normalsize

    ```
    --------------       -------------     -----------------
    | database 1 |------>|           |     |               |<-----> user 1
    --------------       |           |     |               |          :
          :              |   DBMS    |<--->|  Application  |          :
    --------------       |           |     |               |          :
    | database N |------>|           |     |               |<-----> user N
    --------------       -------------     -----------------
    ```

------------------------------------------------------------------------

For example, Excel can open and allow manipulation of multiple monthly timesheet spreadsheets.

------------------------------------------------------------------------

**data model**[@wiki-data-model]
:   A data model explicitly determines the structure of data. The term is used in two distinct but closely related senses:

    [_definition A_] Abstract model of the problem domain that describes how data elements are related to one another and to properties of the real world entities in a particular application domain.

    [_definition B_] A set of rules prescribing data structure and the relationships between data elements. This specification can be then implemented by effectively hard-coding these rules into a specific database-management system.

------------------------------------------------------------------------

The most common example for _definition A_ is a manufacturing company that has customers, products, orders etc. and the data model describes their relations with specific constraints. In the case of an agency-wide timesheet, the model needs to specify a date period, a department, an employee and so on. One of the constraints would be the fact that a timesheet is for a single individual for one specific time period.

An example for _definition B_ is how Excel's data model is based on tables of data organized strictly in rows and columns in fixed length and width spreadsheets.

------------------------------------------------------------------------

**database schema**[@schema]
: The database schema is like a blueprint that describes the layout of the data contained in the database: what kinds of fields are present and how they are organized. Compared to the abstract concept of data models, a schema is a concrete file whose format depends on the used database-management system.

------------------------------------------------------------------------

The database schema is very similar to an Excel template. For example, the timesheet template has to adhere to Excel's data model (i.e., has to stick with rows and columns) and it expects a specific type of data at certain places (e.g., duration of time at "Daily totals").

To come a full circle: once a timesheet has been filled out and stored by HR based on their rules, it becomes the database.

2.2 Introduction to CRMs
-----------------------

**CRM** may refer to one of the following definitions that are usually used interchangeably:

  1. _One approach to capture and to manage an organization's interactions and relationships with and among entities._

The broadness of the definition is deliberate (and so is leaving the acronym unexpanded) because making it specific depends on the context (i.e., organization type it is used in connection with). Sections [2.2.1](#customer-rms) and [2.2.2](#constituent-rms) elaborate further on this topic.

  2. _Application software[^footnote-application_software_definition] that provides an interface to capture, process and analyze interaction data according to the requirements in the business domain.

The definition intentionally uses the phrase "application software" instead of the word "database" commonly (and incorrectly) used in  literature describing CRMs. This distinction is important because a CRM, as an application software, consists of a **persistence layer** and a **(graphical) user interface**.

[^footnote-application_software_definition]: **Application software**[@tth]: A program or group of programs that is designed for the end user. (...) Application software cannot run on itself but is dependent on system software to execute.

  * The **persistence layer**'s role is simply to store captured data. It is usually a database-management system but persistence can be achieved by other means as well[^footnote-persistence_example].

[^footnote-persistence_example]: For example, data can be stored in discrete files in the file system or in memory during the execution of a program.

  * A **(graphical) user interface** is optimized to provide an efficient workflow and hides the minutae of how data is stored by the persistence layer. It is mostly an implicit contract between the user and the application: the users expect their input to be saved and that it can be recalled at a later time.

    \scriptsize Figure 2. A simplified graphical representation of CRMs \normalsize

    ```
    ---  ==============================================
         |                                            |
     C   |  user interface                          <-----> users
         |                                            |
     R   |--------------------------------------------|
         |                                            |
     M   |  persistence layer (DBMS, files etc.)      |
         |                                            |
    ---  ==============================================
    ```

### 2.2.1 Customer Relationship Management Systems {#customer-rms}

Mostly used by commercial organizations to preserve "_information about the interactions between a customer and a business_" [@sh-crm] with a usually one-dimensional goal to maximize profits [@wiki-crm].

### 2.2.2 Constituent (Relationship) Management Systems {#constituent-rms}

Non-profit organizations require a different approach to capture relationships. Even though they may have clients who receive services in some form, the word **customer** does not naturally apply to them. Its meaning is also too narrow to refer to other entities (i.e., individual, agency etc.) connected to non-profits.

The umbrella term **constituent** better encompasses all the different types of entities. A constituent is therefore someone who takes part in the life of the organization, sometimes taking on multiple roles during the same timeframe. Complexity is further exacerbated by the fact that each role has its own set of interactions and organizational requirements. Examples for constituent roles are that of a client, a volunteer or a donor.

The two most common approaches to constituent management[@techsoup;@idealware] by a non-profit are:

* either using a collection of **specialist CRMs**, each of them developed for a specific purpose, such as

    + volunteer management systems (e.g., Volunteer Reporter, Samaritan)
    + donor management systems (e.g., Raiser's Edge, Talisma)
    + case and/or client management systems (e.g., Slate, ClientTrack)

* or rolling out a single **generalist CRM** application that tries to satisfy all needs but usually only to a certain extent (e.g., CiviCRM, Salesforce)

\newpage
2.3 Free (libre) and open source software (FLOSS)
---------------------------------

### 2.3.1 Brief history

#### 1970s

Computers are built from scratch by research organizations and custom software has to be written to operate them. "Software was not yet standardized and was not considered to be a monetizable product."[@roads-and-bridges]

#### 1981[@roads-and-bridges]

IBM introduces the "IBM PC" or "Personal Computer". Industry adoption is high winnowing out the competition and capturing half of the market share by 1986.[@23inroadsandbridges]

Standardized hardware brought along the opportunity to standardize software. IBM hires Microsoft to write the operating system for their PC and they deliver MS-DOS in the same year. Other companies follow suit.

Turning software into business proved lucrative, resulting in commercial licenses promoting the creation of proprietary products, preventing users from copying, modifying or redistributing software.

#### 1983

Concern rises among computer scientists "about the closed and proprietary direction that software was taking".[@roads-and-bridges] As a response, Richard Stallman launches GNU, a free operating system, also inadvertently laying the foundation for the "free software movement".[@https://www.gnu.org/gnu/initial-announcement.html]

#### 1985

Stallman founds the Free Software Foundation to support the objectives of the "free software movement".[@https://www.gnu.org/gnu/manifesto.html]

#### 1992

The growth of the World Wide Web gains momentum and becomes more widely available.

#### 1996

The commercialization of the web begins to take advantage of the new medium with great success and huge gains.

#### 1998

In a move unprecented at the time from a software company, Netscape releases the source code of its high market-share web browser. This event becomes the catalyst to a group of technologists, who have been advocating a more pragmatic approach to the Free Software Foundation's principles, to create the Open Source Initiative. The new organization's focus was to promulgate "the practical benefits of free software"[@roads-and-bridges] without "the ideological and confrontational connotations of the term"[@https://en.wikipedia.org/wiki/Open-source_software_movement]

### 2.3.2 Open source versus free software

#### 2.3.2.1 Common ground

Both **free[^footnote-word_free] software** and **open source software** do roughly mean the same: "_users have the freedom to run, copy, distribute, study, change and improve the software_"[@https://www.gnu.org/philosophy/free-sw.en.html][^footnote-compare_os].

[^footnote-word_free]: "_Many languages have two separate words for “free” as in freedom and “free” as in zero price. For example, French has “libre” and “gratuit”. Not so English; there is a word “gratis” that refers unambiguously to price, but no common adjective that refers unambiguously to freedom._"[@https://www.gnu.org/philosophy/categories.en.html]

[^footnote-compare_os]: Compare with the summary from the Open Source Initiative's own summary: "_Generally, Open Source software is software that can be freely accessed, used, changed, and shared (in modified or unmodified form) by anyone. Open source software is made by many people, and distributed under licenses that comply with the [Open Source Definition](https://opensource.org/osd-annotated)._"[@https://opensource.org/faq#osd]

See [Glossary](#glossary) for their formal definitions.

#### 2.3.2.2 Differences

"_Open source is a development methodology; free software is a social movement._"[@https://www.gnu.org/philosophy/open-source-misses-the-point.en.html] Although often discussed together, they are politically distinct: "free software" being more closely associated with ethics ("_essential respect for the users' freedom"[@https://www.gnu.org/philosophy/open-source-misses-the-point.en.html]) and "open source" with pragmatism (i.e., a practical, business-case approach to free software[@https://opensource.org/history]).

On the practical side, every existing free software would qualify as open source but not vice versa. Exceptions include the following:

  * Open source licenses are more permissive (or restrictive, depending on the perspective).

    For example, some licences that do not allow modification of program  are still deemed as valid open source licenses by the Open Source Initiative whereas these terms are unacceptable by the Free Software Foundation as they limit the users' freedom.

  * Difference between the groups' relationship between free and proprietary software.

    Members of the open source community are willing to coexist with the makers of proprietary software[@https://en.wikipedia.org/wiki/Open-source_software_movement,@https://opensource.org/faq#permissive] and feel that the issue of whether software is open source is a matter of practicality[@https://opensource.org/history]. One example is [tivoization](https://en.wikipedia.org/wiki/Tivoization).

    In contrast, members of the free software community maintain the vision that all software is a part of freedom of speech and that proprietary software is unethical and unjust[@https://www.gnu.org/philosophy/open-source-misses-the-point.en.html,@https://www.gnu.org/proprietary/proprietary.en.html,@https://www.gnu.org/proprietary/proprietary-surveillance.en.html,@https://www.gnu.org/proprietary/proprietary-back-doors.en.html].

### 2.3.3 Licenses[^footnote-which_license]

[^footnote-which_license]: Choosing a FLOSS license depends largely on the use case and can be controversial, see [@https://blog.p2pfoundation.net/why-apache-defeated-the-gpl-license-developer-freedom-vs-user-freedom/2013/01/21,@https://softwareengineering.stackexchange.com/questions/107883/agpl-what-you-can-do-and-what-you-cant,@https://news.ycombinator.com/item?id=1273231,@roads-and-bridges].

#### 2.3.3.1 Why are licenses necessary?[^footnote-osguide]

[^footnote-osguide]: Content based on [github.com/github/opensource.guide] used under the CC-BY-4.0 license.

An original creative work (such as writing, graphics, or code) is under exclusive copyright by default, meaning that by law only the author has a say in what others can do with it. Open source is an unusual circumstance, however, because the author expects that others will use, modify, and share the work. But because the legal default is still exclusive copyright, a license is needed to explicitly state these permissions.

Without a license, everybody who contributes to the project also becomes an exclusive copyright holder of their work. That means nobody can use, copy, distribute, or modify their contributions – and that “nobody” includes the author as well.

#### 2.3.3.2 Free software licenses

Free software tend to be licensed under [copyleft](#glossary) licenses[^footnote-copyleft] that basically allow the creation of derivative works but require them to use the same license as the original work.[@https://opensource.org/faq#copyleft] For software, the added stipulation is that the original/derivative program's source code also has to be made available to recipients to prevent the creation of proprietary products[@https://www.gnu.org/copyleft/copyleft.html].

[^footnote-copyleft]: Also referred to as *reciprocal* or *protective* licenses.

The most prominent example are the versions of the GNU General Public License[^footnote-gpl_v3].

[^footnote-gpl_v3]: The latest version is the [GNU General Public License v3.0](https://www.gnu.org/licenses/gpl-3.0.en.html) and [an extensive legal analysis is also available by the Software Freedom Law Center](https://www.softwarefreedom.org/resources/2014/SFLC-Guide_to_GPL_Compliance_2d_ed.html).

#### 2.3.3.2 Open source licenses

Open source licenses are licenses that comply with the [Open Source Definition](https://opensource.org/osd) (i.e., they allow software to be freely used, modified, and shared), including non-copyleft[^footnote-noncopyleft] (or "permissive") licenses that allow proprietary derivative works[@https://opensource.org/faq#permissive].

[^footnote-noncopyleft]: As the defintion of open source software is an extension of [the four essential freedoms of the Free Software Definition](https://www.gnu.org/philosophy/free-sw.html), all copyleft licenses are also open source licenses.

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

### 2.3.5 Commercialization of open source software

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

3 Project rationale
===================

3.1 Problem statement
---------------------

### 3.1.1 Organizational difficulties

As constituents can have more than one role and may be affiliated with multiple services, their data is oftentimes managed individually by each department. For example, Joe can be a SIP client and SIP volunteer but he may be also volunteering for Access News and sometimes donating a small amount.

This decentralization of information sources simplifies management for programs and services by only dealing with client data that pertains to them, using their own specialized and mostly proprietary software. For example, SIP and CORE maintains client information in Slate, the Low Vision Clinic uses EyeCare.

Departments on the other hand, that need to see the big picture (such as Resource Development, Billing, HR), draw the short straw because data will need to be aggregated manually and consolidated into their own proprietary software (e.g., Raiser's Edge, Quickbooks) if automation is missing or difficult to implement (if not impossible). Software at Society for the Blind do not communicate directly with each other because they are native Windows applications[^footnote-native_apps]. Many of these vendors are starting to move to the Cloud, sharing the largest common platform (the World Wide Web) and technologies (web standards such as HTML, CSS, Javascript) but instead of embracing open standards to enable interoperation and collaboration, many of them just keep continuing bad practices.[@dzone-cloud;@iw-cloud]

[^footnote-native_apps]: With Slate being one exception but it can be viewed as a native application because it is not maintained anymore and its closed source.

### 3.1.2 Insufficient flexibility and accessibility support of major CRMs

Approaches to adopting CRMs (generalist versus specialist) for a traditional organization are well documented, including best practices and their pros and cons[^footnote-annexes].[@sh-crm;@wiki-crm;@techsoup;@idealware;@heller-crm]

[^footnote-annexes]: See [Annexes] A.1 for a comparison summary.

Although when it comes to blindness organizations, they are found lacking:

  1. **Accessibility is addressed as an afterthought.**

     A fierce market dictates that a software should satisfy the needs and expectations of the majority of the users (e.g., maximalize visual pleasure, optimize for mouse usage). These properties and accessibility are not mutually exclusive but cutting corners yield faster and easier results[^footnote-web_cut_corner]. An analogy would be building a house solely by how it should look with disregard to safety standards: it can be done with toothpicks, paper mache and so on but it wouldn't be safe or useful for everyone.

[^footnote-web_cut_corner]: One example of such shortcut is ignoring the semantic purpose of HTML elements, defined by web standards, by purposely misusing or abusing them to achieve a desired visual effect.

  2.  **They don't necessarily cater to the needs of non-profits.**

      Even solutions touted to be specifically for non-profits tend to be overly rigid as vendors are trying to attract as large an audiance as possible, requiring significant trade-offs[^footnote-tradeoffs].

      The best example is managing educational services. Most CRMs' can be used that way indirectly, by using their generic case management system. This would need to be modified (if possible) but in many cases the organization's only option is to conform to the tool, instead of the other way around.

     Products specifically for educational purposes are either one or more of the following:

      * expensive (with hidden costs) (e.g., [Salesforce Higher Ed](https://www.salesforce.com/solutions/industries/higher-ed/overview/))

      * suitable only for traditional services, such as K-12 or higher education (e.g., [Salesforce Higher Ed](https://www.salesforce.com/solutions/industries/higher-ed/overview/), [Affirma Educational Service Dynamics](http://www.affirmaconsulting.com/work/crm/educational-service-dynamics-crm/), [Ellucian](http://www.ellucian.com/),[CiviSchool](https://wiki.civicrm.org/confluence/display/CRMDOC/CiviSchool))

      * has poor documentation and/or defunct (e.g., [CiviSchool](https://wiki.civicrm.org/confluence/display/CRMDOC/CiviSchool))

      * is too narrow in scope (e.g., [Intellum](https://www.intellum.com), [Canvas LMS](https://www.canvaslms.com/), [Blackboard](http://www.blackboard.com/))

      * provides one (non-modifiable) uniform scheme to track student/client progress and course/services properties (see examples above)

      The corollary of the last item is that an organization with multiple schemes either needs to change its internal processes (and retroactively update their records) or needs to adopt two or more specialist software that may have compatibility issues. Society for the Blind's CORE and SIP departments are the perfect example: they provide very similar services but their finances and the way they operate are fundamentally different.

[^footnote-tradeoffs]: Such as making the software proprietary. On the other hand, making the source code available is in itself no guarantee either. For example, if the application is written in a way that would require the vendors's exact infrastructure specifications to run, requiring such extensive re-writes that would amount to creating solution from scratch.

3.2 Proposed approach
---------------------

To solve the aforementioned issues, to maximize its usefulness to the community and to promote easier collaboration, the end product should be:

  * **free software** (therefore **open source**)

  * **web-based**

  * implemented according to the **Agile software development principles**

  * based on the **Microservice Architecture**

  * using the **Event Sourcing** architectural model

TODO: expand on each item
<!--- TODO
### 3.2.1 Open source
 collaboration and usefulness

### 3.2.4 Web-based application
 for cross-platform compatibility and higher availability

### 3.2.3 Agile software development principles
 for maximum flexibility

### 3.2.2 Microservice Architecture
 to solve above issues, easy to (re)configure and set up and because components can be replaced other organizations may only adopt portions of it with their custom solutions.-> that is where we come in (open sourcehoz is tartozik ez)

### 3.2.5 Event Sourcing
 for persistence (know the state that can be recreate from the series of events even if the main state db is discarded, see fowler)
-->

\newpage
4. Project aims
===============

4.1 Main goal {#maingoal}
-------------

Develop a constituent relationship and service program management system that is

  * tailored to fit the needs of blindness organizations

    \scriptsize Lowering the bar for easy adoption as much as possible. \normalsize

  * easily configurable by end users

    \scriptsize No technological background knowledge or programming expertise needed to set up. \normalsize

  * extensible with new functionality without disruptions

    \scriptsize For example adding a new department or deciding to add an agency-wide notification system for clients. \normalsize

  * robust <!--- TODO add citation -->

    \scriptsize A system that is running for a long time without the need of any user intervention and is able to cope with errors and erroneous input automatically. \normalsize

  * technology-agnostic <!--- TODO add citation -->

    \scriptsize That is, functionality is independent of the choices in technology used, making it easy to swap them out without the end user noticing the change. \normalsize

4.2 Objectives
--------------

  Develop a web-based agency-wide management system

  a. with subsystem[^footnote-subsystem] for educational services departments (SIP, CORE)

  b. and, depending on assessments, integrate existing solutions or create new subsystems for

     * Resource Development

     * Retail Services

     * Low Vision Clinic

[^footnote-subsystem]: Subsystem is equivalent to a web service in the context of this proposal but the former is used to emphasize the hierarchical relationships between the objectives below.

\newpage
5. Project implementation
=========================

5.1 Activitiy plan {#activity}
------------------

<!--- Extra newlines (i.e., backslashes below) are for PDF niceness but
      completely unnecessary for word so use the vim command below to
      remove it:
      :g/^\\$/d
-->
Table: Activity plan

**Activity/Task**                                       **Responsibility**       **Start**        **End**
------------------------------------------------------- ---------------------- -----------   ------------
**0 [Build local development environment](#env510)**    Attila Gulyas          11/1/2017     12/15/2017
                                                        GNT Solutions
.............................................
**1 [Plan agency-wide schema](#plan511)**               Attila Gulyas           11/1/2017     2/15/2018
                                                        Staff
\
1.1 [Collect information about services](#collect5111)
    [and departmental processes](#collect5111)
1.2 [Evaluate workflows](#eval5112)
1.3 [Identify service boundaries](#id5113)
.............................................
**2 [Develop subsystem for educational](#dev512)**      Attila Gulyas          11/1/2017     6/15/2018
  **[services departments](#dev512)**
\
2.1 [Cater for functionality common](#dev512)           Attila Gulyas          11/1/2017     4/15/2018
    [for both CORE and SIP](#cater5121)
2.2 [Implement CORE-specific features](#imp5122)        Attila Gulyas          11/1/2017     6/15/2018
                                                        Aser Tolentino
2.3 [Implement SIP-specific features](#imp5123)         Attila Gulyas           2/15/2018     6/15/2018
.............................................
**3 [Prepare to move to the Cloud](#prep513)**          Attila Gulyas          12/15/2017     2/1/2019
\
3.1 [Replicate local development](#local5131)           Attila Gulyas          12/15/2017     3/1/2018
    [environment in the Cloud](#local5131)
3.2 [Experiment with collaboration between](#exp5133)   Attila Gulyas           3/1/2018      4/15/2018
    [local and remote subsystems](#exp5133)
3.3 [Deploy stable educational](#dummy5132)             Attila Gulyas           4/15/2018     9/20/2018
    [subsystems for testing](#dummy5132)
3.4 [Put data-processing subsystems into](#proc5134)    Attila Gulyas           6/15/2018     10/1/2018
    [production](#proc5134)
3.5 [Finish moving educational services](#fin5135)      Attila Gulyas          10/1/2018      2/1/2019
    [and assess results](#fin5135)
.............................................
**4 [Focus on Resource Development](#resdev514)**       Attila Gulyas           6/15/2018    12/15/2018
\
4.1 [Develop subsystem to consolidate](#vol5141)        Attila Gulyas           6/15/2018     8/15/2018
    [volunteer management](#vol5141)
4.2 [Assess departmental needs and](#assess5142)        Attila Gulyas           6/15/2018    10/31/2018
    [current tools](#assess5142)                        Lina Lloyd \
                                                        Liz Culp
4.3 [Create subsystem to replace or](#don5143)          Attila Gulyas           8/15/2018    12/15/2018
    [integrate current solutions for](#don5143)
    [donor and campaign management](#don5143)
.............................................
**5 Retail services**                                   Attila Gulyas           2019
.............................................
**6 Low Vision clinic**                                 Attila Gulyas           2019

Notes:

  * Writing documentation and testing is not listed as an activity because it is intrinsic to the Agile methodology.

  * Most of the activities overlap because they are dependent on each other.

### 5.1.0 Build local development environment {#env510}

Utilize unused computers and servers to a local server or server farm to support following stages. Coordinate networking needs with GNT Solutions (DNS, bandwidth, firewall rules adjustments and cabling).

### 5.1.1 Plan agency-wide schema {#plan511}

Tasks for this activity are not dated because the entire process is inherently iterative[^footnote-no_task_dates].

[^footnote-no_task_dates]: That is, gather and evaluate data, form hypotheses, test and go back to a previous step if results do not add up.

#### 5.1.1.1 Collect information about services and departmental processes {#collect5111}

#### 5.1.1.2 Evaluate workflows {#eval5112}

Many of the current practices are the product of the limitations of the used software solutions and not the requirement of the specific domain.

Examples:

  * Volunteer times are aggregated manually from hard-copies at various places around the agency and from different programs/departments. (The sign-in sheets can also be a security issue because a malicious individual could collect the name of volunteers/visitors and the dates & times they were at the agency.)

  * Coordination of volunteer applications and trainings are coordinated via emails and personal conversation. The process works but it always holds the risk of information not getting to the relevant person, miscommunication and misunderstandings that are hard to catch. (In contrast, a central system were every participant is added and can be audited later would make these issues obvious.)

  * Volunteer applications are stored as hard copy files and look-up is manual from filing cabinets. Same applies to DOR authorizations with an informal digital methodology in place with the steps of scanning, OCR[^footnote-ocr], naming results and moving to a folder.

    DOR authorizations are sometimes submitted by counselors by mail that could be just submitted through and agency portal taking care of logging it and doing OCR.

  * Scheduling classes at CORE is done manually instead of only specifying certain metrics and let the work done by a scheduling subsystem.

  * CORE students usually call the absence line when they are going to be absent and checking the voicemails is one extra step each day

  * SIP's monthly, quarterly and yearly reports are all done by hand even though the data exists in Slate but reporting has never been implemented and extracting data is excruciatingly painful.

  * Inventories are always done by hand and stored at various places. Comparison with the previous results is also done manually instead of just diffing the current and previous versions digitally. (See next item.)

  * Agency-wide information and documents internal to a department are kept in a central file repository. Finding and updating information is cumbersome, because of the need to remember file system paths, and error-prone, because of proliferation of duplicated documents when the original is not found. (One solution would be a global knowledge base that everyone can edit with assigned maintainers whose role would be to keep it up-to-date and consistent. This would help the executive assistant tremendously but would also be helpful with random calls around the agency.)

[^footnote-ocr]: Optical Character Recognition

All these can be automated and only expose parts of the workflows that are significant to end users.


#### 5.1.1.3 Identify service boundaries {#id5113}

In order to create a collaborative ecosystem of subsystems service boundaries need to be identified and their interactions explicitly enumerated.

### 5.1.2 Develop subsystem for educational services departments {#dev512}

#### 5.1.2.1 Cater for functionality common for both CORE and SIP {#cater5121}

  * handle and log initial contact (a.k.a. inquiry or referral)

  * scheduling

  * note taking system with easy consolidation

  * billing

  * flexible reporting

#### 5.1.2.2 Implement CORE-specific features {#imp5122}

#### 5.1.2.3 Implement SIP-specific features {#imp5123}

### 5.1.3 Prepare to move to the Cloud {#prep513}

#### 5.1.3.1 Replicate local development environment in the Cloud {#local5131}

#### 5.1.3.2 Experiment with collaboration between local and remote subsystems {#exp5133}

#### 5.1.3.3 Deploy stable subsystems for testing {#dummy5132}

#### 5.1.3.4 Put data-processing subsystems into production {#proc5134}

#### 5.1.3.5 Finish moving services and assess results {#fin5135}

### 5.1.4 Focus on Resource Development {#resdev514}

#### 5.1.4.1 Develop subsystem to consolidate volunteer management {#vol5141}

#### 5.1.4.2 Assess departmental needs and current tools {#assess5142}

#### 5.1.4.3 Create subsystem to replace or integrate current solutions for donor and campaign management {#don5143}

5.2 Budget {#bdgt}
----------

Table: Budget

**Activity**                                               **From**    **From**    **Cost**
------------------------------------------------------- ----------- ----------- -----------
**3 [Prepare to move to the Cloud](#prep513)**          12/15/2017     2/1/2019
\
3.1 [Replicate local development](#local5131)           12/15/2017     3/1/2018  [$40.04](https://cloud.google.com/products/calculator/#id=3a39d0d1-67c0-467e-82c0-ff1b48545b88)
    [environment in the Cloud](#local5131)
\
3.2 [Experiment with collaboration between](#exp5133)    3/1/2018      4/15/2018 [$35.42](https://cloud.google.com/products/calculator/#id=c77898a4-c560-4639-91ed-dc4d63696d4d)
    [local and remote subsystems](#exp5133)
\
3.3 [Deploy stable educational](#dummy5132)              4/15/2018     9/20/2018 [$519.93](https://cloud.google.com/products/calculator/#id=92c04925-6eb6-4373-9399-1c38050ad23f)
    [subsystems for testing](#dummy5132)
\
3.4 [Put data-processing subsystems into](#proc5134)     6/15/2018     10/1/2018 [$35.97](https://cloud.google.com/products/calculator/#id=92c04925-6eb6-4373-9399-1c38050ad23f)[^footnote-price]
    [production](#proc5134)
\
**Total**                                                                        **$631.36**
\
**Ongoing costs at full capability**                     10/1/2018               **[$3117.06](https://cloud.google.com/products/calculator/#id=3c01e636-6ae5-4585-8ae7-cd41e33bec7d)**
(see [_Notes_](#budgetnotes))

[^footnote-price]: Only adding the difference between task **3.3** and **3.4** which is 11 days at the same price a day as **3.3**.

### 5.2.1 Notes {#budgetnotes}

  * Prices are based on the Google Cloud platform (click on prices to see configuration details) and are highly dependent on duration of commitment (e.g., a 3 year commitment would mean a 57% price reduction)
Cost is an estimate of the "worst case scenario" if all the required virtual servers in the cloud would be started from day one.

  * _Ongoing costs at full capability_ estimate is based on "worst cost scenario" when **all** services (and not just the educational services department) are running at full steam

  * No research done yet for any possible discounts for non-profits

6. Long-term vision {#vision}
=============================

6.1 Inability to meet deadline(s)
---------------------------------

Activity and task deadlines are conservative estimates but they may prove to be too ambitious for the only two developers (i.e., the authors of this proposal).

### 6.1.2 Recommended mitigation strategy

Because of the open source nature of the project, anyone is able to contribute and therefore larger exposure would mean more collaborators.

Ways to promote project:

  * advertise undertaking in online developer communities (both technology-specific and -agnostic)

  * set a low bar for aspiring developers and technology enthusiasts

  * open for discussion even to people who are intrigued and just would like to know more

  * organize after hour meet-ups and/or study groups for interested parties, such as co-workers, SFTB, college or high school students, and so on

The **long-term vision** is to put Society for the Blind on the information technology map as a hub for knowledge exchange that nurtures the local tech community without any barriers and bias.

The agency probably wouldn't immediately benefit from these events directly they would also be helpful to attract attention. For example, each gathering could start with a short introduction of Society for the Blind and our mission. Many participants may move on quickly or never contribute to internal projects but there are always people who just need the opportunity or a slight nudge to start learning.

7. License
==========

licenses exist to unambiguously tell in what ways source code can be handled if it ever comes to a legal dispute but of course their language depends on the interpretations that wins in a legal case that will become the precedent (or not). With that said, the writers of this proposal feel strongly about using a more restrictive license towards user freedom therefore recommending a copyleft license (AGPLv3)

8. business strategy or Marketing?
============

9. Reporting {#report}
======================

Weekly reports on current progress, challenges and amount of time spent on specific activity or task.

10. Monitoring and evaluation
============================

Continuous accessibility evaluation by Aser Tolentino.

\newpage
Glossary
========

**Application software**[@tth]
: A program or group of programs that is designed for the end user. (...) Application software cannot run on itself but is dependent on system software to execute.

**copyleft**[@https://en.wikipedia.org/wiki/Copyleft]
:   A form of licensing to maintain copyright conditions for works but giving permission to recipients of the work to reproduce, change or distribute it, with the accompanying requirement that any resulting copies or adaptations are also bound by the same licensing agreement.

    Copyleft licenses for software require that information necessary for reproducing and modifying the work must be made available to recipients of the binaries. The source code files will usually contain a copy of the license terms and acknowledge the authors.

**CRM**[@sh-crm;@wiki-crm;@techsoup;@idealware]
:   May refer to one of the following definitions that are usually used interchangeably:

    [_methodology_] One approach to capture and to manage an organization's interactions and relationships with and among entities.

    [_computer science_] Application software[^footnote-application_software_definition] to persist, process and analyse captured interaction data.

    \scriptsize Figure 2. A simplified graphical representation of CRMs \normalsize

    ```
    ---  ==============================================
         |                                            |
     C   |  user interface                          <-----> users
         |                                            |
     R   |--------------------------------------------|
         |                                            |
     M   |  persistence layer (DBMS, files etc.)      |
         |                                            |
    ---  ==============================================
    ```

**database**[@wiki-database]
: A database is an organized collection of data.

**database-management system (DBMS)**[@wiki-database;@techtarget-database]
:   A database management system (DBMS) is software for creating and managing databases. The DBMS provides users and programmers with a systematic way to create, retrieve, update and manage data.

    \scriptsize Figure 1. The role of a DBMS in a generic application from data to end users \normalsize

    ```
    --------------       -------------     -----------------
    | database 1 |------>|           |     |               |<-----> user 1
    --------------       |           |     |               |          :
          :              |   DBMS    |<--->|  Application  |          :
    --------------       |           |     |               |          :
    | database N |------>|           |     |               |<-----> user N
    --------------       -------------     -----------------
    ```

**data model**[@wiki-data-model]
:   A data model explicitly determines the structure of data. The term is used in two distinct but closely related senses:

    [_definition A_] Abstract model of the problem domain that describes how data elements are related to one another and to properties of the real world entities in a particular application domain.

    [_definition B_] A set of rules prescribing data structure and the relationships between data elements. This specification can be then implemented by effectively hard-coding these rules into a specific database-management system.

**database schema**[@schema]
: The database schema is like a blueprint that describes the layout of the data contained in the database: what kinds of fields are present and how they are organized. Compared to the abstract concept of data models, a schema is a concrete file whose format depends on the used database-management system.

\newpage
Annexes
=======

A.1 Comparison of CRM implementation approaches
-----------------------------------------------

A.2 Arguments against using Salesforce
--------------------------------------

A.3 Microservices
---------------------------

\newpage
References
==========

