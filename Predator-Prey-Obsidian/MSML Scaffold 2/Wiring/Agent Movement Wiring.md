- All [[Agent Movement Wiring|agents move]] (if possible) to an available random neighboring location.

## Legacy Code

```python
def move_agents(params, substep, state_history, prev_state):
    """
    Move agents.
    """
    sites = prev_state['sites']
    agents = prev_state['agents']
    busy_locations = [agent['location'] for agent in agents.values()]
    new_locations = {}
    for label, properties in agents.items():
        new_location = get_free_location(properties['location'], sites, busy_locations)
        if new_location is not False:
            new_locations[label] = new_location
            busy_locations.append(new_location)
        else:
            continue
    return {'update_agent_location': new_locations}
```

Can add in a [[Free Locations Metric]]
Uses [[Update Agent Locations Mechanism]]