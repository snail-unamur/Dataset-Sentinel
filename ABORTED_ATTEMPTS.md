# Projects Status

---

## jsoup

- **Status:** Partial
- `measure`: OK, working.
- `instrumentconstructor`: Not working.

---

## JavaParser

- **Status:** Partial
- `measure`: Working (+/-), not seeing a lot of csv files which is not normal.

- `instrumentconstructor`: Not working, due to the project architecture which contains many subprojects which make analysing project very difficult.

---

## Guava

- **Status:** Partial
- `measure`: OK, working.
- `instrumentconstructor`: Not working.

---

## Joda-Time

- **Status:** Partial
- `measure`: OK, working.
- `instrumentconstructor`: Not working.

---

## Gson

- **Status:** Skipped, small project with 36k lines of code (measured with cloc).

---

## AssertJ Core

- **Status:** Partial
- `measure`: Working with no issue. command used: "mvn clean test -pl assertj-core -Dmaven.test.failure.ignore=true -Dspotless.check.skip=true -Denforcer.skip=true"

- `instrumentconstructor`: Not working — after ~7-8 hours of investigation, concluded it has too many issues. The project has multiple packages which causes Spoon to generate duplicate and ignored classes that are very hard to handle.

---
