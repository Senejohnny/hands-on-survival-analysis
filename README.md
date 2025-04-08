# Hands-on Survival Analysis

## Introduction
Survival analysis, originally developed for healthcare mortality studies, has evolved into a versatile statistical method for analyzing time-to-event data across diverse fields from marketing & economy to sociology & engineering. Survival analysis potentials and use are often overlooked across descriptive, predictive, and prescriptive analytics. This lack of awareness often leads to employing suboptimal approaches when handling time-to-event problems. Specially, during partial information access due to missing data.

This introductory tutorial is prepared for practicing and aspiring data scientists and analysts who are interested in adding survival analysis into their toolkit. It provides a brief introduction to survival statistics. Through hands-on experience with the lifelines python library and notebook, participants will have dedicated time for Q&A and to execute the specification, fitting, and evaluation of models using a real-world dataset.


## 


- Building the book 
``` 
jupyter-book build .
``` 


- Running locally 
``` 
python3.11 -m http.server 8000 --directory _build/html
```
- Killing the running local host
``` 
kill -9 $(lsof -t -i:3000)
``` 

- Exporting the page to a remote repo github and run an action
```
ghp-import -n -p -f _build/html
```