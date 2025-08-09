# Prompt
The purpose of this Project is to simulate a BIOREACTOR WITH SUBSTRATE INHIBITION.This Project was done in five folds or steps:
i)Simulate the continuous bioreactor for a time frame with fixed inputs.
ii)Simulate the continuous bioreactor with a step response in flow rate.
iii)Fit baseline maximum growth rate, µmax (mu_max), given set of data.
iv)Fit growth kinetics for max growth rate µmax, the Monod Constant, K, and inhibition factor Ki.
v) Optimize Fin for best production.
Below are the links to every step respectively.

# Modeling Equations:


μ=(μ_max S)/(K+S+S^2/K_i )
dX/dt=F_in/V (X_in-X)+μX
dS/dt=F_in/V (S_in-S)-Y_SX μX
dP/dt=F_in/V (P_in-P)+Y_PX μX

# Simulation Parameters
t_end=100; % total simulation hrs

# Initial Conditions:
X(1)= 0.1;% g cells/ L
S(1)= 20;% g substrate/ L
P(1)= 0;% g protein /L

# Nominal Parameter Values (To Be Fitted):
mu_max = 0.5;% maximum growth rate h-1
K= 20;% Monod growth constant g substrate/L
Ki= 50;% Substrate inhibition growth constant g substrate/L

# Input 
Fin=100;% feed flow rate L/hr


#  Parameters:
V=1000;% bioreactor volume L
YSX = 1.5;% yield g substrate/ g cells
YPX = 0.5;% yield g protein/ g cells
Xin = 0;% feed biomass concentration g cells/L
Sin = 80;% feed substrate concentration g substrate/L
Pin = 0;% feed protein concentration g protein/L
# Optimization
Objective Function for Production:
Production here is the sum of protein product produced, P, over the whole run.  The formula to calculate this is straightforward the volumetric flowrate, Fin, times the exit protein concentration at that sample time P(i) times the duration of sample, delt, all summed over the run. Goal is to maximize this amount. 
## Prod=Prod+Fin*P(i)*delt
Use the best set of parameters found in Part 5 as your base model to be optimized for production. Here only maximizing a fixed flowrate, Fin so no need for a graph of Fin just embed the best production and Fin in the title.  So could use best parameters from part 5 and start with Part 4 ic since it has one for loop for trying different combinations for different combinations of mu_max which you can hijack and switch to different combinations of Fin.  

