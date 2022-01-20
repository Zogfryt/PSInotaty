# Co to?

Simulated annealing jest to algorytm probabilistyczny, służacy do szukania globalnego optima funckji.

# Parametry

## Temperatura

Jest to wartość która określa zasoby algorytmu. Algorytm startuje od pewnego <code>Tmax</code>
która z każdym przejściem algorytmu jest pomniejszana, aż nie dojdzie do <code>Tmin</code> które zazwyczaj jest równe 0.

## Funkcja Prawdopodobieństwa

Funkcja określająca szanse danego stanu sprawdzanego na bycie aktualnym stanem. Innymi słowy majać aktaulny stan s oraz jego sąsiada s' określa jaką szanse ma algorytm do przejścia ze stanu s do stanu s'. Funkcja przyjmuje zazwyczaj trzy parametry: f(s), f(s') oraz temperature. Im wyższa temperatura tym większe szanse algorytmu do przejścia do stanu gorszego.

## Warunek restartu

Nie jest to oficjalna część algorytmu jednak, pomaga z wychodzenia z lokalnego optimum. Gdy warunek jest spełniony, algorytm przechodzi do całkowicie losowego stanu i od niego wznawia działanie.

# Działanie algorytmu

Algorytm zaczyna od pewnego stanu. Na początku mając wysoką temperaturę algorytm działa na zasadzie przeszukiwania funckji gdyż nie idzie jedynie w kierunku polepszającego się stanu. Im bardziej nasz algorytm się chłodzi tym bardziej zaczyna chodzić po stanach które polepszają wynik.

Pseudokod:
```
    e0 = random_stan
    for Tmax to Tmin
        E0 = f(e0)
        e1 = Next(e1)
        E1 = f(e1)
        ΔE = E1 - E0
        if(P(E0,E1,T) > random(0,1))
            e0 = e1

(e0-obecny stan, E0-energia ob.s.m e1-nowy stan, E1 - energia n.s.)
```

Niektóre implementacje kodu posiadają jeszcze warunek że jeśli E1>E0 to P(E1,E0,T) = 1. Nie jest to zawsze najlepsze rozwiązanie gdyż może spowodować utknięcie w optimum lokalnym.