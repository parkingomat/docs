# Dokumentacja dombot

+ [Dokumentacja projektu](https://docs.dombot.pl/)

+ [Aplikacja frontendowa laczaca sie z api](https://app.dombot.pl/)

+ [Dostep API](https://api.dombot.pl/)

+ [Logo](https://logo.dombot.pl/)


## Struktura projektu:

### Konfiguracja
kazdy modul udostepnia wlasne akcje, zdarzenia i konfiguracje,
ktore w sekcji konfiguracja mozna edytowac
np zewnetrzne uslugi wymagaja autoryzacji, ktora tutaj mozna zdefiniowac
Wszystkie dane konfiguracji docelowo beda szyfrowane metoda keepass w lokalnym pliku

[https://pypi.org/project/pykeepass/](https://pypi.org/project/pykeepass/)

## Oferta

 Stale zdarzają się, że sytuacje niedopatrzenia odnośnie zarządzania domenami internetowymi, dlatego domeny regularnie "spadają", potem "spekulant" je kupuje i odsprzedaję ... koszt domeny i jej utrzymania jest na tyle niski, że wielu ludzi zapomina o nich, bo to wydarzenia zbyt rzadkie, raz do roku. Dlatego proponuję rozwiązanie, asystenta do spraw domen, na wzór [#ChatuGPT](https://www.openai.com), który mając dostęp do providerów domen i usług sam wykona:  
> 1\. Zmianę konfiguracji DNS  
> 2\. Przedłuży domenę internetową  
> 3\. Utworzy certyfikat  
> 4\. Przeniesie domeny pomiędzy providerami  
> 5\. Przniesie serwis pomiędzy wybranymi providerami  
> 6\. Stworzy ofertę sprzedaży domeny  
> pomagając kompleksowo tak jak administrator sieci.  
> Usługa będzie bezpłatna, dostepna w ramach systemu operacyjnego [#PoLoGoS](https://www.pologos.com) a jedynym kosztem będzie uruchomienie tego systemu w ramach własnej infrastruktury, za instalację Cloud na VPS będę pobierał opłatę, pytanie jaki koszt systemu do automatyzacji zarządzania setkami i tysiącami usług opartych o własną infrastrukturę będzie uzasadniony?  




Usluga jednorazowa jest nie pewna dla kupca z 2 przycznym nie wie czy sprzedający usługę będzie wspierał dalej usługę
Ale pojawia sie inny problem czyli zaufanie w kierunku z pewnością konieczności mostka w logowaniu do operatora.
Wielkość uslug zmian jest zabezpieczona dodatkowym kodem np sms, ljb autoryzacja wielopoziomowa.


przy opcji #lifetime #ondemand kod platformy mamy u siebie, więc też odpowiadamy za bezpieczeństwo, konieczna jest samodzielna instalacja na RPI ZERO W i wpiąć w hub USB


## MODEL BIZNESOWY

niszczące dla niezmieniającego się biznesu z pewnością, bo logiczne jest, że w gronie klientów znajdzie się konkurencja, która będzie się starała tak pozyskany kod wykorzystać by poszerzyć grono swoich klientów. chatGPT też można stworzyć na podstawie już istniejących rozwiązań ale najwięcej kosztuje uczenie modelu i tutaj jest podobnie, bo logikę, którą udostępnimy w wersji lifetime będzie ulegała poprawie i pomijajac łatki bezpieczeństwa, uzyskanie aktualizacji funkcjonalności będzie wymagało subsrkypcji, bo taki model gwarantuje długofalowe wsparcie i opłacalnoś modelu biznesowego dla obu stron.





### Dane 
Dane przechowywane jako rezultaty funkcji modulow, aplikacji, api beda zapisane w bazie danych sqlite lokalnie
w celu ustandaryzowania beda okreslane typy danych, aby mozliwe bylo latwe tworzenie nowych funkcjonalnosci w oparciu
o juz istniejace rozwiazania

np typ danych:
  + kolejka zadan
  + zdarzenie w kalendarzu
    +event:
      + planowanie
      + trwanie
      + zakonczenie
    + config:
      + zakres dat
        + start
        + stop

  + domena internetowa
  
    + zdarzenia czasowe, cykl zycia domeny
      + wygasniecie
      + usuniecie
      
    + zdarzenia kontrolowane
      + rejestracja
      + przedluzenie waznosci
      + zmiana danych
      + transfer 
        + do innego operatora z tymi samymi danymi
        + do innego operatora + zmiana danych
      + po wygasnieciu
      + na zadanie
  
Zdarzenia dla kazdego typu danych

## Moduly
Podstawowe moduly Core niezbedne do dzialania platformy:

  + konfiguracja
  + autoryzacja
  + profile
    + dane usera do logowania
    + rola w systemie
  + dashboard
    + lista 
      + modulow
      + aplikacji
      + api
     
### Modul Core: kalendarz, planowanie zadan
w celu okreslenia czasu lub zakresu dat wszelkich zdarzen mozna uzyc wewnetrznej bazy danych sqlite
Pozniej mozliwy bedzie eksport do innych formatow, czy synchronizacja z innymi platformami dla terminow

### Modul Core: kolejka zadan, queue
mozliwa do reuzycia w przypadku innych aplikacji czy api
pozwala na globalne zarzadzanie kolejkami zadan do wykonania

### Modul Core: konfiguracja
sluzy do zapisywania danych sytemowych, usera, modulow, api
+ zasoby
  + w przypadku VPS
  
+ wyglad 
  + template
    + mode: white/black

### Modul Core: profile/customers
w celu umozliwienia zarzadzania roznymi danymi w granicach jednego konta
jest mozliwe wykorzystanie wielu profili, np dla klientow koncowych, przy obsluge klientow, dzialalnosci miedzynarodowej,
struktura reseller
+ dane usera dla rejestracji domen
+ dane dla rozliczen 
+ rola

### Modul Core: Dashboard
+ dodawanie modulow systemu z listy
+ dodawanie Api i Aplikacji zewnetrznych

### Moduly wewnetrzne uzytkownika
Moduly dystrybuowane przez producenta platformy dombot

+ zdarzenia, actions, events
+ role poziomu dostepu uzytkownika dla kazdej akcji
  
### Moduly zewnetrzne spolecznosci
Marketplace, platne i darmowe aplikacje dedykowane dla dombot pisane przez zewnetrznych tworcow oraz providerow uslug

  + Aplikacja
    + konfiguracja
    + funkcje
      + parametry
      + rezultat
      
### API dombot, dostepne na zewnatrz      
uslugi dostepne poprzez API

  + autoryzacja
  + konfiguracja
  + planowanie
  + funkcje
    + parametry
    + rezultat


## Moduly z marketplace
Funkcjonalności dla zalogowanych użytkowników

[MODULY.md](MODULY.md)
