# Binary Tree

```haskell
data Tree a = EmptyTree | Node a (Tree a) (Tree a) deriving (Show, Read, Eq)

singleton :: a -> Tree a
singleton x = Node x EmptyTree EmptyTree

treeInsert :: (Ord a) => a -> Tree a -> Tree a

treeInsert x EmptyTree = singleton x
treeInsert x (Node a left right)
    | x == a = Node x left right
    | x < a  = Node a (treeInsert x left) right
    | x > a  = Node a left (treeInsert x right)
```

```javascript
const EmptyTree = [];

function singleton(x) {
    return [x, EmptyTree, EmptyTree];
}

function treeInsert(x, [a, left, right] = EmptyTree) {

    if (typeof a === 'undefined') {
        return singleton(x);
    }

    if (x == a) return [x, left, right];
    if (x < a)  return [a, treeInsert(x, left), right];
    if (x > a)  return [a, left, treeInsert(x, right)];

}

function treeElem(x, [a, left, right] = EmptyTree) {

    if (typeof a === 'undefined') {
        return false;
    }

    if (a == x) return true;
    if (x < a)  return treeElem(x, left);
    if (x > a)  return treeElem(x, right);

}
```
