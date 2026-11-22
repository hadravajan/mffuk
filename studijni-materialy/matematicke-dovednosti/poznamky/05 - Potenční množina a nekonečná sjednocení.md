---
tags: [matematicke-dovednosti, mnoziny]
cviceni: [5, 6]
---

# 05 – Potenční množina, indexovaná sjednocení a průniky

> [!abstract] Cíl
> Rozumět tomu, že prvky potenční množiny jsou **množiny**, umět počítat velikosti, a převádět sjednocení a průniky přes mnoho množin na kvantifikátory.

Zdroj: **cvičení 5 (úloha 5, 6)** a **cvičení 6 (úlohy 2, 3, 5)**.

---

## 1. Potenční množina

$$\mathcal P(A)=2^A=\{X\mid X\subseteq A\}\quad\text{(množina všech podmnožin }A).$$

> [!important] Klíčová věta
> $$X\in\mathcal P(A)\;\Longleftrightarrow\;X\subseteq A .$$
> Prvky $\mathcal P(A)$ jsou **množiny**, ne prvky $A$. Vždy je $\emptyset\in\mathcal P(A)$ a $A\in\mathcal P(A)$.

**Příklady:**

$$
\begin{aligned}
\mathcal P(\{1,2\})&=\{\emptyset,\{1\},\{2\},\{1,2\}\} &&(4=2^2\text{ prvky})\\
\mathcal P(\{a\})&=\{\emptyset,\{a\}\} &&(2^1=2)\\
\mathcal P(\emptyset)&=\{\emptyset\} &&(2^0=1)\\
\mathcal P(\mathcal P(\emptyset))&=\mathcal P(\{\emptyset\})=\{\emptyset,\{\emptyset\}\} &&(2^1=2)
\end{aligned}
$$

> [!tip] Proč $|\mathcal P(A)|=2^{|A|}$
> Při tvorbě podmnožiny rozhodneš u **každého** prvku $A$ dvě možnosti: „vezmu / nevezmu“. Pro $n$ prvků to dává $2\cdot2\cdots2=2^n$ možností. Pro $n=0$ je jedna možnost (nevzít nic), proto $|\mathcal P(\emptyset)|=1$.

### $k$-prvkové podmnožiny

$\binom{A}{k}$ je množina všech $k$-prvkových podmnožin $A$ a pro $|A|=n$ platí $\left|\binom{A}{k}\right|=\binom{n}{k}$. Například $\binom{\{1,2,3\}}{2}=\{\{1,2\},\{1,3\},\{2,3\}\}$. Součet přes všechna $k$ dá celou potenční množinu:
$$
\mathcal P(A)=\bigcup_{k=0}^{n}\binom{A}{k},\qquad \sum_{k=0}^{n}\binom nk=2^n.
$$

> [!warning] Pozor na rozdíl $\in$ vs. $\subseteq$ u $\mathcal P$
> Pro $A=\{1,2\}$: $\{1\}\in\mathcal P(A)$ ✔, ale $1\notin\mathcal P(A)$ (jednička není podmnožina). Zato $\{\{1\}\}\subseteq\mathcal P(A)$ ✔.

---

## 2. Velikosti (cv. 5, úloha 5)

$$|A\cup B|=|A|+|B|-|A\cap B|,\quad|A\times B|=|A|\cdot|B|,\quad|\mathcal P(A)|=2^{|A|}.$$

Navíc: $|\mathcal P(A\times B)|=2^{|A|\cdot|B|}$.

---

## 3. Indexovaná (nekonečná) sjednocení a průniky

Pro množiny $A_1,A_2,A_3,\dots$:

$$
x\in\bigcup_{i=1}^{\infty}A_i\;\Longleftrightarrow\;\exists i\in\mathbb N : x\in A_i,\qquad
x\in\bigcap_{i=1}^{\infty}A_i\;\Longleftrightarrow\;\forall i\in\mathbb N : x\in A_i .
$$

> [!important] Paměťová pomůcka
> **Sjednocení = existenční kvantifikátor** („je v **nějaké**“), **průnik = univerzální kvantifikátor** („je ve **všech**“). Stejně jako $A\cup B\leftrightarrow\lor$ a $A\cap B\leftrightarrow\land$.

Totéž platí pro konečné indexy, např. $\bigcup_{i=1}^{10}$.

### Postup při výpočtu $\bigcup_{i=1}^{10}M_i$ nebo $\bigcap_{i=1}^{10}M_i$

1. **Vypiš** množiny $M_1,M_2,\dots,M_{10}$ (nebo je seskup do skupin se stejným obsahem).
2. Sjednocení = **sesypej** všechny prvky dohromady (bez opakování); průnik = ponech jen to, co je **v každé** množině.
3. Sleduj závorky: $\{\ \}$ okolo celého sjednocení dělá z výsledku **jeden prvek** nové množiny.

