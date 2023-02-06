Определение 6.1. Машина Тьюринга (Tm) является формальной системой:
T = (Q, Σ, Γ, δ, q0, F), где Q — конечное множество состояний; Γ — конечное
множество допустимых символов ленты, один из них, обычно обозначаемый
буквой B, есть пробел; Σ⊆Γ \ {B} — множество входных символов;
δ : Q ×Γ→ Q × (Γ \ {B}) × {L, R} — функция следующего такта (движения),
для некоторых аргументов может быть не определена8
; q0∈Q — начальное состояние; F ⊆ Q — множество конечных состояний. 

<h4>
Постройте машину Тьюринга, которая на вход получает натуральное число N и добавляет 
к нему 1 в двоичной записи. Входом является число N в двоичном виде (например, 100111 -> 101000). 
Используйте эмулятор
</h4>

```
; Machine starts in state 0.

; State 0: read the leftmost symbol
0 * * r 0
0 _ _ l s1

; State s1 add one to last digi
s1 _ _ * halt-accept ; read all digits
s1 0 1 * halt-accept ; operation complete
s1 1 0 l s2

;State s2 translating the digit of a number
s2 0 1 * halt-accept ; operation complete
s2 1 0 l s2
s2 _ 1 * halt-accept ; operation complete
```

[Ссылка на решение](https://morphett.info/turing/turing.html?3538911ad51f2852d03a9d0c5754aec8)