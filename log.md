⚡️[Previous #100DaysOfCode log](https://twitter.com/most_mojo/status/1085674532982214662)

---

### Day 1: Saturday, 4th May, 2019

**Today's Progress**

• Key CSS grid terms: `container, row, column, area, items, cells, display: grid`.

• Downloaded new Mozilla Firefox and checked out grids in dev tools w/ line numbers.

• Practiced moving grids around on codepen with `grid-row` & `grid-column` syntax.

**Link(s) to work**

1. [Codepen grids](https://codepen.io/most_mojo/pen/RmwKWd)

---

### Day 2: Sunday, 5th May, 2019

**Today's Progress**

• Continued learning CSS grid - infinite `col` span using -1.

• Name grid lines: ex. `grid-template-rows: [ header-start ] 100px [ header-end box-start ] 200px [ box-end main-start ] 400px [ main-end footer-start ] 100px [ footer-end ];`.

• Functionality of cols using `grid-template-columns: repeat(3, [ col-start ] 1fr [ col-end ]) 200px [ grid-end ]; &rarr; col-start-1 col-end-1, col-start-2 col-end-2`, etc.

**Link(s) to work**

1. [Codepen grids](https://codepen.io/most_mojo/pen/RmwKWd)

---
### Day 3: Monday, 6th May, 2019

**Today's Progress**

• More on CSS grids. New elements: `grid-auto-rows` for `implicit` grids w/ keyword `dense` to avoid 'holes'.

• Elements similar to flexbox: `justify-items` and `align-items` (and self) for X & Y axis alignment. Also, `max-content` and `min-content` for responsive layouts w/ `auto-fit`/ `auto-fill`.

• Started NEXTER project by Jonas Schmedtmann to put all grid-work into practice. To remember: `grid-template-columns:
    [sidebar-start]8rem [sidebar-end full-start] 1fr [center-start] repeat(8, [col-start] minmax(min-content, 14rem) [col-end]
    )[center-end] 1fr [full-end];` &rarr; All naming, numeric and minmax functions utilized in one place 🤓.

**Link(s) to work**

1. [Codepen grids](https://codepen.io/most_mojo/pen/EzagWr)
2. [Nexter project](https://github.com/mostmojo/nexter)

---
