---
# try also 'default' to start simple
theme: default
# some information about your slides, markdown enabled
title: Welcome to Slidev
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# apply any unocss classes to the current slide
class: text-center
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# https://sli.dev/guide/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/guide/syntax#mdc-syntax
mdc: true
---

# Datetime Manipulation in JavaScript

Everything you need to know about manipulating dates and times in JavaScript.

Eason Chang

---

# Agenda

<Toc minDepth="1" maxDepth="1"></Toc>

---

# Introduction

---

## About me

- Eason Chang
- Taiwanese 🇹🇼🧋
- Frontend Developer
- I created **Timez - Timezone Converter** project recently

---

## Time is everywhere

- **Post time** - Blog system
- **Event time in local timezone** - Reservation system
- **Message time** - Chat system
- **Execution time, Timestamp** - Logging system

---

## Time is complex

- ISO 8601
- leap year, leap second
- timezone
- UTC vs GMT
- offset
- IANA string
- daylight saving time

## Time is expensive

- Y2K bug
- Cloudflare Leap Second Issue

---

# Basic Concepts

How to handle date and time in a software system?

- Frontend vs Backend
- Storage
- Calculation
- Display
- Deal with timezones, locale

---

## Time representation & storage

- Unix time (milliseconds since 1970-01-01)
- ISO 8601 (YYYY-MM-DDTHH:mm:ss.sssZ)
- Always use UTC timezone in backend and storage for consistency
- Convert to local timezone in frontend

---

## Time representation & storage - Unix timestamp

- Unix time (milliseconds since 1970-01-01)
  - 1627800000000

```js {monaco-run}
console.log(Date.now());
```

---

## Time representation & storage - ISO 8601

- ISO 8601 (YYYY-MM-DDTHH:mm:ss.sssZ)
  - 2021-08-01T12:34:56.789+08:00

```js {monaco-run}
console.log(new Date().toISOString());
```

![ISO8601](/iso8601.png)

---

## Time calculation

- Add, subtract, compare
- Timezone conversion
- Do it in both frontend and backend, depends on the use case

---

## Time display

- Do it in frontend
- Display in user local timezone
- Display in user locale
- Display in relative time (e.g. "5 minutes ago")

## Take away 1

- Always use UTC in backend and storage
- Convert to local timezone and user locale in frontend

---

# Time manipulation in JavaScript

- Vanilla JS: `Date` object + `Intl` API
- `moment.js`
- `date-fns`
- `day.js`
- `luxon`
- Future JS: `Temporal` API

---

## Some statistics

![Downloads](/download-trend.jpg)

---

## Some statistics (cont.)

![Statistics](/statistics.jpg)

---

## Time operations

- Get current time
- Parse from string
- Add, Substract
- Compare
- Format to display in locale
- Convert to other timezone

## Vanilla JS

`Date` object + `Intl` API

```js {monaco-run}
const date = new Date();
console.log(date.toISOString());
```

- Pros
  - No extra dependency
- Cons
  - Cannot convert to other timezone
  - `Intl` do not support legacy browsers (IE)


---

## moment.js

- Pros
  - Most popular
  - Support legacy browsers (IE)
- Cons
  - Deprecated since 2020
  - Large bundle size
  - Object is mutable

---

## date-fns

- Pros
  - Small bundle size
  - Support tree-shaking
  - Immutable object
  - Support functional programming
  - 
  

---

## day.js

- Pros
  - Small bundle size
  - Same API as `moment.js`
- Cons
  - Need load locales manually

---

## luxon

---

## Temporal API

---

## Comparison

Comparison table TBD

---

## How to decide

Decision tree TBD

![Decision tree](/decide.webp)

---

## Conclusion

- Use `Vanilla JS` for simple operations
- Use `date-fns` for more complex operations
- Use `luxon` for more advanced operations
- Avoid using `moment.js` for new projects
- Always use UTC in backend and storage
- Convert to local timezone and user locale in frontend

## References

- https://github.com/you-dont-need/You-Dont-Need-Momentjs
- https://npm-compare.com/moment,date-fns,dayjs,luxon
- https://npmtrends.com/date-fns-vs-dayjs-vs-luxon-vs-moment
- https://mui.com/x/react-date-pickers/#date-library
