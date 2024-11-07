# Projekt Aplikacji Power Apps -- TiSP

## Narzędzia
1. **Power Apps**: Do stworzenia aplikacji.
2. **Microsoft Power Automate**: Do automatyzacji przepływów pracy.
3. **Microsoft To-Do**: Do zarządzania indywidualnymi zadaniami pracowników.
4. **Microsoft Teams**: Do komunikacji, współpracy i importu danych personalnych.
5. **Excel/CSV**: Do ręcznego importu danych personalnych z Teta.me i Tidaro.

## Przepływ pracy
1. **Import danych**:
   - **Teams**: Import danych personalnych z zespołów w Teams.
   - **Excel/CSV**: Ręczny import danych personalnych z Teta.me i Tidaro.
2. **Tworzenie zadań**:
   - Team Leader tworzy zadania w aplikacji Power Apps, określając czas trwania, minimalną i maksymalną liczbę osób oraz wymagania dotyczące lokalizacji.
   - Zadania mogą być oznaczane metkami lub hashtagami (np. "telefonista", "piszący maile", "dobry negocjator").
3. **Przypisywanie zadań**:
   - Ręczne przypisywanie zadań na zasadzie matrycy: oś X to sloty czasowe, oś Y to nazwiska członków zespołu.
   - Możliwość włączenia lub wyłączenia danej osoby do danego zadania w danym czasie.
   - Podsumowania w każdej kolumnie (ilość osób przypisanych do zadania) i w każdym wierszu (ilość przypisanych godzin w ciągu dnia).
   - Zadania w danych przedziałach czasowych mogą się różnić, np. między 8:00 a 10:00 mogą być do wyboru trzy zadania.
   - Nie można przypisać danej osoby do wielu zadań w tym samym czasie.
4. **Synchronizacja z To-Do**:
   - Codziennie o 7 rano zadania są synchronizowane z Microsoft To-Do każdego pracownika.
5. **Monitorowanie postępów**:
   - Pracownicy odhaczają zakończone zadania w To-Do.
   - Aplikacja monitoruje postępy i generuje raporty dla Team Leaderów.
6. **Feedback**:
   - Team Leader otrzymuje informację zwrotną, jeśli plan nie zadziałał lub pracownik pominął zadanie.

## Interfejs aplikacji
1. **Ekran główny**: Przegląd zadań na dany dzień, z możliwością filtrowania według zespołu, lokalizacji i statusu zadania.
2. **Tworzenie zadania**: Formularz do tworzenia nowych zadań z polami na nazwę zadania, opis, czas trwania, minimalną i maksymalną liczbę osób oraz wymagania dotyczące lokalizacji.
3. **Przypisywanie zadań**: Widok matrycy z możliwością przypisywania zadań do pracowników, uwzględniający ich dostępność i lokalizację.
4. **Raporty**: Sekcja z raportami o postępach zespołu, z możliwością generowania raportów dziennych, tygodniowych i miesięcznych.

## Pytania do doprecyzowania
1. **Integracja z Teta.me i Tidaro**: Czy możemy sprawdzić, czy firma ma dostęp do API tych platform? Jeśli nie, jak często będą aktualizowane dane importowane ręcznie?
2. **Import danych z Teams**: Jakie dokładnie dane personalne są dostępne w Teams i jak często będą aktualizowane?
3. **Metki/hashtagi**: Czy masz już listę metek/hashtagów, które będą używane do oznaczania pracowników? Jakie są kryteria przypisywania tych metek?
4. **Feedback**: Czy feedback ma być automatyczny (np. brak odhaczenia zadania) czy pracownicy mają ręcznie zgłaszać problemy?
