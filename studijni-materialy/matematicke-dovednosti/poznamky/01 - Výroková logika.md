---
tags: [matematicke-dovednosti, logika]
cviceni: [1, 2]
---

# 01 – Výroková logika

> [!abstract] Co se tu naučíš
> Číst a psát logické spojky, správně **negovat** výroky, poznat **ekvivalentní** formule a zjednodušovat je. Je to základ pro kvantifikátory ([[02 - Kvantifikátory]]) i pro množiny ([[03 - Množiny - zápis a pojmy]]): každý množinový vztah se nakonec převádí na výrok o prvcích.

Zdroj: zadání a řešení **cvičení 1 a 2**.

---

## 1. Výrok a logické spojky

**Výrok** je tvrzení, o kterém má smysl říct, že je pravdivé (1) nebo nepravdivé (0). Z jednoduchých výroků skládáme složené pomocí spojek.

| Spojka | Značení | Čteme | Pravdivé, když… |
| --- | --- | --- | --- |
| negace | $\neg p$ | „není pravda, že $p$“ | $p$ je nepravdivý |
| konjunkce | $p \land q$ | „$p$ a zároveň $q$“ | platí **oba** |
| disjunkce | $p \lor q$ | „$p$ nebo $q$“ | platí **aspoň jeden** (i oba) |
| implikace | $p \Rightarrow q$ | „jestliže $p$, pak $q$“ | neplatí situace „$p$ pravda, $q$ nepravda“ |
| ekvivalence | $p \Leftrightarrow q$ | „$p$ právě tehdy, když $q$“ | $p$ a $q$ mají **stejnou** hodnotu |

### Pravdivostní tabulka

| $p$ | $q$ | $p\land q$ | $p\lor q$ | $p\Rightarrow q$ | $p\Leftrightarrow q$ |
| :-: | :-: | :-: | :-: | :-: | :-: |
| 1 | 1 | 1 | 1 | 1 | 1 |
| 1 | 0 | 0 | 1 | **0** | 0 |
| 0 | 1 | 0 | 1 | 1 | 0 |
| 0 | 0 | 0 | 0 | 1 | 1 |

> [!warning] Implikace a „nepravdivý předpoklad“
> $p \Rightarrow q$ je **nepravdivá jen v jediném případě**: $p$ platí a $q$ neplatí. Když $p$ neplatí, implikace je pravdivá, ať je $q$ jakékoli („z nepravdy plyne cokoli“). Tohle se vrací u prázdné množiny a u vět typu „pro každé $x$ z prázdné množiny…“.

**Jak si implikaci zapamatovat:** $p \Rightarrow q$ je „slib“. Slib porušíš jen tehdy, když nastane $p$ a ty nesplníš $q$. Když $p$ nenastane, slib nemůžeš porušit.

---

## 2. Negace – nejdůležitější dovednost

### Základní pravidla

$$
\begin{aligned}
\neg(A \land B) &\equiv \neg A \lor \neg B &&\text{(De Morganův zákon)}\\
\neg(A \lor B) &\equiv \neg A \land \neg B &&\text{(De Morganův zákon)}\\
\neg(A \Rightarrow B) &\equiv A \land \neg B\\
\neg(A \Leftrightarrow B) &\equiv (A \land \neg B) \lor (\neg A \land B)\\
\neg\neg A &\equiv A
\end{aligned}
$$

> [!tip] Slovní návod
> - Negace „a“ je „nebo“ a obráceně (a negují se obě části).
> - Negace implikace **není implikace**. Je to „předpoklad platí, **a přesto** závěr neplatí“.
> - Negace nerovnosti: $\neg(a<b) \equiv a\ge b$, $\neg(a=b)\equiv a\ne b$.

### Příklady z cvičení 2

**Negace slovních výroků** (cv. 2, úloha 4):

| Původní výrok | Negace |
| --- | --- |
| Je-li středa a není slunečno, jdu plavat. | Je středa, není slunečno a (přesto) nejdu plavat. |
| Jestliže je mokro, pak pršelo nebo projel kropicí vůz. | Je mokro a (přesto) nepršelo a ani neprojel kropicí vůz. |
| Nebude-li pršet, nezmokneme. | Nebude pršet a (přesto) zmokneme. |

Schéma je vždy stejné: $\neg(P \Rightarrow Q) \equiv P \land \neg Q$.

**Negace složených formulí** (cv. 2, úloha 6). Postup: odstraň nejdřív implikace uvnitř nebo negaci „prosekej“ dovnitř krok po kroku.

$$
\begin{aligned}
\neg\big((A \land B) \Rightarrow (C \lor D)\big)
&\equiv (A \land B) \land \neg(C \lor D)\\
&\equiv A \land B \land \neg C \land \neg D .
\end{aligned}
$$

