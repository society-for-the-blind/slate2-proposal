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
3 Project rationale
===================

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

  1. **Accessibility is an afterthought.**

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
