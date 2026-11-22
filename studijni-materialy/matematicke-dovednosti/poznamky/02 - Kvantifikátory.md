---
tags: [matematicke-dovednosti, kvantifikatory]
cviceni: [3, 4]
---

# 02 – Výroky s kvantifikátory

> [!abstract] Proč to je důležité pro množiny
> Skoro každé tvrzení o množinách se přepisuje do kvantifikátorů: $A\subseteq B$ znamená „pro každý prvek z $A$ platí, že leží v $B$“. Kdo umí kvantifikátory, umí množinový zápis. Na testu z množin jsou kvantifikátory **ve skoro každé úloze**.

Zdroj: zadání a řešení **cvičení 3 a 4** (a část cvičení 1).

---

## 1. Dva kvantifikátory

| Zápis | Čteme | Příklad |
| --- | --- | --- |
| $\forall x : V(x)$ | pro každé $x$ platí $V(x)$ | $\forall x\in\mathbb N : x^2>0$ |
| $\exists x : V(x)$ | existuje $x$, pro které platí $V(x)$ | $\exists x\in\mathbb R : (x>0\land x^2+x-4<20)$ |
| $\exists!\,x : V(x)$ | existuje **právě jedno** $x$ s $V(x)$ | |

> [!tip] Vždy uveď, přes jakou množinu kvantifikuješ
> Píšeme $\forall x\in\mathbb Z$, $\exists a\in A$ atd. Na testu bez toho ztrácíš body, protože výrok nemá jednoznačný význam.

**Konvence kurzu:** $\mathbb N=\{1,2,3,\dots\}$ (bez nuly), $\mathbb N_0=\mathbb N\cup\{0\}$. Pokud zadání neříká doménu, použij $\mathbb N$.

---

## 2. Negace

$$
\neg(\forall x : V(x)) \equiv \exists x : \neg V(x),\qquad
\neg(\exists x : V(x)) \equiv \forall x : \neg V(x).
$$

**Pravidlo:** negace *převrátí kvantifikátor* a *znegovanou vlastnost* nechá uvnitř. U víc kvantifikátorů za sebou se převrátí **všechny** a pořadí se zachová:

$$
\neg\big(\forall n\,\exists m : P(n,m)\big)\equiv \exists n\,\forall m : \neg P(n,m).
$$

### „Pozor na záporné věty“ (cv. 3)

| Věta | Zápis | Ekvivalentně |
| --- | --- | --- |
| Ne každý student získá zápočet. | $\neg(\forall s : \text{získá})$ | $\exists s : \text{nezíská}$ |
| Žádný student nezíská zápočet. | $\neg(\exists s : \text{získá})$ | $\forall s : \text{nezíská}$ |
| Neexistuje student, který nezíská zápočet. | $\neg(\exists s : \text{nezíská})$ | $\forall s : \text{získá}$ |

> [!warning] „Žádný“ ≠ „ne každý“
> „Žádný student nezíská“ říká, že **všichni získají**. „Ne každý student získá“ říká, že **aspoň jeden nezíská**. To jsou dvě zcela jiná tvrzení.

### Procvičené negace (cv. 3, úloha 3)

| Původní | Negace |
| --- | --- |
| Každý student byl na imatrikulaci. | Existuje student, který nebyl na imatrikulaci. |
| Libovolný student, který umí derivovat, umí integrovat. | Existuje student, který umí derivovat, ale neumí integrovat. |
| Někteří vyučující nikdy neučili v S1. | Všichni vyučující alespoň jednou učili v S1. |
| Žádná přednáška není v N4. | Alespoň jedna přednáška je v N4. |
| Není zde nikdo, kdo nemá maturitu. | Je zde alespoň jeden, kdo nemá maturitu. |

Vzor druhého řádku: $\neg\big(\forall s\,(D(s)\Rightarrow I(s))\big)\equiv\exists s\,(D(s)\land\neg I(s))$. Negace „$\forall$ + implikace“ je „$\exists$ + konjunkce“.

---

## 3. Kvantifikace s omezující podmínkou

Zápis $\forall x\in\mathbb R,\ x>0 : V(x)$ je **zkratka**:

$$
\forall x\in\mathbb R : (x>0 \Rightarrow V(x)),
\qquad\qquad
\exists x\in\mathbb R,\ x>0 : V(x)\ \text{ je zkratka }\ \exists x\in\mathbb R : (x>0 \land V(x)).
$$

