# Azure Bot Service
---
### QnA Maker and Azure Bot Service
#### 1.Wstęp
- Przedstawienie serwisu:
QnA Maker to serwis pozwalający na stworzenie i publikowanie bazy wiedzy posiadającej zdolności przetwarzania języka naturalnego.
Azure Bot Service to framework do tworzena i zarządzania botami na Azure.
- Opis działania serwisu:

QnA Maker: 
Zadaniem serwisu jest stwozenie bazy wiedzy. Jest to możliwe do zrobienia poprzez: wygenerowanie jej na podstawie istniejącego dokumentu/strony FAQ, stworzenie jej na podstawie zapisu rozmów, lub ręczne edytowanie pytań i odpowiedzi. Często te techniki są ze sobą łączone. W kolejnym kroku poprzez proces uczenia maszynowego wiedza jest generalizowana.

Azure Bot Service:
Udostępnia on stworzoną bazę wiedzy jako bota, bez konieczności pisania kodu dla bota.
#### 2.Przypadki użycia
Oba serwisy wspomagają się w celu stworzenia botów. Zastosowania botów:
- Bot wspierający klientów (taki jak np. w sieci Orange)
- Bot realizujący zakupy na podstawie opisu produktów w języku naturalnym podczas konwersacji.
#### 3.Jak używać
Oba zasoby wymagają stworzenia zasobu Machine Learnng, który pozwala na kożystanie z Azure Machine Learning studio.
- Pricing:

QnA Maker: 
Wersja bezpłatna - 3 TPS (transakcje na sekunde), bezpłatne dokumenty zarządzane na miesiąc: 3
Wersja standardowa - 3 TPS (transakcje na sekunde), €8,433 dla nieograniczonej liczby zarządzanych dokumentów

Azure Bot Service:
Wersja bezpłatna - 10 000 komunik./miesiąc
Wersja premium -  Nieograniczona liczba komunikatów, €0,422 za 1000 komunikatów

---
### Bot Framework Composer
#### 1.Wstęp
- Przedstawienie serwisu:
Jest to graficzny  edytor pozwalający na tworzenie zaawansowanych botów do rozmów bez konieczności pisania kodu. Serwis ten jest open-source.
- Opis działania serwisu:
Serwis jest graficznym designerem botów do rozmów który kożysta z innych serwisów, tj. jak LOUIS. W trakcie rozmowy zapamiętuje dane o konwersacji oraz interpretuje ją w celu zrozumienia intencji użytkownika. Na podstawie zebranych danych pozwala na stworzenie zadowalających odpowiedzi w trakcie rozmowy.
#### 2.Przypadki użycia
Serwis ten służy do tworzenia botów do rozmów. Boty tego typu mogą być wykożystywane w celach rozrywkowych, bądź jako boty zapewniające porady.
#### 3.Jak używać
Do kożystania z Bot Framework Composer wymagane jest posiadanie .NET Core SDK 3.1 oraz Bot Framework Emulator. Po zainstalowaniu tych wymagań nalleży zainstalować samego Bot Framework Composer. 

Twożenie bota:
W aplikacji należy wybrać opcję "Create from scratch". Następnie należy skonfigurować bota, zaczynając od podania warunków rozpoczęcia konwersacji (np. prośba o podanie wieku lub prośba o podanie imienia). Następnie kożystając z graficznego interfejsu można zdefiniować podstawowe odpowiedzi, tj. odpowiedź na powitanie. W ten sposób tworzona jest podstawowa część bota. W dalszej kolejności należy stworzyć dialogi - funkcjonalność która w trakcje rozmowy zapisuje informacje i wykożystując LUISa rozpoznaje intencje użytkownika i na podstawie zebranych danych tworzy odpowiedź wyświetlaną w trakcie konwersacji. Kolejnymi istotnymi funkcjami które należy zaimplementować są karty (pozwalające na udzielenie odpowiedzi w formie graficznej), oraz nadmiarowość komunikatów takich jak powitanie (by np. bot witał użytkownika za każdym razem troche inaczej). Wszytkie opisane akcje są możliwe do wykonania przy pomocy graficznego interfejsu (łączenie bloków), co pozwala na szybkie stworzenie bota.

- Pricing:
Niie znalazłem wersji bezpłatnej
Cena: $60/miesiąc (10,000 wiadomości)