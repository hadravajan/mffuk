---
tags: [matematicke-dovednosti, tahak]
cviceni: [5, 6]
---

# 06 – Pasti a tahák před testem

> [!abstract] Jak to používat
> Přečti si to večer před testem a ještě jednou ráno. Nahoře je tahák (co musíš umět), dole seznam nejčastějších chyb a doporučený postup při psaní.

---

## 1. Tahák: co musíš umět zpaměti

### Zápis množin

| Typ | Vzor |
| --- | --- |
| výčtem | $\{1,3,5,7,9\}$, $\{1,3,5,\dots\}$ |
| vlastností | $\{x\in X\mid V(x)\}$ |
| předpisem | $\{f(x)\mid x\in X\}=\{y\mid\exists x\in X : y=f(x)\}$ |

Pozor: $\{a,b\}=\{b,a\}=\{a,a,b\}$; $\emptyset\neq\{\emptyset\}$; $\{\{a\},\{b\}\}\neq\{a,b\}$.

### Vztahy mezi množinami

| Tvrzení | Zápis |
| --- | --- |
| $A\subseteq B$ | $\forall x\in A : x\in B$ |
| $A=B$ | $A\subseteq B\land B\subseteq A$ |
| $A\nsubseteq B$ | $\exists x\in A : x\notin B$ |
| $A\cap B=\emptyset$ | $\forall x\in A : x\notin B$ |
| $A\setminus B\ne\emptyset$ | $\exists x\in A : x\notin B$ |
| $x\in\bigcup A_i$ | $\exists i : x\in A_i$ |
| $x\in\bigcap A_i$ | $\forall i : x\in A_i$ |

### Operace

$$
A\cup B=\{x\mid x\in A\lor x\in B\},\quad
A\cap B=\{x\mid x\in A\land x\in B\},\quad
A\setminus B=\{x\in A\mid x\notin B\}.
$$

### Potenční množina a velikosti

$$
X\in\mathcal P(A)\Leftrightarrow X\subseteq A,\qquad |\mathcal P(A)|=2^{|A|},\qquad |A\cup B|=|A|+|B|-|A\cap B|,\qquad |A\times B|=|A||B|.
$$

### Prázdná množina

$\emptyset\subseteq A$ vždy. $\mathcal P(\emptyset)=\{\emptyset\}$. $\forall x\in\emptyset$ vždy pravdivé, $\exists x\in\emptyset$ vždy nepravdivé.

### Logika

$$
\neg(P\land Q)\equiv\neg P\lor\neg Q,\ \ \neg(P\lor Q)\equiv\neg P\land\neg Q,\ \ \neg(P\Rightarrow Q)\equiv P\land\neg Q,\ \ \neg\forall\equiv\exists\neg,\ \ \neg\exists\equiv\forall\neg .
$$

---

## 2. Nejčastější pasti

