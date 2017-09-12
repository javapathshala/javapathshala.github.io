---
layout: page
sidebar: right
breadcrumb: true
comments: true
title: "Serial Version UID"
teaser: Serial Version UID is declared in java classes in relation to java object serialization & de-serialization process"
categories:
          - core-java
tags:
          - core-java
          - serialVersionUID
          - serialization
---
During object serialization, the default Java serialization mechanism writes the metadata about the object, which includes class name, field names and types, and super class. This class definition is stored as a part of the serialized object. This stored metadata is used as a maker for deserialization process to reconstitute the objects and map the stream data into the class attributes with the appropriate type.

When java class is serialized, serialization mechanism automatically computes a hash value. Object Stream Class computes SerialVersionUID() method passes the class name, sorted member names, modifiers, and interfaces to the secure hash algorithm (SHA), which returns a hash value. This computed hash value is known as serialVersionUID or SUID. It is used as a marker or version control in a Serializable class. If SUID is not defined in java class, JVM will automatically compute the hash value based on various aspects of Serializable class.

So during de-Serializable process, JVM first evaluates the SUID of the serialized class and compares the SUID value with the one of the object. If the SUID values match then the object is said to be compatible with the class and hence it is de-serialized.  If not InvalidClassException exception is thrown.

Changes to a serializable class can be compatible or incompatible. Following is the list of changes which are compatible:
- Add fields
- Change a field from static to non-static
- Change a field from transient to non-transient
- Add classes to the object tree

List of incompatible changes:
- Delete fields
- Change class hierarchy
- Change non-static to static
- Change non-transient to transient
- Change type of a primitive field

If SUID is absent, JVM will use its own algorithm to generate a default SUID & thus resulting in an exception if prior release version object is used.  Also it will not proceed for making compatible changes. The only way to get rid of the exception is to recompile and deploy the application again. The default SUID computation is highly sensitive to class details and may vary from different JVM implementation, and result in an unexpected InvalidClassExceptions during the deserialization process. JDK has a build in command called “serialver” to generate the serialVersionUID automatically.

If SUID is declared using the statement: private final static long serialVersionUID = <integer value> then if any of the mentioned compatible changes are made the class need not to be recompiled. But for incompatible changes there is no other way than to compile again.