> [!important] Zlaté pravidlo
> - **$\forall$ se podmínkou spojuje implikací $\Rightarrow$.**
> - **$\exists$ se podmínkou spojuje konjunkcí $\land$.**
>
> Kdyby ses spletl(a) (např. $\forall x : (x>0 \land V(x))$), tvrdil(a) bys, že *každé* $x$ je kladné – a to je jiný výrok.

**Příklady z cv. 4, úloha 1** (přepis na kvantifikaci přes celé $\mathbb R$):

$$
\forall x<0 : x^2>0 \;\longrightarrow\; \forall x\in\mathbb R : (x<0\Rightarrow x^2>0),
$$
$$
\forall y\ne0 : y^3\ne0 \;\longrightarrow\; \forall y\in\mathbb R : (y\ne0\Rightarrow y^3\ne0),
$$
$$
\exists z>0 : z^2=2 \;\longrightarrow\; \exists z\in\mathbb R : (z>0\land z^2=2).
$$

Stejný princip platí i pro množiny: $\forall a\in A : V(a)$ je totéž co $\forall a : (a\in A \Rightarrow V(a))$ a $\exists a\in A : V(a)$ je totéž co $\exists a : (a\in A\land V(a))$.

---

## 4. Prázdná množina

Pro $M=\emptyset$:

- $\forall x\in M : V(x)$ je **vždy pravdivý** (není co porušit – „slib bez předpokladu“),
- $\exists x\in M : V(x)$ je **vždy nepravdivý** (není nic, co by mohlo vlastnost splnit).

To platí pro libovolné $V$. Vzorový příklad (cv. 3, úl. 1d): $\forall x\in\emptyset : x^2\ne k$ je pravdivé pro každé $k$, $\exists x\in\emptyset : x^2\ne k$ je nepravdivé pro každé $k$.

**Důsledek pro množiny:** $\emptyset\subseteq A$ platí pro každou množinu $A$, protože $\forall x\in\emptyset : x\in A$ je vždy pravdivé. Tohle je klíč k úloze „které výroky o $\emptyset$ jsou pravdivé“ ([[03 - Množiny - zápis a pojmy]]).

**Rozdíl mezi $\forall$ a $\exists$ na neprázdné množině:** $\forall \Rightarrow \exists$ (co platí pro všechny, platí pro aspoň jednoho), ale obráceně ne. Na prázdné množině ani první implikace neplatí (levá strana je pravdivá, pravá nepravdivá).

---

## 5. Pořadí kvantifikátorů

> [!danger] $\forall x\,\exists y$ a $\exists y\,\forall x$ jsou různá tvrzení!
> - $\forall n\,\exists m : m>n$ — „ke každému $n$ existuje větší $m$“ — pravda v $\mathbb N$ ($m=n+1$). Volba $m$ **smí záviset** na $n$.
> - $\exists m\,\forall n : m>n$ — „existuje $m$ větší než všechna $n$“ — nepravda v $\mathbb N$. Jedno pevné $m$ musí fungovat pro všechna $n$.

Stejné kvantifikátory (dva $\forall$ nebo dva $\exists$) lze prohodit.

### Jak dokazovat pravdivost / nepravdivost

| Výrok | Pravdivost dokážu… |
| --- | --- |
| $\forall x : V(x)$ | pro **libovolné** (obecné) $x$ ukážu $V(x)$ |
| $\forall x : V(x)$ je nepravdivý | najdu **protipříklad** $x$ s $\neg V(x)$ |
| $\exists x : V(x)$ | **najdu** konkrétní $x$ a ověřím $V(x)$ |
| $\exists x : V(x)$ je nepravdivý | ukážu $\forall x : \neg V(x)$ |

**Příklady (cv. 4, úloha 2), všechno přes $\mathbb Z$:**

| Výrok | Pravda? | Zdůvodnění |
| --- | --- | --- |
| $\forall n\,\exists m : n^2<m$ | ano | $m=n^2+1$ |
| $\exists n\,\forall m : n<m^2$ | ano | $n=-1$, protože $m^2\ge0$ |
| $\forall n\,\exists m : n+m=0$ | ano | $m=-n$ |
| $\exists n\,\forall m : nm=m$ | ano | $n=1$ |
| $\exists n\,\exists m : n^2+m^2=5$ | ano | $n=2,\ m=1$ |
| $\exists n\,\exists m : n+m=4\land n-m=2$ | ano | $n=3,\ m=1$ |
| $\forall n\,\forall m\,\exists p : p=(m+n)/2$ | **ne** | $n=0,\ m=1$ dává $p=\tfrac12\notin\mathbb Z$ |
| $\forall n\,\exists m : n\le m+1$ | ano | $m=n$ |
| $\exists n\,\forall m : n\le m+1$ | **ne** | k libovolnému $n$ vezmi $m=n-2$: $n>n-1$ |
| $\exists n\,\forall m : n^2\le m^2+1$ | ano | $n=0$ |

