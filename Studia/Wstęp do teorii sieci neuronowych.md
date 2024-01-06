# Wykład 1 - 02.02
SNE = Wyk + ĆW (Lab)

Program jako zaliczenie
Obecności na laboratoriach
Wykład obecność nieobowiązkowa ale plusy za obecność 

## Historia DL (Deep Learning)

McCulloch-Pitts (1943)

Rosenblatt (1962) - 1 Boom
Perceptron jeden neuron
![[Pasted image 20230302083205.png]]
Minsky i Papert (1969) Książka "Perceptron"
Dla XORa nie ma sposobu uczenia - the XOR Affair

Fukushima (1970)
Neocognitron 

Hinton i inni (1986) - 2 Boom
Backwards propagation of errors - propagacja wsteczna błędu
skomplikowana sieć neuronowa - duża ilość obliczeń w propagacji wstecznej błędu

Hinton i inni (2010) - 3 Boom
Deep Learning
CNN

## Komputer Kwantowy

Historia QC - Quantum Computing

Yuri Manin (1980)
Feynman (1981)
D-Wave Systems (1999) 
Google - Quantum AI Lab (2013)
IBM (2023) - 400 qubitów 2025
Nagrody nobla - Aspect, Zeilinner, Clauser

## Model neuronów M.-P. (1943)

![[Pasted image 20230302083205.png]]

x$_n$ = {0, 1} $\subset$ R$^m$
y $\in$ {0, 1} $\subset$ R
w$_i$ $\in$ R - waga

Funkcja progowa
f(x) = {0 gdy x < 0, 1 gdy x >= 0}

## Model neuronu M.-P.

y = f((suma i=1 do m wi ui) - theta)

Przykład (OR)
![[or-gate 1.png]]
A = u$_1$, B = u$_2$

f(w$_1$*u$_1$ + w$_2$*u$_2$ - $\theta$)

1. 
(u$_1$, u$_2$) = (0, 0) |---> y = 0
0 = f(-$\theta$) <=> -$\theta$ < 0

2. (u$_1$, u$_2$) = (1, 0) |---> y = 1
0 = f(w$_1$ - $\theta$) <=> w$_2$ - $\theta$ $\geq$ 0

3. (u$_1$, u$_2$) = (0, 1) |---> y = 1
0 = f(w$_2$ - $\theta$) <=> w$_2$ - $\theta$ $\geq$ 0

4. (u$_1$, u$_2$) = (1, 1) |---> y = 1
0 = f(w$_1$ + w2 -$\theta$) <=> w$_1$ + w$_2$ - $\theta$ $\geq$ 0

przykładowy zestaw rozwiązań
$\theta$ = 1, w$_1$ = 2, w$_2$ = 2

Przykład (XOR)

1. 
(u$_1$, u$_2$) = (0, 0) |---> y = 0
0 = f(-$\theta$) <=> -$\theta$ < 0

2. (u$_1$, u$_2$) = (1, 0) |---> y = 1
0 = f(w$_1$ - $\theta$) <=> w$_2$ - $\theta$ $\geq$ 0

3. (u$_1$, u$_2$) = (0, 1) |---> y = 1
0 = f(w$_2$ - $\theta$) <=> w$_2$ - $\theta$ $\geq$ 0

4. (u$_1$, u$_2$) = (1, 1) |---> y = 1
0 = f(w$_1$ + w2 -$\theta$) <=> w$_1$ + w$_2$ - $\theta$ $\lt$ 0

(2) + (3) = w$_1$ + w$_2$ - 2$\theta$ $\geq$ 0
(1) + (4) = w$_1$ + 2$_2$ - 2$\theta$ < 0
Sprzeczność!
dlatego nie można wyuczyć XORa

y = f(suma i = 1 do m wi * ui - theta)

n = m + 1, w$_n$ := -$\theta$, u$_n$ := 1
=>
y = (suma i=1 do n wi * ui)

iloczyn skalarny
w = [w1, w2, w3 ... wn], u = [u1, u2, u3 ... un]
y = f(w $\bullet$ u)