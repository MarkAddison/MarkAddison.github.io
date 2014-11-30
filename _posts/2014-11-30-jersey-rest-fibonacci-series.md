---
layout: post
title: Jersey REST Fibonacci Series
modified: 2014-11-30
categories: java
comments: false
excerpt:
tags: []
image:
feature:
date: 2014-11-30T17:04:01+00:00
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

A quickly developed Jersey REST implementation of a Fibonacci series 'service'.


###Prerequisites
You will need to install the following technical components:

* Java 1.7.x
* Maven 3.0.5
* Nexus 2.8.1

###Create a new Java project in using Jersey Grizzly quickstart
To create the Jersey web-app project, execute the following Maven archetype command in the directory where the new project should reside:

```
mvn archetype:generate -DarchetypeArtifactId=jersey-quickstart-webapp -DarchetypeGroupId=org.glassfish.jersey.archetypes
    -DinteractiveMode=false -DgroupId=com.addison -DartifactId=jersey-webapp -Dpackage=com.addison -DarchetypeVersion=2.13
```

{% highlight text %}
    jersey-webapp
    ¦   pom.xml
    ¦
    +---src
    +---main
        +---java
        ¦   +---com
        ¦       +---addison
        ¦               MyResource.java
        ¦
        +---resources
        +---webapp
        ¦   index.jsp
        ¦
        +---WEB-INF
                web.xml{% endhighlight %}
### Java project skeleton structure

This essentially creates a very simple REST web-app, which retrieves a static string response.