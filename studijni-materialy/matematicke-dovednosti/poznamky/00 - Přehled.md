---
tags: [matematicke-dovednosti, prehled]
---

# Matematické dovednosti – studijní poznámky

Poznámky k předmětu **Matematické dovednosti** (MFF UK, ZS 2026/27, cvičící Jana Maxová), sestavené ze zadaných úloh a vzorových řešení **cvičení 1–6**. Informace o předmětu a o zápočtu jsou v [[predmet]].

> [!important] Test v pondělí: množiny
> Nejdůležitější jsou **03, 04, 05** (cvičení 5 a 6). Logika a kvantifikátory (01, 02) jsou potřeba, protože každé tvrzení o množinách se do nich přepisuje.

## Obsah

| # | Poznámka | Cvičení | Hlavní témata |
| --- | --- | --- | --- |
| 01 | [[01 - Výroková logika]] | 1, 2 | spojky, negace, obměna, zjednodušování |
| 02 | [[02 - Kvantifikátory]] | 3, 4 | $\forall,\exists$, negace, prázdná množina, přepis vět |
| **03** | [[03 - Množiny - zápis a pojmy]] | **5, 6** | zápis množin, $\emptyset$, počet prvků |
| **04** | [[04 - Podmnožiny a množinové operace]] | **5, 6** | $\subseteq$, $\cup$, $\cap$, $\setminus$, důkazy rovností |
| **05** | [[05 - Potenční množina a nekonečná sjednocení]] | **5, 6** | $\mathcal P(A)$, $\bigcup$, $\bigcap$, inkluze mezi množinami |
| 06 | [[06 - Pasti a tahák na test]] | 5, 6 | tahák, pasti, jak psát odpovědi |

## Doporučené pořadí

1. Pokud logika není jistá: 01 → 02 (rychle).
2. **03 → 04 → 05** (podrobně, příklady počítej na papír).
3. **06** večer před testem.
4. **Cvičné PDF** ve složce `cviceni/`: [[cviceni/Cvicna-pisemka-mnoziny.pdf|Cvičná písemka – množiny]] (s místem na řešení) a [[cviceni/Cvicna-pisemka-mnoziny-reseni.pdf|Řešení]] (otevři až po vyřešení!).

## Použité značení (podle kurzu)

- $\mathbb N=\{1,2,3,\dots\}$, $\mathbb N_0=\mathbb N\cup\{0\}$, $\mathbb Z$ celá čísla, $\mathbb Q$ racionální, $\mathbb R$ reálná.
- $x\mid y$: $x$ dělí $y$ ($\exists k\in\mathbb Z : y=kx$), $x\nmid y$ neplatí.
- $\mathcal P(A)=2^A$: potenční množina. $\binom{A}{k}$: $k$-prvkové podmnožiny $A$.
- $A\setminus B$ (na cvičení 1 psáno také $A-B$): rozdíl množin.

## Upozornění ke zdrojům

Při zpracování jsem narazil na několik **drobných nepřesností ve vzorových řešeních**. Jsou označené přímo v poznámkách (ve značce „Poznámka k oficiálnímu řešení“ nebo kurzívou):

- cv. 6, úl. 4c: počet prvků je **4** (v řešení stojí 3, ačkoli vyjmenovává čtyři) → [[03 - Množiny - zápis a pojmy]],
- cv. 4, úl. 3: zápis $\{x\in\mathbb Z\mid x\le1\}$ neodpovídá výčtu $\{-1,-2,\dots\}$ → [[02 - Kvantifikátory]],
- cv. 5, úl. 4d: zápis „$(\exists x\in A)\lor(\exists x\in B)$“ je nepřesný → [[04 - Podmnožiny a množinové operace]].
