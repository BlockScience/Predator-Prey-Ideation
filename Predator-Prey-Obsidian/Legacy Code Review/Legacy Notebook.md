Original link: https://github.com/cadCAD-org/demos/blob/master/demos/Agent_Based_Modeling/prey_predator_abm/Predator_Prey_ABM_model.ipynb
## Predator Prey Agent-based modeling

There are a lot of possible ABMs for any given phenomenon. cadCAD allows you to add, modify and remove simulation blocks and steps at will.

For this demo, we'll adopt a model based on a grid world, on which preys and predators take the following actions at each [[Agent State-Age|timestep of their lives]]:

1. [[Food Growth Wiring|Food is grown]] on every [[Global State-Sites|site]].
2. All [[Agent|agents]] [[Increase Agent Age Wiring|digest some of the food on their stomach and get older]].
3. All agents move (if possible) to an available random neighboring location.
4. The agents reproduce themselves if there is an available partner nearby
5. The prey agents feed on the available food
6. The predator agents hunts the nearby preys
7. All old enough agents die

There is an inherent stochastic nature on this model, and every time that you run it, we'll have a completely different result for the same parameters. But we can see that there is sort of a random equilibrium that converges to the dynamical equilibrium which we presented on the dynamical simulation.

ABMs tend to produce rich, high density datasets. We'll plot some of this data, but invite the reader to fork this repository and trace the network relations between the agents, or the geospatial statistics around the ABM, for example.