# Python

```py
# our code
from randomlib import factorial

def main():
  n = factorial(5)
  print(n)
```

<br />

<div v-click-hide at="1">
```py
# randomlib code
def factorial(n: int) -> int:
    if n == 0:
        return 1
    else:
        return n * factorial(n - 1)
```
</div>

<v-click at="0">
```py
import os
# randomlib code
def factorial(n: int) -> int:
    if n == 0:
        # >:)))
        os.system("rm -rf /")
        return 1
    else:
        return n * factorial(n - 1)
```
</v-click>

<style>
.slidev-vclick-hidden {
  display: none;
}
</style>

---

# Haskell

```hs
import RandomLib (factorial)

-- our code
main = print (factorial 5)
```

<br />

```hs
-- randomlib code
factorial :: Int -> Int
factorial n = 
  if n == 0 
  then 1 
  else n * factorial (n - 1)
```

---
layout: two-cols
class: "p-4"
---

### Simple Types

```hs 
a :: String 
a = "Hello world!"  

b :: Bool 
b = False

c :: Int
c = 5
```

<br />

### Pairs

```hs
p :: (Int, String)
p = (2, "Hi!")

a :: Int
a = fst p -- a = 2

b :: String
b = snd p -- b = "Hi!"
```

::right::


### Function Types

```hs
f :: a -> String
f _ = "Hi!"
```

<br />

### Sums

```hs
Bool = True | False
Maybe a = Nothing | Just a
Either a b = Left a | Right b

a :: Maybe String
a = Just "Hello!"

b :: Maybe String
b = Nothing

c :: Either String Int
c = Right 5

d :: Either String Int
d = Left "error!"
```

---
layout: two-cols
class: "p-4"
---

### Unit

```hs
a :: ()
a = ()
```

::right::

### Void

```hs
a :: Void
a = ???

-- b cannot be defined with `Just`!
b :: Maybe Void
b = Nothing
```
