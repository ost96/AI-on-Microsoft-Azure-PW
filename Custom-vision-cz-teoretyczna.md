# Computer Vision
---
## Computer Vision API
---
#### 1.Wstęp
- Przedstawienie serwisu:
API pozwala na identyfikację osoby na podstawie zdjęcia jej twarzy oraz na analizie cech twarzy tj. kolor włosów, czy pokazywane emocje.
- Opis działania serwisu:
Usługa jest dostępna dzięki licznym serwisom udostępnianym jako jedna usługa poprzez rest api. Serwisy te kożystają z technologii sztucznej inteligencji.
#### 2.Przypadki użycia
- System do poszukiwania zagininych osób
- System zliczający ludzi na zdjęciu
- System do określania czy dana osoba czuje się komfortowo (po emocjach okazywanych na twarzy)
#### 3.Jak używać
Pierwszym krokiem do kożystania z zasobu jest stworzenie subskrypcji do zasobu w portalu Azure. Po stworzeniu subskrypcji użytkownik ma dostęp do subscription keys które są niezbędne do wysyłania zapytań poprzez API.
- Pricing:
Wersja darmowa: 20 Transactions Per Minute, 5000 transakcji/miesiąc
Wersja S1: 10 TPS, 100M+ transactions — $0.893 per 1,000 transactions

---
## Custom Vision Service
---
#### 1.Wstęp
- Przedstawienie serwisu:
Jest to jedna z usług Azure Cognitive Services która pozwala na zaawansowane przetwarzanie, rozpoznawanie i klasyfikację obrazów bez posiadania wiedzy z zakresu uczenia maszynowego.
- Opis działania serwisu:
Serwis posiada kilka przetrenowanych wcześniej modeli które pozwalają na przyśpieszenie procesu uczenia. Są to: Food, Landmarks i Reatail - do innych zadań należy skożystać z ogólnego modelu General. Ponieważ model jest już częściowo wyuczony wystarcza podać zaledwie kilka obrazów do pojedyńczego taga by był on w stanie rozpoznawać podobne obrazy.
#### 2.Przypadki użycia
- System do rozróżniania marek samochodów
- System do rozpoznawania krajobrazów
- System do rozpoznawania zawodów ludzi po ich ubiorach służbowych
#### 3.Jak używać
Wymagane jest stworzenie pojedyńczego zasobu na Azure (Custom Vision Service). Po stworzeniu i wyuczeniu modelu istnieje możliwość udostępnienia go jako API.
- Pricing:
Wersja darmowa: 2 Transactions Per Second, 1h trenowania na miesiąc, max obrazów uczących: 5000
Wersja standart: 10 TPS, €1,687 za 1000 transakcji i €0,591 za każde 1 000 uczących

---
## Video Indexer service
---
#### 1.Wstęp
- Przedstawienie serwisu:
Jest to usługa pozwalająca na opisanie tego co jest przedstawiane w plikach wideo. Pozwala ona min. na rozpoznawanie twarzy, rozpoznawanie tekstu cy przypisywanie etykiet do przedmiotów z filmu.
- Opis działania serwisu:
Po załadowania filmu proces indeksowania rozpoczyna się automatycznie. W efekcie uzyskiwany jest obiekt insights który zawiera wyciągnięte z filmu informacje, takie jak etykiety występujących w filmie obiektów, twarze, emocje ludzi.
#### 2.Przypadki użycia
- System do kamer rozpoznający czy na filmie obecni są ludzie
- System dla newidomych - pozwala na opisywanie filmu poprzez etykiety obiektów
- System szpiegowski wychwytujący tekst pokazywany przez krótki moment na filmach.
#### 3.Jak używać
Wymagane jest stworzenie subskrybcji do zasobu w celu uzyskania subscription key. Jest on potrzebny do założenia konta w Video Indexer Developer portal z którego można kożystać z tej usługi.
- Pricing:
Wersja darmowa: do 10h darmowego użytkowania dla użytkowników kożystających z portalu usługi, do 40h za darmo przy kożystaniu jedynie z API
Wersja standart: koszt uzależniony od ilości pamięci zajmowanej przez film. Przykład ceny:158 GB filmu dziennie - €86,720 miesięcznie.
