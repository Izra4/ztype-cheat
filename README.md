# 🕹️ ZType Auto Shoot Cheat

This script automatically types and shoots enemies in [zType](https://zty.pe) by injecting keystrokes based on the active word target.

## ⚙️ How to Use

1. Open [https://zty.pe](https://zty.pe) in your browser.
2. Start the game by clicking **New Game**.
3. Paste the following code into the Console:

```js
document.addEventListener('keydown', function(e) {
    const target = ig?.game?.currentTarget;
    if (target && target.remainingWord?.length > 0) {
        const correctLetter = target.remainingWord[0];
        ig.game.bufferLetter(correctLetter);
        ig.game.shoot();
    }
});
```

For automatically shoot after the first letter
```js
let autoShoot = true;

const autoShootInterval = setInterval(() => {
    if (!autoShoot) return;

    const target = ig?.game?.currentTarget;
    if (target && target.remainingWord?.length > 0) {
        const correctLetter = target.remainingWord[0];
        ig.game.bufferLetter(correctLetter);
        ig.game.shoot();
    }
}, 100);