Všimni si dvojic (h) a (i): stejná nerovnost, jiné pořadí kvantifikátorů, opačná pravdivost.

---

## 6. Přepis vět do formulí (cv. 3 úl. 4, cv. 4 úl. 7)

**Obecný postup (4 kroky):**

1. Najdi **kvantifikační slova**: „každý, všechna, libovolný“ → $\forall$; „existuje, nějaký, aspoň jeden“ → $\exists$; „žádný“ → $\forall\neg$ (nebo $\neg\exists$).
2. Najdi, **přes co** se kvantifikuje (množina $M$, nebo všechna přirozená čísla).
3. Převeď podmínky: „je sudé“ $\to 2\mid x$; „je liché“ $\to 2\nmid x$; „dělitel“ $\to d\mid n$.
4. Dosaď do pravidla z části 3: za $\forall$ dej implikaci, za $\exists$ konjunkci.

**Příklady:**

| Věta | Formule |
| --- | --- |
| Žádné číslo z $M$ není větší než 57. | $\forall x\in M : x\le57$ |
| Existuje číslo, které je aspoň tak velké jako všechna čísla z $X$. | $\exists n\in\mathbb N\ \forall x\in X : n\ge x$ |
| Všechna sudá čísla z $X$ jsou druhou mocninou nějakého čísla z $Y$. | $\forall x\in X : (2\mid x \Rightarrow \exists y\in Y : x=y^2)$ |
| Pro každé $a\in A$ a každé $b\in B$ je $ab=16$. | $\forall a\in A\ \forall b\in B : ab=16$ |
| Pro žádné $c\in C$ a $d\in D$ neplatí $cd=7$. | $\forall c\in C\ \forall d\in D : cd\neq7$ |
| Existuje číslo, jehož každý dělitel je menší než 523. | $\exists n\in\mathbb N\ \forall d\in\mathbb N : (d\mid n\Rightarrow d<523)$ |
| Existuje sudé číslo, které dělí všechna čísla z $A$. | $\exists n\in\mathbb N : (2\mid n\land\forall a\in A : n\mid a)$ |
| Pokud má $x$ dělitele z $A$, má i dělitele z $B$. | $(\exists a\in A : a\mid x)\Rightarrow(\exists b\in B : b\mid x)$ |
| Každé liché číslo větší než všechna čísla z $K$ je v $L$. | $\forall x\in\mathbb N : \big((2\nmid x\land\forall k\in K : x>k)\Rightarrow x\in L\big)$ |

