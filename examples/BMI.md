# BMI

```haskell
bmiTell :: (RealFloat a) => a -> a -> [Char]
bmiTell weight height
    | bmi <= 18.5 = "You're underweight, you emo, you!"
    | bmi <= 25.0 = "You're supposedly normal. Pffft, I bet you're ugly!"
    | bmi <= 30.0 = "You're fat! Lose some weight, fatty!"
    | otherwise   = "You're a whale, congratulations!"
      where bmi   = weight / height ^ 2
```

```javascript
function bmiTell(weight, height) {

    const bmi = weight / height ** 2;

    switch (true) {
        case bmi <= 18.5: return "You're underweight, you emo, you!";
        case bmi <= 25.0: return "You're supposedly normal. Pffft, I bet you're ugly!";
        case bmi <= 30.0: return "You're fat! Lose some weight, fatty!";
        default:          return "You're a whale, congratulations!";
    }

}
```

