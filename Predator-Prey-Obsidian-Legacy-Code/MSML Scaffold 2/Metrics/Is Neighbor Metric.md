- Domain of [[Locations Space]] that gives locations to query
- Uses [[MSML Scaffold 2/State Variables/Global State-Sites|Global State-Sites]]
## Legacy Code

```python
def is_neighbor(location_1: tuple, location_2: tuple) -> bool:
    dx = np.abs(location_1[0] - location_2[0])
    dy = (location_1[1] - location_2[0])
    distance = dx + dy
    if distance == 1:
        return True
    else:
        return False
```
