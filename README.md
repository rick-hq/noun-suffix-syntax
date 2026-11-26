# Noun Suffix Syntax (NSS) v1.0
**A lightweight standard for Inline Entity Tagging using Chrono-Descriptor suffixes.**

Noun Suffix Syntax (NSS) attaches compact, machine-readable timeline and classification metadata directly onto major specific nouns (entities) inside running prose—eliminating parenthetical clutter while keeping text human-scannable and regex-parseable.

---

## 1. Core Pattern
`Entity<yearSTART~yearEND-hyphenated-descriptor>`

* **No space** between the final word of the entity and `<`.
* **No internal spaces** inside `<...>`; words in the descriptor are joined by single hyphens (`-`).
* **Descriptor rule:** 2–4 factual, concrete words (no generic fluff adjectives like *famous* or *iconic*).

### Examples
* **Single-year event:** `Apollo 11<1969-first-crewed-moon-landing>`
* **Closed historical span:** `Roman Empire<b27~476-Mediterranean-superpower>`
* **Ongoing entity / living person:** `Python<1991~-high-level-programming-language>`

---

## 2. Range Operator (`~`)
The tilde (`~`) strictly means **"to / through"**:
* `1939~1945` — Closed span from start year to end year.
* `1991~` — Open-ended span from start year to the ongoing present.
* *(Omitted)* — Single-year milestone (`1969`).

---

## 3. Prefix Codes (`f → [c/r/s] → b`)
Prefixes attach directly to the start or end digits in a strict outer-to-inner order:

| Code | Meaning | Example |
| :--- | :--- | :--- |
| **`f`** | **Fictional / Mythic** | `Middle-earth<f-Tolkien-high-fantasy-realm>` |
| **`c`** | **Circa** (approximate) | `Homer<cb800-epic-Greek-poet>` |
| **`r`** | **Pre** (before bound) | `Beowulf<r1000-Old-English-epic-poem>` |
| **`s`** | **Post** (after bound) | `Voynich Manuscript<s1404-encrypted-medieval-codex>` |
| **`b`** | **BCE** (Before Common Era) | `Aristotle<b384~b322-Greek-polymath>` |

---

## 4. Deep-Time Scale Units (`ka`, `Ma`, `Ga`)
For prehistoric, geological, and cosmic timelines (`b10ka` and older):
* **`ka`** = Kilo-annum (1,000 years) — e.g., `Homo sapiens<b300ka~-modern-human-species>`
* **`Ma`** = Mega-annum (1,000,000 years) — e.g., `Tyrannosaurus rex<b68Ma~b66Ma-Late-Cretaceous-theropod>`
* **`Ga`** = Giga-annum (1,000,000,000 years) — e.g., `Earth<b4.54Ga~-terrestrial-inner-planet>`
* **Omit `c` by default** on scaled numbers (rounding already implies approximation).
* **Omit `b`** for future projections — e.g., `Red Giant Sun<5Ga-solar-expansion-phase>`.

---

## 5. HTML / XML Escaping Note
In raw HTML environments where `<...>` may be parsed as markup tags, escape brackets (`&lt;...&gt;`) or wrap NSS tokens in inline code backticks (`` `Entity<...>` ``).

---

## License
Released under **CC BY 4.0** — free to use, adapt, and build parsers or plugins upon with attribution.
