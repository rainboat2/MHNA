# MHNA

## Q1

```SQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX ub: <tju:#>
SELECT *
WHERE
{
  ?Y rdf:type ub:GraduateCourse .
  ?D rdf:type ub:Department .
  ?X ub:memberOf ?D.
  ?X ub:takesCourse ?Y.
} ;
```



## Q2 

```SPARQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX ub: <tju:#>
SELECT *
WHERE
{
  ?Y rdf:type ub:GraduateCourse .
  ?F rdf:type ub:FullProfessor .
  ?D rdf:type ub:Department .
  ?X ub:memberOf ?D.
  ?X ub:takesCourse ?Y.
  ?F ub:teacherOf ?Y.
} ;
```




### Q3

```SPARQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX ub: <tju:#>
SELECT *
WHERE
{
  ?Y rdf:type ub:GraduateCourse .
  ?F rdf:type ub:FullProfessor .
  ?D rdf:type ub:Department .
  ?X ub:memberOf ?D.
  ?X ub:takesCourse ?Y.
  ?F ub:teacherOf ?Y.
} ;
```



## Q4

```SPARQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX ub: <tju:#>
SELECT *
WHERE
{
  ?F rdf:type ub:FullProfessor .
  ?D rdf:type ub:Department .
  ?X ub:memberOf ?D.
  ?X ub:advisor ?F.
} ;
```



## Q5

```SPARQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX ub: <tju:#>
SELECT *
WHERE
{
  ?F rdf:type ub:FullProfessor .
  ?U rdf:type ub:University .
  ?D rdf:type ub:Department .
  ?X ub:memberOf ?D.
  ?X ub:advisor ?F.
  ?F ub:mastersDegreeFrom ?U.
} ;
```



## Q6

```SPARQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX ub: <tju:#>
SELECT *
WHERE
{
  ?Y rdf:type ub:GraduateCourse .
  ?F rdf:type ub:FullProfessor .
  ?D rdf:type ub:Department .
  ?S rdf:type ub:GraduateStudent .
  ?X ub:memberOf ?D.
  ?X ub:takesCourse ?Y.
  ?F ub:teacherOf ?Y.
  ?S ub:advisor ?F.
} ;
```























# backup

## Q5 (6个点)

```SPARQL
explain ANALYZE 
SPARQL SELECT ?X, ?Y, ?D, ?F, ?P, ?Z WHERE {
  ?X rdf:type <GraduateStudent> .
  ?Y rdf:type <GraduateCourse> .
  ?F rdf:type <FullProfessor> .
  ?D rdf:type <Department> .
  ?P rdf:type <Publication> .
  ?Z rdf:type <GraduateStudent> .
	?X <memberOf> ?D.
	?X <takesCourse> ?Y.
	?F <teacherOf> ?Y.
  ?Z <advisor> ?F .
} ;


# virtuoso
SPARQL PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX ub: <tju:#>
SELECT *
FROM <LUBM10>
WHERE
{
  ?X rdf:type ub:GraduateStudent .
  ?Y rdf:type ub:GraduateCourse .
  ?F rdf:type ub:FullProfessor .
  ?D rdf:type ub:Department .
  ?P rdf:type ub:Publication .
  ?Z rdf:type ub:GraduateStudent .
  ?X ub:memberOf ?D.
  ?X ub:takesCourse ?Y.
  ?F ub:teacherOf ?Y.
  ?P ub:publicationAuthor ?F.
  ?Z ub:advisor ?F.
} ;


# gstore
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX ub: <tju:#>
SELECT *
WHERE
{
  ?X rdf:type ub:GraduateStudent .
  ?Y rdf:type ub:GraduateCourse .
  ?F rdf:type ub:FullProfessor .
  ?D rdf:type ub:Department .
  ?Z rdf:type ub:GraduateStudent .
  ?X ub:memberOf ?D.
  ?X ub:takesCourse ?Y.
  ?F ub:teacherOf ?Y.
  ?Z ub:advisor ?F.
} ;
```



## Q6 (7个点)

```SPARQL
# openGauss-graph
explain ANALYZE 
SPARQL SELECT ?X, ?Y, ?D, ?F, ?P, ?Z, ?C WHERE {
  ?X rdf:type <GraduateStudent> .
  ?Y rdf:type <GraduateCourse> .
  ?F rdf:type <FullProfessor> .
  ?D rdf:type <Department> .
  ?P rdf:type <Publication> .
  ?Z rdf:type <GraduateStudent> .
  ?C rdf:type <University> .
	?X <memberOf> ?D.
	?X <takesCourse> ?Y.
	?F <teacherOf> ?Y.
  ?Z <advisor> ?F .
  ?Z <undergraduateDegreeFrom> ?C.
} limit 100000;


# virtuoso
SPARQL PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX ub: <tju:#>
SELECT *
FROM <LUBM10>
WHERE
{
  ?X rdf:type ub:GraduateStudent .
  ?Y rdf:type ub:GraduateCourse .
  ?F rdf:type ub:FullProfessor .
  ?D rdf:type ub:Department .
  ?P rdf:type ub:Publication .
  ?Z rdf:type ub:GraduateStudent .
  ?C rdf:type ub:University .
  ?X ub:memberOf ?D.
  ?X ub:takesCourse ?Y.
  ?F ub:teacherOf ?Y.
  ?P ub:publicationAuthor ?F.
  ?Z ub:advisor ?F.
  ?Z ub:undergraduateDegreeFrom ?C.
} ;

# gstore
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX ub: <tju:#>
SELECT *
WHERE
{
  ?X rdf:type ub:GraduateStudent .
  ?Y rdf:type ub:GraduateCourse .
  ?F rdf:type ub:FullProfessor .
  ?D rdf:type ub:Department .
  ?Z rdf:type ub:GraduateStudent .
  ?C rdf:type ub:University .
  ?X ub:memberOf ?D.
  ?X ub:takesCourse ?Y.
  ?F ub:teacherOf ?Y.
  ?Z ub:advisor ?F.
  ?Z ub:undergraduateDegreeFrom ?C.
} ;
```



## Q2 （2个点）

```SPARQL
# openGauss-graph
explain ANALYZE 
SPARQL SELECT ?X, ?D WHERE {
  ?X rdf:type <GraduateStudent> .
  ?D rdf:type <Department> .
	?X <memberOf> ?D.
} ;

# virtuoso
SPARQL PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX ub: <tju:#>
SELECT *
FROM <LUBM10>
WHERE
{
  ?X rdf:type ub:GraduateStudent .
  ?D rdf:type ub:Department .
  ?X ub:memberOf ?D.
} ;


# gstore
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX ub: <tju:#>
SELECT *
WHERE
{
  ?X rdf:type ub:GraduateStudent .
  ?D rdf:type ub:Department .
  ?X ub:memberOf ?D.
} ;
```
