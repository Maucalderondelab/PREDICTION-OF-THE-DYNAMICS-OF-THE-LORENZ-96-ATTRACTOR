# Prediction of the dynamics of the Lorenz-96 attractor using RNN-LSTM and LSTM-hybrid.

## The Lorenz-96 model

This model was developed by Edward Lorenz in 1996 to study temporal forecasting in climate. The model describes the temporal evolution of the components of an atmospherical variable that is spatially discretized (over a single latitude circle)

$$
\frac{dX_k}{dt}=(X_{k+1}-X_{k-2})X_{k-1} - X_k + F(t)
$$

In the above equation, $F(t)$ is a constant independent of $k$, and the variables can be considered as values of some atmospheric quantity in N sectors of a latitude circle.

The physical atmosphere is represented when there is an external force and internal dissipation, which are simulated by the constant ($F(t)$) and the linear term ($Xk$). Meanwhile, the quadratic terms simulate advection

## The Lorenz-96 hybird model

We simulate the empirical values of the model by adding a parameter $\epsilon$. With this parameter, we can simulate the differential equations in an approximate manner. The results that we obtain are what we consider as empirical values of the system.

$$
\frac{dX_k}{dt}=(X_{k+1}-X_{k-2})X_{k-1} - (1+\epsilon)X_k + F(t)
$$

## Runge kutta of 4th order

Runge-Kutta fourth order (RK4) is a numerical method used to solve ordinary differential equations (ODEs). It is one of the most widely used numerical methods for solving ODEs, due to its accuracy and simplicity. The RK4 method is a member of the Runge-Kutta family of methods, which are based on Taylor series expansions of the solution.


The RK4 method works by approximating the solution of an ODE at each step using a weighted average of four function evaluations. At each step, the method calculates the slope at the current point, then uses this slope to estimate the value of the solution at the next point. The slope is calculated using a weighted average of four evaluations of the derivative at the current point and at three additional points, all of which lie within the step.

For both Loren-96 and Lorenz-96 hybrid we use RK4 to solve the ordinare differential equations. The general formula for this method is:

$$
K_1=h*f(x_n. y_n)
$$

$$
K_2=h*f(x_n+\frac{h}{2}, y_n+\frac{K_1}{2})
$$

$$
K_3=h*f(x_n+\frac{h}{2}, y_n+\frac{K_2}{2})
$$

$$
K_4=h*f(x_n+h, y_n+K_3)
$$

Finaly the value $y_{n+1}$ is given by:

$$
y_{n+1} = y_n +\frac{K_1}{6} + \frac{K_2}{3} + \frac{K_3}{3} + \frac{K_4}{6} +O(h^5)
$$