> [!danger] Zkontroluj tyto věci, než odevzdáš
> 1. **$\in$ vs. $\subseteq$.** $2\in A$ (prvek), $\{2\}\subseteq A$ (podmnožina). U množin množin to rozhoduje o správnosti.
> 2. **$\emptyset$ vs. $\{\emptyset\}$.** Počet prvků: 0 vs. 1. $\mathcal P(\emptyset)$ má 1 prvek.
> 3. **Počítání prvků:** rozepiš zápisy na stejné objekty ($\{\}=\emptyset$, $\{b,a\}=\{a,b\}$) a počítej jen nejvyšší úroveň závorek.
> 4. **$\forall$ s implikací, $\exists$ s konjunkcí.** Nikdy ne naopak.
> 5. **Pořadí kvantifikátorů**: $\forall x\,\exists y$ není $\exists y\,\forall x$.
> 6. **Negace $\subseteq$:** $\exists x\in A : x\notin B$. (Ne „$B\subseteq A$“.)
> 7. **Doména:** u každého kvantifikátoru napiš, přes co běží. Kdo je $\mathbb N$: $\{1,2,3,\dots\}$, $\mathbb N_0$ obsahuje nulu.
> 8. **„Dvě různá čísla“** → musíš napsat $x_1\neq x_2$.
> 9. **„Libovolný/každý“ = $\forall$**, **„některý/existuje/aspoň jeden“ = $\exists$**, **„žádný“ = $\forall$ s negací** (nebo $\neg\exists$).
> 10. **Závorky u $\bigcup$ a $\bigcap$:** $\{\bigcup\ldots\}$ (obaluje výsledek) vs. $\bigcup\{\ldots\}$ (sjednocuje množiny, v nichž je jeden prvek).
> 11. **Rozdíl množin není symetrický** a není asociativní.
> 12. **Důkaz rovnosti = ekvivalence nebo dvě inkluze; vyvrácení = jeden protipříklad.** Nestačí „na obrázku vypadá…“.
> 13. **Prázdná množina a $\forall$:** $\forall x\in\emptyset : \dots$ je pravdivé.
> 14. **Nepodléhej první intuici u „$A\cup(B\cap C)$ vs. $A\cap(B\cup C)$“.** Jsou různé (v obecném případě).

---

## 3. Mapa: které cvičení k čemu

| Co trénovat | Cvičení | Poznámky |
| --- | --- | --- |
| Negace výroků, implikace | 1, 2 | [[01 - Výroková logika]] |
| Kvantifikátory, negace, prázdná množina | 3, 4 | [[02 - Kvantifikátory]] |
| Zápis množin (výčet, vlastnost, předpis) | **5** (1–3, 7), **6** (1) | [[03 - Množiny - zápis a pojmy]] |
| Počty prvků, vnořené množiny, $\emptyset$ | 1 (6, 7), 5 (6), **6** (4) | [[03 - Množiny - zápis a pojmy]] |
| Podmnožina, rovnost množin, operace | **5** (4, 8), 1 (8) | [[04 - Podmnožiny a množinové operace]] |
| Potenční množina, indexované $\bigcup,\bigcap$ | 5 (5, 6), **6** (2, 3, 5) | [[05 - Potenční množina a nekonečná sjednocení]] |

---

## 4. Jak psát odpověď (a získat body)

> [!tip] Doporučený postup u každé úlohy
> 1. **Přečti zadání celé** a podtrhni kvantifikační slova (každý, existuje, žádný, aspoň).
> 2. **Napiš domény** ($x\in A$, $k\in\mathbb Z$, …).
> 3. U zápisů **zkus malý příklad** (např. pro $X=\{1,2,3\}$ vyjdou očekávané prvky?).
> 4. U „pravda / nepravda“: **zdůvodni** (protipříklad, nebo krátký argument). Samotné „ano/ne“ bývá za méně bodů.
> 5. U rovností množin: napiš, jestli dokazuješ ekvivalencemi, nebo vyvracíš protipříkladem.
> 6. Při počítání prvků **vypiš všechny prvky** (stačí na jeden řádek).

**Čas:** písemka trvá 15–20 minut pro max. 20 bodů. Rozpočet: cca 3–4 minuty na úlohu, nejtěžší nech na konec a **nenech žádnou úlohu prázdnou** – částečné body se počítají.

---

## 5. Plán přípravy (doporučení)

1. **30 min:** přečti [[03 - Množiny - zápis a pojmy]], [[04 - Podmnožiny a množinové operace]] a [[05 - Potenční množina a nekonečná sjednocení]] (stačí projít příklady a ukázat si na papír, jak vychází).
2. **40 min:** vyřeš cvičné PDF (části 1–5), pak si ho zkontroluj podle klíče.
3. **20 min:** část 6 (cvičná písemka) **na čas**, 20 minut. Pak vyhodnoť.
4. **10 min:** projdi svoje chyby, přečti si znovu sekci „Nejčastější pasti“ výše.

⬅️ [[05 - Potenční množina a nekonečná sjednocení]] · [[00 - Přehled]]
