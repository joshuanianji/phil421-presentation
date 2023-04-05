---
layout: intro
---

# Monads to the rescue!

<v-click>

<h2>A <span class="pop">type</span> that represents <span class="pop">computation</span>, while making sure we work with <span class="pop">pure functions</span></h2>
</v-click>

<style>
span.pop {
    font-weight: extrabold;
    color: #4EC5D4;
}
</style>

---
layout: two-cols-header
class: pr-4
---
# What is a Computation?

::left::

## Error Handling

`Either a b` or `Maybe a` Type.

```hs
f :: Int -> Maybe Int
g :: Int -> Either String Int
```

<br />

### Recall

```hs
Maybe a = Nothing | Just a
Either a b = Left a | Right b
```

::right::

## Side effects

`IO a` Type (Input/Output)

```hs
f :: Int -> IO Int
```

<br />

<v-click>
```hs
import RandomLib (factorial)

-- our code
main = print (factorial 5)
```
</v-click>

<v-click>
```hs
print :: a -> IO ()
```
</v-click>

<br />

<v-click>
```hs
import RandomLib (factorial)

-- our code
main :: IO ()
main = print (factorial 5)
```
</v-click>