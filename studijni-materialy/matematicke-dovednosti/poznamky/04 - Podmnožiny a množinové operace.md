---
tags: [matematicke-dovednosti, mnoziny]
cviceni: [1, 5, 6]
---

# 04 – Podmnožiny, sjednocení, průnik, rozdíl

> [!abstract] Cíl
> Umět **definovat** vztahy mezi množinami pomocí kvantifikátorů, **spočítat** množinové operace a **dokázat nebo vyvrátit** rovnost dvou množinových výrazů. Podmnožina, sjednocení a průnik jsou podle všeho těžiště pondělního testu.

Zdroj: **cvičení 5 (úlohy 4, 5, 8)**, **cvičení 1 (úloha 8)**, **cvičení 6 (úloha 3)**.

---

## 1. Definice operací

Pro množiny $A,B$:

| Operace | Zápis | Definice | Slovně |
| --- | --- | --- | --- |
| sjednocení | $A\cup B$ | $\{x\mid x\in A\lor x\in B\}$ | v $A$ **nebo** v $B$ (i v obou) |
| průnik | $A\cap B$ | $\{x\mid x\in A\land x\in B\}$ | v $A$ **a zároveň** v $B$ |
| rozdíl | $A\setminus B$ | $\{x\in A\mid x\notin B\}$ | v $A$, ale **ne** v $B$ |
| kartézský součin | $A\times B$ | $\{(a,b)\mid a\in A\land b\in B\}$ | všechny **uspořádané** dvojice |
| potenční množina | $\mathcal P(A)=2^A$ | $\{X\mid X\subseteq A\}$ | množina **všech podmnožin** $A$ |

> [!tip] Spojky ↔ operace
> $\cup$ se chová jako $\lor$, $\cap$ jako $\land$, $\setminus$ jako „$\land\neg$“. Každý množinový výraz tak převedeš na logický výrok o prvku $x$ a pak použiješ [[01 - Výroková logika]].

**Příklad:** $A=\{1,2,3,4\}$, $B=\{3,4,5\}$.

$$
A\cup B=\{1,2,3,4,5\},\quad A\cap B=\{3,4\},\quad A\setminus B=\{1,2\},\quad B\setminus A=\{5\}.
$$

> [!warning] Rozdíl není symetrický
> $A\setminus B\neq B\setminus A$ (obecně). Rozdíl také **neodečítá čísla**: $\{1,2,3\}\setminus\{3,4\}=\{1,2\}$ (čtyřka v $A$ nebyla, takže se nic „záporného“ neděje). Na cvičení 1 se rozdíl píše i jako $A-B$.

**Dvojice vs. množina:** $(a,b)\neq(b,a)$ pro $a\ne b$ (dvojice je **uspořádaná**), ale $\{a,b\}=\{b,a\}$. Proto $A\times B\neq B\times A$ (obecně).

---

## 2. Být podmnožinou a další základní vztahy (cv. 5, úloha 4)

> [!important] Základní slovník – umět zpaměti
> | Tvrzení | Kvantifikátory |
> | --- | --- |
> | $A\subseteq B$ | $\forall x\in A : x\in B$ |
> | $A=B$ | $\forall x\,(x\in A\Leftrightarrow x\in B)$, nebo $A\subseteq B\land B\subseteq A$ |
> | $A\nsubseteq B$ | $\exists x\in A : x\notin B$ |
> | $A\cap B=\emptyset$ | $\forall x\in A : x\notin B$ (ekvivalentně $\neg\exists x\,(x\in A\land x\in B)$) |
> | $A\cap B\neq\emptyset$ | $\exists x\in A : x\in B$ |
> | $A\cup B\neq\emptyset$ | $\exists x\,(x\in A\lor x\in B)$, tj. $A\neq\emptyset$ nebo $B\neq\emptyset$ |
> | $A\setminus B\neq\emptyset$ | $\exists x\in A : x\notin B$ — **totéž co $A\nsubseteq B$** |
> | $A\setminus B=\emptyset$ | $\forall x\in A : x\in B$ — **totéž co $A\subseteq B$** |
> | $A\subsetneq B$ | $A\subseteq B\land\exists x\in B : x\notin A$ |

