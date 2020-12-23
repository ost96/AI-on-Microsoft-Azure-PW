# Computer Vision - Sprawozdanie część praktyczne, projekt 'pjeski' - system do rozpoznawania rasy/wieku psów
---
### Link do filmu wyślę w formularzu
---
### Scenariusz / Use case
Prezentowany projekt realizuje 2 funkcjonalności: rozpoznanie rasy psa ze zdjęcia (dostępne rasy to: Beagle, Bulldog, German Shepherd, Golden Retriever i Siberian Huskie). Dodatkowo system jest w stanie rozpoznać czy pies przedstawiony na zdjęciu to szczeniak, czy dorosły pies.


- Use case "Zdefiniowanie rasy psa": Użytkownik wgrywa zdjęcie psa (zakładając że rasa danego psa zawiera się w jednej z dostępnych), a system określa z jak dużą dozą prawdopodobieństwa jest to jedna ze znanych mu ras. Dodatkowo określany jest też wiek psa.

- Use case "Zbadanie wieku psa nieznanej rasy": Użytkownik wgrywa zdjęcie psa nieznanej rasy. System będzie w stanie określić czy to szczeniak, czy dorosły pies.

---
### Wykonane kroki:
1. Stworzenie konta w Custom Vision Service portal
2. Zainstalowanie potrzebnych zasobów
3. Stworzenie odpowiednich tagó
4. Zebranie odpowiednich zdjęć psów
5. Przypisanie tagów do zdjęć
6. Wytrenowanie mdelu
7. Przetestowanie modelu

---
### Architektura
Projekt w całości zrealizowany w MS Custom Vision Service
