---
title: .abapgit.xml
---

**.abapgit.xml** is a special abapGit file. It contains meta information of the abapGit project.

Example: abapGit own .abapgit.xml

```xml
<?xml version="1.0" encoding="utf-8"?>
<asx:abap xmlns:asx="http://www.sap.com/abapxml" version="1.0">
 <asx:values>
  <DATA>
   <MASTER_LANGUAGE>E</MASTER_LANGUAGE>
   <STARTING_FOLDER>/src/</STARTING_FOLDER>
   <FOLDER_LOGIC>PREFIX</FOLDER_LOGIC>
   <IGNORE>
    <item>/.travis.yml</item>
    <item>/CONTRIBUTING.md</item>
    <item>/LICENSE</item>
    <item>/README.md</item>
    <item>/package.json</item>
    <item>/changelog.txt</item>
   </IGNORE>
  </DATA>
 </asx:values>
</asx:abap>
```

# Description

## Master Language

The language in which all documentation and dictionary elements texts will be created. Follows SAP `sy-langu` values.

## Starting Folder

The Git repository folder that defines the root folder where deserialization starts.

## Folder Logic

abapGit follows two folder logics: PREFIX and FULL

### PREFIX

A package name must contain its parent package name as a prefix. Examples:

Valid prefix:
* ZFOO
  * **ZFOO**_BAR
    * **ZFOO_BAR**_QUX

will give folder structure /foo/bar/qux/

Invalid prefix:
* ZFOO
  * ZBAR

### FULL

Any package name is accepted

* ZSOMETHING
  * ZHELLO

will give folder structure /zsomething/zhello/

## Ignore

Files which abapGit will not download into your ABAP system.