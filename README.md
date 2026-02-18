# Invented-oyster
You care more about what you think I think of you than what I actually think of you.

![buh](https://github.com/nicolasbaez/Invented-oyster/blob/main/xp060.gif)
```javascript
setup = (_) => createCanvas((w = 500), w, WEBGL);
k = 0;
draw = (_) => {
  background(16);
  rotateX(k);
  rotateY(k / 2);
  for (i = -w / 2; i <= w / 2; i += w / 10) {
    for (j = -w / 2; j <= w / 2; j += w / 10) {
      fill(0, noise(i, j, k) * 255, noise(j, k, i) * 255, noise(k, i, j) * 255);
      push();
      translate(i, j);
      box(w / 12);
      pop();
    }
  }
  if (k == 0) saveGif("xp060.gif", 600, { delay: 0, units: "frames" });
  k += 0.01;
};