$$
\begin{aligned}
\neg\big((A\Rightarrow B)\Rightarrow(C\Rightarrow D)\big)
&\equiv (A\Rightarrow B)\land \neg(C\Rightarrow D)\\
&\equiv (A\Rightarrow B)\land C\land\neg D .
\end{aligned}
$$

### Příklady z cvičení 1

> [!example] Úloha 1 (cv. 1)
> Negace výroku „Jestliže je dnes svátek, žádný student není ve škole.“
>
> Je to implikace $P \Rightarrow Q$ s $P$ = „je svátek“ a $Q$ = „žádný student není ve škole“. Negace je $P \land \neg Q$.
> $\neg Q$ = „**není pravda**, že žádný student není ve škole“ = „**alespoň jeden** student **je** ve škole“. Správně je tedy **(b)**: *Dnes je svátek a alespoň jeden student je ve škole.*

> [!example] Úloha 2 (cv. 1)
> Negace výroku „V každém ročníku je student, který má výuku alespoň tři dny v týdnu.“
>
> Struktura: $\forall \text{ročník}\ \exists \text{student}\ (\ge 3 \text{ dny})$. Negace prohodí kvantifikátory a znegujeme vlastnost: $\exists \text{ročník}\ \forall \text{student}\ (\le 2 \text{ dny})$. Správně je **(d)**.

---

## 3. Ekvivalence a obměna implikace

Dvě formule jsou **ekvivalentní** ($\equiv$), když mají stejnou pravdivostní hodnotu pro každé ohodnocení proměnných (stejnou tabulku).

$$
A \Rightarrow B \;\equiv\; \neg A \lor B \;\equiv\; \neg B \Rightarrow \neg A \;\equiv\; \neg(A \land \neg B)
$$

> [!important] Tři příbuzné implikace – nezaměňovat!
> K implikaci $A \Rightarrow B$ existují:
> - **obměna** $\neg B \Rightarrow \neg A$ – je **ekvivalentní** s původní,
> - **obrácená implikace** $B \Rightarrow A$ – **není** ekvivalentní,
> - **negace** $A \land \neg B$ – tvrdí opak.

### Další užitečné ekvivalence

$$
\begin{aligned}
A \Leftrightarrow B &\equiv (A \Rightarrow B) \land (B \Rightarrow A) \equiv \neg A \Leftrightarrow \neg B\\
A \land B &\equiv \neg(A \Rightarrow \neg B)\\
A \,\mathrm{xor}\, B &\equiv (A \lor B)\land(\neg A\lor\neg B) \equiv A \Leftrightarrow \neg B\\
\neg(A \,\mathrm{xor}\, B) &\equiv A \Leftrightarrow B
\end{aligned}
$$

**Distributivita:**

$$
A \lor (B \land C) \equiv (A \lor B) \land (A \lor C),\qquad
A \land (B \lor C) \equiv (A \land B) \lor (A \land C).
$$

**Absorpce a tautologie:** $A \land (B\lor\neg B) \equiv A$, $\;A \lor (B \land \neg B) \equiv A$, $\;A \lor \neg A$ je vždy pravdivé.

### Příklad: obměna (cv. 2, úloha 8)

| Implikace | Obměna |
| --- | --- |
| Jestliže prší, jsou ulice mokré. | Jestliže ulice nejsou mokré, neprší. |
| Je-li $x$ sudé nebo $y$ sudé, pak $xy$ je sudé. | Není-li $xy$ sudé, pak $x$ není sudé **a zároveň** $y$ není sudé. |
| Nebude-li pršet, nezmokneme. | Zmokneme-li, pak bude pršet. |

Všimni si druhého řádku: negace „$x$ sudé **nebo** $y$ sudé“ je „$x$ liché **a** $y$ liché“.

> [!example] Úloha 3 (cv. 1): které výroky jsou ekvivalentní s $A \Rightarrow \neg B$?
> $A \Rightarrow \neg B \equiv \neg A \lor \neg B \equiv \neg(A \land B)$ a obměna je $B \Rightarrow \neg A$.
> Ekvivalentní jsou tedy **(b)** $\neg(A\land B)$, **(c)** $B\Rightarrow\neg A$ a **(e)** $\neg A\lor\neg B$.
> Neekvivalentní: (a) $A\land\neg B$ je negace něčeho jiného; (d) $\neg B\Rightarrow A \equiv B \lor A$.

---

## 4. Zjednodušování formulí

Dvě cesty (cv. 2, úlohy 1, 9, 10):

1. **Tabulka**: u dvou proměnných jsou jen 4 řádky. Spočítej tabulku a najdi jednodušší formuli se stejným sloupcem.
2. **Algebra**: přepiš implikace na $\neg \ldots \lor \ldots$ a použij distributivitu, absorpci atd.

**Vzorové zjednodušení:**

$$
(A\land B)\lor A \equiv A,\qquad (A\lor B)\land B\equiv B,\qquad (\neg A\lor B)\land A\equiv A\land B .
$$

