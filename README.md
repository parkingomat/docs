# Dokumentacja dombot
[http://docs.dombot.pl/](http://docs.dombot.pl/)

## Struktura projektu:

### Konfiguracja
kazdy modul udostepnia wlasne akcje, zdarzenia i konfiguracje,
ktore w sekcji konfiguracja mozna edytowac
np zewnetrzne uslugi wymagaja autoryzacji, ktora tutaj mozna zdefiniowac
Wszystkie dane konfiguracji docelowo beda szyfrowane metoda keepass w lokalnym pliku

[https://pypi.org/project/pykeepass/](https://pypi.org/project/pykeepass/)

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


## Funkcjonalności dla zalogowanych użytkowników

### Modul: Analizowanie
+ dodaj nazwe glowna
+ dodaj nazwy pokrewne do porownania
+ tabela porownawcza
  +  dodaj usluge, ktora oferuje parametry
    + np. ilosc wynikow w wyszukiwarce
    ...
    

### Modul: Monitorowanie domen
+ funkcja dodaj domenę
+ lista
  + nazwa
  + dane z WHOIS
  + rejestrator
  + hosting
  + dns
  + e-mail do kontaktu  
  + funkcja:
    + usuń domenę z listy    
    + ustaw kod AuthInfo
    
### Modul: Zarządzanie (Posiadane Domeny)
+ funkcja dodaj domenę
+ lista
  + nazwa
  + dane z WHOIS
  + rejestrator
  + hosting
  + e-mail do kontaktu
  + e-mail do potwierdzenia transferu
  + finanse (koszty, zarobki, prowizje,  ...)
  + funkcja:
    + usuń domenę z listy
    + przedłuż    
    + transferuj
    + pobierz kod AuthInfo
    
    

### Modul: Rejestratorzy
+ operacje a liscie (checkbuttons):
  + porównaj ceny 
    + rejestracji
    + przedłużenia
        
+ lista
  + nazwa
  + cennik
  + dane do faktury
  + lista podpiętych domen
  + funkcja:
    + zarządzanie domenami
    + usuń rejestratora
    + kontakt

### Modul: Usługodawcy 

+ lista
  + konto użytkownika
  + usługa:
    + hosting, vps, ..


### Modul: Serwery DNS
+ funkcja dodaj serwer
  + lista
    + nazwa operatora
    + lista serwerów: ns1,...    
    + funkcja:
      + usuń
      + edytuj
      
      
### Modul: Aplikacje otwartozrodlowe opensource
+ lista
  + url
    + repozytorium
    + readme
    + logo


### Modul: Aplikacje platne z autoryzowanym dostepem
+ lista
  + nazwa


### Modul: Dostep do uslugi API, publicznych, otwartych
np wyszukiwarki, whois, itd
+ lista
  + nazwa
  + limit zapytan 
    + jak w CRON, na godzine,minute, dzien, ..
  + url 
    + dokumentacja
    + endpoint
    + logo


### Modul: Dostep do uslugi API, platnych, autoryzowanych
+ lista
  + nazwa
  + url 
    + dokumentacja
    + oferta
    + licencja
    + endpoint
    + logo

### Modul: Planowanie
okreslenie w czasie operacji, planowanie zdarzen kaskadowo
+ Rejestracja
+ Przedłużanie
+ Przechwytywanie
+ Sprzedaż
+ Instalacja Aplikacji
