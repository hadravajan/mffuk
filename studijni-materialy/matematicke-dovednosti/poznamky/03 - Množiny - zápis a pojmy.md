---
tags: [matematicke-dovednosti, mnoziny]
cviceni: [5, 6]
---

# 03 – Množiny: zápis a základní pojmy

> [!abstract] Cíl
> Umět množinu **přečíst**, **zapsat** (třemi způsoby), **spočítat její prvky** a nenechat se zmást vnořenými závorkami a prázdnou množinou. Tohle je jádro cvičení 5 a 6 a velká část testu.

Zdroj: **cvičení 5 a 6** (úlohy o zápisech a o počtu prvků).

---

## 1. Co je množina a co je prvek

**Množina** je soubor navzájem rozlišitelných objektů – **prvků**. Množina je určena **jen tím, jaké prvky obsahuje**.

- $a\in A$: $a$ **je prvkem** množiny $A$; $a\notin A$: není.
- Na **pořadí** a na **opakování** nezáleží:
$$\{a,b\}=\{b,a\}=\{a,a,b,b,b\}.$$
- $|A|$ (mohutnost, velikost) je u konečné množiny počet **různých** prvků.

### Prázdná množina

$$\emptyset=\{\}\quad\text{je množina bez prvků, tj.}\quad \forall x : x\notin\emptyset,\qquad |\emptyset|=0 .$$

> [!danger] Největší past kapitoly: $\emptyset$ vs. $\{\emptyset\}$
> - $\emptyset$ je **prázdná krabice** (0 prvků).
> - $\{\emptyset\}$ je **krabice, ve které leží prázdná krabice** (1 prvek, a tím prvkem je $\emptyset$).
>
> Proto $\{\emptyset\}\neq\emptyset$. Podobně $\{\{a\},\{b\}\}\neq\{a,b\}$: vlevo jsou prvky **množiny** $\{a\}$ a $\{b\}$, vpravo **objekty** $a$ a $b$.

> [!tip] Obrázek „krabice“
> Složené závorky jsou krabice. Prvky množiny jsou to, co leží **přímo** v největší krabici – ne to, co je zanořeno hlouběji. Při počítání prvků se podívej jen na nejvyšší úroveň.

---

## 2. Tři způsoby zápisu množiny

### (A) Výčtem prvků (jen pro konečné množiny, nebo „…“ když je vzor zřejmý)

$$A=\{1,3,5,7,9\},\qquad L=\{1,3,5,7,\dots\}.$$

### (B) Vydělením z jiné množiny vlastností

Pro množinu $A$ a výrok $V(x)$:
$$B=\{x\in A\mid V(x)\}$$
čteme „množina všech $x$ z $A$, pro která platí $V(x)$“. Svislá čára znamená „takové, že“. Např. $\{n\in\mathbb N\mid 2\mid n\}$ jsou sudá přirozená čísla.

### (C) Obor hodnot funkce / předpis pro prvky

Pro funkci $f$ a množinu $A$:
$$\{f(x)\mid x\in A\}=\{y\in B\mid \exists x\in A : f(x)=y\}.$$
Například $\{2k\mid k\in\mathbb N\}=\{2,4,6,\dots\}$.

> [!important] Převod mezi (B) a (C)
> Zápis (C) vždy převedeš na (B) pomocí $\exists$:
> $$\{f(x)\mid x\in A\}\;=\;\{y\mid \exists x\in A : y=f(x)\}.$$
> Příklad: $\{(2k+1)^2\mid k\in\mathbb Z\}=\{n\in\mathbb Z\mid \exists k\in\mathbb Z : n=(2k+1)^2\}$.
> Toho se využívá v obou směrech: pozná-li se tvar „$\exists k : x=\dots$“, jde zkrátit na zápis (C).

**Co je „dobře napsaná“ množina:** po svislé čáře musí být **výrok** (pravdivý/nepravdivý pro každé $x$), před ní **kde $x$ žije** (z jaké množiny je bereme).

