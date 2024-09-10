# MDP REPRESENTATION

## AIM:
The aim of this experiment is to create a Markov Decision Process (MDP) representation and implement it in Python to model the decision-making process in a manufacturing factory 

## PROBLEM STATEMENT:

### Problem Description
The problem is to develop a Reinforcement Learning model for product detection in a manufacturing factory. The model should determine whether a product is ready to be exported or faulty based on its features. The goal is to optimize the production process and reduce the number of faulty products while maximizing the number of products ready for export.

### State Space
{F,J,E} -> {0,1,2}

where,

F -> Faulty
J-Juction(decision making state)
E -> Export

### Sample State
Dimensions: (Length, Width, Height) = (10 cm, 5 cm, 2 cm). Weight: 100 grams. Color: Blue.

### Action Space
{F,E} -> {0,1} where, "E->Export" , "F->Mark as Faulty"

### Sample Action
E-> 1
product is ready for Export.

### Reward Function
R = { +10 for correctly exporting a ready product, -10 for exporting a faulty product}

### Graphical Representation
![alt text](<WhatsApp Image 2024-08-27 at 14.20.58_d3714b7b.jpg>)

## PYTHON REPRESENTATION:
```python
P = {
    0: {
        0: [(0.7, 0, 0.0, True), (0.3, 1, 0.0, False)],  
        1: [(0.6, 0, 0.0, True), (0.4, 1, 0.0, False)]   
    },
    1: {
        0: [(0.5, 0, 0.0, True), (0.5, 2, 1.0, False)], 
        1: [(0.9, 2, 1.0, True), (0.1, 0, 0.0, False)]  
    },
    2: {
        0: [(0.8, 2, 0.0, True), (0.2, 1, 0.0, False)],  
        1: [(1.0, 2, 0.0, True)]                         
    }
}

```
## OUTPUT:
```python
{0: {0: [(0.7, 0, 0.0, True), (0.3, 1, 0.0, False)],
  1: [(0.6, 0, 0.0, True), (0.4, 1, 0.0, False)]},
 1: {0: [(0.5, 0, 0.0, True), (0.5, 2, 1.0, False)],
  1: [(0.9, 2, 1.0, True), (0.1, 0, 0.0, False)]},
 2: {0: [(0.8, 2, 0.0, True), (0.2, 1, 0.0, False)], 1: [(1.0, 2, 0.0, True)]}}
```
## RESULT:
The provided problem is successfully modeled as an MDP. The state space, action space, and reward function are defined, and a Python simulation demonstrates how the model makes decisions to maximize rewards. This model can be further trained and refined to optimize the product detection process in the manufacturing factory.
