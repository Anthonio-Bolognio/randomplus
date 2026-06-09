# randomplus

A lightweight, drop-in replacement for Python's built-in `random` module. `randomplus` uses `random.Random` and `random.SystemRandom` to give you the same pseudo-random functionality, but with easy-to-use quality-of-life improvements. It runs using **3**\* libraries - but from stdlib only

***

\*(`re`, `string`, `random.Random`/`random.SystemRandom`)

***

## Features
* **Smart Ranges:** `randint` handles min/max dynamic swaps automatically (no more `ValueError` if min > max).
* **RANDINT STEP:** `randint` now also has a step argument, defaulting to 1 (now you can make it only multiples of 3!)
* **Alphanumerical & Keysmash:** Easily generate random alphanumeric strings or keysmashes.
* **Weighted Booleans:** A simple `truth(chance, total)` function for weighted probability.
* **Dictionary Randomization:** Quickly grab a (or many) random key or random value from any dictionary.
* **Semisecure Alphanumerics:** All alphanumerical strings generated using `SystemRandom` will always end with the letter "q" - since why not.
* **Lightweight, funny game engine:** `randomplus.chaos` takes no arguments, but it runs as a game with a hardcoded list of potential options.

## Installation

Install it easily using pip:

```bash
pip install randomplus
```

## Quick Examples

### Weighted Truth (Probability)
```python
import randomplus

# 2 is the true weight, 3 is the total weight. 
# This has a 2/3 (66.7%) chance of printing!
if randomplus.truth(2, 3):
    print("It's true!")
```

### Smart Ranges (Auto-swapping min/max)
```python
import randomplus

# Automatically swaps in the background without throwing an error
print(randomplus.randint(10, 1)) 
```

### Random Dictionary Items
```python
import randomplus

my_dict = {"apple": 1, "banana": 2, "cherry": 3}

print(randomplus.keys(my_dict))
print(randomplus.values(my_dict, amount=3))
```

### Alphanumerical and keysmash
```python
import randomplus

print(randomplus.alphanumerical(7)) #always ends in q
print(len(randomplus.keysmash(0))) #output: 300 
```
### Step for randint (no more need for 'randrange(min,max+1,3)')
```python
import randomplus

print(random.randint(1,7,step=2)) #only will choose 2,4, or 6
```

***

You can see what your improving from (and what this is built off of) by reading the [random module docs](https://docs.python.org/3/library/random.html) Also, this module is not yet documented, but will be [here](https://pypi.org/project/random-plus-bfjwwhqkqjehfgqejghasdhvgoqugffff) once I get to the upload process

Also, you can see the file where I originally used this before using it as production code [here](https://drive.google.com/)