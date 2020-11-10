# Azure Cognitive Language Services
---
### Azure Content Moderator
#### 1.Wstęp
- Przedstawienie serwisu:
Microsoft Azure Content Moderator to serwis zapewniający moderację treści takich jak obrazy, tekst i video, pod kątem treści obraźliwych lub nie odpowiednich dla dzieci.
- Opis działania serwisu:
Pozwala on na podstawie określonych zasad i progów na automatyczne zatwierdzanie lub odżucanie treści albo przekazywanie ich do oceny człowiekowi. Badane treści mogą pochodzić przykładowo od chatbotów, rozmów na forach lub dokumentów. Dane są wysyłane do Content Moderatora przy pomocy API które w odpowiedzi zwraca listę potencjalnie niechcianych wyrazów oraz ich kategorię w formacie JSON.
#### 2.Przypadki użycia
- Nadzorowanie kultury rozmowy w komunikatorach - możliwe jest wychwytywanie obraźliwych wyrazów z tekstu w czasie rzeczywistym.
- Moderowanie wycieku danych osobowych w rozmowach - Content moderator ma funkcjonalność zwracjącą potencjale informacje pozwalające na identyfikacje osoby (tj. adres)
#### 3.Jak używać
Wymagane jest stworzenie pojedyńczego zasobu na Azure (Content Moderator). Zasobowi temu jest przypisywany subscription key przy użyciu którego można wysyłać zapytania do stworzoneggo serwisu.
- Pricing:
Wersja darmowa: 1 Transaction Per Second
Wersja standart: 10 TPS, cena zależy od ilości wykonywanych transakcji i wacha się od $1 do $0.40 za 1000 transakcji.
---
### Language Understanding Intelligent Service
#### 1.Wstęp
- Przedstawienie serwisu:
Jest to usługa wykorzystująca machne learning która pozwala na takie przetwarzanie tekstu by wydobyć z niego kluczowe informacje i zaklasyfikować je w odpowiedni sposób.
- Opis działania serwisu:
LUIS dokonuje podziału podanego tekstu na słowa znaczące na podstawie których generowana jest najbardziej prawdopodobna intencja urzytkownka. Mając wyodrębniony cel (np. zakup biletu) i parametry jakie go opisują (cena, czas) możliwa jest inteligentna komunikacja z użytkownikiem.
#### 2.Przypadki użycia
- Bot do rozmów - użytkownik wpisuje komunikat, a LUIS po jego przetworzeniu jest w stanie wyodrębnić intencje urzytkownika co pozwoli na stworzenie odpowiedniej odpowiedzi.
- Bot do realizacji zakupów - na podstawie wyodrębnionej intencji możliwe jest zrealiizowanie zakupu na podstawie jego opisu w języku naturalnym.
#### 3.Jak używać
Należy stwożyć w azure serwis Language Understanding. Następnie należy zdefiniować intencjie i znaczące wyrazy (entities) i douczyć LOUISA do wybranej tematyki. Tak stworzony zasób można wykożystywać dalej w aplikacjach.
- Pricing:
Wersja darmowa: 5 TPS
Wersja standart: 50 TPS, żądania tekstowe €1,265 za 1000 transakcji, żądania wymawiane €4,639 za 1000 transakcji
---
### Text Analytics API
#### 1.Wstęp
- Przedstawienie serwisu:
Najwększą zaletą serwisu jest to że pozwala on na określenienie sentymentu danego tekstu (np. czy dana opinia jest pozytywna czy negatywna). Dodatkowo umożliwia on detekcję języka tekstu i wychwytywanie kluczowych sformułowań.
- Opis działania serwisu:
Mając dostęp do konsoli API Text Analytics możliwe jest wysyłanie zapytań w formacie JSON do serwisu. Zapytanie zawiera tekst który ma zostać zbadany, w odpowiedzi oceniana jest wartość sentymentu, w przedziale od 0 do 1 (1 - pozytywne nastawienie, 0 - negatywne nastawienie, 0.5 brak nastawienia).
#### 2.Przypadki użycia
- system wystawiający punktową ocenę biznesom/usługom na podstawie komentarzy o nich.
- Filtr negatywnych ocen biznesów/usług
#### 3.Jak używać
Należy stworzyć zasób Text Analytics i uzyskać access key pozwalający na kożystanie z API Text Analytics. Następnie należy udać się na stronę https://[location].dev.cognitive.microsoft.com/docs/services/TextAnalytics.V2.0
z której można przy pomocy klucza wysyłać zapytania do API.
- Pricing:
Wersja darmowa: do 5000 transakcji na miesiąc
Wersja standart: 0–500 000 rekordów tekstu — €1,687 za 1 000 rekordów tekstu
Istnieją wyższe wersje tej usługi, najdroższa wersja S4: €4216,492 miesięcznie
Do 10,000,000 transakcji na miesiąc