---

## 3. Prvek, podmnožina, rovnost – nesměšovat

| Symbol | Význam | Příklad (pravda) |
| --- | --- | --- |
| $x\in A$ | $x$ je **prvek** $A$ | $2\in\{1,2,3\}$ |
| $A\subseteq B$ | **každý prvek** $A$ je prvkem $B$ | $\{1,2\}\subseteq\{1,2,3\}$ |
| $A\subsetneq B$ | $A\subseteq B$ a $A\ne B$ (vlastní podmnožina) | $\{1\}\subsetneq\{1,2\}$ |
| $A=B$ | mají **stejné prvky** | $\{1,2\}=\{2,1,1\}$ |

> [!warning] $\in$ a $\subseteq$ jsou různé věci
> - $2\in\{1,2,3\}$, ale $\{2\}\subseteq\{1,2,3\}$ (a **ne** $2\subseteq\ldots$, ani $\{2\}\in\ldots$).
> - Pro $S=\{1,\{1\}\}$ platí: $1\in S$, $\{1\}\in S$ (obojí jsou prvky) **a** $\{1\}\subseteq S$ (protože $1\in S$), **a** $\{\{1\}\}\subseteq S$ (protože $\{1\}\in S$). Ale $\{1,\{1\}\}\in S$ neplatí.

---

## 4. Úlohy o $\emptyset$ (cv. 5, úloha 6)

Které výroky jsou pravdivé?

| Výrok | Pravda? | Zdůvodnění |
| --- | --- | --- |
| (a) $x\in\{x\}$ | **ano** | $\{x\}$ je množina, jejímž (jediným) prvkem je $x$ |
| (b) $\emptyset=\{\emptyset\}$ | ne | vlevo 0 prvků, vpravo 1 prvek |
| (c) $\emptyset\in\{\emptyset\}$ | **ano** | $\emptyset$ je jediný prvek množiny $\{\emptyset\}$ |
| (d) $\emptyset=\mathcal P(\emptyset)$ | ne | $\mathcal P(\emptyset)=\{\emptyset\}$ má 1 prvek |
| (e) $\emptyset\in\{\}$ | ne | $\{\}$ nemá žádný prvek |
| (f) $\emptyset\in\mathcal P(\emptyset)$ | **ano** | $\mathcal P(\emptyset)=\{\emptyset\}$ |

Navíc pro opakování: $\emptyset\subseteq A$ platí pro **každou** množinu $A$ (viz [[02 - Kvantifikátory]], část 4), tedy i $\emptyset\subseteq\emptyset$ a $\emptyset\subseteq\{\emptyset\}$. Ale $\emptyset\in A$ platí jen tehdy, když je $\emptyset$ **prvkem** $A$.

---

## 5. Kolik má množina prvků? (cv. 1 úl. 6, 7; cv. 6 úl. 4)

**Postup:**

1. Podívej se na **nejvyšší úroveň** závorek – to jsou prvky.
2. Rozpoznej, které zápisy jsou **stejný objekt**: $\{\}=\emptyset$, $\{b,a\}=\{a,b\}$, $\{1,1\}=\{1\}$, $\{\{\},\{\}\}=\{\emptyset\}$.
3. Spočítej **různé** objekty.

### Příklady z cvičení

> [!example] $\{a,\{\},\{a,b\},\{a\},\emptyset,\{b,a\},b,a\}$ (cv. 1, úl. 6)
> Prvky na nejvyšší úrovni: $a$, $\{\}$, $\{a,b\}$, $\{a\}$, $\emptyset$, $\{b,a\}$, $b$, $a$.
> Stejné objekty: $\{\}=\emptyset$; $\{a,b\}=\{b,a\}$; $a$ je tam dvakrát.
> **Různé prvky: $a,\ b,\ \emptyset,\ \{a\},\ \{a,b\}$ → 5 prvků.**

