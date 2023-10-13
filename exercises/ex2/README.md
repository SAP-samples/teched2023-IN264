# Exercise 2 - Exercise 2 Description

In this exercise, we will create...

## Exercise 2.1 Sub Exercise 1 Description

After completing these steps you will have created...
1)How to do a Save as New Project of the sample Employee Onboarding Process Project
2)Add parallel branches to add new Training and Equipment determination rules
3)Configure the decision to determine Equipments for the newly hired employee
4) Configure the decision to determine Trainings for the newly hired employee
5) Add Action based on CAP Service
6) Release and Deploy
7) Run the Process

1. Click here.
<br>![](/exercises/ex2/images/02_01_0010.png)

2.	Insert this line of code.
```abap
response->set_text( |Hello ABAP World! | ). 
```



## Exercise 2.2 Sub Exercise 2 Description

After completing these steps you will have...

1.	Enter this code.
```abap
DATA(lt_params) = request->get_form_fields(  ).
READ TABLE lt_params REFERENCE INTO DATA(lr_params) WITH KEY name = 'cmd'.
  IF sy-subrc = 0.
    response->set_status( i_code = 200
                     i_reason = 'Everything is fine').
    RETURN.
  ENDIF.

```

2.	Click here.
<br>![](/exercises/ex2/images/02_02_0010.png)

## Summary

You've now ...

Continue to - [Exercise 3 - Excercise 3 ](../ex3/README.md)
