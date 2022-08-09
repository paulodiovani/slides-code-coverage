---
theme: gaia
paginate: true
backgroundColor: #333
headingDivider: 2
_class: lead
_paginate: false
_footer: _by Paulo Diovani_
---

<style>
/* Add total page number */
section::after {
  content: attr(data-marpit-pagination) ' / ' attr(data-marpit-pagination-total);
}
</style>

# Code Coverage

A brief introduction of code coverage tools and reports

## Contents

- What is Code Coverage?
- Tools and reporters
- The coverage summary
  + Statements
  + Branches
  + Functions
  + Lines
- Conclusion
  + Coverage X Quality

## Tools

- `Coverage.py` (python)
- `istanbul` (javascript)
- `JaCoCo` (java)
- `mix test --coverage` (elixir)
- `SimpleCov` (ruby)
- `Xdebug` (php)

![bg right](media/image-from-rawpixel-id-3237401-jpeg.jpg)
<!-- image licence: CC0 -->

## References

<!--
footer: '[![license][license-img]][license-link]'
-->

- https://www.atlassian.com/continuous-delivery/software-testing/code-coverage


[license-img]:https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png
[license-link]: http://creativecommons.org/licenses/by-nc-sa/4.0/

<!-- Presentation created with [Marp](https://marp.app/) -->
