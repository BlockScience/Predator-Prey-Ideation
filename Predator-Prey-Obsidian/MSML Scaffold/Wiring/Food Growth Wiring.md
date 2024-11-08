- Food is grown on every site

## Legacy Code

```python
def grow_food(params, substep, state_history, prev_state):
    """
    Increases the food supply in all sites, subject to an maximum.
    """
    regenerated_sites = calculate_increment(prev_state['sites'],
                                          params['food_growth_rate'],
                                          params['maximum_food_per_site'])
    return {'update_food': regenerated_sites}```