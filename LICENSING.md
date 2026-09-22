# Licensing

**Code is Apache-2.0. Written content is CC BY 4.0. The practice record is reserved.**

| Path | Licence |
| ---- | ------- |
| `bin/`, and any code in `skills/` | Apache-2.0 — `LICENSE` |
| `practice/`, `sources/`, `config/`, `README.md`, `INSTALL.md`, skill prose | CC BY 4.0 — `LICENSE-CONTENT` |
| `log/`, `journal/` | All rights reserved — `log/LICENSE` |

## Why three and not one

**Apache-2.0 over MIT** for three reasons specific to this repo. §6 grants no rights to
the author's name or marks, which matters for something tied to a professional identity —
a fork should not be able to imply endorsement. §4(b) makes derivatives carry this
`NOTICE` forward and state their changes, which is closer to real attribution than MIT's
bare notice preservation. And the patent grant is what lets someone adopt this at work
without opening a legal ticket.

**CC BY 4.0 for the prose** because Creative Commons explicitly recommends against CC for
software, and permissive software licences fit prose badly. The track templates and kata
forms are the part people will actually copy.

Not CC BY-**SA**. Share-alike would stop someone pasting a paragraph of a track into their
company's internal docs, which is exactly the adoption worth having.

**`log/` and `journal/` sit outside both grants.** CC licences are irrevocable — a
published version can never be un-licensed, whatever is deleted later. Nobody forking this
wants the daily notes; they want the machinery. Reserving the record costs nothing in
adoption and removes irrevocability from the only files where it would bite.

That those paths are also encrypted is belt and braces, not a substitute. **Encrypted
bytes are still published bytes**, and a key that leaks in five years exposes everything
committed under it.

## Attribution

`CITATION.cff` gives GitHub's "Cite this repository" button a copy-pasteable block. That
does more real attribution work than any licence clause, because it makes crediting the
author the path of least resistance.

Being straight about the limit: the licence is a floor. It buys notice preservation and
no-endorsement. It does not buy a visible "based on Uche's practice" in someone's fork —
that is a social norm, asked for in the README, and most people honour it.

Not legal advice.
