# Strongly Typed FP

<div v-click-hide>

what???

</div>

<div v-click>

<h2>💻 Functional Programming </h2>

- Pure functions
- No side effects
- No mutable state

</div>

<br />

<div v-click>

<h2>💪 Strongly Typed</h2>

- All values have a type
- All types are known at compile time (not runtime)
- Powerful type system (products and sum types, functions, etc)

</div>

---

# Purity: Haskell vs. Python

```hs
-- Haskell
fib :: Int -> Int
fib n
  | n <= 0 = 0
  | n == 1 = 1
  | otherwise = fib (n - 1) + fib (n - 2)
```

<br />

```py
# Python
def fib(n: int) -> int:
  launchthemissiles()
  if n <= 0:
    return 0
  elif n == 1:
    return 1
  else:
    return fib(n - 1) + fib(n - 2)
```