### Negace $A\subseteq B$

$\neg(\forall x\in A : x\in B)\equiv\exists x\in A : x\notin B$. **Neříká**, že „$B$ je podmnožinou $A$“ ani že „$A$ a $B$ jsou disjunktní“; říká jen, že v $A$ je alespoň jeden prvek mimo $B$.

> [!warning] Dva typické omyly
> 1. $A\nsubseteq B$ **neznamená** $B\subseteq A$. Může být $A=\{1,2\}$, $B=\{2,3\}$: ani jedna inkluze neplatí.
> 2. $A\cap B=\emptyset$ **neznamená** $A=\emptyset$ nebo $B=\emptyset$. Množiny $\{1\}$ a $\{2\}$ jsou neprázdné a přesto disjunktní.

### Řešení cv. 5 úl. 4 s vysvětlením

- (a) $A\subseteq B$: $\forall x\in A : x\in B$.
- (b) $A=B$: $(\forall x\in A : x\in B)\land(\forall x\in B : x\in A)$.
- (c) $A\nsubseteq B$: $\exists x\in A : x\notin B$.
- (d) $A\cup B\neq\emptyset$: $(\exists x\in A : x=x)\lor(\exists x\in B : x=x)$, stručněji $\exists x : (x\in A\lor x\in B)$. *(V řešení cvičení je zápis „$(\exists x\in A)\lor(\exists x\in B)$“ – říká totéž, ale u $\exists$ by měla následovat vlastnost; bezpečnější je psát $\exists x\,(x\in A\lor x\in B)$.)*
- (e) $A\cap B=\emptyset$: $\forall x\in A : x\notin B$.
- (f) $A\setminus B\neq\emptyset$: $\exists x\in A : x\notin B$.

### Vztah $A\subseteq B$ a operací

$$
A\subseteq B\;\Longleftrightarrow\;A\cup B=B\;\Longleftrightarrow\;A\cap B=A\;\Longleftrightarrow\;A\setminus B=\emptyset .
$$

---

## 3. Zákony pro množinové operace

Pro libovolné množiny $A,B,C$:

| Zákon | Vzorec |
| --- | --- |
| komutativita | $A\cup B=B\cup A$, $\;A\cap B=B\cap A$ |
| asociativita | $(A\cup B)\cup C=A\cup(B\cup C)$, totéž pro $\cap$ |
| **distributivita** | $A\cup(B\cap C)=(A\cup B)\cap(A\cup C)$ |
| **distributivita** | $A\cap(B\cup C)=(A\cap B)\cup(A\cap C)$ |
| absorpce | $A\cup(A\cap B)=A$, $\;A\cap(A\cup B)=A$ |
| idempotence | $A\cup A=A$, $\;A\cap A=A$ |
| s prázdnou množinou | $A\cup\emptyset=A$, $\;A\cap\emptyset=\emptyset$, $\;A\setminus\emptyset=A$, $\;\emptyset\setminus A=\emptyset$ |
| **De Morgan (rozdíl)** | $A\setminus(B\cup C)=(A\setminus B)\cap(A\setminus C)$ |
| **De Morgan (rozdíl)** | $A\setminus(B\cap C)=(A\setminus B)\cup(A\setminus C)$ |
| rozdíl jako průnik | $A\setminus B=A\cap B^{c}$ (kde $B^c$ je doplněk do univerza) |

Odpovídají to přesně logickým zákonům z [[01 - Výroková logika]] (distributivita $\land,\lor$; De Morgan).

> [!warning] Neplatí (obecně)
> - $A\cup(B\cap C)\ne A\cap(B\cup C)$ – nepřehoď $\cup$ a $\cap$. Protipříklad: $A=\{1\}$, $B=C=\emptyset$ → levá strana $\{1\}$, pravá $\emptyset$.
> - $A\setminus(B\setminus C)\ne(A\setminus B)\setminus C$ – rozdíl není asociativní.
> - $(A\setminus B)\cup B\neq A$ (vychází $A\cup B$).

