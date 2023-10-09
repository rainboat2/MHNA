# Workload Queries

## 低选择性查询(W1)
### Q1

```SPARQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX ub: <tju:#>
SELECT * WHERE {
    ?X rdf:type ub:GraduateStudent .
    ?X ub:takesCourse ?Y .
}
```

### Q2

```SPARQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX ub: <tju:#>
SELECT * WHERE {
	?X rdf:type ub:GraduateStudent .
	?Y rdf:type ub:GraduateCourse .
	?X ub:takesCourse ?Y .
	?X ub:name ?Z .
}
```

### Q3

```SPARQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX ub: <tju:#>
SELECT * WHERE {
	?X rdf:type ub:UndergraduateStudent .
	?X ub:takesCourse ?Y .
}
```

### Q4

```SPARQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX ub: <tju:#>
SELECT * WHERE {
	?X ub:worksFor ?Y .
	?Y ub:subOrganizationOf ?Z .
	?A ub:advisor ?X .
}
```

### Q5

```SPARQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX ub: <tju:#>
SELECT * WHERE {
	?Y rdf:type ub:Department .
	?X ub:worksFor ?Y .
	?Y ub:subOrganizationOf ?Z .
}
```

### Q6

```SPARQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX ub: <tju:#>
SELECT * WHERE {
	?X ub:name ?Y1 .
	?X ub:emailAddress ?Y2 .
	?X ub:telephone ?Y3 .
	?X ub:memberOf ?Y4.
}
```

### Q7

```SPARQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX ub: <tju:#>
SELECT * WHERE {
	?X rdf:type ub:ResearchGroup .
	?X ub:subOrganizationOf ?Y .
}
```

### Q8

```SPARQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX ub: <tju:#>
SELECT * WHERE {
    ?X rdf:type ub:GraduateStudent .
    ?X ub:takesCourse ?Z .
    ?B ub:teacherOf ?Z .
    ?X ub:memberOf ?Y .
    ?Y ub:subOrganizationOf ?A .
}
```



## 高选择性查询(W2)

### Q9
```SPARQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX ub: <tju:#>
SELECT * WHERE {
	?x rdf:type ub:GraduateStudent . 
	?x ub:takesCourse <http://www.Department0.University0.edu/GraduateCourse0>
}
```

### Q10

```SPARQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX ub: <tju:#>
SELECT * WHERE {
	?x rdf:type ub:Publication . 
	?x ub:publicationAuthor <http://www.Department0.University0.edu/AssistantProfessor0> .
}
```

### Q11

```SPARQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX ub: <tju:#>
SELECT * WHERE {
  ?x ub:worksFor <http://www.Department0.University0.edu> . 
  ?x ub:name ?n . 
  ?x ub:emailAddress ?em . 
  ?x ub:telephone ?t . 
  ?x rdf:type ub:FullProfessor.
}
```

### Q12

```SPARQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX ub: <tju:#>
SELECT * WHERE {
  ?x rdf:type ub:GraduateStudent .
  ?x ub:memberOf <http://www.Department0.University0.edu>
}
```

### Q13

```SPARQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX ub: <tju:#>
SELECT * WHERE {
  ?x rdf:type ub:GraduateStudent . 
  ?y rdf:type ub:GraduateCourse . 
  ?x ub:takesCourse ?y . 
  <http://www.Department0.University0.edu/AssistantProfessor0> ub:teacherOf ?y .
}
```

### Q14

```SPARQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX ub: <tju:#>
SELECT * WHERE {
  ?x rdf:type ub:GraduateStudent . 
  ?y rdf:type ub:Department . 
  ?x ub:memberOf ?y . 
  ?x ub:emailAddress ?em . 
  ?y ub:subOrganizationOf <http://www.University0.edu> .
}
```

### Q15

```SPARQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX ub: <tju:#>
SELECT * WHERE {
	?X rdf:type ub:ResearchGroup .
	?X ub:subOrganizationOf ?Y .
	?Y ub:subOrganizationOf <http://www.University0.edu> .
}
```

### Q16

```SPARQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX ub: <tju:#>
SELECT * WHERE {
	?X rdf:type ub:GraduateCourse . 
	<http://www.Department0.University0.edu/GraduateStudent0> ub:takesCourse ?X .
}
```