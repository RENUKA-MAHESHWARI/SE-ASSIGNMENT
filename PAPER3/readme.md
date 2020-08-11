# An Empirical Study of Method Chaining in Java


#### Authors Tomoki Nakamaru, Tomomasa Matsunaga, Tetsuro Yamazaki, Soramichi Akiyama, Shigeru Chiba



> Venue Mon 29 Jun 2020 10:48 - 10:54 at MSR:Zoom - Programming Languages & Models 
>> Chair(s): Dimitris Kolovos


[PAPER LINK](https://2020.msrconf.org/details/msr-2020-papers/2/An-Empirical-Study-of-Method-Chaining-in-Java)


#### Media 

https://youtu.be/28kH_Rs4CD4?t=26


INTRODUCTION : 

    Method chaining is the practice of calling different methods in a single line instead of calling diffrent methods with a same object
refrence separately. In method chaining write object refrence once and then call methods by separating them by a dot.

Method chaining improves code read ability. So that it is agood practice but it is also a bad practice because it reduces code 

readability,sometimes it becomes difficult to understand the code.It also voilates law of Demeterit introduces Null-pointer exceptions,it 

is not reconcilable with most debuggers because in method chaining we cannot put a breakline on which we can stop the code,it hides the 

type of object.

In this paper there are two research questions that is :

Q1 : Is method chaining widely accepted by real world programmers?

Q2 : How can we extend java language to support the increasing trends?

  
 To answer these questions they introduced 2814 java repositries from github and analyzed historical trendsa in frequency of method 

chaining.

 As much frequency greater the support for acceptance of method chaining.

To measure the frequency we use frequency indicator that is

 r = number of method invocations in chains / number of method invocations

Most of the dataset is taken from most stared 1000 java repositries from github.

Method chaining is divided into three groups that are : 

 - SHORT  length range is 2<len<8 
 - LONG   length range is 8<len<42
 - EXTLONG length range is 42<=len

To calculate most use of method chains in different forms we calculate it as Un.

Un : The ratio of repositries that contain one or more method chains whose length is longer than or equal to n.

NULL EXCEPTION AVOIDANCE : If a method chain returns null it cannot continue the related methods . To avoid this Null exception use get

(qname) in  the method chain.It is called safe call method.

So now coming on the research questions :

Q1 :  Is method chaining widely accepted by real world programmers?

   The answer is Yes. Because the ratio of method chaining is increasing. Most of the repositries contain method chains. In 2010 the ratio 

of method chaining was 16.0% and in 2018 it is increased to 23.1% . This means that method chaining is accepted by real world programmers.

Q2 : How can we extend JAVA language to support increasing trends?

    They found two language features and four API designs which allow programmer to chain more method invocations.If it is adopted at least 
10% non-chained methods canbe converted into chained methods.


RESULTS : 

 We have find the supportive evidance for acceptance of method chaining . Many programmers  use method chaining because it reduces code and 

it donnot need to introduce variables.  We also introduced API designs for method chaining in java.