> [!example] $\{\emptyset,\{\emptyset\},\{\{\emptyset\}\},\{\},\{\{\},\{\}\}\}$ (cv. 6, úl. 4b)
> $\{\}=\emptyset$ a $\{\{\},\{\}\}=\{\emptyset\}$. Množina je tedy $\{\emptyset,\{\emptyset\},\{\{\emptyset\}\},\emptyset,\{\emptyset\}\}$, různé prvky: $\emptyset$, $\{\emptyset\}$, $\{\{\emptyset\}\}$ → **3 prvky**.

> [!example] $\{x,y,z\}\cup\{z,y,x\}\cup\{x,\{y,z\}\}\cup\{\{y\}\cup\{z\}\}$ (cv. 6, úl. 4c)
> Pozor: $\{y\}\cup\{z\}=\{y,z\}$ (sjednocení dvou množin je množina), takže poslední člen je $\{\{y,z\}\}$.
> Postupně: $\{x,y,z\}\cup\{z,y,x\}=\{x,y,z\}$; přidáním $\{x,\{y,z\}\}$ přibude prvek $\{y,z\}$; přidáním $\{\{y,z\}\}$ nepřibude nic nového (prvek $\{y,z\}$ už tam je). Různé prvky: $x$, $y$, $z$, $\{y,z\}$ → **4 prvky**.
>
> *(V řešení z cvičení stojí „3 prvky“, ale hned vedle jsou vyjmenovány čtyři objekty $x,y,z,\{y,z\}$. Správně je 4. Je to nejspíš překlep, ale kdybys to na cvičení řešil(a) jinak, ověř si to u cvičící.)*

> [!example] $\{1\}\cup\{1,1\}\cup\{1,\{1\},1\}\cup\{1,\{1,1\},1\}$ (cv. 6, úl. 4d)
> Je $\{1,1\}=\{1\}$, $\{1,\{1\},1\}=\{1,\{1\}\}$, $\{1,\{1,1\},1\}=\{1,\{1\}\}$. Sjednocení: **$1$ a $\{1\}$ → 2 prvky.**

> [!example] 9 prvků v (cv. 6, úl. 4a)
> $\{a,b,c,\{a,b,c\},\{\{a\},\{b\},\{c\}\},\{a\},\{b\},\{c\},\{\{a\}\},\{c,b,a\}\}$.
> $\{c,b,a\}=\{a,b,c\}$ – stejný objekt jako čtvrtý prvek. Různé: $a,b,c,\{a,b,c\},\{\{a\},\{b\},\{c\}\},\{a\},\{b\},\{c\},\{\{a\}\}$ → **9 prvků**.

> [!example] Sjednocení $\bigcup_{i=1}^{10}\{i,2i,3i\}$ (cv. 1, úl. 7)
> Vypíšeme: $i=1:\{1,2,3\}$, $2:\{2,4,6\}$, $3:\{3,6,9\}$, $4:\{4,8,12\}$, $5:\{5,10,15\}$, $6:\{6,12,18\}$, $7:\{7,14,21\}$, $8:\{8,16,24\}$, $9:\{9,18,27\}$, $10:\{10,20,30\}$.
> Dohromady (bez opakování): $\{1,2,3,4,5,6,7,8,9,10,12,14,15,16,18,20,21,24,27,30\}$ → **20 prvků**.

---

## 6. Přepis slovního popisu do množinového zápisu

Tohle je **nejčastější typ úlohy** (cv. 5 úl. 7, cv. 6 úl. 1). Postup:

> [!tip] Recept
> 1. **Z čeho beru prvky?** → napiš to před svislou čáru: $\{x\in X\mid\dots\}$.
> 2. **Jaká vlastnost?** → po svislé čáře. Každé slovo „existuje / pro každé / aspoň / některé“ je kvantifikátor ([[02 - Kvantifikátory]]).
> 3. **Zkontroluj** na jednom malém příkladu (např. $X=\{1,2,3\}$), že zápis dává, co chceš.

### Řešené úlohy – cvičení 5

