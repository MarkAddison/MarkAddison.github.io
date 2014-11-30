---
layout: post
title: Spring Hibernate Using Annotations
excerpt: "An example showing how to use annotations when implementing persistent code using spring hibernate"
modified: 2014-11-26
categories: spring database
comments: true
excerpt:
tags: []
image:
  feature:
date: 2014-11-26T15:04:01+00:00
---

<section id="table-of-contents" class="toc">
  <header>
<h3>Overview</h3>
  </header>
<div id="drawer" markdown="1">
*  Auto generated table of contents
{:toc}
</div>
</section><!-- /#table-of-contents -->

This tutorial will show you how to use annotation with Spring Hibernate

###Prerequisites
You will need to install the following technical components:

* Java 1.7.x
* Maven 3.0.5
* Spring Framework
* Hibernate

###Create a new Java project in Maven
The simplest way to quickly create a new Java project in Maven is to utilise Maven Archetype (Quickstart)

```
$ mvn archetype:generate -DgroupId=com.addison.database -DartifactId=SpringHibernateUsingAnnotations
  -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
```

### Java project skeleton structure
    SpringHibernateUsingAnnotations
    │   pom.xml
    │
    └───src
        ├───main
        │   └───java
        │       └───com
        │           └───addison
        │               └───database
        │                       App.java
        │
        └───test
            └───java
                └───com
                    └───addison
                        └───database
                                AppTest.java

This essentailly creates a Hello world application! Since we do not need App or AppTest classes, these should just be deleted.

### Data Entities
For this example let us consider persisting a **Person** entity, with attributes first name, last name, phone number, e-mail; and an **Address**, which is modelled as another first class entity.

#### Annotated Person Entity
{% highlight java %}
import javax.persistence.*;

@Entity
@Table(name = "person")
public class Person {
   @Id @GeneratedValue
   @Column(name = "id")
   private int id; // generated unique ID

   @Column(name = "first_name", nullable = false, length = 20)
   private String firstName;

   @Column(name = "last_name", nullable = false, length = 20)
   private String lastName;

   @Column(name = "phone_number", nullable = true, length = 20)
   private String phoneNumber;

   @Column(name = "email", nullable = true, length = 60)
   private String email;

   private Address address;
}
{% endhighlight %}

#### Annotated Address Entity
{% highlight java %}
import javax.persistence.*;

@Entity
@Table(name = "address")
public class Address {
   @Column(name = "line1", nullable = false, length = 40)
   private String line1;

   @Column(name = "line2", nullable = true, length = 40)
   private String line2;

   @Column(name = "town_city", nullable = false, length = 30)
   private String townCity;

   @Column(name = "county", nullable = true, length = 40)
   private String county;

   @Column(name = "post_code", nullable = true, length = 8)
   private String postCode;
}
{% endhighlight %}