Třetí krok po kroku: $(\neg A\lor B)\land A \equiv (\neg A\land A)\lor(B\land A) \equiv \text{(nepravda)}\lor(A\land B) \equiv A\land B$.

$$
\begin{aligned}
(A \land B)\Rightarrow(B\Rightarrow A)
&\equiv \neg(A\land B)\lor(\neg B\lor A)\\
&\equiv \neg A\lor\neg B\lor\neg B\lor A\\
&\equiv A\lor\neg A &&\text{(tautologie, vždy pravdivé)}
\end{aligned}
$$

$$
A \Rightarrow(\neg A\land B)\equiv \neg A\lor(\neg A\land B)\equiv\neg A .
$$

**Jak vyjádřit libovolnou tabulku:** pro každý řádek s hodnotou 1 napiš konjunkci literálů (např. řádek $A{=}0,B{=}1$ dá $\neg A\land B$) a všechny tyto konjunkce spoj disjunkcí.

---

## 5. Úlohy se „skutečnými“ pravdivostními hodnotami

U výroků jako $(2+3<4)\Rightarrow(4-3=1)$ spočítej nejdřív pravdivost částí a pak použij tabulku:

- $2+3<4$ je **0**, $\;4-3=1$ je **1**.
- konjunkce $0\land1=0$; disjunkce $0\lor1=1$; implikace $0\Rightarrow1=1$; $1\Rightarrow0$ by bylo $0$.

---

## 6. Čtení „pravda / nepravda“ z textu (cv. 1, úloha 4)

Označ $N$ = „dnes je neděle“, $U$ = „v učebně je alespoň jeden učitel“. Pak:

| Možnost | Symbolicky | Poznámka |
| --- | --- | --- |
| (a) Jestliže je neděle, v učebně není žádný učitel. | $N \Rightarrow \neg U$ | |
| (b) Dnes je neděle nebo v učebně není žádný učitel. | $N \lor \neg U$ | $\equiv \neg N \Rightarrow \neg U$, **není** ekvivalentní s (a) |
| (c) Jestliže je v učebně učitel, není neděle. | $U \Rightarrow \neg N$ | obměna (a), tedy $\equiv$ (a) |
| (d) Je-li neděle, je každá osoba v učebně učitel. | $N \Rightarrow \text{každý je učitel}$ | jiné tvrzení |

Ekvivalentní jsou jen (a) a (c): obě jsou pravdivé, nebo obě nepravdivé. O (b) a (d) se rozhoduje zvlášť podle skutečné situace v učebně.

> [!warning] Čti zadání doslova
> V těchto úlohách se často mění jediné slovo („je“ / „není“, „nebo“ / „a“). Než odpovíš, přepiš si každou možnost symbolicky a teprve pak porovnávej. Tady (b) vypadá podobně jako (a), ale chybí v něm negace u $N$.

---

## 7. Bonus: ostrov poctivců a padouchů (cv. 1)

A: „Alespoň dva z nás jsou poctivci.“ B: „Nejvýše dva z nás jsou poctivci.“ C: „Všichni jsme poctivci.“

**Postup:** poctivec mluví pravdu, padouch lže (jeho výrok je nepravdivý).

1. **C** nemůže být poctivec: kdyby ano, byli by poctivci všichni, ale pak by B ($\le 2$ poctivci) mluvil nepravdu, a B by tedy byl padouch – spor. Takže **C je padouch**.
2. **B**: kdyby B byl padouch, jeho výrok „nejvýše dva“ by byl nepravdivý, tedy by byli poctivci všichni tři – ale C je padouch. Spor. Takže **B je poctivec** a jeho výrok platí (poctivců je nejvýše dva; sedí to, C je padouch).
3. **A**: zbývá ověřit obě možnosti.
   - A poctivec: poctivci jsou A, B (dva) – A mluví pravdu ✓.
   - A padouch: poctivec je jen B (jeden) – výrok „alespoň dva“ je nepravdivý, což sedí s tím, že A je padouch ✓.

Obě možnosti jsou konzistentní, takže u A se **nedá určit**. Správná je odpověď **4**: *B je poctivec, C je padouch, A nelze určit.*

---

## Shrnutí na jednu stránku

- $\neg(A\land B)\equiv\neg A\lor\neg B$, $\;\neg(A\lor B)\equiv\neg A\land\neg B$.
- $\neg(A\Rightarrow B)\equiv A\land\neg B$.
- $A\Rightarrow B\equiv\neg A\lor B\equiv\neg B\Rightarrow\neg A$.
- Obrácená implikace $B \Rightarrow A$ **není** ekvivalentní s $A\Rightarrow B$.
- Implikace je nepravdivá **jen** při „$1\Rightarrow0$“.

➡️ Další: [[02 - Kvantifikátory]] · ⬅️ [[00 - Přehled]]