---

## 4. Cvičení 6, úloha 2 – kompletně

Označme $M_i=\{j\in\mathbb N\mid j^2\le i\}$ a $N_i=\{j\in\mathbb N\mid j^2<i\}$.

| $i$ | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| $M_i$ | $\{1\}$ | $\{1\}$ | $\{1\}$ | $\{1,2\}$ | $\{1,2\}$ | $\{1,2\}$ | $\{1,2\}$ | $\{1,2\}$ | $\{1,2,3\}$ | $\{1,2,3\}$ |
| $N_i$ | $\emptyset$ | $\{1\}$ | $\{1\}$ | $\{1\}$ | $\{1,2\}$ | $\{1,2\}$ | $\{1,2\}$ | $\{1,2\}$ | $\{1,2\}$ | $\{1,2,3\}$ |

*(Kontrola: $M_4$ obsahuje $2$, protože $2^2=4\le4$; $N_4$ ne, protože $4<4$ neplatí. $M_9$ obsahuje $3$, protože $9\le9$; $N_9$ ne, ale $N_{10}$ ano.)*

Tedy různé množiny, které se vyskytují: u $M$: $\{1\},\{1,2\},\{1,2,3\}$; u $N$: $\emptyset,\{1\},\{1,2\},\{1,2,3\}$.

| Zadání | Sjednocení | Průnik |
| --- | --- | --- |
| (a) $\bigcup M_i$ resp. $\bigcap M_i$ | $\{1,2,3\}$ | $\{1\}$ |
| (b) $\bigcup N_i$ resp. $\bigcap N_i$ | $\{1,2,3\}$ | $\emptyset$ |
| (c) $\bigcup\{M_i\}$ (množina s **jedním prvkem $M_i$**) | $\{\{1\},\{1,2\},\{1,2,3\}\}$ | $\emptyset$ |
| (d) $\bigcup\{N_i\}$ | $\{\emptyset,\{1\},\{1,2\},\{1,2,3\}\}$ | $\emptyset$ |
| (e) $\big\{\bigcup M_i\big\}$ resp. $\big\{\bigcap M_i\big\}$ | $\{\{1,2,3\}\}$ | $\{\{1\}\}$ |

**Co je „past“:**

