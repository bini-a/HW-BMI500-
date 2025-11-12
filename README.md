

#  Homework 11 BMI 500 - Model-based Machine Learning

##  Biniam Garomsa 
 bgaroms@emory.edu

### Question Number 2
### Key Insights
- Measures such as social distancing and restrictive interventions help with reducing the maximum number of infected agents at the same time, which will directly impact healthcare by avoiding overburden and better survival. 
- Comparative and sensitivy analysis using environments with and without social distance shows that infection rates and the timing of infection peaks are slower with social distancing.

- Our model is very simplistic and lacks robustness, which means the results are not directly applicable to real world without further validation.  
### Comparative Model performance

We created a 75×75  grid and populated with 100 agents, initialized randomly (95 agents as susceptible, 5 agents as infected and 0 agents as recovered).
#### A. Base Model
We then run our base model for 200 steps starting recording the subgroup population at each step. Below is our  result.   p is the probability that the susceptible agent becomes infected. q is the probability of recovering at each time step, after which they
transition to the recovered state.
<table align="center">
  <tr>
    <td><img src="Base model p:0.05, q:0.02.png" width="230"><br><b>p=0.05, q=0.02</b></td>
    <td><img src="Base model p:0.05, q:0.05.png" width="230"><br><b>p=0.05, q=0.05</b></td>
    <td><img src="Base model p:0.1, q:0.02.png"  width="230"><br><b>p=0.1, q=0.02</b></td>
    <td><img src="Base model p:0.1, q:0.05.png"  width="230"><br><b>p=0.1, q=0.05</b></td>
  </tr>
</table>



Higher p resulted in slightly higher infection rates, faster time to peak and larger recovered population. On the other hand, Higher q resulted in lower infection rates, faster time to peak and slightly smaller recovered population. 


Rerunning the base model simulation with other random initial conditions and averaging the population subgroup count results in the figure below. Now the curves are smoother, and the trend shows decreasing infection spread coupled with increasing recovery while the susceptible population stays almost the same. 
<table align="center">
  <tr>
    <td><img src="AVERAGED Base model.png" width="350"><br><b></b></td>

  </tr>
</table>

#### B. Extending the Model: Social Distancing and Intervention Strategies

We further introduced changes to model social distancing and intervention strategious. First, we introduced a reduced probability of moving at each step by favoring the probability of agents staying (p(STAY) = 80%) at the same place and lowering movement to neighbroing cells. Second, to simulate agents actively moving away from cells with infected individuals, we reduced the   probability p that
the susceptible agent becomes infected. Sample runs for 200 trials with different p and q values are shown below.


<table align="center">
  <tr>
    <td><img src="Social Distancing p:0, q:0.05.png" width="230"><br><b>p=0, q=0</b></td>
    <td><img src="Social Distancing p:0.05, q:0.05.png" width="230"><br><b>p=0.05, q=0</b></td>
    <td><img src="Social Distancing p:0.08, q:0.05.png" width="230"><br><b>p=0.08, q=0</b></td>
    <td><img src="Social Distancing p:0.1, q:0.05.png" width="230"><br><b>p=0.1, q=0</b></td>
  </tr>
</table>
The result shows that reducing probability of moving to different cells (which correspond to enforcing social distancing) correlates with the maximum number of infections at each time window. We also rerun the extended model simulation with  random initial conditions and averaged the subgroup count results in the figure below. 

<table align="center">
  <tr>
    <td><img src="AVERAGED Social Distancing model.png" width="350"><br><b></b></td>


  </tr>
</table>

#### Analyze and Compare Results 

Then, we did a comparative analysis between the results of the two models keeping the p and q values same for both. The first panel shows the results from the base model. The lower panel shows the results from extended model with social distancing.

- Base model
<table align="center">
  <tr>
    <td><img src="Base model p:0, q:0.05.png" width="230"><br><b>p=0, q=0</b></td>
    <td><img src="Base model p:0.05, q:0.05.png" width="230"><br><b>p=0.05, q=0</b></td>
    <td><img src="Base model p:0.08, q:0.05.png" width="230"><br><b>p=0.08, q=0</b></td>
    <td><img src="Base model p:0.1, q:0.05.png" width="230"><br><b>p=0.1, q=0</b></td>
  </tr>
</table>
<table align="center">
  <tr>
    <td><img src="Base model p:0.05, q:0.02.png" width="230"><br><b>p=0.05, q=0.02</b></td>
    <td><img src="Base model p:0.05, q:0.05.png" width="230"><br><b>p=0.05, q=0.05</b></td>
    <td><img src="Base model p:0.1, q:0.02.png"  width="230"><br><b>p=0.1, q=0.02</b></td>
    <td><img src="Base model p:0.1, q:0.05.png"  width="230"><br><b>p=0.1, q=0.05</b></td>
  </tr>
