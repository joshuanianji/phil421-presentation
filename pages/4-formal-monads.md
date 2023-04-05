---
layout: two-cols-header
class: pr-4
---

# Formal Definition

::left::

```hs
return :: a -> m a 
```

<br />

<v-click>
```hs
return :: a -> Maybe a
return a = Just a

return :: a -> Either String a
return a = Right a
```
</v-click>

::right::

```hs
bind :: m a -> (a -> m b) -> m b
```

<br />

<v-click>

```hs
bind :: Maybe a -> (a -> Maybe b) -> Maybe b
bind Nothing _ = Nothing
bind (Just val) f = f val
```

</v-click>

---

# Example of Bind

1. User types in a name 
2. We print out the name 

<br />

<v-click>
```hs
-- useful functions
readLn :: IO String
print :: String -> IO ()

-- RECALL:
bind :: m a -> (a -> m b) -> m b
```
</v-click>

<br />

<v-click>
```hs
main :: IO ()
main = bind readLn print
```
</v-click>

---
layout: two-cols-header
class: pr-4
---

# Equivalent Definitions

::left:: 

```hs
fmap :: (a -> b) -> m a -> m b
return :: a -> m a
join :: m (m a) -> m a
```

<br />

<v-click>

```hs
bind :: m a -> (a -> m b) -> m b
bind m f = join (fmap f m)
```

</v-click>

::right::

<v-click>

$$
\begin{align*}
RM\diamond &. \quad \frac{A \to B}{\diamond A \to \diamond B} \\
T\diamond &. \quad A \to \diamond A \\
4\diamond &. \quad \diamond \diamond A \to \diamond A \\
\end{align*}
$$

<!-- Are computations just $\diamond$ in $KT4 = S4$? -->

</v-click>

---
layout: image
---

<BigImage imgsrc="/img/paper.png" />

$$\quad m \iff \diamond$$