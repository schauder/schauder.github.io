---
layout: default
status: publish
published: true
title: "Speaker Info"
author:
  display_name: Jens Schauder
  login: admin
  email: jens@schauderhaft.de
  url: http://blog.schauderhaft.de
order: 0
---

This page contains all the information about me and the talks I'm currently offering as a speaker, that is typically requested by organizers of conferences.
If you want me to speak at your event, please contact me.
If you want me to speak about a different topic, let me know.

# Bio #
## Deutsch ##
Jens Schauder hat vor unglaublich langer Zeit auf einem in Assembler programmierbaren Tischrechner angefangen zu programmieren. 
Nach über 30 Jahren, davon fast 20 als Consultant für meist große Konzerne, hat er es 2017 geschafft sich beim Spring Data Team einzuschleichen. 
Dort arbeitet er meist an den Modulen Commons, JPA und JDBC, erzählt davon auf Konferenzen oder hilft anderen Entwicklern auf Stackoverflow.
Wenn er nicht programmiert, spielt er mit seinen Kindern, läuft, macht Freeletics, spielt oder organisiert die JUG Ostfalen.

## English ##
A long long time ago in a city far away Jens Schauder started coding on a desktop calculator programmable in assembly. 
Over 30 years later, after almost 20 years as a consultant working mostly with huge enterprises, he managed to sneak into the Spring Data Team. 
Here he works mainly on the “Commons”, “JPA” and “JDBC” modules and tells about it at conferences or helps other developers on StackOverflow.
In his spare time he likes to spend time with his kids, running, bouldering, JUG organizing or dying doing Freeletics.

# Talks #

## Nur ein Quantensprung oder ist es was wirklich Neues?

Was sind Quantencomputer und wird es demnächst ein Spring Quantum geben?

Im Oktober 2019 hat Google verkündet, dass sie "Quantum Supremacy" erreicht haben.
Da fragt sich der nervöse Softwareentwickler, ob er schon wieder was Neues lernen muss, oder ob es reicht eine weiteres Spring Modul auf start.spring.io auszuwählen.

Wir werden uns die Sache von der Basis her anschauen.
Wie funktioniert ein Quantencomputer?
Wie wird er programmiert?
Wo kann man das ausprobieren?
Warum gibt es einen solchen Hype darum?
Und haben wir wirklich "Quantum Supremacy" erreicht?

Am Ende des Vortrags werdet ihr den Titel verstehen und euch eine fundierte Meinung bilden können, ob ihr tiefer in das Thema einsteigt oder ob ihr das Feld den Akademikern überlassen wollt.

## Spring Data JPA from 0-100 in 60 minutes.

JPA is the most popular persistence technology for JAVA. 
In this talk, we'll look into how it works and how it integrates with Spring by means of Spring Data JPA.
We'll look at the various ways one may use Spring Data from ready-made queries over query derivation, query by example, specifications, paging and sorting to custom method implementations.

We'll also take a look at common pitfalls of JPA and how to circumvent them.
And if time is left we'll take a glance at other technologies available to Java developers to complement JPA and how these integrate with Spring Data.

Participants will learn to distinguish between JPA and Spring Data JPA, the various features Spring Data JPA offers and when to use which feature to achieve their goal.

## Spring Data JDBC: The new kid on the block ##

Mit Spring Data ist bekannt für seine von Domain Driven Design inspirierte Repository Abstraktion.
Diese erlaubt den Zugriff auf unterschiedliche Persistenztechnologien wie JPA, MongoDb, Redis und andere mit einer konsistenten API.
Seit dem Lovelace Release Mitte des Jahres gibt es eine weitere Technologie, die unterstützt wird: JDBC.

Dieser Talk wird den aktuellen Stand von Spring Data JDBC demonstrieren und erläutern warum JDBC neben JPA Sinn macht.
Darüber hinaus gibt er Einblick in wesentliche Designgrundlagen und Entscheidungen, die Spring Data JDBC zu Grunde liegen.

Nach dem Vortrag sollten Teilnehmer in der Lage sein, für sich zu entscheiden, ob der Einsatz von Spring Data JDBC für ihre Persistenzbedürfnisse eine Option ist.

## The new kid on the block: Spring Data JDBC ##

Spring Data is mostly known as a way to create Repositories as described in Domain Driven Design (DDD) for persistence technologies like JPA, MongoDB, Redis, and others. We now support another technology: JDBC.
Spring Data JDBC is an opinionated library for persisting your data to a relational database. 
This talk will describe the current state of Spring Data JDBC, its features and the underlying design decisions, especially how the Spring Data team attempts to walk the tightrope of offering a DDD-based API and at the same time allow precise control of each and every SQL statement issued to the database. 

After this talk, the audience will be able to make a well-grounded decision if Spring Data JDBC is worth to look into for their specific challenges and what to expect from it.

## Domain Driven Design with Relational Databases using Spring Data JDBC ##

Domain Driven Design introduces the concepts of Aggregate, AggregateRoot, and Repository. 
If one takes these concepts serious certain habits we picked up while <strikethrough>fighting</strikethrough> working with JPA become unacceptable.
Even more, a substantial part of the complexity of JPA seems to become superfluous.
The result will be performant, scalable, and maintainable. 

A drawback of this approach is that we might have to fight our database administrator. 
But you can't have it all, can you?

As it turns out Spring Data JDBC supports this approach rather well.

In this talk, I'll present how to design an object model the DDD way, why this might be a good idea and how to build a persistence layer for it backed by Spring Data JDBC.

