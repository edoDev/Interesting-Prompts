# Cool CSS Snippets

A collection of modern, pure-CSS techniques using newer features like `@property`, `:focus-within`, and `scrollbar-gutter`.

---

## 1. Spinning Conic Gradient

Creates a continuously rotating conic gradient using an animated custom property.

```css
@property --a {
  syntax: "<angle>";
  initial-value: 0deg;
  inherits: false;
}

@keyframes spin {
  to {
    --a: 360deg;
  }
}

.card {
  background: conic-gradient(from var(--a), red, yellow);
  animation: spin 3s linear infinite;
}
```

**How it works**
- `@property` registers `--a` as an angle so it can be smoothly animated.
- The keyframe drives the angle from `0deg` → `360deg`.
- The conic gradient uses that animated angle as its starting point, producing a continuous spin.

Useful for loading indicators, colorful backgrounds, or animated borders.

---

## 2. `:focus-within` for Form Groups

Highlights an entire container when any child inside it receives focus.

```css
/* Use :focus-within in CSS! */
.field:focus-within {
  border-color: red;
}
```

**How it works**
- `:focus-within` matches an element if **it or any of its descendants** currently has focus.
- Perfect for form groups, cards, or custom inputs where you want the whole wrapper to respond visually.

---

## 3. Stable Scrollbar Gutter

Prevents layout shift when a scrollbar appears by always reserving space for it.

```css
/* Reserve room for the scrollbar so content doesn’t jump */
.scroll-container {
  overflow-y: auto;
  scrollbar-gutter: stable;
}

/* Symmetric gutter on both sides for perfect centering */
.scroll-container {
  overflow-y: auto;
  scrollbar-gutter: stable both-edges;
}
```

**How it works**
- `scrollbar-gutter: stable` reserves space on the scrollbar side even when not needed.
- `stable both-edges` reserves space on **both** left and right for perfect centering.

---

## 4. Pure CSS Animated Counter

Animates a number from 0 to a target value with no JavaScript.

```css
@property --num {
  syntax: "<integer>";
  initial-value: 0;
  inherits: false;
}

.stat {
  counter-reset: n var(--num);
  animation: count 2s forwards;
}

.stat::after {
  content: counter(n);
}

@keyframes count {
  to {
    --num: 100;
  }
}
```

**How it works**
- `@property` registers `--num` as an integer so it can be animated.
- A CSS counter is bound to the animated value.
- `::after` displays the counter.
- Change the final number in the keyframe and adjust the duration as needed.
