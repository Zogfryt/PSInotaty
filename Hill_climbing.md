# Co to jest?

Algorytm iteracyjny z rodziny local search. Jest to algorytm **zachłanny**, mający jako argument wektor zmiennych **x** oraz funkcje heurystyczną **f(x)**. Działa poprzez przeszukiwanie sąsiadów (a w ogólnym przypadku zmianę jednej wartości w wektorze x) oraz sprawdzanie ich wartości w funckji **f**. Jeśli wynik się polepszył przesuwa się do tego punktu.

# Rodzaje

## Simple Hill Climbing (first choice)
Odmiana polegająca na braniu pierwszego poprawiającego stanu.

## Steepest Ascent Hill Climbing (Best choice)

Przechodzi przez wszystkich sąsiadów aktualnego stanu, po czym przechodzi do najlepszego

## Stochastic Hill Climbing (Random Choice)

Wybiera losowego sąsiada, i na podstawie poprawy wyniera czy do nieog przejśc czy nie

## Worst Choice Hill Climbing

Odmiana egzotyczna. Polega na przeszukaniu wszystkich sąsiadów tak jak w <code>First Choice</code>, lecz wybiera stan który najmniej poprawia obecną sytuację.
# Problemy Hill Climbing

## Maksimum lokalne

Polega na zatrzymaniu się algorytmu na maksimum lokalnym, gdyż stanu sąsiadujące nie dają lepszego efektu. Powoduje to nie dotarcie do globalnego maksimum przez algorytm. (Warto zaznaczyć że ten algorytm nie został do tego stworzony)

## Grzbiety i doliny

Pojawia się gdy, w funkcji istnieje wąskie wzniesienie, które nie pokrywa się z kierunkiem przeszukiwania algorytmu. Algortm wtedy zaczyna poruszać się po grzbiecie zygzakiem (ponieważ nie może trafić na szczyt grzbietu, raz jest z prawej, raz jest z lewej). Powoduje to problemy w działąniu algorytmu, wymagające zmniejszenia wykonywanego kroku.

Przykład grzbietu  
![Ridge](.\obrazy\Ridge.png)

## Płaszczyzna

Objawiający się trafieniem algorytmu na płaszczyzne, gdzie wszyscy sąsiedzi są równi lub ledwie co rozróżnialni. Powoduje to nie możliwością znalezienia właściwego kierunku i nie owocne szukanie rozwiązania

