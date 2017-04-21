# Literal String Interpolation
- PEP 498에 정의되어있다
- python 3.6 부터 사용이 가능하다

```python
>>> from datetime import datetime
>>> now = datetime.now()
>>> name = 'Claude'
>>> age = 22
>>> f'my name is {name}, my age is {age}, today is {now: %Y-%m-%d %H:%M:%S}'
'my name is Claude, my age is 22, today is  2017-04-21 11:29:47'
```

## escape
```python
>>> foo = 'test'
>>> f'{foo} {{bar}}'
'test {bar}'
```

## 참고
- https://www.python.org/dev/peps/pep-0498/