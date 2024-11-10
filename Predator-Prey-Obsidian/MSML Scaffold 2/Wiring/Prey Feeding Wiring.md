## Legacy Code


```python
def feed_prey(params, substep, state_history, prev_state):
    """
    Feeds the hungry prey with all food located on its site.
    """
    agents = prev_state['agents']
    sites = prev_state['sites']
    preys = {k: v for k, v in agents.items() if v['type'] == 'prey'}
    hungry_preys = {label: properties for label, properties in preys.items()
                    if properties['food'] < params['hunger_threshold']}

    agent_delta_food = {}
    site_delta_food = {}
    for label, properties in hungry_preys.items():
        location = properties['location']
        available_food = sites[location]
        agent_delta_food[label] = available_food
        site_delta_food[location] = -available_food

    return {'agent_delta_food': agent_delta_food,
            'site_delta_food': site_delta_food}```

