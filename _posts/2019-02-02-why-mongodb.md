---
layout: post
title:  "Why MongoDB ?"
date:   2019-02-02 17:10:00 +0800
categories: javascript database mongodb nodejs
---
I've discovered [MongoDB](https://www.mongodb.com) roughly one year ago now - basically since I've started developing under NodeJS. 

MongoDB is a **document-oriented database system**. This is my first experience with this kind of DBMS. Previously I've been working exclusively with RDMS (Relational Database Management System) like SQL Server, Oracle, Postgres or MySQL. Everything was about table structure, column types, indexes...

Now the question would be, why MongoDB has been the natural companion of my discovery of NodeJS?

Well, first of all - MongoDB models or schemas are very easy to implement in NodeJS thanks to a bunch of very powerful tools. 
The most famoust being [Mongoose](https://mongoosejs.com/) which act as an **ORM** (Object Relational Mapping) tool.

Second - they both speak the same languages. Objects are stored in JSON-based structures and MongoDB ignore joins or table structure.

That's definitly not the only solution but, so far, that made the development of my prototypes so much faster and efficient. 