And I'll even figuratively bring some candy to pacify the Database Admins.

## Domain Driven Design mit Relationalen Datenbanken (und Spring Data JDBC) ##

Domain Driven Design (DDD) führt die Konzepte Aggregate, Aggregateroot und Repository ein.
Wenn man diese Konzepte ernst nimmt stellt man fest, dass viele Dinge, die man sich <strikethrough>im Kampf</strikethrough> in der Arbeit mit JPA angewöhnt hat nicht wirklich akzeptabel sind.
Mehr noch, es werden sogar ganze Features von JPA überflüssig oder zumindest wesentlich weniger wichtig.

In diesem Vortrag stelle ich vor welche Auswirkungen DDD auf ein Objekt Modell hat,
 und wie dies massiv die Komplexität reduziert.
 Wir werden sehen, wie es Integrationstests vereinfacht und ganze Kategorien von Fehlern vermeidet, die aktuell in sehr vielen Datenbankanwendungen vorhanden sind.

Diese Designentscheidungen eröffnen schließlich auch noch die Möglichkeit über die Vor- und Nachteile von Foreignkeys nach zu denken um diese gezielter und bewusster einsetzen zu können.

Das beschriebene Vorgehen ist integraler Bestandteil der Architektur von Spring Data JDBC und in den letzten ca 10 Minuten werden wir dies nutzen um uns das Ganze in der Praxis anzuschauen. 

## Kommunikation für Softwareentwickler und alle anderen. ##

Kommunikation mit Computern ist wundervoll einfach. Sie erfolgt fast ausschließlich schriftlich, d.h. Ich kann mir so viel Zeit lassen wie ich will und mir über die Formulierung und meine Ziele in Ruhe Gedanken machen. Und wenn ich was falsches Schreibe, bekomme ich eine Fehlermeldung, und kann es nochmal versuchen. Aber am wichtigsten: Wenn ich zweimal das Gleiche tue, bekomme ich das gleiche Ergebnis. 
Mit Menschen ist dies alles viel komplizierter. Aber auch das kann man lernen!
Warum ändert kaum jemand seine Meinung, wenn er mit Fakten konfrontiert wird? Wie erziehe ich Manager, Ehemänner und Kinder? Sollte ich Entwickler, die sich an Architekturvorgaben nicht halten durch Schläge oder durch Liebesentzug strafen? Und wie kann ich das üben, wo ich doch meinen Lebensabschnittsgefährten, nach einem fehlgeschlagenen Testlauf, nicht so einfach neu instanzieren kann?

## Communication for Software Developers and all Others. ##

Communication with Computers is wonderfully easy. It’s almost exclusively in writing. This means I can take as much time as I want to fine tune my wording and to reflect on my goals. And if I write something that doesn’t work I get an error and can try again. But most importantly: If I do the same thing twice, I get the same result.
Everything is much more complicated than this with real humans. But you can still learn it!
Why does hardly anybody change his mind based on facts? How do I train manager, spouses, and children? How should I penalize a developer not conforming to architecture rules? How can I practice this when I can’t just reinstantiate my spouse after a failed test run? 

## Das Leben als OSS Entwickler - Wie fühlt sich das an? Und wie wird man einer? ##

Im Februar 2017 habe ich bei Pivotal angefangen zu arbeiten und wurde ein Teil des Spring Data Teams. Mit meinem Hintergrund als Enterprise Software Entwickler war dies eine ziemliche Umstellung. Seit dem gehen mir 2 Fragen im Kopf herum:
Was macht es möglich, dass die Arbeit an einem Open Source Software Projekt so anders (und angenehmer) ist?
Wie bin ich hier gelandet?

In diesem Vortrag beantworte ich die Fragen, so weit ich es kann. Als Grundlage werde ich erzählen, wie mein Arbeitsalltag aussieht, und einiges an Anekdoten aus meinem Leben.

Nach dem Vortrag solltet ihr in der Lage sein zu entscheiden, ob OSS Entwicklung etwas für euch ist. Ihr bekommt vielleicht die eine oder andere Idee, was ihr in eurem Team verändern könntet und wie ihr eure Karriere vorantreibt und weiterentwickelt. Und wenn das alles nichts für euch ist, könnt ihr wenigstens Hoffnung daraus ziehen, das jemand, der so viele dumme Dinge getan hat wie ich trotzdem den beinahe perfekten Job gefunden hat.

## Being an OSS Developer - What does it feel like and how do you get there? ##

In February 2017 I joined Pivotal and became part of the Spring Data Team. 
Coming from a career as a consultant (read software developer) for huge enterprises this was a huge change for me. 
And certainly a change for the better. 
Ever since I can’t get two kinds of questions out of my head: 
Why is working on Open Source Software so different (and so much more fun)? How the f*** did I manage to get here?

In this talk I’ll try to answer these questions as far as I have answers. 
As a basis I will explain how working in the Spring Data team does work, and I will tell a good measure of anecdotes from my life.

In the end you should be able to decide, if you would like to work on a similar team. 
You might have some ideas about changing things in your team and possibly how to approach your career. 
And if nothing else you may funnel hope from the fact that someone doing as many stupid things as I did, did still end up with something pretty close to the perfect job.



# Links #

Blog: http://blog.schauderhaft.de

Twitter: https://twitter.com/jensschauder

GitHub: https://github.com/schauder

Xing: https://www.xing.com/profile/Jens_Schauder

LinkedIn: https://www.linkedin.com/in/jens-schauder/

# Foto #

![Foto of Jens Schauder](/assets/profile-small.jpg)
