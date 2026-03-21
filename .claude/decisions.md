# Decisions Log - Rozhodnutia projektu

> Tento súbor zaznamenáva dôležité rozhodnutia a ich dôvody.
> Formát: dátum, rozhodnutie, dôvod, alternatívy.

---

## 2026-03-20 | Založenie projektu

### Rozhodnutie: Štruktúra dokumentácie
- **Čo:** Vytvorený CHARACTER_BIBLE.md, CONTENT_STRATEGY.md, PROMPTS_*.md, TOOLS_RESEARCH.md
- **Prečo:** Potrebná kompletná dokumentácia pred začatím generovania obsahu
- **Alternatívy:** Mohlo sa začať rovno s generovaním, ale bez dokumentácie by nebola konzistentnosť

### Rozhodnutie: Referenčné fotky v repozitári
- **Čo:** Referenčné fotky vozidiel uložené priamo v Git repo
- **Prečo:** Jednoduchý prístup pre Claude aj používateľa
- **Riziko:** Veľkosť repo môže narásť, zvážiť Git LFS v budúcnosti

### Rozhodnutie: Konverzia AVIF → PNG
- **Čo:** Kawasaki fotky konvertované z AVIF na PNG
- **Prečo:** AVIF nie je univerzálne podporovaný, PNG je bezstratový a kompatibilný
- **Nástroj:** heif-convert

---

## 2026-03-21 | Claude konfigurácia

### Rozhodnutie: Vytvorenie .claude/ priečinka s memory + decisions + style-guide
- **Čo:** Pridané CLAUDE.md + .claude/memory.md, decisions.md, style-guide.md
- **Prečo:** Zabezpečenie konzistentnosti medzi Claude sessions
- **Alternatívy:** Mohol sa použiť len CLAUDE.md, ale separátne súbory sú prehľadnejšie

---

## Template pre nové rozhodnutia
```
## YYYY-MM-DD | Názov oblasti

### Rozhodnutie: Krátky popis
- **Čo:** Čo presne sa rozhodlo
- **Prečo:** Dôvod rozhodnutia
- **Alternatívy:** Čo iné sa zvažovalo
- **Dopad:** Aký má dopad na projekt
```
