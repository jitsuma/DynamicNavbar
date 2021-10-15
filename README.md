# Dynamic Navbar

## Objective
element A (nav)

- distance from top is 200px
- nav height = 100px

element B (summary)

- distance from top = 400px
- height = 200px

Transition:
when A reaches top of window

1. nav width full -> 135px
2. opacity turn to transparent 50%
3. scale element B (0.98 -> 1)

## Script
Define selectors

```
const nav = document.querySelector(".navbar");
      const navLinks = document.querySelector(".navbar-nav");
      const headline = document.querySelector(".headline");
      const summary = document.querySelector(".summary");
      const profile = document.querySelector(".profile");
```

Functions
```
      function checkY() {
        console.log(window.scrollY);
        if (window.scrollY > 200) {
          nav.classList.add("fix-nav"); <!-- makes element A (nav) fixed to the left -->
          summary.classList.add("zoom"); <!-- scales element B (summary) 0.98 -> 1 -->
          navLinks.style = "display: none"; <!-- gets rid of additional links when nav shrinks -->
          profile.style.marginTop = nav.offsetHeight + "px"; <!-- adjusts height from top when nav shrinks -->
        } else {
          nav.classList.remove("fix-nav");
          summary.classList.remove("zoom");
          navLinks.style = "display: show";
          profile.style.marginTop = 0;
        }
      }

      window.addEventListener("scroll", checkY);
```
