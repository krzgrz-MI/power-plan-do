# System Zarządzania Zadaniami w Microsoft 365

## Krok 1: Konfiguracja Microsoft Planner

1. 
Utwórz Plan:

  - Otwórz Microsoft Planner i utwórz nowy plan.
  - Nazwij plan, np. "Codzienny Harmonogram Zadań".
  - Utwórz segmenty (buckets) dla każdego przedziału czasowego, np. "8:00-11:00 Połączenia z Klientami", "11:00-13:00 Zarządzanie Zamówieniami", itp.

2. 
Dodaj Zadania:

  - W każdym segmencie dodaj odpowiednie zadania.
  - Przypisz zadania odpowiednim członkom zespołu.
  - Ustaw daty końcowe (terminy) dla każdego zadania, aby były zgodne z dziennym harmonogramem.

## Krok 2: Konfiguracja Microsoft To Do

1. 
Utwórz Udostępnioną Listę:

  - Otwórz Microsoft To Do i utwórz nową listę o nazwie "Codzienne Zadania".
  - Dodaj zadania podobne do tych, które utworzyłeś w Planner z konkretnymi przedziałami czasowymi.
  - Udostępnij tę listę wszystkim członkom zespołu, aby mogli oznaczać zadania jako ukończone.

2. 
Przypisz i Zaplanuj Zadania w To Do:

  - Dla każdego zadania ustaw powiadomienia na konkretne godziny.
  - Choć nie możesz przypisać zadań do wielu osób bezpośrednio w To Do, opisz odpowiedzialności w opisie zadania lub użyj podzadań.

## Krok 3: Automatyzacja za pomocą Power Automate

### Automatyzacja Tworzenia Zadań

1. 
Zaloguj się do Power Automate:

  - Otwórz Power Automate ze swojego konta Microsoft 365.

2. 
Utwórz Nowy Przepływ (Flow):

  - Rozpocznij nowy zautomatyzowany przepływ.

3. 
Wyzwalacz (Trigger):

  - Użyj wyzwalacza cyklicznego (recurrence), aby ustawić przepływ na codzienne uruchamianie o określonej godzinie.

4. 
Akcje w Planner:

  1. 
Dodaj Zadania do Planner:

    - Dodaj akcję "Utwórz zadanie" (Create task) w Microsoft Planner.
    - Określ ID planu i ID bucket. Ustaw tytuł zadania i przypisz zadania dynamicznie, jeśli to możliwe.

5. 
Akcje w To Do:

  1. 
Utwórz Zadania w To Do:

    - Dodaj akcję "Utwórz zadanie" (Create task) w Microsoft To Do dla każdego członka zespołu.

### Śledzenie Ukończenia Zadań

1. 
Wyzwalacz:

  - Ustaw inny przepływ z wyzwalaczem cyklicznym, aby sprawdzać status zadań.

2. 
Wymień Zadania w Planner:

  - Dodaj akcję "Wymień zadania" (List tasks) z określonego planu.

3. 
Sprawdź Status Zadań:

  - Użyj warunków (conditions), aby sprawdzić, czy zadania są ukończone.
  - Powiadomienie lub aktualizacja dokumentu/arkusza, jeśli zadania są nieukończone lub ukończone.

## Praktyczny Przykład w Power Automate

### Utwórz Codzienne Zadania w Planner

1. 
Rozpocznij Zautomatyzowany Przepływ:

  - Wyzwalacz: Cykliczny (codziennie o 7:00).

2. 
Utwórz Zadanie w Microsoft Planner:

  - Akcja: "Utwórz zadanie".
  - Plan ID: [Wybierz swój plan]
  - Bucket ID: [Wybierz odpowiedni bucket]
  - Tytuł: "Połączenia z Klientami"
  - Data końcowa: Dzisiaj
  - Przypisz do: [Treść dynamiczna lub zdefiniowani użytkownicy]

### Sync Zadania z To Do

1. 
Utwórz Zadanie w Microsoft To Do:

  - Akcja: "Utwórz zadanie".
  - Tytuł: "Połączenia z Klientami"
  - Data końcowa: Dzisiaj
  - Godzina przypomnienia: 8:00 AM

### Śledzenie Ukończenia Zadań

1. 
Wyzwalacz na Koniec Dnia:

  - Wyzwalacz cykliczny ustawiony na koniec dnia pracy.

2. 
Wymień Zadania w Planner:

  - Akcja: "Wymień zadania" w Planie.

3. 
Warunek do Sprawdzania Statusu:

  - Jeżeli Status Zadania jest inny niż Ukończone:
    - Akcja: Wyślij powiadomienie do ciebie/managera.

## Podsumowanie

Wykorzystując Microsoft Planner, Microsoft To Do i Power Automate:
- 
Planner
: Tworzenie i przypisywanie zadań w określonych przedziałach czasowych z widocznością dla wszystkich członków zespołu.
- 
To Do
: Udostępnianie codziennych list zadań i zarządzanie indywidualnym postępem z powiadomieniami na czas.
- 
Power Automate
: Automatyzacja tworzenia codziennych zadań i synchronizacja między Planner i To Do, zapewniając możliwość śledzenia i otrzymywania powiadomień o ukończeniu zadań.

## Dodatkowe Zasoby

- 
Dokumentacja Microsoft
: Odwiedź przewodniki Microsoft dotyczące szczegółowych instrukcji na temat Power Automate, Planner, i To Do.
- 
Szablony & Samouczki
: Przeglądaj szablony w Power Automate do automatyzacji zarządzania zadaniami.