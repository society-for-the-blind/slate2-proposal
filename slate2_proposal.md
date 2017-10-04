I. Executive Summary
====================

II. Context
===========

1. Disambiguation of database-related concepts and terms
--------------------------------------------------------

The word "database" is often used as a shorthand for "database system" or "database schema" or sometimes even incorrectly for software that employs a database system to store its data.

Microsoft Excel is going to be used below to demonstrate database-related concepts but it is only a spreadsheat (i.e., record-keeping software) and it is lacking data management features that automatically keep data and their relations consistent in full-fledged database-management systems.

**database**[@wiki_database]
: A database is an organized collection of data. For example, a filled out Excel timesheet.

**database-management system (DBMS)**[@wiki_database;@techtarget_database]
: A database management system (DBMS) is software for creating and managing databases. The DBMS provides users and programmers with a systematic way to create, retrieve, update, manage and analyze data.

    --------------       -------------     -----------------
    | database 1 |------>|           |     |               |<-----> user 1
    --------------       |           |     |               |          :
          :              |   DBMS    |<--->|  Application  |          :
    --------------       |           |     |               |          :
    | database N |------>|           |     |               |<-----> user N
    --------------       -------------     -----------------

    For example, Excel can open multiple spreadsheets with which the user can work with.

**data model**[@wiki_data_model]
:   A data model explicitly determines the structure of data. The term is used in two distinct but closely related senses:

    [_data modeling_] Abstract model that describes how data elements are related to one another and to properties of the real world entities in a particular application domain. For example the customers, products, and orders found in a manufacturing organization.

    For example, to create an agency-wide timesheet, the model needs to specify a date period, a department, an employee etc. One timesheet is for a single individual for one specific time period and so on.

    [_software_] A set of rules prescribing data structure and the relationships between data elements. This specification can be then implemented by effectively hard-coding these rules into a specific database-management system.

   For example, how Excel's data model is based on tables of data organized in rows and columns.

**database schema**[@schema]
: The database schema is like a blueprint that describes the layout of the data contained in the database: what kinds of fields are present and how they are organized. Compared to the abstract concept of data models, a schema is a concrete file whose format depends on the used database-management system.

  For example imagine an agency-wide timesheet template in Excel:

  *  it expects a specific type of data at certain places (e.g., duration of time at "Daily totals") and

  *  the template itself has to adhere to how Excel organizes data (i.e., it has to stick with rows and columns instead of trying to use floating bubbles connected with arrows.)

1. Introduction to CRMs
-----------------------

"CRM" may refer to one of the following definitions that are usually used interchangeably:

  * [_methodology_] One approach to capture and to manage an organization's interactions and relationships with and among entities.

  * [_software_] Application software[^footnote-application_software_definition] to persist, process and analyse captured interaction data.

[^footnote-application_software_definition]: **Application software**: _"A program or group of programs that is designed for the end user. (...) Application software cannot run on itself but is dependent on system software to execute."_[@tth]

The broadness of the first definition is deliberate (and so is leaving the acronym unexpanded) because making it specific depends on the context (i.e., organization type it is used in connection with).

The second definition intentionally uses the phrase "[application software](#glossary)" instead of the word "database" commonly (and incorrectly) used in  literature describing CRMs. This distinction is important because a CRM, as an [application software](#glossary), consists of a **persistence layer** and a **graphical user interface**.

  1. The **persistence layer** stores captured data and is usually a database system (or DBMS) but persistence can be achieved by other means as well. For example, data can be stored in discrete files in the file system or in memory during the execution of a program.

  2. A **graphical user interface** hides the specific details of the storage mechanism. It is mostly an implicit contract between the user and the application: the users expect ttheir input to be saved and that it can be recalled at a later time.

A simplified graphical representation of CRMs:

      ---  ==============================================
           |                                            |
       C   |  user interface                          <-----> USERS
           |                                            |
       R   |--------------------------------------------|
           |                                            |
       M   |  persistence layer (DBMS, files etc.)      |
           |                                            |
      ---  ==============================================




2. Customer Relationship Management Systems {#customer-rms}
-------------------------------------------

Mostly used by commercial organizations to preserve "information about the interactions between a customer and a business" [@sh_crm] with a usually the one-dimensional goal to maximize profits [@wiki_crm].

3. Constituent (Relationship) Management Systems
------------------------------------------------

Non-profit organizations require a different approach to capture relationships. Even though they may have clients who receive services in some form, the word **customer** does not naturally apply to them. Its meaning is also too narrow to refer to entities (i.e., individual, agency etc.) connected to non-profits.

The umbrella term **constituent** better encompasses all the roles an entity can fulfill. A constituent is therefore someone who takes part in the life of the organization, sometimes taking on multiple roles during the same timeframe. Complexity is further exacerbated by the fact that each role has its own set of interactions and organizational requirements.

Examples for constituent roles are that of a client, a volunteer or a donor and these are reflected in the two most common approaches to digital constituent management by a non-profit by[^footnote-crm_examples1]:

* either using a collection of specialist CRMs, each of them developed for a specific purpose, such as

    + volunteer management systems (e.g., Volunteer Reporter, Samaritan)
    + donor management systems (e.g., Raiser's Edge, Talisma)
    + case and/or client management systems (e.g., Slate, ClientTrack)

* or rolling out a single CRM application that tries to satisfy all needs but usually only to a certain extent (e.g., CiviCRM, Salesforce)

[^footnote-crm_examples1]: See [@techsoup;@idealware] for more examples.

III. Project rationale
======================

1. Problem statement
--------------------

2. Proposed solution
--------------------
 but they are also relevant by pointing out pros and cons of each approach. Later sections of this proposal will further evaluate these solutions in the context of blindness organizations, focusing on accessibility and on the limiting factors such as the size of an agency.


For these very reasons, the roles are oftentimes managed together by each department, instead of departments dedicated to a specific role[^functional_departments].

[^functional_departments]: The reason behind this practice is manyfold but it is usually caused by tight budgets and as a corollary, employees having multiple responsibilites that blurs the line further. On the bright side, this simplifies management of most departments by decentralizing the sources of information on various constituent groups. Departments, that need the big picture, draw the short straw: data will need to be aggregated manually if automation is missing or difficult (if not impossible). An example for the latter is when the data managed by systems that do not directly communicate each other and/or their proprietary nature does not enable reliable workarounds.

specialist crm approach issues because of  functional_departments: everyone needs to use many different software (price, learning curve, differing levels of accessibility)

Glossary
========

**Application software**
: _"A program or group of programs that is designed for the end user. (...) Application software cannot run on itself but is dependent on system software to execute."_[@tth]

**CRM**
:   May refer to one of the following definitions that are usually used interchangeably:

    [_methodology_] One approach to capture and to manage an organization's interactions and relationships with and among entities.

    [_computer science_] Application software[^footnote-application_software_definition] to persist, process and analyse captured interaction data.

References
==========
