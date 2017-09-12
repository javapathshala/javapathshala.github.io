---
layout: page
sidebar: right
breadcrumb: true
comments: true
title: "Defensive Copies"
teaser: "The simplest way to avoid problems with concurrency is to share only immutable data between threads. Immutable data is data which cannot changed"
categories:
          - core-java
          - concurrency
---
- An immutable class may have some mutable data which is uses to manage its state but from the outside this class nor any attribute of this class can get changed.
- For all mutable fields, e.g. Arrays, that are passed from the outside to the class during the construction phase, the class needs to make a defensive-copy of the elements to make sure that no other object from the outside still can change the data.
- You must protected your classes from calling code. Assume that calling code will do its best to change your data in a way you didn't expect it. While this is especially true in case of immutable data it is also true for non-immutable data which you still not expect that this data is changed outside your class.
- To protect your class against that you should copy data you receive and only return copies of data to calling code.-

The following example creates a copy of a list (ArrayList) and returns only the copy of the list. This way the client of this class cannot remove elements from the list.

{% highlight java %}
public class MyDataStructure {
  List<String> list = new ArrayList<String>();
  public void add(String s) {
    list.add(s);
  }
/**
   * Makes a defensive copy of the List and return it
   * This way cannot modify the list itself
   *
   * @return List<String>
   */
  public List<String> getList() {
    return Collections.unmodifiableList(list)  }
}
{% endhighlight %}
