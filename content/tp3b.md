+++
type   = "page"
title  = ""
+++

CouchDB: Expressing queries
===========================

Requirement
-----------

-   [CouchDB](http://couchdb.apache.org/)
-   [cURL](http://curl.haxx.se/download.html)
-   [AlloCine files](/files/Allocine.zip)

To Hand In
----------

This exercise will be handed in electronically:

-   You will form groups of 2 or three
-   A report with answers and explanations of the principle you adopted in PDF
-   The report will state the JavaScript answers to the questions.

To Do
-----

For this exercise you will use a set of file containing information about the films presented in Grenoble in 2011 (information retrieved from AlloCine API). Each of these files contains the films presented in a cinema of Grenoble at that time (i.e. there is a file per cinema and a total number of 9).

Start by creating and populating a new database in CouchDB using the data contained in the files named `allocineGrenobleN.txt` with *N* from *1* to *9*. For this purpose execute the following commands:

```
curl -X PUT http://localhost:5984/allocine

curl -T "allocineGrenoble1.txt" http://localhost:5984/allocine/allocineGrenoble1
curl -T "allocineGrenoble2.txt" http://localhost:5984/allocine/allocineGrenoble2
curl -T "allocineGrenoble3.txt" http://localhost:5984/allocine/allocineGrenoble3
curl -T "allocineGrenoble4.txt" http://localhost:5984/allocine/allocineGrenoble4
curl -T "allocineGrenoble5.txt" http://localhost:5984/allocine/allocineGrenoble5
curl -T "allocineGrenoble6.txt" http://localhost:5984/allocine/allocineGrenoble6
curl -T "allocineGrenoble7.txt" http://localhost:5984/allocine/allocineGrenoble7
curl -T "allocineGrenoble8.txt" http://localhost:5984/allocine/allocineGrenoble8
curl -T "allocineGrenoble9.txt" http://localhost:5984/allocine/allocineGrenoble9
```

***In your report give the code and a screen shot with the content on the database.***

Using this database answer the following questions and do not forget to give:

-   the code of the answer
-   the screenshots with the content of the database

Feel free to use the [CouchDB book](http://guide.couchdb.org/) for getting some inspiration.

### Question 1

Note that the data set is quite complete. Define a simplified view in MapReduce that contains for each theatre the films presented in it. **Hint**: You do not need a "reduce" here.

### Question 2

Modify your answer to question 1 for filtering the theatres outside Grenoble downtown (e.g., do not include the theatres in Saint Martin d'Hères).

### Question 3

Give the number of films that each theatre is presenting. **Hint**: You need a "reduce" here.

### Question 4

Give the list of films with a press rating higher than 4 stars. **Attention**: filter duplicates.

### Question 5

Give the list of films presented 2 years ago (10.12.2011), and for each film, the theatre where it was presented and its schedule.

### Question 7 (BONUS)

Give the list of films and for every film the list of theatres that present it. This question is a challenge but we encourage you to try to solve it.


---
**Acknowledgment**

Dr. Alexandre Termier, University Joseph Fourier originally designed this exercise. It has been slightly modified for this course.