# Dokumentacja dombot

## Struktura projektu:

### Modul Core
Podstawowe mouduly niezbedne do dzialania platformy

  + konfiguracja
  + autoryzacja
    + dane usera do logowania
    + rola w systemie
  + dashboard
    + lista 
      + modulow
      + aplikacji
      + api
 
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
      
### API      
uslugi dostepne poprzez API

    + autoryzacja
    + konfiguracja
    + funkcje
      + parametry
      + rezultat

## Funkcjonalności dla zalogowanych użytkowników

### Konfiguracja


### Dashboard
+ dodawanie modulow systemu z listy
+ dodawanie Api i Aplikacji zewnetrznych


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
    
    

## Modul: Rejestratorzy
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

## Modul: Usługodawcy 

+ lista
  + konto użytkownika
  + usługa:
    + hosting, vps, ..


## Modul: Serwery DNS
+ funkcja dodaj serwer
  + lista
    + nazwa operatora
    + lista serwerów: ns1,...    
    + funkcja:
      + usuń
      + edytuj
      
      
## Modul: Aplikacje otwartozrodlowe opensource
+ lista
  + url
    + repozytorium
    + readme
    + logo


## Modul: Aplikacje platne z autoryzowanym dostepem
+ lista
  + nazwa


## Modul: Dostep do uslugi API, publicznych, otwartych
np wyszukiwarki, whois, itd
+ lista
  + nazwa
  + limit zapytan 
    + jak w CRON, na godzine,minute, dzien, ..
  + url 
    + dokumentacja
    + endpoint
    + logo


## Modul: Dostep do uslugi API, platnych, autoryzowanych
+ lista
  + nazwa
  + url 
    + dokumentacja
    + oferta
    + licencja
    + endpoint
    + logo

## Modul: Planowanie
okreslenie w czasie operacji, planowanie zdarzen kaskadowo
+ Rejestracja
+ Przedłużanie
+ Przechwytywanie
+ Sprzedaż
+ Instalacja Aplikacji