> [!example] Větší věta: „$M$ obsahuje všechny dělitele čísla 15, pak $M$ obsahuje i všechny dělitele čísla 27“
> $$\big(\forall d\in\mathbb N : (d\mid15\Rightarrow d\in M)\big)\Rightarrow\big(\forall d'\in\mathbb N : (d'\mid27\Rightarrow d'\in M)\big)$$
> Tady je „obsahuje všechny X“ typu $X\subseteq M$ – opět $\forall$ s implikací.

**Vazba „právě tehdy, když“** se píše jako $\Leftrightarrow$ mezi dvěma celými výroky (cv. 3, úl. 4l; cv. 4, úl. 7f).

---

## 7. Pravidla pro „vytýkání“ výroku bez proměnné (cv. 4)

Pokud $A$ **nezávisí** na $x$ a $M\ne\emptyset$:

$$
\begin{aligned}
A\land(\forall x\in M : B(x)) &\equiv \forall x\in M : (A\land B(x))\\
A\land(\exists x\in M : B(x)) &\equiv \exists x\in M : (A\land B(x))\\
A\lor(\forall x\in M : B(x)) &\equiv \forall x\in M : (A\lor B(x))\\
A\lor(\exists x\in M : B(x)) &\equiv \exists x\in M : (A\lor B(x))
\end{aligned}
$$

Podmínka $M\neq\emptyset$ je u některých řádků podstatná (u prázdné množiny se kvantifikátory chovají podle části 4).

---

## 8. $\forall$ a $\exists$ vs. $\land$ a $\lor$ (cv. 4, úloha 5)

Tyto dvojice **nejsou ekvivalentní**:

$$
\forall x\,(A(x)\lor B(x)) \quad\text{vs.}\quad \big(\forall x\,A(x)\big)\lor\big(\forall x\,B(x)\big),
$$
$$
\exists x\,(A(x)\land B(x)) \quad\text{vs.}\quad \big(\exists x\,A(x)\big)\land\big(\exists x\,B(x)\big).
$$

**Protipříklad:** doména $\mathbb N$, $A(x)$: „$x$ je sudé“, $B(x)$: „$x$ je liché“.

- $\forall x\,(A\lor B)$ je pravdivé (každé číslo je sudé nebo liché), ale „všechna jsou sudá, nebo všechna jsou lichá“ je nepravdivé.
- $\exists x\,(A\land B)$ je nepravdivé (žádné číslo není sudé i liché), ale $(\exists x\,A)\land(\exists x\,B)$ je pravdivé.

Zachované implikace jsou jen jedním směrem: $\exists x\,(A\land B)\Rightarrow(\exists x\,A\land\exists x\,B)$ a $(\forall x\,A\lor\forall x\,B)\Rightarrow\forall x\,(A\lor B)$.

---

## 9. Další úlohy z cvičení 4

### Hustota: $\forall x\in M\ \forall y\in M\ \big(x<y\Rightarrow\exists z\in M : x<z<y\big)$

| $M$ | Pravda? | Důvod |
| --- | --- | --- |
| $\mathbb R$ | ano | $z=\frac{x+y}2$ |
| $\mathbb Z$ | **ne** | $x=1,y=2$: celé číslo mezi nimi není |
| $\mathbb Q$ | ano | průměr dvou racionálních čísel je racionální |
| $\{2\}$ | ano | předpoklad $x<y$ nikdy není splněn → implikace pravdivá |

### Množina s maximem a bez minima (cv. 4, úl. 3)

Hledáme $B\subseteq\mathbb Z$ s $\ (\exists b\in B\ \forall x\in B : x\le b)$ a $(\forall x\in B\ \exists b\in B : b<x)$, tj. **má největší prvek, ale nemá nejmenší**. Příklad: záporná celá čísla $B=\{-1,-2,-3,\dots\}=\{x\in\mathbb Z\mid x<0\}$.

> [!note] Poznámka k oficiálnímu řešení
> V řešení je zapsáno $B=\{x\in\mathbb Z\mid x\le1\}=\{-1,-2,-3,\dots\}$. Ty dvě množiny se **nerovnají** (první obsahuje i $0$ a $1$). Pro množinu $\{x\mid x\le1\}$ obě podmínky také platí, ale pro výčet $\{-1,-2,\dots\}$ má být $x\le-1$ (nebo $x<0$). Na to pozor při opisování.

### Horní mez a supremum (cv. 4, úl. 6)

- $c$ je horní mez množiny $A\subseteq\mathbb R$: $\ \forall a\in A : a\le c$.
- $A$ má horní mez: $\ \exists c\in\mathbb R\ \forall a\in A : a\le c$.
- $s$ je supremum $A$: $\ (\forall a\in A : a\le s)\land\big(\forall d\in\mathbb R : (\forall a\in A : a\le d)\Rightarrow s\le d\big)$ — $s$ je **nejmenší** horní mez.
- Příklady: $\sup(1,3)=3$ (do množiny nepatří), $\sup[7,8]=8$ (patří, je to i maximum).

---

## Shrnutí

- $\neg\forall\equiv\exists\neg$, $\ \neg\exists\equiv\forall\neg$.
- $\forall$ + podmínka → implikace; $\exists$ + podmínka → konjunkce.
- Prázdná množina: $\forall$ pravdivé, $\exists$ nepravdivé.
- Pořadí $\forall\exists$ vs. $\exists\forall$ **záleží**.
- $\forall x\,(A\lor B)\not\equiv\forall x A\lor\forall x B$ a $\exists x\,(A\land B)\not\equiv\exists xA\land\exists xB$.

⬅️ [[01 - Výroková logika]] · ➡️ [[03 - Množiny - zápis a pojmy]] · [[00 - Přehled]]