---

## 4. Jak dokázat rovnost množin

**Metoda 1: řetěz ekvivalencí (stejné prvky).** Vezmi libovolné $x$ a upravuj výrok „$x\in\text{levá strana}$“ až na „$x\in\text{pravá strana}$“. Všechny kroky musí být **ekvivalence** ($\Leftrightarrow$).

**Metoda 2: dvě inkluze.** Dokaž $L\subseteq P$ a $P\subseteq L$. Pro každou: „Nechť $x\in L$. Pak … Tedy $x\in P$.“

**Metoda 3: tabulka členství** (jako pravdivostní tabulka). Pro každou kombinaci „leží $x$ v $A$/$B$/$C$?“ spočítáš, zda $x$ leží ve výrazu. Pro tři množiny je 8 řádků. Pokud se sloupce shodují, množiny jsou rovné; pokud ne, řádek s rozdílem ti **dá protipříklad**.

> [!example] Příklad: $(A\setminus B)\setminus(B\setminus C)=A\setminus B$ (cv. 5, úl. 8: (e)=(h))
> Pro libovolné $x$:
> $$
> \begin{aligned}
> x\in(A\setminus B)\setminus(B\setminus C)
> &\Leftrightarrow x\in A\setminus B\ \land\ x\notin B\setminus C\\
> &\Leftrightarrow (x\in A\land x\notin B)\ \land\ \neg(x\in B\land x\notin C)\\
> &\Leftrightarrow (x\in A\land x\notin B)\ \land\ (x\notin B\lor x\in C).
> \end{aligned}
> $$
> V posledním kroku je druhý činitel pravdivý automaticky, protože už víme $x\notin B$. Zůstává $x\in A\land x\notin B$, tedy $x\in A\setminus B$. $\blacksquare$

> [!example] Příklad: $(B\cup C)\setminus A=(B\setminus A)\cup(C\setminus A)$ (cv. 5, úl. 8: (f)=(g))
> $$
> \begin{aligned}
> x\in(B\cup C)\setminus A&\Leftrightarrow(x\in B\lor x\in C)\land x\notin A\\
> &\Leftrightarrow(x\in B\land x\notin A)\lor(x\in C\land x\notin A)\quad\text{(distributivita)}\\
> &\Leftrightarrow x\in(B\setminus A)\cup(C\setminus A).\ \blacksquare
> \end{aligned}
> $$

> [!example] Příklad: $A\cup(B\cap C)=(A\cup B)\cap(A\cup C)$ (cv. 5, úl. 8: (a)=(c))
> $x\in A\cup(B\cap C)\Leftrightarrow x\in A\lor(x\in B\land x\in C)\Leftrightarrow(x\in A\lor x\in B)\land(x\in A\lor x\in C)\Leftrightarrow x\in(A\cup B)\cap(A\cup C)$ – opět distributivita logických spojek. Obdobně (b)=(d): $A\cap(B\cup C)=(A\cap B)\cup(A\cap C)$.

---

## 5. Cvičení 5, úloha 8 – kompletní tabulka členství

Které z množin (a)–(h) jsou si rovny?

| (a) | $A\cup(B\cap C)$ | (e) | $A\setminus B$ |
| --- | --- | --- | --- |
| (b) | $A\cap(B\cup C)$ | (f) | $(B\cup C)\setminus A$ |
| (c) | $(A\cup B)\cap(A\cup C)$ | (g) | $(B\setminus A)\cup(C\setminus A)$ |
| (d) | $(A\cap B)\cup(A\cap C)$ | (h) | $(A\setminus B)\setminus(B\setminus C)$ |

Tabulka (1 = „$x$ leží v množině“):

