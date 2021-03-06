# scripture-burrito
A data interchange format for Bible-centric content. Supports licenses, multimedia project data...

## History
This proposal has been prepared by the ETEN Project Portability Working Group which was
formed after meetings in Philadelphia in July 2018. The group has since met several times
virtually, culminating in two days of face meetings in Orlando on January 17-18, 2019. The
meeting was attended by

* Han Chung
* Jesse Griffin
* Mark Howe
* Joel Mathew
* Tim Steenwyk
* Benjamin Varghese
* Andi Wu

## Scope
The original focus of the group was specific to translation project portability between translation
applications. This focus has been broadened to include any Bible-centric content and the entire
ecosystem, including publication. Further, the intent is not to create new data formats
unnecessarily, but rather define a portable way of interchanging existing formats between
applications and ecosystems. This necessarily includes existing and future client/server
architectures and the attendant need to uniquely identify users, organizations and content.
Because of the enlarged scope, the group is now known as the Scripture Burrito (SB) Working
Group.

## Goal
Lossless portability of Scripture-related metadata and data between translation and publication
users, applications and ecosystems.

## Features
* a single container format to span the entire Scripture life cycle, from translation, through
community testing and checking, to publication
* support for canonical and quasi-canonical translations in multiple media (initially text,
audio, video, print on demand and braille)
* support for a wide range of resources relating to scripture, such as lexicons,
cross-references, translation manuals, and commentaries
* mechanisms for linking related content, both at a burrito-to-burrito and
ingredient-to-ingredient level
* identification of people, organizations and content via namespaced ids relating to multiple
authenticating servers

## Formats
The proposal describes a recipe for assembling a burrito by organizing ingredients into a specific,
hierarchical structure. That structure could be represented as nested directories on a filesystem, or
as a ZIP file, or in any other system-dependent way.

## Metadata
The proposed format is based on the forthcoming DBL Metadata 2.3, which already offers many of
the desired features. SB Metadata 0.1 has an XML and a JSON expression . Content servers may
store SB metadata in either format and should allow metadata input and output for any burrito in
either format. SB 0.1 will include features present in unfoldingWord Resource Container metadata,
including better support for public licences and non-scriptural content.

## Canonical Text
The proposal is to support both USFM and USX, since significant existing ecosystems use both
expressions. Content servers may store canonical text in either or both formats and should allow
input and output of any burrito in either format. USFM/USX v3.0 is preferred, but older versions
will be supported and declared via the format section of the metadata.

## Other Ingredient Formats
Existing standards should be embraced where possible. Legacy character-based markup
schemes should be deprecated in favour of popular, modern formats such as XML and JSON.
(Versification schemes are one example requiring urgent attention.)

## Supporting Technologies

* USFM ↔ USX convertors in C#, Javascript and Python
* Metadata XML ↔ JSON convertors in C#, Javascript and Python
* Modular, RESTful interfaces for supporting server technology
