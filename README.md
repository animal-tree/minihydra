<img width="50%" alt="logo" src="https://github.com/animal-tree/minihydra/assets/142250284/5de30581-c323-4c74-8e50-5bb91cd89b1e">

```console
pip install minihydra
```

### Reading in args

```python
# run.py

from minihydra import just_args

args = just_args()

print(args, '\n')
print(args.hello)
print(args.number)
print(args.goodbye.cruel)
```

```
> python run.py hello=world number=42 goodbye.cruel='[world]'

{'hello': 'world', 'number': 42, {'goodbye': {'cruel': ['world']}}}

world
42
[world]
```

### Via yaml

```yaml
# path/to/args.yaml

hello: world
number: 42
goodbye:
  cruel: 
    - world
```

```python
# run.py

from minihydra import just_args

args = just_args(source='path/to/args.yaml')

print(args, '\n')
print(args.hello)
print(args.number)
print(args.goodbye.cruel)
```

```
> python run.py number=43

{'hello': 'world', 'number': 43, {'goodbye': {'cruel': ['world']}}}

world
43
[world]
```

### As a decorator

```python
# run.py

from minihydra import get_args

@get_args(source='path/to/args.yaml')
def main(args):
    print(args)

if __name__ == '__main__':
    main()
```

```
> python run.py

{'hello': 'world', 'number': 42, {'goodbye': {'cruel': ['world']}}}
```

### Advanced

**Further features include literals, function calls, instantiation, imports, interpolation, custom grammars, expanding module and yaml search paths, project directory inference, instantiation tinkering-syntax inference, portals, and pseudonyms.**

For deeper documentation, please consider [sponsoring](https://github.com/sponsors/animal-tree).

[//]: # (:fleur_de_lis:)

[//]: # (### Literals: )

[//]: # (lists, dicts, floats, ints, booleans, null, inf, strings; put lists and dicts in quotes)

[//]: # ()
[//]: # (### imports)

[//]: # (Or via reserved task= keyword argument)

[//]: # ()
[//]: # (### instantiate)

[//]: # (Path/To.py -> Cow "Moo")

[//]: # (signature matching)

[//]: # ()
[//]: # (### interpolation)

[//]: # ()
[//]: # (### grammars)

[//]: # ()
[//]: # (### yaml search paths)

[//]: # (project directory inference, instantiation tinkering inference, portals, pseudonyms)

<img width="60%" alt="logo" src="https://github.com/animal-tree/minihydra/assets/142250284/77803168-0569-4b53-92a7-d62193f30083">

[Licensed under the MIT license.](MIT_LICENSE)
