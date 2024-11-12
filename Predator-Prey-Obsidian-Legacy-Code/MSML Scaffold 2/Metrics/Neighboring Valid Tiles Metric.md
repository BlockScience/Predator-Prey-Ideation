- Domain of [[Locations Space]] that gives locations to query
- Uses [[MSML Scaffold 2/State Variables/Global State-Sites|Global State-Sites]]


```python
def check_location(position: tuple,
                   all_sites: np.matrix,
                   busy_locations: List[tuple]) -> List[tuple]:
    """
    Returns an list of available location tuples neighboring an given
    position location.
    """
    N, M = all_sites.shape
    potential_sites = [(position[0], position[1] + 1),
                       (position[0], position[1] - 1),
                       (position[0] + 1, position[1]),
                       (position[0] - 1, position[1])]
    potential_sites = [(site[0] % N, site[1] % M) for site in potential_sites]
    valid_sites = [site for site in potential_sites if site not in busy_locations]
    return valid_sites
```
