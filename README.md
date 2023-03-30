# Prediction of the dynamics of the Lorenz-96 attractor using RNN-LSTM and LSTM-hybrid.

## The Lorenz-96 model

This model was developed by Edward Lorenz in 1996 to study temporal forecasting in climate. The model describes the temporal evolution of the components of an atmospherical variable that is spatially discretized (over a single latitude circle)

$$
\frac{dX_k}{dt}=(X_{k+1}-X_{k-2})X_{k-1} + X_k + F(t)
$$

In the above equation, $F(t)$ is a constant independent of $k$, and the variables can be considered as values of some atmospheric quantity in N sectors of a latitude circle.

The physical atmosphere is represented when there is an external force and internal dissipation, which are simulated by the constant ($F(t)$) and the linear term ($Xk$). Meanwhile, the quadratic terms simulate advection
