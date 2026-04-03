
# 🏁 AutoMate

### Twój Asystent Motoryzacyjny

Mobilna aplikacja do zarządzania flotą samochodów, harmonogramem przeglądów i historią serwisową — z ciemnym motywem sportowym.

---

## Opis projektu

AutoMate rozwiązuje problem śledzenia przeglądów, serwisów i codziennej obsługi samochodów. Aplikacja daje kierowcy jedno miejsce, w którym widzi co wymaga uwagi dzisiaj, przegląda całą flotę, dodaje nowe pojazdy i sprawdza pełną historię każdego auta.

Projekt obejmuje trzy warstwy:
- **React App** — działająca aplikacja mobilna z nawigacją, formularzami i zarządzaniem stanem
- **Design System** — spójny zestaw tokenów (kolory, typografia, spacing) i 12 reużywalnych komponentów UI

Interfejs jest zaprojektowany w estetyce sportowej: ciemne tło z teksturą carbon fiber, czerwone gradienty z efektem neonowej poświaty i ostre typograficzne kontrasty.

---

## Funkcjonalności

### Dashboard
Główny ekran po otwarciu aplikacji. Pokazuje pasek postępu zadań na dany dzień (ile z zaplanowanych obsług zostało wykonanych) oraz listę samochodów wymagających uwagi. Każde auto można oznaczyć jako obsłużone jednym tapnięciem — progress bar aktualizuje się natychmiast.

### Garaż
Pełna lista wszystkich samochodów użytkownika wyświetlana w siatce 2×2. Każda karta zawiera ikonę, nazwę, przebieg i badge z liczbą dni do następnego przeglądu. Auta z terminem ≤ 2 dni dostają wyróżnienie w postaci czerwonego badge'a z ikoną ostrzeżenia. Na górze ekranu znajduje się wyszukiwarka filtrująca po nazwie i modelu w czasie rzeczywistym.

### Dodawanie samochodu
Formularz z trzema polami: nazwa własna (np. "Mój BMW"), marka i model (np. "BMW M3 G80") oraz częstotliwość przeglądów w dniach. Przycisk "Zapisz" jest nieaktywny do momentu wypełnienia wymaganych pól. Po zapisaniu użytkownik jest przekierowywany do Garażu, gdzie nowe auto pojawia się natychmiast.

### Szczegóły samochodu
Widok po kliknięciu w kartę auta. Zawiera duży placeholder na zdjęcie, dwie karty statystyk (następny przegląd z podświetleniem jeśli bliski termin, data ostatniej obsługi) oraz chronologiczną listę historii serwisowej z ikonami opisującymi typ czynności. Przycisk "Obsłuż teraz" dodaje nowy wpis do historii i aktualizuje datę ostatniej obsługi.

### Profil i ustawienia
Karta użytkownika z awatarem (inicjały w gradiencie), nazwa i badge planu Premium. Dwa bloki statystyk: liczba posiadanych aut i wykonanych zadań. Poniżej lista ustawień: Powiadomienia PUSH, Ciemny motyw, Edytuj profil, Wyloguj się (wyróżnione kolorem ostrzegawczym).

---

## Ekrany

Aplikacja składa się z 5 ekranów mobilnych w rozmiarze 390×844px (iPhone 14):

| # | Ekran | Opis |
|---|-------|------|
| 01 | Dashboard | Progress bar zadań, lista aut do obsługi z przyciskami akcji |
| 02 | Garaż | Wyszukiwarka + siatka 2×2 z badge'ami pilności |
| 03 | Dodaj samochód | Placeholder zdjęcia, 3 pola formularza, przycisk z walidacją |
| 04 | Szczegóły | Zdjęcie, statystyki, historia serwisowa, przycisk obsługi |
| 05 | Profil | Avatar, statystyki użytkownika, lista ustawień |

<img width="1240" height="667" alt="image" src="https://github.com/user-attachments/assets/8aa9b2b7-24b8-4466-b1ec-3336553f60b1" />


---

## Design System

### Kolorystyka

Motyw "Sporty Carbon" — ciemne tło z teksturą, czerwone gradienty jako akcenty, jasny tekst na kontrastowym tle.

| Token | Hex | Rola |
|-------|-----|------|
| Red Bright | `#FF1744` | Główny akcent — przyciski, gradienty, nawigacja aktywna |
| Red Dark | `#D50000` | Końcówka gradientów, stany hover |
| Background | `#0D0D0F` | Tło ekranów |
| Card | `#161619` | Tło kart, inputów, elementów UI |
| Surface | `#111114` | Nawigacja dolna, placeholdery |
| Text | `#F2F2F5` | Tekst główny |
| Text Secondary | `#8A8A95` | Placeholdery, opisy, daty |
| Border | `#252529` | Obramowania wszystkich elementów |
| Yellow | `#FFD600` | Badge "Konto Premium" |

### Efekty

- **Red Gradient** — `linear-gradient(135deg, #FF1744, #D50000)` na przyciskach CTA, nawigacji aktywnej i awatarze
- **Red Glow** — `box-shadow: 0 6px 24px rgba(255,23,68,0.35)` na przyciskach i elementach wyróżnionych
- **Carbon Fiber** — subtelna tekstura `repeating-linear-gradient` na tle ramek
- **Border Radius** — `16px` dla kart, `12px` dla mniejszych elementów, `44px` dla ramek telefonu

