- Domain of [[Locations Space]] that gives locations to query


## Legacy Code

```python
def nearby_agents(location: tuple, agents: Dict[str, dict]) -> Dict[str, dict]:
    """
    Filter the non-nearby agents.
    """
    neighbors = {label: agent for label, agent in agents.items()
                 if is_neighbor(agent['location'], location)}
    return neighbors
```