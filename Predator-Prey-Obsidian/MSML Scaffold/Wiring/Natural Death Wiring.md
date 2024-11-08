#WIP 
## Legacy Code

```python
def natural_death(params, substep, state_history, prev_state):
    """
    Remove agents which are old or hungry enough.
    """
    agents = prev_state['agents']
    maximum_age = params['agent_lifespan']
    agents_to_remove = []
    for agent_label, agent_properties in agents.items():
        to_remove = agent_properties['age'] > maximum_age
        to_remove |= (agent_properties['food'] <= 0)
        if to_remove:
            agents_to_remove.append(agent_label)
    return {'remove_agents': agents_to_remove}
```