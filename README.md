# MHNA

## LUBM queries

## Q1

```SQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX ub: <http://www.lehigh.edu/~zhp2/2004/0401/univ-bench.owl#>
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
PREFIX ub: <http://www.lehigh.edu/~zhp2/2004/0401/univ-bench.owl#>
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
PREFIX ub: <http://www.lehigh.edu/~zhp2/2004/0401/univ-bench.owl#>
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
PREFIX ub: <http://www.lehigh.edu/~zhp2/2004/0401/univ-bench.owl#>
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
PREFIX ub: <http://www.lehigh.edu/~zhp2/2004/0401/univ-bench.owl#>
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
PREFIX ub: <http://www.lehigh.edu/~zhp2/2004/0401/univ-bench.owl#>
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

## DBpedia queries

## Q1

```SQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX dbo: <http://dbpedia.org/ontology/>
SELECT * WHERE {
    ?x rdf:type dbo:Athlete.
    ?y rdf:type dbo:Settlement.
    ?x dbo:birthPlace ?y.
    ?y dbo:country ?z.
}
```



## Q2 

```SPARQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX dbo: <http://dbpedia.org/ontology/>
SELECT * WHERE {
    ?x rdf:type dbo:Athlete.
    ?y rdf:type dbo:Settlement.
    ?x dbo:birthPlace ?y.
    ?y dbo:country ?z.
  	?x dbo:deathPlace ?A.
}
```




### Q3

```SPARQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX dbo: <http://dbpedia.org/ontology/>
SELECT * WHERE {
    ?x rdf:type dbo:Athlete.
    ?y rdf:type dbo:Settlement.
    ?x dbo:birthPlace ?y.
    ?y dbo:country ?z.
  	?x dbo:deathPlace ?A.
  	?A dbo:country ?B.
}
```



## Q4

```SPARQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX dbo: <http://dbpedia.org/ontology/>
SELECT * WHERE {
    ?x rdf:type dbo:Athlete.
    ?y rdf:type dbo:Settlement.
    ?x dbo:birthPlace ?y.
    ?y dbo:deathPlace ?z.
}
```



## Q5

```SPARQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX dbo: <http://dbpedia.org/ontology/>
SELECT * WHERE {
  	?x rdf:type dbo:Athlete.
    ?z rdf:type dbo:Settlement.
    ?A rdf:type dbo:Movie.
    ?x dbo:occupation ?y.
    ?x dbo:deathPlace ?z.
    ?A dbo:director ?x.
}
```



## Q6

```SPARQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX dbo: <http://dbpedia.org/ontology/>
SELECT * WHERE {
  	?x rdf:type dbo:Athlete.
    ?z rdf:type dbo:Settlement.
    ?A rdf:type dbo:Movie.
  	?x dbo:birthPlace ?B
    ?x dbo:occupation ?y.
    ?x dbo:deathPlace ?z.
    ?A dbo:director ?x.
}
```
