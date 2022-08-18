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

`99% ⬆`

A brief introduction of code coverage, tools, and reports,
  helping you keeping up with code quality.

---

Paulo Diovani Gonçalves

`@paulodiovani`

`linkedin.com/in/paulodiovani`

![width:200px](./media/codeminer.svg)

![bg left brightness:0.5](./media/avatar.jpg)

---

## Contents

- What is Code Coverage?
- Tools and reporters
- How to read and use the coverage report?
- Conclusion
- References

---

## What is Code Coverage

> Code coverage (a.k.a. test coverage) is a metric that can help you understand how much of your source is tested.

---

<!--
_footer: Image by rawpixel.com
-->


###  What percentage of coverage should I aim for?

> That is not the point...

![bg right brightness:0.5](./media/image-from-rawpixel-id-2619266-png.png)

---

<!--
_footer: Image by martinfowler.com
-->

> High coverage does not equal good tests

![center width:480](./media/coverage-vs-quality.png)

Monitor coverage is good, but requiring it as a target may lead to bad tests and false positives.

---

### What is a good test?

🤔

> A good test suite is one that doesn’t take long to run, and if all the tests are passing, provides you with confidence that your software is working as expected.
>
> -- codeacademy.com

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

![center width:800px](./media/coverage-monitor-jenkins.png)

![center width:800px](./media/coverage-monitor-codecov.png)

---

## How to read and use the coverage report

- Statements
  * `const foo = 123`, `someFn()`
- Branches
  * `if (foo === true) {}`, `switch (bar) {}`, `try {} catch (e) {}`
- Functions
  * `function fn() {}`, `const fn = () => {}`
- Lines
  * `...`

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

![center width:1024px](./media/html-report-index-01.png)

---

![center width:1024px](./media/html-report-index-email.png)

---

![center width:1024px](./media/html-report-email-header-before.png)

![center width:1024px](./media/html-report-email-code-before.png)

---

```javascript
describe('/lib/retrieveEmail', () => {
  describe('.getEmail', () => {
    context('when there are emails', () => {
      it('read and return the first message', async () => {
        const email = await getEmail({ from: 'foobar@example.com' })

        expect(email).to.eq('foobar')
      })
    })
  })
})
```

---

![center width:1024px](./media/html-report-email-header-after-01.png)

![center width:1024px](./media/html-report-email-code-after-01.png)

---

```javascript
describe('/lib/retrieveEmail', () => {
  describe('.getEmail', () => {
    context('when there are emails', () => {
      it('read and return the first message', async () => {
        const email = await getEmail({ from: 'foobar@example.com' })

        expect(email).to.eq('foobar')
      })
    })

    context('when there are no emails', () => {
      it('returns null', async () => {
        gmailMock.users.messages.list.resolves({ data: { messages: null } })

        const email = await getEmail({ from: 'foobar@example.com' })

        expect(email).to.eq(null)
      })
    })
  })
})
```

---

![center width:1024px](./media/html-report-email-header-after-02.png)

![center width:1024px](./media/html-report-email-code-after-02.png)

---

![center width:1024px](./media/html-report-index-authenticate.png)

---

![center width:1024px](./media/html-report-authenticate-header-before.png)

![center width:1024px](./media/html-report-authenticate-code-before.png)

---

```javascript
describe('/lib/authenticate', () => {
  describe('.authenticate', () => {
    context('when platform is not provided', () => {
      it('authenticate user with google by default', () => {
        const client = authenticate() // call without args

        // expect(client).to.eq(...)
      })
    })
  })
})
```

---

![center width:1024px](./media/html-report-authenticate-header-after.png)

![center width:1024px](./media/html-report-authenticate-code-after.png)

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
- [codecademy.com/article/tdd-u1-good-test](https://www.codecademy.com/article/tdd-u1-good-test)


[license-img]:https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png
[license-link]: http://creativecommons.org/licenses/by-nc-sa/4.0/

<!-- Presentation created with [Marp](https://marp.app/) -->