**1. a 2. Množina $A$ a sudá čísla (kvantifikátory ↔ vztah množin)**

Nechť $S$ je množina všech sudých celých čísel. Tři různá tvrzení o množině $A\subseteq\mathbb Z$:

| Slovní tvrzení | Formule | Vztah $A$ a $S$ |
| --- | --- | --- |
| (a) Každé číslo z $A$ je sudé. | $\forall a\in A : \frac a2\in\mathbb Z$ (nebo $\forall a\in\mathbb Z : (a\in A\Rightarrow\frac a2\in\mathbb Z)$) | $A\subseteq S$ |
| (b) $A$ obsahuje všechna sudá čísla. | $\forall a\in\mathbb Z : (\frac a2\in\mathbb Z\Rightarrow a\in A)$ | $S\subseteq A$ |
| (c) $x\in A$ právě tehdy, když je $x$ sudé. | $\forall a\in\mathbb Z : (a\in A\Leftrightarrow\frac a2\in\mathbb Z)$ | $A=S$ |

Naučí tě to hlavní věc: **směr implikace určuje směr inkluze.** „$a\in A\Rightarrow a$ je sudé“ je $A\subseteq S$; „$a$ je sudé $\Rightarrow a\in A$“ je $S\subseteq A$; obě naráz je rovnost.

**3. Liché přirozené číslo (co nejvíc způsobů)**

$$
\begin{aligned}
L&=\{1,3,5,7,\dots\}=\{2n-1\mid n\in\mathbb N\}=\{2n+1\mid n\in\mathbb N_0\}\\
&=\{n\in\mathbb N\mid 2\nmid n\}=\{n\in\mathbb N\mid \exists k\in\mathbb N_0 : n=2k+1\}\\
&=\{n\in\mathbb N\mid n\equiv1\pmod2\}=\{n\in\mathbb N\mid \forall k\in\mathbb N : 2k\neq n\}.
\end{aligned}
$$

(Ověř si u každého, že dá $1,3,5,\dots$. Pozor na to, odkud $n$ nebo $k$ běží: $n\in\mathbb N$ ($n\ge1$) versus $k\in\mathbb N_0$ ($k\ge0$).)

**7. Zapište množinovým zápisem**

| Úloha | Zápis | Poznámka |
| --- | --- | --- |
| (a) mocniny dvojky | $A=\{2^k\mid k\in\mathbb N\}=\{x\in\mathbb N\mid\exists k\in\mathbb N : x=2^k\}$ | |
| (b) celočíselní dělitelé $n\in\mathbb Z$ | $B=\{x\in\mathbb Z\mid x\mid n\}=\{x\in\mathbb Z\mid\exists k\in\mathbb Z : n=kx\}$ | $x\mid n$ znamená „$x$ dělí $n$“ |
| (c) druhé mocniny lichých celých čísel | $C=\{(2k+1)^2\mid k\in\mathbb Z\}$ | |
| (d) prvočísla | $D=\{p\in\mathbb N\mid p>1\land\forall d\in\mathbb N : (d\mid p\Rightarrow d=1\lor d=p)\}$ nebo $\{p\in\mathbb N\mid\lvert\{d\in\mathbb N\mid d\mid p\}\rvert=2\}$ | dva dělitelé = $1$ a $p$ |
| (e) čísla s právě 3 děliteli | $E=\{x\in\mathbb N\mid\lvert\{d\in\mathbb N\mid d\mid x\}\rvert=3\}=\{p^2\mid p\in D\}$ | jsou to druhé mocniny prvočísel |
| (f) čísla s právě 12345 děliteli | $F=\{x\in\mathbb N\mid\lvert\{d\in\mathbb N\mid d\mid x\}\rvert=12345\}$ | stejná konstrukce jako (e) |
| (g) prvky aspoň ve dvou z $M_1,\dots,M_n$ | $G=\bigcup_{1\le i<j\le n}(M_i\cap M_j)$ | $x\in G\Leftrightarrow\exists i\neq j : x\in M_i\land x\in M_j$ |
| (h) podmnožiny $M$ sudé velikosti | $H=\{X\in\mathcal P(M)\mid\exists k\in\mathbb N_0 : \lvert X\rvert=2k\}$ | |

