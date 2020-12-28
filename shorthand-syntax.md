## Design

- Brackets of outer layers can be ignored
- "=" key-value separator need to be used with the " " separator, " " separator is supported in first level
- ":" key-value separator need to be used with the "," separator, "," separator is supported in sub levels
- Support "append" action for array argument 

## Argument Pattern: Single value

```json
"value"
```

```bash
--param value
```

## Argument Pattern: Simple Array

```json
[
    "A",
    "B",
    "C"
]
```

```bash
--list-param A B C
```

```bash
--list-param A,B,C
```

## Argument Pattern: Object

```json
{
    "name": "device-1",
    "year": "2020",
    "properties": {"serial": "abc", "count": 3}
}
```

```bash
--object-param name=device-1 year=2020 properties={serial:abc,count:3}
```

```bash
--object-param name:device-1,year:2020,properties:{serial:abc,count:3}
```

## Argument Pattern: Single Object Array

```json
[{
    "name": "device-1",
    "year": "2020",
    "properties": {"serial": "abc", "count": 3}
}]
```

```bash
--object-list-param name=device-1 year=2020 properties={serial:abc,count:3}
```

```bash
--object-list-param name:device-1,year:2020,properties:{serial:abc,count:3}
```

## Argument Pattern: Multiply Object Array

```json
[
    {"name": "device-1", "year": "2020", "properties": {"serial": "abc", "count": 3}},
    {"name": "device-2", "year": "2021", "properties": {"serial": "def", "count": 1}},
]
```

```bash
--object-list-param name=device-1 year=2020 properties={serial:abc,count:3}
--object-list-param name=device-2 year=2021 properties={serial:def,count:1}
```

```bash
--object-list-param name:device-1,year:2020,properties:{serial:abc,count:3}
--object-list-param name:device-2,year:2021,properties:{serial:def,count:1}
```

```bash
--object-list-param name:device-1,year:2020,properties:{serial:abc,count:3} name:device-2,year:2021,properties:{serial:def,count:1}
```
