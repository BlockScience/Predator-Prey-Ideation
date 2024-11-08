## Legacy Code

```python
def hunt_prey(params, substep, state_history, prev_state):
    """
    Feeds the hungry predators with an random nearby prey.
    """
    agents = prev_state['agents']
    sites = prev_state['sites']
    hungry_threshold = params['hunger_threshold']
    preys = {k: v for k, v in agents.items()
             if v['type'] == 'prey'}
    predators = {k: v for k, v in agents.items()
                 if v['type'] == 'predator'}
    hungry_predators = {k: v for k, v in predators.items()
                        if v['food'] < hungry_threshold}
    agent_delta_food = {}
    for predator_label, predator_properties in hungry_predators.items():
        location = predator_properties['location']
        nearby_preys = nearby_agents(location, preys)
        if len(nearby_preys) > 0:
            eaten_prey_label = random.choice(list(nearby_preys.keys()))
            delta_food = preys.pop(eaten_prey_label)['food']
            agent_delta_food[predator_label] = delta_food
            agent_delta_food[eaten_prey_label] = -1 * delta_food
        else:
            continue

    return {'agent_delta_food': agent_delta_food}
```