*Proč jsou čísla s 3 děliteli právě $p^2$:* dělitelé libovolného $x$ se dělí do dvojic $(d,x/d)$. Lichý počet dělitelů nastane jen tehdy, když je $x$ druhá mocnina $m^2$ (dvojice $(m,m)$ se „sloučí“). Pak dělitelé $m^2$ jsou $1,m,m^2$ (a žádný další), což nastane jen pro $m$ prvočíslo.

### Řešené úlohy – cvičení 6 (úl. 1)

Dané: $X,Y,Z\subseteq\mathbb N$ pevné množiny.

| Slovní popis | Zápis |
| --- | --- |
| (a) čísla z $X$ dělitelná **některým** číslem z $Y$ | $A=\{x\in X\mid\exists y\in Y : y\mid x\}$ |
| (b) čísla z $Y$, která jsou součtem **dvou různých** čísel z $X$ | $B=\{y\in Y\mid\exists x_1,x_2\in X : (x_1\ne x_2\land y=x_1+x_2)\}$ |
| (c) čísla z $Z$ větší než **libovolné** číslo z $Y$ | $C=\{z\in Z\mid\forall y\in Y : z>y\}$ |
| (d) rozdíly dvou různých čísel z $X$ | $D=\{d\in\mathbb Z\mid\exists x_1,x_2\in X : (x_1\neq x_2\land d=x_1-x_2)\}$ |
| (e) celočíselné násobky čísla z $X$ **nebo** $Y$ | $E=\{k\cdot x\mid k\in\mathbb Z\land x\in X\cup Y\}$ |
| (f) druhé mocniny čísel z $X$, větší než libovolné z $Y$, ale menší než některé z $Z$ | $F=\{n^2\mid n\in X\land(\forall y\in Y : n^2>y)\land(\exists z\in Z : n^2<z)\}$ |

> [!warning] Tři častá nedorozumění v těchto úlohách
> 1. **„Libovolné“ znamená $\forall$**, „některé“ znamená $\exists$.
> 2. **„Dvě různá čísla“**: vezmeš $x_1,x_2$ a **musíš napsat** $x_1\neq x_2$; bez toho by mohlo být $x_1=x_2$.
> 3. **Kam patří výsledek**: v (a),(b),(c) jde o *čísla z dané množiny* ($x\in X$, $y\in Y$, $z\in Z$) – nepiš $\{x\in\mathbb N\mid\dots\}$. V (d),(e) výsledek **není** z $X$, proto bereš širší množinu ($\mathbb Z$, nebo předpis typu $\{f(\cdot)\mid\dots\}$).

*(O (e): zda násobek bere $k\in\mathbb N$, nebo $k\in\mathbb Z$, záleží na výkladu „celočíselný násobek“. Řešení kurzu používá $k\in\mathbb Z$ – zahrnuje i $0$ a záporné násobky. Na testu **vždy napiš, odkud $k$ bereš**.)*

---

## 7. Co si odnést

- Množina = její prvky; pořadí a opakování nehrají roli.
- $\emptyset$ (0 prvků) $\ne\{\emptyset\}$ (1 prvek).
- Zápisy $\{x\in A\mid V(x)\}$ a $\{f(x)\mid x\in A\}$ se převádějí přes $\exists$.
- Při počítání prvků hledej **stejné objekty v různém zápisu** ($\{\}=\emptyset$, $\{a,b\}=\{b,a\}$).
- „Libovolný“ = $\forall$, „některý/existuje“ = $\exists$, „dva různé“ = $x_1\neq x_2$.

⬅️ [[02 - Kvantifikátory]] · ➡️ [[04 - Podmnožiny a množinové operace]] · [[00 - Přehled]]
