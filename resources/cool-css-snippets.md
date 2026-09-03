---
title: Cool CSS Snippets
tags: [reference]
source: local
date_added: 2026-08-06
description: Pure-CSS techniques using @property, :focus-within, and scrollbar-gutter.
---

A collection of modern, pure-CSS techniques using newer features like `@property`, `:focus-within`, and `scrollbar-gutter`.

## 1. Spinning conic gradient

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

- `@property` registers `--a` as an angle so it can be smoothly animated.
- The keyframe drives the angle from `0deg` → `360deg`.
- The conic gradient uses that animated angle as its starting point.

## 2. `:focus-within` for form groups

Highlights an entire container when any child inside it receives focus.

```css
.field:focus-within {
  border-color: red;
}
```

`:focus-within` matches an element if it or any descendant currently has focus.

## 3. Stable scrollbar gutter

Prevents layout shift when a scrollbar appears by always reserving space for it.

```css
.scroll-container {
  overflow-y: auto;
  scrollbar-gutter: stable;
}

.scroll-container {
  overflow-y: auto;
  scrollbar-gutter: stable both-edges;
}
```

## 4. Pure CSS animated counter

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
