<!-- @ver:1.1.15.31 -->
# beFlow v. 1.1.15.32

<!-- @changelogstart -->
## Release 1.1.15.32 z 28.05.2024
- [x] Obsługa błedów odczytu uszkodzonych modeli
- [x] Odczyt IFCEntity

## Release 1.1.15.31 z 28.05.2024
- [x] Usunięcie poważnego błędu z synchronizacją
- [x] Naprawa komunikatu po synchronizacji

## Release 1.1.15.30 z 23.05.2024
- [x] Zmieniono podjeście do zarządzania backupami - użytkownik wybiera będzie backupował. Teraz backupy tworzą się w postaci plików zip
- [x] Obsługa kilku projektów w jednym folderze

## Release 1.1.15.29 z 17.05.2024
- [x] Dodano obsługę typów danych
- [x] Dodano ostrzeżenie o duplikowaniu projektu w folderze
      
## Release 1.1.15.28 z 10.05.2024 - release nie był udostępniany publicznie
- [x] Usunięto problemy z kolorowaniem (komórka nazwa)

## Release 1.1.15.27 z 06.05.2024 - release nie był udostępniany publicznie
- [x] Naprawiono bieżące błędy zgłoszone przez użytkowników związane ze stabilnością
- [x] Dodano pełną obsługę API w wersji 5.43

## Release 1.1.15.26 z 30.04.2024 - release był udostępniany wybranym użytkownikom
- [x] Naprawiono bieżące błędy zgłoszone przez użytkowników związane ze stabilnością
- [x] Zmieniono wersję BimVision na 2.28.0
      
## Release 1.1.15.25 z 25.04.2024  - release nie był udostępniany publicznie
- [x] Naprawiono bieżące błędy zgłoszone przez użytkowników związane tworzeniem projektu

## Release 1.1.15.24 z 17.04.2024
- [x] Naprawiono błędy związane z wyłaczeniem się excela
- [x] Przeniesiono obsługę excela do COM po stronie Excel z Bim Vision - stabilniejsze działanie
- [x] Zaktualizowano kod po stronie komunikacji
## Release 1.1.15.23 z 16.04.2024
- [x] Błedy kodowania znaków w pliku bazy csv i json
## Release 1.1.15.22 z 12.04.2024

zrealizowane zmiany 

- [x] Zmiana modelu komunikacji między BIM VISION – EXCEL – problemy z komunikacją

    Wykorzystujemy IFCOpenShell do pobrania danych z modelu BIM, co znacznie przyspiesza proces przetwarzania danych. Aplikacja przelicza HASH pliku Ifc i porównuje go przy każdym otwarciu z wygenerowaną bazą. Oznacza to tyle że po modyfikacji pliku Ifc lub jego podmienieniu program ponownie stworzy bazę danych.
    
    Baza danych zapisywana jest w pliku .json w katalogu głównym projektu. 
    
    ![image](https://github.com/pe0067/beflow/assets/86341947/9f01bab1-f2ea-49c7-a8bd-1746c6118696)
    
    Utworzenie bazy danych ma miejsce przy pierwszym uruchomieniu projektu i po każdej aktualizacji modelu IFC. Proces trwa kilka minut i zależy od wielkości pliku IFC.  

- [x] Zmiany w Highlight Values - obsługa błędnych komórek
- [x] Zmiana modelu zapisu tabel
- [x] Stawiamy na optymalizację działania, dlatego długo szukaliśmy rozwiązania które będzie dobrym kompromisem między wydajnością i funkcjonalnością. Nowe BeFlow oparte jest o rozwiązanie hybrydowe. Łączymy szybkość działania PowerQuery i zwykłych tabel Excel. Cały proces działa niezauważalnie dla użytkownika i nie wymaga większej wiedzy niż poprzednio. 

    Zastosowanie Query wyniosło część zajmującą zarządzaniem modelem do baz danych CSV na zewnątrz. Pozwala to na błyskawiczną synchronizację z modelem.  
    
    a. Użytkownik zaakceptuje uruchamianie makr w pliku excel.
    
    ![image](https://github.com/pe0067/beflow/assets/86341947/6590a16c-3c51-48a8-a9cb-9044d128048a)
    
    b. Dodawanie wierszy tylko z poziomu BIM VISION 
    
    ![image](https://github.com/pe0067/beflow/assets/86341947/854b715b-f1a0-4485-8fbe-36c0b4fcf56f)
    
    c. Usuwanie wierszy i kolumn oraz zmiana nazwy za pomocą funkcji do tego przeznaczonych 
    
    ![image](https://github.com/pe0067/beflow/assets/86341947/1eac2503-9145-4e79-9a8b-27c3541ae83b)
    
    d. Tworzenie i edycja tabeli za pomocą kreatora.  
    
    ![image](https://github.com/pe0067/beflow/assets/86341947/c7792f8f-6c16-48c1-982d-6f2869b27ae9)
    
    e. Zmiana nazwy kolumn z parametrami. Nowy zapis to #PropSet.ParamName, należy zwrócić uwagę na znaki ‘#’ i ‘.’. 

- [x] Optymalizacja funkcji

    a. Zoptymalizowano funkcje dodawania elementów 
    b. Zoptymalizowano synchronizację danych 
    c. Zoptymalizowano kolorowanie elementów 
    d. Zoptymalizowano działanie funkcji tworzenia i zarządzania filtrami.  

    ![image](https://github.com/pe0067/beflow/assets/86341947/8340a9ec-56ab-4c76-aa16-699eef0268ae)

    e. Znika combobox z ribbona – ze względu na błędy w działaniu i brak możliwości naprawy. 

- [x] Naprawa błedów 

    a. Naprawa błędów wynikających z wad poprzedniego połączenia. 
    b. Naprawa błedów synchronizacji, dodawania wierszy, kolorowania, filtrowania. 
    c. HighlightValue – naprawa błędów wynikających z niepoprawnego interpretowania kolorów.        

- [x] Poprawa bezpieczeństwa

    Dodaliśmy obsługę licencjonowania. W wewnątrz firmy program licencjonuje się automatycznie. Na zewnątrz robi to przez podanie kodu autoryzacyjnego podczas uruchomienia.

    ![image](https://github.com/pe0067/beflow/assets/86341947/6bb32470-3ad4-4c10-8f26-0aa03b204db6)

- [x] Nowe przyciski wsparcia użytownika

    Dodajemy przyciski w BimVision: instrukcji obsługi oraz zgłaszania problemów.

    ![image](https://github.com/pe0067/beflow/assets/86341947/de078c90-bb50-476f-ac9a-9a5a74f72599)

    Dodaliśmy ekran z changelogiem, który wyświetli ten dokument!

<!-- @changelogend -->
