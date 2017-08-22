

```python
def string_to_dict(record):
    """Works as long there no spaces between elements/records"""
    
    import re
    
    rec = '{"' +  re.sub('\s+', '"', record.strip().replace('\n', '","')).replace('=', ':') + '"}'
    return eval(rec)
```


```python
def string_to_json(record):
    """Works as long there no spaces between elements/records"""
    
    import re
    import json
    
    rec = '{"' +  re.sub('\s+', '"', record.strip().replace('\n', '","')).replace('=', ':') + '"}'
    return json.dumps(eval(rec))
```


```python
example_1 = """A = yes
B = true
C = 12.34
D = 92.34"""
```


```python
example_2 = """

A = yes
B = true
C = 12.34
D = 92.34

"""
```


```python
string_to_dict(example_1)
```




    {'A': 'yes', 'B': 'true', 'C': '12.34', 'D': '92.34'}




```python
string_to_dict(example_2)
```




    {'A': 'yes', 'B': 'true', 'C': '12.34', 'D': '92.34'}




```python
string_to_json(example_1)
```




    '{"A": "yes", "C": "12.34", "B": "true", "D": "92.34"}'




```python
string_to_json(example_2)
```




    '{"A": "yes", "C": "12.34", "B": "true", "D": "92.34"}'


