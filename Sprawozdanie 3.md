# Azure Cognitive Speech Services
---
### Transcribe speech input to text
#### 1.Wstęp
- Przedstawienie serwisu:
Serwis ten pozwala na przetwarzanie w czasie rzeczywistym mowy na tekst, an następnie udostępnia go innym zasobom, np. przy użyciu REST API.
- Opis działania serwisu:
Działanie serwisu bazuje na użyciu uczzenia maszynowego i sztucznej inteligencji. Domyślnie do przetwarzania mowy na teks używany jest "Universal language model" - model wytrenowany przez Microsoft na ich własnych danych. Model ten jest przeznaczony do ogólnych typów konwersacji, jednak możliwe jest wyszkolenie nowego modelu do specyficznych typów konwersacji (np. zawierających dużo technicznych czy naukowych sformułowań).
#### 2.Przypadki użycia
- Tworzenie napisów do filmów
- Tworzenie botów rozpoznawających mowę
- Tworzenie systemów przetwarzających mowę na tekst dla osób głuchych.
#### 3.Jak używać
Należy stworzyć zasób Speech w portlu Azure. Mając działający zasób możliwe jest kożystanie z niego przy pomocy jego API. Aby wykożystać ten serwis w aplikacji należy się odwołać do odpowiednich endpointów podając przy tym subscription key wygenerowany przez serwis.
- Pricing:
wersja bezpłatna: max równoczesnych żądań: 1, Bezpłatne godziny audio na miesiąc: 5
wersja standart: max równoczesnych żądań: 20, €0,844 za godzinę audio
---
### Synthesize Text Input to Speech
#### 1.Wstęp
- Przedstawienie serwisu:
Serwis pozwala na syntetyzację mowy z tekstu. Serwis ten skupia się nie tylko na dokładności przekazu ale też jakości syntetyzowanego głosu, np. poprzez użycie modelowanych ścieżek głosowych. Serwis ten posiada 75 różnych typów głosów dla 45 różnych języków.
- Opis działania serwisu:
Tekst jest używany jako input w tym serwisie, po przetworzeniu jest przekazywany do syntetyzatora który zamienia go na na mowę.
#### 2.Przypadki użycia
- tworzenie botów z którymi możliwe jest poruzumienie się przy użyciu mowy.
- tworzenie aplikacji poruzumiwających się z człowiekiem w środowiskach i sytuacjach w których wyświetlanie tekstu jest nieodpowiednie - np. dla kierowców w trakcie jazdy.
- przetwarzanie e-booków na mowę - umożliwienie czytania książek dla niewidomych.
#### 3.Jak używać
Należy stworzyć zasób Speech w portlu Azure. Udostępni on endpointy i klucze dzięki którym możliwe stanie sę komunikowania z serwisem z poziomu aplikacji. Aby wybrać rodzaj głosu jaki będzie tworzony należy zmodyfikować obiekt "SpeechConfig".
W przypadku nagrania audio dłuższego niż 10 minut należy skożystać z Long Audio API - asynchronicznej wersji serwisu specjalizującej się w długich nagraniach.
- Pricing:
wersja bezpłatna: max równoczesnych żądań: 1, Bezpłatne znaki na miesiąc: 5 million
wersja standart: max równoczesnych żądań: 20, €3,374 za 1 mln znaków
---
### Translate speech with the speech service
#### 1.Wstęp
- Przedstawienie serwisu:
Serwis zapewnia natychmiastowe tłumaczenie mowy na inny język. Serwis jest w stanie automatycznie rozpoznać język jaki ma przetłumaczyć. Następnie po dokonaniu tłumaczenia syntetyzuje odpowiedź jako mowę.
- Opis działania serwisu:
Rozpoznawanie języka działa dzięki uczeniu maszynowemu na zbiorze danych liczęcym tysiące godzin rozmów. Moduł tłumaczący również opiera się o technologię uczenia maszynowego. Podczas tłumaczena rozmowy dzięki funkcjonalności detekcji ciszy możliwe jest precyzyjne określenie kiedy użytkownik skończył mówić. W następnej kolejności wypowiedziane zdanie jest zamieniane na tekst i przesyłane przy pomocy API do serwisu. W nim tekst jest poddawany normalizacji, a następnie tłumaczony przy użyciu uczenia maszynowego. Następnie przetłumaczony tekst jest zwracany do aplikacji i syntetyzowany na mowę.
#### 2.Przypadki użycia
- Tłumacz do zwykłych rozmów
- Tłumacz mediów, tj. filmy
- Tłumacz wsparcia dla klientów
#### 3.Jak używać
Należy stworzyć zasób Speech w portlu Azure. Tak jak w przypadku wcześniejszych serwisów, do użycia tego serwisu w aplikacji należy odwołać się do udostępnionych przez niego endpointów przy użyciu subscription key.
- Pricing:
wersja bezpłatna: max równoczesnych żądań: 1, Bezpłatne godziny audio na miesiąc: 5
wersja standart: max równoczesnych żądań: 20, €2,11 za godzinę audio