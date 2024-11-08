Original link: https://github.com/cadCAD-org/demos/blob/master/demos/Agent_Based_Modeling/prey_predator_abm/model/partial_state_update_block.py

## Code

```python
from .parts.environment import *
from .parts.agents import *

partial_state_update_block = [
    {
        # environment.py
        'policies': {
            'grow_food': grow_food
        },
        'variables': {
            'sites': update_food
        }
    },
    {
        # agents.py
        'policies': {
            'increase_agent_age': digest_and_olden
        },
        'variables': {
            'agents': agent_food_age

        }
    },
    {
        # agents.py
        'policies': {
            'move_agent': move_agents
        },
        'variables': {
            'agents': agent_location

        }
    },
    {
        # agents.py
        'policies': {
            'reproduce_agents': reproduce_agents

        },
        'variables': {
            'agents': agent_create

        }
    },
    {
        # agents.py
        'policies': {
            'feed_prey': feed_prey
        },
        'variables': {
            'agents': agent_food,
            'sites': site_food
        }
    },
    {
        # agents.py
        'policies': {
            'hunt_prey': hunt_prey
        },
        'variables': {
            'agents': agent_food
        }
    },
    {
        # agents.py
        'policies': {
            'natural_death': natural_death
        },
        'variables': {
            'agents': agent_remove
        }
    }
]
```


## Notes

Looking at the legacy code, we can find that the following wirings and mechanisms should be in our future model:

1. [[Food Growth Wiring]]
	1. [[Update Food Mechanism]]
2. [[Increase Agent Age Wiring]]
	1. [[Update Agents Mechanism]]
3. [[Agent Movement Wiring]]
	1. [[Update Agent Locations Mechanism]]
4. [[Agent Reproduction Wiring]]
	1. [[Create Agents Mechanism]]
5. [[Prey Feeding Wiring]]
	1. [[Update Agents Mechanism]]
	2. [[Update Food Locations Mechanism]]
6. [[Hunt Prey Wiring]]
	1. [[Update Agents Mechanism]]
7. [[Natural Death Wiring]]
	1. [[Update Agents Mechanism]]