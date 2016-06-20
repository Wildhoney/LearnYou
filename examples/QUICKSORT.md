# QuickSort

```haskell
quickSort :: Ord a => [a] -> [a]
quickSort [] = []
quickSort (x:xs) = lessThanOrEqual ++ [x] ++ greaterThan
    where
        lessThanOrEqual = quickSort [ a | a <- xs, a <= x ]
        greaterThan = quickSort [ a | a <- xs, a > x ]
```

```javascript
function quickSort([ x = [], ...xs ]) {

    if (x.length === 0) {
        return [];
    }

    const lessThanOrEqual = quickSort(xs.filter(a => a <= x));
    const greaterThan = quickSort(xs.filter(a => a > x));
    return [ ...lessThanOrEqual, x, ...greaterThan ];

}
```

