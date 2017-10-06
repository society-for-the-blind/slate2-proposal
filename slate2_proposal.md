\newpage
1 Executive Summary
====================

\newpage
2 Context
===========

2.1 Disambiguation of database-related concepts and terms
--------------------------------------------------------

An agency-wide timesheet, represented as Microsoft Excel spreadsheet, will be used as an example to demonstrate database-related concepts.

\scriptsize
_Caveat_: Microsoft Excel is only a spreadsheat application (i.e., record-keeping software) not a DBMS but its functionality bears close resemblance to the way database-management systems structure their data to draw parallels between them.[^footnote-why_excel_is_not_a_dbms]
\normalsize

[^footnote-why_excel_is_not_a_dbms]: It would be possible to use Microsoft Excel as a DBMS but because neither integrity nor consistency is enforced on data and their relations, these would have to be maintained manually, defeating the purpose of database-management systems.

------------------------------------------------------------------------

**database**[@wiki_database]
: A database is an organized collection of data.

------------------------------------------------------------------------

For example, a spreadsheet with multiple tabs for each filled out timesheet belonging to an employee for a specific month.

The word "database" is mostly used as a shorthand for "database-management system" or "database schema" though and sometimes even incorrectly for software that employs a database-management system to store application data in one or more databases.

------------------------------------------------------------------------

**database-management system (DBMS)**[@wiki_database;@techtarget_database]
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

**data model**[@wiki_data_model]
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

