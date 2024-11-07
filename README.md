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


# Prompts

## First one
Pomóż mi proszę zaprojektować aplikację w Power Apps która ma na celu usprawnienie pracy w dwóch zespołach w naszym biurze. Oba zespoły składają się z 22 osób plus team leader. Każdy z zespołów pracuje w trybie hybrydowym 1:1, czyli 50% czasu spędza w biurze domowym a drugą połowę u nas w biurze. W naszym biurze wszyscy pracują na open space i nie mają przypisanych biurek, lecz zmieni się to niedługo a aplikacją do rezerwacji miejsc przy biurkach jest Tidaro. Zarządzanie urlopami i wnioskowaniem pracą z domu jest platforma Teta.me a planowaniem zadań w efekcie końcowym miał by być dla każdego pracownika jego osobisty Microsoft To-Do. Aplkiacja powinna spełniać następujące funkcje: Podstawowe -  włatwy i przejrzysty sposób móc wszystkim członkom zespołu przydzielać predefiniowane zadania, które mają określony początek i koniec w ciągu dnia pracy (na przykład "zadzwoń do klienta między 8:00 a 10:00") takie zadania mogą wykonywać pojedyńcze osoby albo większe grupy niezależnie od siebie ale w tym samym czasie. Codziennie może być inny rozkład zadań i przypisanych do nich osób z zespołu. Jeżeli potrzebna jest w zadaniu współpraca nie można mieszać osób przebywających na home office z tymi w biurze. osoby będące na urlopie nie powinny być widoczne w zasobach możliwych do przydzielenia. Każde zadanie posiada zakres minimalnej oraz maksymalnej liczby osób, która może się nim zajmować w ciągu danego czasu. Nie można przydzielić za dużo lub za mało osób do zadania. Po ustaleniu planu na tydzień indywidualne listy zadań powinny być codziennie o 7 rano przydzielane w aplikacjach To-Do danych pracowników oraz po zakończeniu oczekiwać na odchaczenie. Zakończenie wszystkich zadań w To-Do po zakończeniu dnia pracy uznawane jest jako pozytyw i nie potrzebny jest feedback. Jeżeli jakieś zadane zostało pominięte Team Leader powinien otrzymać ogólną infromację zwrotną o wynikach całego zespołu po zakończeniu dnia. Zaproponuj proszę narzędzia oraz flow tego rodzaju aplikacji, jej interfejs oraz zadaj mi maksymalną ilość pytań aby doprecyzować możliwości wyjścia i wejścia danych z innych źródeł (Teta, Tidaro, Teams, Tabele Exela, CSV itd.)

## Second one
- Teta posiada API nie mam informacji jednak czy nasza firma wykupiła taki dostęp
- Tidaro także nie mam informacji o tym czy API jest dostępne
- Dane z tabel ograniczałyby się do "ręcznie" importowanych danych personalnych z Tety oraz Tidaro
- Teams może także służyć do importowania danych personalnych ponieważ obie grupy mają swoje Zespoły na Teamsie
- Zadania mogą być proponowane wg metek lub hashtagów dowiązanych do poszczególnych pracowników (n.p. "telefonista" "piszący maile" "dobry negocjator" itd.) ale na wstępie ręczne przypisywanie było by najprostrze. Na zasadzie matrycy - oś X to poszczególne sloty czasowe oś Y nazwiska członków zespołu, na przekroju obu list możliwość włączenia lub wyłączenia danej osoby do danego zadania w danym czasie oraz podsumowania w każdej kolumnie i każdym wierszu (w kolumnie ilość osób przypisanych do danego zadania a w każdym wierszu ilość przypożądkowanych godzin w ciągu dnia. Zadania w danych przedziałach czasowych mogą się różnić i np między 8:00 a 10:00 mogą być do wyboru trzy zadania. Oczywiście nie można przypisać danej osoby do wielu zadań w tym samym czasie.
- Feedback miałby być na zasadzie zgłoszenia jeżeli plan nie zadziałał lub pracownik pominął zadanie
