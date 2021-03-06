---
layout: default
title: "Reactive access to Relational Databases."
category: talk
---

Das reaktive Programmiermodell verspricht bessere Skalierbarkeit als klassische (Servlet-basierte) Ansätze. 
Die ist in Zeiten, in denen man jeden CPU Zyklus einzeln bezahlt, äußerst relevant und erstrebenswert.

Andererseits sind relationale Datenbanken mit SQL basierten Schnittstellen seit 30 Jahren die Arbeitstiere von Enterpriseanwendungen.
Javas Zugriffstechnologie JDBC ist aber eine blockierende API und als solche nicht geeignet für das reaktive Programmiermodell.

Seit einiger Zeit ist Bewegung in diese Konfliktsituation gekommen und unterschiedliche Gruppen arbeiten daran den Konflikt zu lösen.

In diesem Vortrag werde ich vorstellen, 

- was reaktive Programmierung ist, 
- warum sie sich nicht mit blockierenden APIs verträgt,
- und welche Workarounds und echte Alternativen es gibt.

Dabei werden sowohl die theoretischen Konzepte vorgestellt, als auch praktische Code Beispiele gezeigt.

   