The broadness of the definition is deliberate (and so is leaving the acronym unexpanded) because making it specific depends on the context (i.e., organization type it is used in connection with). Sections [2.3](#customer-rms) and [2.4](#constituent-rms) elaborate further on this topic.

  2. _Application software[^footnote-application_software_definition] that provide an interface to capture, process and analyze interaction data according to the requirements in the business domain.

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

2.3 Customer Relationship Management Systems {#customer-rms}
-------------------------------------------

Mostly used by commercial organizations to preserve "_information about the interactions between a customer and a business_" [@sh_crm] with a usually the one-dimensional goal to maximize profits [@wiki_crm].

2.4 Constituent (Relationship) Management Systems {#constituent-rms}
------------------------------------------------

Non-profit organizations require a different approach to capture relationships. Even though they may have clients who receive services in some form, the word **customer** does not naturally apply to them. Its meaning is also too narrow to refer to other entities (i.e., individual, agency etc.) connected to non-profits.

The umbrella term **constituent** better encompasses all the different types of entities. A constituent is therefore someone who takes part in the life of the organization, sometimes taking on multiple roles during the same timeframe. Complexity is further exacerbated by the fact that each role has its own set of interactions and organizational requirements. Examples for constituent roles are that of a client, a volunteer or a donor.

The two most common approaches to constituent management[@techsoup;@idealware] by a non-profit are:

* either using a collection of **specialist CRMs**, each of them developed for a specific purpose, such as

    + volunteer management systems (e.g., Volunteer Reporter, Samaritan)
    + donor management systems (e.g., Raiser's Edge, Talisma)
    + case and/or client management systems (e.g., Slate, ClientTrack)

* or rolling out a single **generalist CRM** application that tries to satisfy all needs but usually only to a certain extent (e.g., CiviCRM, Salesforce)

3 Project rationale
======================

3.1 Problem statement
---------------------

Because constituents can have more than one role and may be affiliated with multiple services, their data is oftentimes managed individually by each department. For example, Joe can be a SIP client and SIP volunteer but he may be also volunteering for Access News and sometimes donating a small amount. This decentralization of information sources simplify management for programs and services by only dealing with client data that pertains to them, using their own specialized, proprietary software. Departments on the other hand that need to see the big picture (such as Resource Development, Billing, HR), will draw the short straw because data will need to be aggregated manually if automation is missing or difficult to implement (if not impossible) because of incompatible systems.

, instead of departments dedicated to a specific role[^functional_departments].

[^functional_departments]: The reason behind this practice is manyfold but it is usually caused by tight budgets and as a corollary, employees having multiple responsibilites that blurs the line further. On the bright side, this simplifies management of most departments by decentralizing the sources of information on various constituent groups. Departments, that need the big picture, draw the short straw: data will need to be aggregated manually if automation is missing or difficult (if not impossible). An example for the latter is when the data managed by systems that do not directly communicate each other and/or their proprietary nature does not enable reliable workarounds.


Each approach (generalist versus specialist) have their pros & cons and best practices (with necessary trade-offs) are available on how to adopt the best solution for traditional organizations. All of these are well-documented.[@sh_crm;@wiki_crm;@techsoup;@idealware;@heller_crm] See (Annex).

The fundamental issues with the existing products are:

  1. **Accessibility is mostly addressed as an afterthought**

     A fierce market dictates that a software should satisfy the needs and expectations of the majority of the users (e.g., maximalize visual pleasure, optimize for mouse usage). These properties and accessibility are not mutually exclusive but cutting corners yield faster and easier results[^footnote-web_cut_corner]. An analogy would be building a house solely by how it should look with disregard to safety standards: it can be done with toothpicks, paper mache and so on but it wouldn't be safe or useful for everyone.

[^footnote-web_cut_corner]: One example of such shortcut is ignoring the semantic purpose of HTML elements, defined by web standards, by purposely misusing or abusing them to achieve a desired visual effect.

  2.  **They don't necessarily cater to the needs of blindness organizations**

      The best example is managing educational services. Most solutions offer case management capabilities but these have to be modified (if at all possible). Products specifically for this purpose are either one or more of the following:

      * expensive (with hidden costs) (e.g., [Salesforce Higher Ed](https://www.salesforce.com/solutions/industries/higher-ed/overview/))

      * suitable only for traditional services (e.g., [Salesforce Higher Ed](https://www.salesforce.com/solutions/industries/higher-ed/overview/), [Affirma Educational Service Dynamics](http://www.affirmaconsulting.com/work/crm/educational-service-dynamics-crm/), [Ellucian](http://www.ellucian.com/),[CiviSchool](https://wiki.civicrm.org/confluence/display/CRMDOC/CiviSchool))

      * has poor documentation and/or defunct (e.g., [CiviSchool](https://wiki.civicrm.org/confluence/display/CRMDOC/CiviSchool))

      * is too narrow in scope (e.g., [Intellum](https://www.intellum.com), [Canvas LMS](https://www.canvaslms.com/), [Blackboar](http://www.blackboard.com/))

      * provides one (non-modifiable) uniform scheme to track student/client progress and course/services properties (see examples above)

      The corollary of the last item is that an organization with multiple schemes either needs to change its internal processes (and retroactively update their records) or needs to implement two or more specialist software that may have compatibility issues. Society for the Blind's CORE and SIP departments are the perfect example: they provide very similar services but their finances and the way they operate are fundamentally different.

3.2 Proposed solution
--------------------

address issue (1) - sound fundamental, es cask aztan a visual


specialist crm approach issues because of  functional_departments: everyone needs to use many different software (price, learning curve, differing levels of accessibility)

Glossary
========

**Application software**[@tth]
: A program or group of programs that is designed for the end user. (...) Application software cannot run on itself but is dependent on system software to execute.

**CRM**[@sh_crm;@wiki_crm;@techsoup;@idealware]
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

**database**[@wiki_database]
: A database is an organized collection of data.

**database-management system (DBMS)**[@wiki_database;@techtarget_database]
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

**data model**[@wiki_data_model]
:   A data model explicitly determines the structure of data. The term is used in two distinct but closely related senses:

    [_definition A_] Abstract model of the problem domain that describes how data elements are related to one another and to properties of the real world entities in a particular application domain.

    [_definition B_] A set of rules prescribing data structure and the relationships between data elements. This specification can be then implemented by effectively hard-coding these rules into a specific database-management system.

**database schema**[@schema]
: The database schema is like a blueprint that describes the layout of the data contained in the database: what kinds of fields are present and how they are organized. Compared to the abstract concept of data models, a schema is a concrete file whose format depends on the used database-management system.

Annexes
========

A.1 Specialist versus generalist approach to CRMs - Best practices and pros & cons
----------------------------------------------------------------------------------

A.2 Arguments against using Salesforce
--------------------------------------

References
==========