| $A$ | $B$ | $C$ | (a) | (b) | (c) | (d) | (e) | (f) | (g) | (h) |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| 1 | 1 | 1 | 1 | 1 | 1 | 1 | 0 | 0 | 0 | 0 |
| 1 | 1 | 0 | 1 | 1 | 1 | 1 | 0 | 0 | 0 | 0 |
| 1 | 0 | 1 | 1 | 1 | 1 | 1 | 1 | 0 | 0 | 1 |
| 1 | 0 | 0 | 1 | 0 | 1 | 0 | 1 | 0 | 0 | 1 |
| 0 | 1 | 1 | 1 | 0 | 1 | 0 | 0 | 1 | 1 | 0 |
| 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 1 | 0 |
| 0 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 1 | 1 | 0 |
| 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |

Stejné sloupce: **(a)=(c)**, **(b)=(d)**, **(e)=(h)**, **(f)=(g)**. Ostatní dvojice se liší (například (a)≠(b) na řádku $A{=}1,B{=}0,C{=}0$).

Jak čteš řádek: třetí řádek $(1,0,1)$ znamená $x\in A$, $x\notin B$, $x\in C$. Pak $x\in(e)=A\setminus B$ ✔ (1), ale $x\notin(f)$ ($x\in A$, takže není v $(B\cup C)\setminus A$) ✔ (0).

---

## 6. Cvičení 1, úloha 8 – čtyři množiny

Pro libovolné $A,B,C,D$ definujme
$$
M_1=A-(B\cup C\cup D),\quad M_2=A-(B\cap C\cap D),\quad M_3=(A-B)\cup(A-C)\cup(A-D),\quad M_4=(A-B)\cap(A-C)\cap(A-D).
$$

Podle De Morganových zákonů pro rozdíl:

- $M_1=M_4$, protože $A\setminus(B\cup C\cup D)=(A\setminus B)\cap(A\setminus C)\cap(A\setminus D)$,
- $M_2=M_3$, protože $A\setminus(B\cap C\cap D)=(A\setminus B)\cup(A\setminus C)\cup(A\setminus D)$.

A protože $M_1$ je „prvky $A$ mimo **všechny** z $B,C,D$“, zatímco $M_2$ je „prvky $A$ mimo **aspoň jednu** z $B,C,D$“, platí
$$
M_1=M_4\;\subseteq\;M_2=M_3 .
$$
Opačná inkluze obecně neplatí: pro $A=\{1\}$, $B=\{1\}$, $C=D=\emptyset$ je $M_2=\{1\}$, ale $M_1=\emptyset$.

---

## 7. Velikosti množin

Pro konečné množiny:

$$
|A\cup B|=|A|+|B|-|A\cap B|,\qquad |A\times B|=|A|\cdot|B|,\qquad |\mathcal P(A)|=2^{|A|}.
$$

**Proč $-|A\cap B|$:** prvky společné $A$ i $B$ jsme v součtu $|A|+|B|$ započítali dvakrát, jednou je musíme odečíst.

**Tři množiny** (princip inkluze a exkluze):
$$
|A\cup B\cup C|=|A|+|B|+|C|-|A\cap B|-|A\cap C|-|B\cap C|+|A\cap B\cap C| .
$$

**Příklad:** $|A|=10$, $|B|=7$, $|A\cap B|=3$ → $|A\cup B|=14$ a $|A\times B|=70$ a $|\mathcal P(A)|=1024$.

Úlohy typu „v třídě má 20 lidí angličtinu, 15 němčinu, 5 obojí…“ jsou přesně $|A\cup B|=|A|+|B|-|A\cap B|$.

---

## 8. Co si odnést

- $A\subseteq B$ znamená $\forall x\in A : x\in B$; negace je $\exists x\in A : x\notin B$.
- $A\setminus B\neq\emptyset\iff A\nsubseteq B$.
- $\cup\leftrightarrow\lor$, $\cap\leftrightarrow\land$; množinové zákony jsou logické zákony.
- Rovnost dokazuj řetězem ekvivalencí nebo dvěma inkluzemi; **vyvracej protipříkladem** (konkrétní malé množiny) nebo tabulkou členství.
- $|A\cup B|=|A|+|B|-|A\cap B|$.

⬅️ [[03 - Množiny - zápis a pojmy]] · ➡️ [[05 - Potenční množina a nekonečná sjednocení]] · [[00 - Přehled]]
