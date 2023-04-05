---
clicks: 1
---
# More Formalities

<div v-click-hide at="1">

| Simple   | `Int`, `String`, `Bool`       |              |
|----------|-------------------------------|--------------|
| Function | `Int -> Int`, `a -> String`   |              |
| Pair     | `(A, B)`                      |              |
| Sum      | `Maybe a = Just a \| Nothing` |              |
| Unit     | `()`                          |              |
| Void     | `Void`                        |              |
| Monad    | `m a`                         | $\diamond A$ |

</div>

<v-click at="0">

| Simple   | `Int`, `String`, `Bool`       | $A$           |
|----------|-------------------------------|---------------|
| Function | `Int -> Int`, `a -> String`   | $A \to B$     |
| Pair     | `(A, B)`                      | $A \land B$   |
| Sum      | `Maybe a = Just a \| Nothing` | $A \lor B$    |
| Unit     | `()`                          | $\top$        |
| Void     | `Void`                        | $\bot$        |
| Monad    | `m a`                         | $\diamond A$  |

</v-click>

<style>
.slidev-vclick-hidden {
    display: none;
}
</style>

---

# A Simple Proof

| **Def 1**                          | **Def 2**                        |
|------------------------------------|----------------------------------|
| `return :: a -> m a`               | `return :: a -> m a`             |
| `bind :: m a -> (a -> m b) -> m b` | `join :: m (m a) -> m a`         |
|                                    | `fmap :: (a -> b) -> m a -> m b` |

<br />

```hs
bind m f = join (fmap f m)
```

<v-click>

$$
\begin{align*}
    \text{BIND:}& \qquad \diamond A \to ((A \to \diamond B) \to \diamond B) \\
    \text{BIND':}& \qquad (\diamond A \land (A \to \diamond B)) \to \diamond B
\end{align*}
$$

</v-click>

---
layout: two-cols
---

# A Simple Proof Cont'd

<v-clicks>

1. $\diamond A \land (A \to \diamond B)$                    <span class="hints">Assume</span>
2. $\diamond A$                                             <span class="hints">1, $\land$-elim</span>
3. $A \to \diamond B$                                       <span class="hints">1, $\land$-elim</span>
4. $\diamond A \to \diamond \diamond B$                     <span class="hints">3, RM$\diamond$</span>
5. $\diamond \diamond B \to \diamond B$                     <span class="hints">T$\diamond$</span>
6. $\diamond B$                                             <span class="hints">2, 4, 5 RPL</span>
7. $(\diamond A \land (A \to \diamond B)) \to \diamond B$   <span class="hints">1-6, RPL</span>
8. $\diamond A \to ((A \to \diamond B) \to \diamond B)$     <span class="hints">7, RPL</span>
9. BIND

</v-clicks>

<style>
span.hints {
    color: #888;
    font-style: italic;
    float: right
}
</style>