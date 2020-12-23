# Custom Vision Service - część teoretyczna
---
#### 1.Wstęp
- Przedstawienie serwisu:
Jest to jedna z usług Azure Cognitive Services która pozwala na zaawansowane przetwarzanie, rozpoznawanie i klasyfikację obrazów bez posiadania wiedzy z zakresu uczenia maszynowego.
- Opis działania serwisu:
Serwis posiada kilka przetrenowanych wcześniej modeli które pozwalają na przyśpieszenie procesu uczenia. Są to: Food, Landmarks i Reatail - do innych zadań należy skożystać z ogólnego modelu General. Ponieważ model jest już częściowo wyuczony wystarcza podać zaledwie kilka obrazów do pojedyńczego taga by był on w stanie rozpoznawać podobne obrazy.
#### 2.Przypadki użycia
- System do rozróżniania marek samochodów
- System do rozpoznawania krajobrazów
-System do rozpoznawania zawodów ludzi po ich ubiorach służbowych
#### 3.Jak używać
Wymagane jest stworzenie pojedyńczego zasobu na Azure (Custom Vision Service). Po stworzeniu i wyuczeniu modelu istnieje możliwość udostępnienia go jako API.
- Pricing:
Wersja darmowa: 2 Transactions Per Second, 1h trenowania na miesiąc, max obrazów uczących: 5000
Wersja standart: 10 TPS, €1,687 za 1000 transakcji i €0,591 za każde 1 000 uczących