</table>
- Extended model (social distancing + intervention)

<table align="center">
  <tr>
    <td><img src="Social Distancing p:0, q:0.05.png" width="230"><br><b>p=0, q=0</b></td>
    <td><img src="Social Distancing p:0.05, q:0.05.png" width="230"><br><b>p=0.05, q=0</b></td>
    <td><img src="Social Distancing p:0.08, q:0.05.png" width="230"><br><b>p=0.08, q=0</b></td>
    <td><img src="Social Distancing p:0.1, q:0.05.png" width="230"><br><b>p=0.1, q=0</b></td>
  </tr>
</table>

The  peak number of infected individuals is  smaller in the simulation with social distancing. The time it takes for the infection to peak is  slower with social distancing, especially for higher p. The time for infection peak is faster for simulation without social distancing. There is an overall higher infection spread and duration in the case of no social distancing , while with social distancing the it is lower.

This indicates that social distancing is beneficial for real-world public helath interventions. It helps curb the infection rate and reduce the maximum number of infected patients at a time, which in turn allows to avoid healthcare overload and mortality.
#### Additional Sensitivity Analysis
<table align="center">
  <tr>
    <td align="center"><img src="p_0.08, q_0.05 Movement-prob_0.12.png" width="220"><br><b>Movement prob = 0.12</b></td>
    <td align="center"><img src="p_0.08, q_0.05 Movement-prob_0.28.png" width="220"><br><b>Movement prob = 0.28</b></td>
    <td align="center"><img src="p_0.08, q_0.05 Movement-prob_0.4.png" width="220"><br><b>Movement prob = 0.40</b></td>
    <td align="center"><img src="p_0.08, q_0.05 Movement-prob_0.52.png" width="220"><br><b>Movement prob = 0.52</b></td>
    <td align="center"><img src="p_0.08, q_0.05 Movement-prob_0.6.png" width="220"><br><b>Movement prob = 0.60</b></td>
  </tr>
  <tr>
    <td align="center"><img src="p_0.08, q_0.05 Movement-prob_0.68.png" width="220"><br><b>Movement prob = 0.68</b></td>
    <td align="center"><img src="p_0.08, q_0.05 Movement-prob_0.76.png" width="220"><br><b>Movement prob = 0.76</b></td>
    <td align="center"><img src="p_0.08, q_0.05 Movement-prob_0.84.png" width="220"><br><b>Movement prob = 0.84</b></td>
    <td align="center"><img src="p_0.08, q_0.05 Movement-prob_0.92.png" width="220"><br><b>Movement prob = 0.92</b></td>
  </tr>
</table>

When the movement probability was lowered, the infection spread slighlty slower and later than the when the probablity was higher. For low movement simulations, the infection peak is reached slower and accompanied by slower recovery rates.




### Suggestions for future modeling improvements

Our current model is very simplistic currently. It does not account for real world variablities such as population movement within and outside their community, asymptomatic infected individuals, and presence of places with large group of people such as schools and bars where infections are highly likely. 

Moreover, the current environment setting of 75*75 grid did not allow for high interaction between the angels even when the probability of moving is set high. We tried a different setting where the grid is updated to 30*30 where more interaction and variability was observed as shown in the figure below.

<table align="center">
  <thead>
    <tr>
      <th></th>
      <th>p = 0</th>
      <th>p = 0.05</th>
      <th>p = 0.08</th>
      <th>p = 0.10</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><b>Modified Base</b></td>
      <td align="center">
        <img src="Modified Base model p:0, q:0.png" width="230"><br>
        <span>base</span>
      </td>
      <td align="center">
        <img src="Modified Base model p:0.5, q:0.png" width="230"><br>
        <span>base</span>
      </td>
      <td align="center">
        <img src="Modified Base model p:0.8, q:0.png" width="230"><br>
        <span>base</span>
      </td>
      <td align="center">
        <img src="Modified Base model p:1, q:0.png" width="230"><br>
        <span>base</span>
      </td>
    </tr>
    <tr>
      <td><b>Modified Social Distancing</b></td>
      <td align="center">
        <img src="Modified Social Distancing p:0, q:0.png" width="230"><br>
        <span>social distancing</span>
      </td>
      <td align="center">
        <img src="Modified Social Distancing p:0.05, q:0.png" width="230"><br>
        <span>social distancing</span>
      </td>
      <td align="center">
        <img src="Modified Social Distancing p:0.08, q:0.png" width="230"><br>
        <span>social distancing</span>
      </td>
      <td align="center">
        <img src="Modified Social Distancing p:0.1, q:0.png" width="230"><br>
        <span>social distancing</span>
      </td>
    </tr>
  </tbody>
</table>

Disclaimer: CHATPGT-5 was/were used to complete
HW #2.A to write a starter code for printing grid output for debugging and align images in this readme file.
