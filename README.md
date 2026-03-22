# stop-slop-pl

Polish AI slop removal. Derivative of [hardikpandya/stop-slop](https://github.com/hardikpandya/stop-slop).

A Claude Code skill that detects and removes AI writing patterns from Polish text. Polish LLM output has its own slop signatures -- filler openers, corporate jargon, passive voice, false agency, formulaic contrasts -- different from English. This skill catches them and helps rewrite into direct, human-sounding Polish.

---

## Co to jest

Skill do Claude Code (i Claude Projects), który wyłapuje i usuwa wzorce pisania AI z polskich tekstów.

Polski tekst generowany przez LLM ma swoje własne schematy — inne niż angielski. Otwieracze-wypełniacze ("W dzisiejszych czasach..."), korporacyjny żargon ("kompleksowe rozwiązania"), strona bierna, fałszywa sprawczość ("rynek wymaga"), formulaiczne kontrasty ("nie chodzi o X, ale o Y"). Ten skill je wyłapuje i pomaga przepisać na prosty, bezpośredni język.

## Jak używać

### Claude Code

Skopiuj katalog do skilli Claude Code:

```bash
cp -r . ~/.claude/skills/stop-slop-pl/
```

Skill jest dostępny gdy piszesz po polsku.

### Claude Projects

Wklej zawartość `SKILL.md` i plików z `references/` do instrukcji projektu (Project Instructions) w Claude.

### API

Dołącz zawartość `SKILL.md` do system promptu. Pliki referencyjne (`references/`) dodaj jako kontekst.

## Co łapie

- **Otwieracze-wypełniacze** — "W dzisiejszych czasach...", "Warto zauważyć, że...", "Nie jest tajemnicą, że..."
- **Wzmacniacze-kule** — "To kluczowe.", "I to zmienia wszystko.", "Nie sposób przecenić..."
- **Żargon korporacyjny** — "kompleksowe rozwiązania", "holistyczne podejście", "stakeholderzy"
- **Przysłówki-wypełniacze** — "niezwykle", "zdecydowanie", "niewątpliwie", "fundamentalnie"
- **Metakomentarze** — "Przyjrzyjmy się temu bliżej...", "Pozwólcie, że wyjaśnię..."
- **Puste deklaratywne** — "Potencjał jest ogromny", "Możliwości są nieograniczone"
- **Kontrasty binarne** — "Nie chodzi o X, ale o Y" (stwierdź Y wprost)
- **Negatywne listowanie** — "To nie jest X. To nie jest Y. To jest Z." (stwierdź Z)
- **Fałszywa sprawczość** — "rynek wymaga", "technologia umożliwia" (nazwij człowieka)
- **Strona bierna** — "Zostało to wdrożone" (nazwij kto wdrożył)
- **Anglicyzmy-buzzwordy** — "mindset", "roadmapa", "deliverables" (użyj polskiego)

Pełna lista w `references/phrases.md` i `references/structures.md`. Przykłady transformacji w `references/examples.md`.

## Ocena tekstu

Skill ocenia tekst w pięciu wymiarach, każdy 1-10:

| Wymiar | Pytanie |
|--------|---------|
| Bezpośredniość | Stwierdzenia czy zapowiedzi? |
| Rytm | Zróżnicowany czy metronomiczny? |
| Zaufanie | Szanuje inteligencję czytelnika? |
| Autentyczność | Brzmi jak człowiek? |
| Gęstość | Coś można wyciąć? |

Poniżej 35/50 — tekst wymaga gruntownej poprawy (częste otwieracze, żargon, strona bierna). Poniżej 50/50 ale powyżej 35 — tekst jest czytelny, ale ma miejsca do wygładzenia.

## Pochodzenie

Oryginalny [stop-slop](https://github.com/hardikpandya/stop-slop) stworzył [Hardik Pandya](https://github.com/hardikpandya). Tamten skill obsługuje angielski. Ten repo to polska adaptacja — inne frazy, inne schematy, inne przykłady.

Polska adaptacja: [0xarise](https://github.com/0xarise)

## Licencja

MIT — patrz [LICENSE](LICENSE).
