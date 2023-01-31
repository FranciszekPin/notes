# Zagadnienia

:vomiting_face: :vomiting_face: :vomiting_face: :vomiting_face: 
:vomiting_face:

## Zadanie 1

**Design and implement features with regard to high performance and capability
to handle large amounts of data**

Zaproponuj miary i przypadki testowe umożliwiające stwierdzenie "high
performance and capability to handle large amounts of data".

### Miary

**Ile zapytań system przetwarza na jednostkę czasu**

Pomiar `X = Z/T`

więcej = lepiej

**Przepustowość pobierania/wysyłania plików**

Pomiar `X = S/T`

`S` - rozmiar danych
`T` - czas

więcej = lepiej

**Ile użytkowników może korzystać jednocześnie z systemu**

Pomiar `U` - liczba użytkowników

więcej = lepiej

**Trwałość bazy danych**

Pomiar `(T - F) / T`

`T` - liczba wszystkich testów
`F` - liczba testów w których dane się uszkodziły

**Maksymalny możliwy rozmiar danych w bazie danych**

Pomiar `U_1 + U_2 + ... + U_n`

`U_i` dane i-tego użytkownika

### Przypadki testowe

**ID**: UC-123

**Tytuł**: Przetwarzanie zapytania o dużym rozmiarze

**Aktor**: Użytkownik

**Warunek początkowy**: użytkownik jest upoważniony do przesyłania danych

**Warunek końcowy**: dane zostają przesłane

**Scenariusz**:

  1. Użytkownik przesyła plik wirus.exe o rozmiarze 100GB
  2. System odbiera plik
  3. Porównujemy przesłany plik (suma kontrolna)

**ID**: IOIOI

**Tytuł**: Pomiar wydajności

**Aktor**: X Użytkowników

**Warunek początkowy**: użytkownicy są upoważnieni do przesyłania danych

**Warunek końcowy**: dane zostają przesłane

**Scenariusz**:
  1. Użytkownicy wysyłają naraz losowe żądania do serwera
  2. Mierzymy czas od wysłania żądań do obsłużenia wszystkich
  3. Powtarzamy wielokrotnie, obliczamy średnią
  

## Zadanie 2

**Work with team members to conduct root cause analysis of issues, review code
and/or design proper testing mechanisms**

Opisz zwinne (agile)  techniki i narzędzia oraz zwinny, np. wg Scrum  proces
weryfikacji i walidacji spełnienia wymagań  funkcjonalnych i niefunkcjonalnych
oprogramowania.

### Techniki

**sprint** - interwał, maskymalnie 1 miesiąc w jego trakcie ma zostać coś
dodanego (increment). Zawiera planowanie sprintu, standupy, ocenę sprintu.
Działania dążą do osiągnięcia celu sprintu wg definition of done. Na końcu
sprintu ma być widoczny efekt.

**daily scrum/standup** - codzienne spotkanie, raportowanie stanu i planów

**sprint review** - prezentacja klientowi postępów oraz efektów sprintu.

**sprint retrospective** - analiza tego co nie poszło, wyciąganie wniosków

### Narzędzia

**product backlog** - uporządkowana, zmieniająca się lista tego co trzeba
zrobić

**sprint backlog** - cel sprintu oraz jego plan

**tabalica zadań** - (np. kaban) - wizualizacja zadań i ich stanu

**wykresy** - np prognozowanie postępów

### Weryfikacja i walidacja wymagań

Opieramy się na definition of done poszczególnych zadań w backlogu, pokazanie
wartości dodanej w sprint review. Jest to łatwiejsze dzięki podziałowi na
incrementy. Stosuje się Unit testy, code review.

## Zadanie 3

**Lead by example, empathy, transparency**

Jak w/w  postulaty można wcielić w życie w Twoim projekcie.

### Example

Stosujemy się do tego czego wymagamy (nie spóźniamy się blebleble), robimy
kawę scrum masterowi, swoimi działaniami dajemy przykład innym pracownikom
np samodoskonaleniem się w scrum i agile, odpowiezialne podejście do 
przydzielonych zadań.

### Empathy

Zespół pracuje w jednym miejscu, pracownicy pomagają sobie. Pracują jako
jeden zespół.

### Transparency

Częste spotkania z klientem, ustandaryzowana zrozumiała dokumentacja, daily
scrum, jawna i zrozumiała reprezentacja informacji (np postępu projektu, 
nizawodności systemu itp).

## Zadanie 4

**Are a self-starter and are able to work well with others in a fast-paced 
agile environment with an emphasis on collaboration**

Jak powinna być zorganizowana praca  inżyniera oprogramowania  będącego 
członkiem zespołu wytwarzającego  oprogramowanie wg metodyki Scrum

### Inżynier w scrum

- wybiera zadania do wykonania w sprincie z product backlogu do sprint
  backlogu (uwzględniając swoje umiejętności, priorytet i czasochłonność)
- wykonuje zadania na podstawie ich definition of done
- dąży do osiągnięcia sprintu, adoptuje się
- codziennie synchronizuje swój postęp z scrum teamem
- odpowiedzialny za zadania, wymusz odpowiedzialność na innych
- komunikuje się z resztą zespołu i scrum masterem
- szeroki zakres umiejętności, brak specjalizacji
- samoorganizuje sprint wraz z resztą zespołu

## Zadanie 5

**Product Owner for all teams on-site**

Scharakteryzuj role, obowiązki, narzędzia, metody pracy Scrum Product Ownera
oraz Scrum Mastera.

### Scrum Master

Pilnuje stosowania zasad scrum oraz efektywności zespołu

#### Role i obowiązki

- Produktywność scrumu, nieprzekraczanie ram czasowych
- komunikuje zmiany w backlogu
- szkoli w zakresie wdrażania scruma
- raportowanie o wynikach sprintu
- Monitorowanie prac 
- Usuwanie przeszkód 

#### Narzędzia

- oprogramowanie (Jira, slack)
- sprint backlog
- tablica zadań
- wykresy

### Product Owner

Odpowiedzialny za maksymalizację wartości produktu wytwarzanego przez zespół

#### Role i obowiązki

- tworzy product backlog, porządkuje, ustala priorytety
- komunikuje się z biznesem i klientami
- odpowiedzialny za realizację wizji produktu i zapewnienia osiągnięcia celu

#### Narzędzia

- product backlog, określanie priorytetów
- user stiories
- narzędzia raportowania, analizy
- prototypy
- tablica koncepcyjna
- ścieżka/mapa rozwoju