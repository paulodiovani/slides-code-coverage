---
theme: gaia
paginate: true
backgroundColor: #333
_class: lead
_paginate: false
_footer: _by Paulo Diovani_
---

<style>
/* Add total page number */
section::after {
  content: attr(data-marpit-pagination) ' / ' attr(data-marpit-pagination-total);
}

a {
  color: inherit;
  text-decoration: none;
}

img[alt~="center"] {
  display: block;
  margin: 0 auto;
}
</style>

# Code Coverage

A brief introduction of code coverage, tools, and reports.

---

## Contents

- What is Code Coverage?
- Tools and reporters
- How to read and use the coverage report?
- Conclusion

---

## What is Code Coverage

> Code coverage (a.k.a. test coverage) is a metric that can help you understand how much of your source is tested.

---

<!--
_footer: Image by rawpixel.com
-->

## Tools

- `Clover`, `Cobertura`, `JaCoCo` (java)
- `Coverage.py` (python)
- `PHPUnit`, `Xdebug` (php)
- `SimpleCov` (ruby)
- `istanbul` (javascript)
- `mix test --coverage` (elixir)

![bg right](media/image-from-rawpixel-id-3237401-jpeg.jpg)

---

<!--
_footer: Image by rawpixel.com
-->

## Reporters

![bg left brightness:0.5](./media/image-from-rawpixel-id-899257-jpeg.jpg)

- `clover`
- `cobertura`
- `html`
- `json`, `json-summary`
- `lcov`
- `text`, `text-summary`

---

<!--
_footer: Image by martinfowler.com
-->

###  What percentage of coverage should I aim for? 

> That is not the point...

![center width:480](./media/coverage-vs-quality.png)

---

## How to read and use the coverage report

- Statements
- Branches
- Functions
- Lines

---

### Examples using...

- [istanbul.js.org](https://istanbul.js.org)
- [github.com/Codeminer42/marvin-cm42](https://github.com/Codeminer42/marvin-cm42/)

```bash
npx nyc npm test
```

```bash
npx nyc --reporter=html npm test
```

---

#### Text report (default)

![center width:800px](./media/text-report-001.png)

---

#### HTML report

![center width:1024px](./media/html-report-001.png)

---

![center width:1024px](./media/html-report-002.png)

---

![center width:1024px](./media/html-report-003.png)

![center width:1024px](./media/html-report-004.png)

---

```javascript
describe('/lib/authenticate', () => {
  describe('.authenticate', () => {
    context('when platform is not provided', () => {
      it('authenticate user with google and returns client', () => {
        const client = authenticate() // call without args

        // expectations goes here
      })
    })
  })

  // ...
```

---

![center width:1024px](./media/html-report-005.png)

![center width:1024px](./media/html-report-006.png)

---

## Conclusion

> Good coverage does not equal good tests

---

## Conclusion

- Do not simply aim for high coverage
- Monitor coverage increase/decrease
- Use to find untested code
- Improve tests, not only coverage

---

## References

<!--
_footer: '[![license][license-img]][license-link]'
-->

- [atlassian.com/continuous-delivery/software-testing/code-coverage](https://www.atlassian.com/continuous-delivery/software-testing/code-coverage)
- [martinfowler.com/bliki/TestCoverage.html](https://martinfowler.com/bliki/TestCoverage.html)
- [istanbul.js.org](https://istanbul.js.org)


[license-img]:https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png
[license-link]: http://creativecommons.org/licenses/by-nc-sa/4.0/

<!-- Presentation created with [Marp](https://marp.app/) -->