- (c) vs. (a): ve (c) jsou **dvojité závorky** $\{\{\dots\}\}$ – každé $\{M_i\}$ je *jednoprvková množina*, jejímž prvkem je celá množina $M_i$. Sjednocením takových množin sbíráme celé množiny $M_i$ (jako samostatné prvky), nesypeme jejich obsah dohromady. Proto je výsledek **množina množin** o 3 prvcích.
- Průnik ve (c): $\{M_1\}\cap\{M_4\}\cap\{M_9\}=\emptyset$, protože jednoprvkové množiny $\{\{1\}\}$, $\{\{1,2\}\}$, $\{\{1,2,3\}\}$ nemají společný prvek.
- (d), $i=1$: $N_1=\emptyset$, tedy $\{N_1\}=\{\emptyset\}$ – množina, která obsahuje prázdnou množinu. Proto přibude prvek $\emptyset$ do sjednocení.
- (e): vnější závorky $\{\ \}$ jsou **mimo** symbol $\bigcup$ nebo $\bigcap$. Nejdřív spočítáš vnitřek (výsledek z (a) nebo (a')) a **pak** ho obalíš.

---

## 5. Cvičení 6, úloha 3 – potence a operace

*Máme libovolné množiny $A,B$. Porovnejte (co do inkluze).*

### (c) $\mathcal P(A\cap B)=\mathcal P(A)\cap\mathcal P(B)$ — **rovnost**

Pro libovolnou množinu $X$:
$$
X\in\mathcal P(A\cap B)\Leftrightarrow X\subseteq A\cap B\Leftrightarrow(X\subseteq A\land X\subseteq B)\Leftrightarrow(X\in\mathcal P(A)\land X\in\mathcal P(B))\Leftrightarrow X\in\mathcal P(A)\cap\mathcal P(B).
$$
Všechny kroky jsou ekvivalence → platí rovnost.

### (b) $\mathcal P(A)\cup\mathcal P(B)\subseteq\mathcal P(A\cup B)$, ale **ne obráceně**

*Důkaz $\subseteq$:* Nechť $X\in\mathcal P(A)\cup\mathcal P(B)$. Pak $X\subseteq A$ nebo $X\subseteq B$. Protože $A\subseteq A\cup B$ a $B\subseteq A\cup B$, v obou případech $X\subseteq A\cup B$, tedy $X\in\mathcal P(A\cup B)$.

*Protipříklad pro $\supseteq$:* $A=\{1\}$, $B=\{2\}$. Pak $\{1,2\}\in\mathcal P(A\cup B)$, ale $\{1,2\}\nsubseteq\{1\}$ a $\{1,2\}\nsubseteq\{2\}$, takže $\{1,2\}\notin\mathcal P(A)\cup\mathcal P(B)$.

> [!tip] Intuice
> Podmnožina sjednocení se může „rozprostřít“ do obou množin zároveň – a taková není podmnožinou ani jedné z nich.

### (a) $\mathcal P(A\setminus B)$ vs. $\mathcal P(A)\setminus\mathcal P(B)$ — **neporovnatelné**

- $\mathcal P(A\setminus B)\nsubseteq\mathcal P(A)\setminus\mathcal P(B)$: levá strana vždy obsahuje $\emptyset$ (prázdná množina je podmnožinou čehokoli), ale $\emptyset\in\mathcal P(B)$, takže $\emptyset\notin\mathcal P(A)\setminus\mathcal P(B)$.
- $\mathcal P(A)\setminus\mathcal P(B)\nsubseteq\mathcal P(A\setminus B)$: pro $A=\{1,2\}$, $B=\{2\}$ je $\mathcal P(A)\setminus\mathcal P(B)=\{\{1\},\{1,2\}\}$, a $\{1,2\}\notin\mathcal P(\{1\})=\{\emptyset,\{1\}\}$.

*(První neinkluze platí pro **všechny** dvojice $A,B$. Druhá platí jen **obecně**: stačí jeden konkrétní protipříklad, jako výše. Pro $A=B$ je totiž $\mathcal P(A)\setminus\mathcal P(B)=\emptyset$, což je podmnožinou čehokoli. Proto říkáme „neporovnatelné v obecném případě“.)*

---

## 6. Cvičení 6, úloha 5

$$
A=\{X\mid X\subseteq\mathbb N\}=\mathcal P(\mathbb N),\qquad
B=\bigcup_{n\in\mathbb N}\{X\mid X\subseteq\{1,\dots,n\}\},\qquad
C=\bigcup_{k=0}^{\infty}\binom{\mathbb N}{k}.
$$

**Výsledek:** $B=C\subsetneq A$.

**Význam množin:**

- $A$ = **všechny** podmnožiny $\mathbb N$ (i nekonečné, např. množina sudých čísel).
- $B$ = podmnožiny nějakého počátečního úseku $\{1,\dots,n\}$ = **konečné** podmnožiny.
- $C$ = sjednocení všech množin „$k$-prvkových podmnožin“ ($k=0,1,2,\dots$) = opět **konečné** podmnožiny.

**Důkaz $B=C$** (obě jsou množina všech konečných podmnožin $\mathbb N$):

- $X\in B\Rightarrow$ pro nějaké $n$ je $X\subseteq\{1,\dots,n\}$, takže $X$ je konečná, má nějaký počet $k\le n$ prvků, a tedy $X\in\binom{\mathbb N}{k}\subseteq C$.
- $X\in C\Rightarrow X$ je $k$-prvková pro nějaké $k$, tedy konečná. Je-li $X=\emptyset$, je $X\subseteq\{1\}$. Jinak vezmi $n=\max X$ a máš $X\subseteq\{1,\dots,n\}$. Tedy $X\in B$.

**Proč $B\subsetneq A$ (ostře):** $B\subseteq A$ je jasné. A $A$ obsahuje navíc třeba množinu všech sudých čísel $S$ (nebo celé $\mathbb N$), která je nekonečná, a proto leží v $A$, ale ne v $B$ ($S$ není podmnožinou žádného $\{1,\dots,n\}$).

---

## 7. Co si odnést

- $X\in\mathcal P(A)\Leftrightarrow X\subseteq A$; $\emptyset$ a $A$ jsou vždy v $\mathcal P(A)$; $|\mathcal P(A)|=2^{|A|}$.
- $\mathcal P(\emptyset)=\{\emptyset\}$ (1 prvek, ne 0!).
- $\bigcup\leftrightarrow\exists$ (někde), $\bigcap\leftrightarrow\forall$ (všude).
- Dvojité závorky $\{\{\dots\}\}$ → zkoumej množinu **množin**; vnější $\{\ \}$ okolo $\bigcup$ se aplikují až **po** výpočtu.
- $\mathcal P(A\cap B)=\mathcal P(A)\cap\mathcal P(B)$ rovnost; $\mathcal P(A)\cup\mathcal P(B)\subseteq\mathcal P(A\cup B)$ jen jedním směrem.

⬅️ [[04 - Podmnožiny a množinové operace]] · ➡️ [[06 - Pasti a tahák na test]] · [[00 - Přehled]]
