---
layout: page
sidebar: right
breadcrumb: true
comments: true
title: "Null Pointer Exception – Blasphemy!"
teaser: "Treat Java as Human. He can accept & comprise on any type of exceptions but “NULL POINTER EXCEPITON” is a SIN."
categories:
          - Core-Java
---
You might have written extremely excellent business logic, algorithms, followed coding guidelines etc. but if code is prone to NULL POINTER exception, it is not worthwhile having the code.

MUST AVOID NULL POINTERIn my experience, I have seen that programmers actually follow the approach of GO-Lucky with this. They believe that their code is perfect & any particular section cannot generate the NULL POINTER.  These proud sections are the real source of NULL POINTER.  
Make your code 100 % error free.

<em>Follow the below mention checkpoints that can help programmers to get rid of Null pointers. </em>

##### Usage of EQUALS Method
Consider the sample code
<pre>if (status.equalsIgnoreCase("In-Progress"))</pre>

This statement looks pretty good & error free but actually it is most common mistake we all do & most dangerous statement in java.
This will throw a NULL POINTER exception if values of status is NULL as NULL cannot invoke equalIgnoreCase().

<em>Remedy:</em>
Change the statement to:
<pre>if ("In-Progress".equalsIgnoreCase(status)) </pre>

In this case, first attribute is of type String [In-Progress is string], so it is capable to invoking equalignoreCase(). Now even if status is NULL, code will work fine as String value can be compared to NULL or Not Null values.

So this small tweak will make your code happy!

##### EMPTY or NULL Collection
There is huge difference between EMPTY & NULL collections e.g. List, Map etc. Empty List is a list that does not contain any elements i.e. LIST.size is 0. Null List is a list that has all elements NULL. So never initialise LIST to Null as
<pre>List list = null; return list;</pre>
but instead do
<pre>List list = Collections.EMPTY_LIST; return list;</pre>
Same way for other collection type, we have Collections.EMPTY_MAP

##### Treat Null Pointer Gracefully

Neither throw or throws Null Pointer exception.  This also states true for the fact that Null Pointer exception is an unchecked exception also. There are much better ways to handle potential null pointer exceptions.
So do not handle exception in below way :
<pre>
try {
      System.out.println(userDTO.getUserId());
    }
catch (NullPointerException npe)
{  //write your code here }
</pre>
If your business logic allows userDTO == null then follow the below approach:
<pre>
if (userDTO != null) {
  System.out.println(userDTO.getUserId());
}
else {
//Other business logic codes here.
}
</pre>

##### Hierarchical Invoking of methods
This coding practise is also one of the potential causes of exception. We generally call methods hierarchically in a single statement like:
<pre>
String value = (String)((service.getSession("key"))
                      .getAttribute("sessionattributename"));
</pre>
Above statement can throw null pointer exception if service.getSession(“key”) is null , so there is need to refractor the code as
<pre>
Session sessionObject= service.getSession("key");
if(sessionObject!=null){
  String value=sessionObject.getAttribute(“sessionattributename”);
}
</pre>

##### Using Third-party Classes.
As Java is growing fast & lots of open source libraries available in market , consider this as a rapid development technique.
org.apache.commons.lang Package provides a StringUtils Class that exposes utility methods to avoid null pointer exception.
Exposed methods : IsEmpty(), StringUtils. IsBlank(), StringUtils.equals().
All these methods are Null pointer safe.
