---
title       : Introduction to SAS
description : This course will provide an intro to SAS.
attachments :
  slides_link : 

---
## Introduction to SAS

```yaml
type: MultipleChoiceExercise
lang: sql
xp: 50
skills: 1
key: bd86b99f37
```

Welcome to the course! Here are some interesting facts about SAS:

* Developed in the early 1970s at North Carolina State
University
* Originally intended for management and analysis of
agricultural field experiments
* Now the most widely used statistical software
* Used to stand for “Statistical Analysis System”, now it is not
an acronym for anything
* Pronounced “sass”, not spelled out as three letters.

`@pre_exercise_code`
```{sql}
# The pre exercise code runs code to initialize the user's workspace.
# You can use it to load packages, initialize datasets and draw a plot in the viewer

connect('postgresql', 'films')
```

`@instructions`
- Statistical Analysis Software
- Statistical Analysis System
- Special Air Service
- Shopping Analysis System

`@hint`
It's not the *Special Air Service*!

`@sct`
```{python}
# SCT written with sqlwhat: https://github.com/datacamp/sqlwhat/wiki
msg_bad = 'Nope, you are off track!'
msg_success = 'Correct, you are smashing it!'

Ex().test_mc(2,[msg_bad, msg_bad, msg_success, msg_bad])
```

---
## SAS Products

```yaml
type: NormalExercise
lang: sql
xp: 100
skills: 1
key: 93f3637144
```

SAS consists of a number of products including:

- Base SAS - data management and basic procedures
- SAS/STAT - statistical analysis
- SAS/GRAPH - presentation quality graphics
- SAS/OR - Operations research
- SAS/ETS - Econometrics and Time Series Analysis
- SAS/IML - interactive matrix language

Let's start by taking a look at Proc SQL.

If you submit the code to the right, you'll see that you get two types of errors.

_SQL_ errors are shown below the editor. These are errors returned by the _SQL_ engine. You should see:

```
syntax error at or near "'DataCamp <3 SQL'" LINE 2: 'DataCamp <3 SQL' ^
```
<br>
_DataCamp_ errors are shown in the **Instructions** box. These will let you know in plain English where you went wrong in your code! You should see:

```
You need to add SELECT at the start of line 2!
```

`@instructions`
Submit the code to the right, check out the errors, then fix them!

`@hint`
In the editor, change line 2 to `SELECT 'DataCamp <3 SQL'`.

`@pre_exercise_code`
```{python}
connect('postgresql', 'films')
```

`@sample_code`
```{sql}
-- Try running me!
'DataCamp <3 SQL'
AS result;
```

`@solution`
```{sql}
-- Try running me!
SELECT 'DataCamp <3 SQL'
AS result;
```

`@sct`
```{sql}
Ex().test_student_typed('SELECT|select', msg='You need to add `SELECT` at the start of line 2!')
Ex().test_has_columns()
Ex().test_error()
```