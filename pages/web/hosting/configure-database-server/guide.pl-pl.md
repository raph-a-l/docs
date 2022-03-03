---
title: 'Konfiguracja serwera baz danych'
slug: konfiguracja-optymalizacja-serwera-bazy-danych
excerpt: 'Dowiedz się, jak skonfigurować i zoptymalizować serwer bazy danych'
section: 'CloudDB'
order: 6
---

**Ostatnia aktualizacja z dnia 03-02-2022**

## Wprowadzenie

Za pomocą serwerów baz Cloud Databases możesz wpłynąć na globalne parametry serwera. Możesz również wyświetlić aktywność swojego serwera. 

**Dowiedz się, jak skonfigurować i zoptymalizować serwer baz danych.**

## Wymagania początkowe

- Posiadanie [Cloud Databases](https://www.ovh.pl/cloud-databases/){.external}
- Dostęp do [Panelu klienta OVHcloud](https://www.ovh.com/auth/?action=gotomanager&from=https://www.ovh.pl/&ovhSubsidiary=pl){.external}.

## W praktyce

### Wyświetl ogólne informacje o serwerze baz danych

Na pasku usług po lewej stronie Panelu [klienta OVHcloud](https://www.ovh.com/auth/?action=gotomanager&from=https://www.ovh.pl/&ovhSubsidiary=pl){.external} przejdź do sekcji `Bazy danych`{.action}, a następnie do odpowiedniej instancji SQL. Następnie przejdź do sekcji `Informacje ogólne`{.action}.

W zakładce tej znajdziesz ważne informacje dotyczące Twojej instancji SQL. Prosimy o poświęcenie kilku minut na sprawdzenie, czy wyświetlane informacje są poprawne lub zgodne z poniższymi wskazówkami.

|Informacja|Szczegóły|
|---|---|
|Status usługi|Pokazuje, czy instancja jest uruchomiona, w trakcie restartu lub zawieszona. Twoja instancja musi być uruchomiona, abyś mógł przeprowadzać na niej działania.|
|Typ|Pokazuje system baz danych używany przez serwer. Jeśli nie masz pewności, czy stosowany typ jest prawidłowy, wiedz, że najczęściej wybieranym jest "MySQL", ale istnieją również inne (PostgreSQL, MariaDB). Na przykład, jeśli Twoja strona WWW korzysta z modułu WordPress, system MySQL jest najlepiej do tego dopasowany.|
|Wersja|Pokazuje wersję systemu baz danych używaną przez serwer. Upewnij się, czy Twoja strona WWW jest kompatybilna z wybraną wersją.|
|RAM|Pokazuje pamięć operacyjną dostępną dla Twojej instancji oraz ewentualne przekroczenia pamięci. Serwer baz danych ma dedykowane i gwarantowane zasoby, jakimi jest pamięć RAM. Jeśli zajdzie taka potrzeba, możesz zwiększyć pamięć RAM, jeśli zużyjesz wszystkie zasoby pamięci Twojej instancji.|
|Infrastruktura|Pokazuje infrastrukturę używaną przez Twoją instancję. Jest to wewnętrzne oznaczenie infrastruktury OVHcloud.|
|Centrum danych|Pokazuje centrum danych, w którym została uruchomiona instancja. Upewnij się, czy centrum danych Twojej instancji jest takie samo, jak centrum danych hostingu OVHcloud, na którym Twoja strona WWW jest lub będzie hostowana.|
|Host|Pokazuje serwer OVHcloud, na którym utworzona jest Twoja instancja. Jest to wewnętrzne oznaczenie infrastruktury OVHcloud i może być wykorzystywane w komunikatach dotyczących [incydentów OVHcloud](https://web-cloud.status-ovhcloud.com/){.external}.|

![Informacje ogólne](images/privatesql01-General-information.png){.thumbnail}

### Autoryzacja adresu IP ( Tylko w ofercie Cloud Databases )

Aby uzyskać dostęp do instancji CloudDB, należy wskazać adresy IP lub zakresy adresów IP, które mogą się łączyć z Twoimi bazami danych.

W tym celu przejdź do paska usług po lewej stronie w Panelu [klienta OVHcloud](https://www.ovh.com/auth/?action=gotomanager&from=https://www.ovh.pl/&ovhSubsidiary=pl){.external}, przejdź do sekcji `Bazy danych`{.action}, a następnie do odpowiedniej instancji SQL. 

Kliknij kartę Autoryzowane `IP`{.action}, a następnie przycisk `Dodaj adres IP/maskę`{.action}.

![cloud databases - bazy danych na instancji](images/clouddb-add-ip.png){.thumbnail}

W oknie, które się wyświetli wskaż adres IP lub maskę, którą chcesz autoryzować w `IP/maska`{.action}. Możesz również dodać opis. Zdecyduj, czy chcesz udzielić dostępu wyłącznie do baz danych czy również do SFTP. Następnie kliknij `Zatwierdź`{.action}.

![cloud databases - bazy danych na instancji](images/clouddb-add-ip-step2.png){.thumbnail}

#### Autoryzacja połączeń do hostingu OVHcloud 

W przypadku hostingu OVHcloud należy autoryzować adres IP "bramy wyjściowej" (gateway). 

Aby uzyskać adres IP "**bramy wyjściowej**", przejdź do [Panelu klienta OVHcloud](https://www.ovh.com/auth/?action=gotomanager&from=https://www.ovh.pl/&ovhSubsidiary=pl){.external}. Kliknij kartę `Web Cloud`, a następnie `Hosting`{.action} w kolumnie po lewej stronie. Wybierz hosting z listy i kliknij zakładkę `FTP - SSH`.

Na stronie znajdziesz wpis **"Serwer FTP"**, pod którym wpiszesz numer klastra, na którym się znajdujesz.

![cloud databases - bazy danych na instancji](images/clouddb-add-ip-step3.png){.thumbnail}

Po odnalezieniu numeru klastra, na którym znajduje się Twój hosting, sprawdź stronę ["Lista adresów IP klastrów i hostingów WWW"](../lista-adresow-ip-klastrow-i-hostingow-www/){.external}. Znajdziesz tam adres IP "**bramy wyjściowej**" dla każdego klastra.

> [!warning]
>
> **Adres IP** klastra nie będzie działał, aby zezwolić na połączenie z serwerem Cloud DB. Należy dodać **adres IP "bramy wyjściowej"**.
>


### Zmiana oferty serwera baz danych

Aby zmienić ofertę serwera baz danych, przejdź do Panelu [klienta OVHcloud](https://www.ovh.com/auth/?action=gotomanager&from=https://www.ovh.pl/&ovhSubsidiary=pl){.external}. Kliknij kartę `Web Cloud`, a następnie `Baza danych`{.action} w panelu po lewej stronie. Wybierz nazwę serwera baz danych.
W zakładce **"Informacje ogólne"**, która jest wyświetlana domyślnie, kliknij `...`{.action} po prawej stronie słowa "RAM", a następnie `Zmień ilość pamięci RAM`{.action}, aby przejść do zlecenia zamówienia na tą zmianę.

![clouddb](images/private-sql-order-ram01.png){.thumbnail}

Wybierz żądaną ilość pamięci RAM i kliknij `Dalej`{.action}. Następnie możesz wybrać żądany okres.

> [!primary]
>
> Pozostały czas do obecnego wygaśnięcia zostanie odpowiednio przekalkulowany. Prorata będzie oparta na dacie wygaśnięcia serwera SQL, a nie na dacie złożonego zamówienia.
> 

Po zatwierdzeniu regulaminów zostaniesz przekierowany do zamówienia, abyś mógł uregulować tą zmianę. Zmiana zostanie wykonana w ciągu kilku godzin.

> [!warning]
>
>  Jeśli dysponujesz aktualnie darmowym prywatnym serwerem SQL w ramach oferty hosting Performance - zmiana oferty spowoduje, iż nie będzie on już darmowy.
> 

### Zmiana konfiguracji serwera baz danych

Przejdź do Panelu [klienta OVHcloud](https://www.ovh.com/auth/?action=gotomanager&from=https://www.ovh.pl/&ovhSubsidiary=pl){.external}. Kliknij kartę `Web Cloud`, a następnie `Baza danych`{.action} w panelu po lewej stronie. Wybierz nazwę prywatnego serwera SQL. 

#### Instancja MySQL i MariaDB

- Kliknij kartę `Konfiguracja`.

W polu **"Ogólna konfiguracja MySQL"** znajdziesz konfigurację aktualnie zdefiniowaną dla Twojej bazy danych. Możesz ją zmienić, po czym kliknąć `Zastosuj`{.action}.

![clouddb](images/private-sql-config02.png){.thumbnail}

- **Rozmiar**: Katalog plików tymczasowych. **/dev/shm** odpowiada instancji pamięci RAM. **/tmp** odpowiada instancji dysku twardego.
- **MaxAllowedPacket**: Maksymalny rozmiar pakietów
- **Max_user_connections**: Liczba autoryzowanych jednoczesnych połączeń na użytkownika.
- **Automatycznie**: Definiuje, czy zapytania są automatycznie zatwierdzane (committed) czy nie.
- **Interactive_timeout**: Czas w sekundach, podczas których serwer czeka na działanie w interaktywnym połączeniu przed jego zamknięciem.
- **InnodbBufferPoolSize**: Wybór rozmiaru pamięci buforowej.
- **Maksymalna liczba połączeń:** Liczba autoryzowanych jednoczesnych połączeń do bazy danych.
- **Wait_timeout**: Czas w sekundach, podczas których serwer czeka na działanie w nieinteraktywnym połączeniu przed jego zamknięciem.
- **Event_scheduler** : Umożliwia uruchamianie wykonywania zaprogramowanych zapytań bezpośrednio na serwerze MySQL.
- **sql_mode** : Opcja **sql_mode** wpływa na składnię SQL oraz sprawdzanie poprawności danych przez MySQL lub MariaDB. Dostępny wyłącznie dla MariaDB.

> [!primary]
> Jeśli na Twojej stronie pojawi się błąd wskazujący **"Too many connections"**, jest to spowodowane przekroczeniem liczby jednoczesnych połączeń do Twojej bazy danych.
> Możesz następnie zwiększyć zmienną **"MaxConnections"**, jeśli nie ma już maksymalnej wartości.
>

> [!primary]
>
> <b>Tmpdir</b>: 
> \- /dev/shm: Serwer baz danych przypisze połowę pamięci RAM do tego katalogu, aby uzyskać większą wydajność.
>
> \- /tmp: Serwer przydzieli nielimitowaną przestrzeń dla tego katalogu na dysku twardym. Zalecamy korzystanie z tego katalogu tylko w przypadku sporadycznych, ciężkich operacji.
>

> [!primary]
>
> sql_mode :
> - NO_ENGINE_SUBSTITUTION,NO_AUTO_CREATE_USER : Tryb domyślny dla MariaDB 10.1.
> - STRICT_TRANS_TABLES,ERROR_FOR_DIVISION_BY_ZERO,NO_AUTO_CREATE_USER,NO_ENGINE_SUBSTITUTION : Tryb domyślny dla MariaDB 10.2 i nowszych wersji.
>
> Zalecamy, aby zawsze używać trybu domyślnego, chyba że baza danych została zaktualizowana z wersji mającej inny tryb domyślny niż bieżąca wersja.
>

Wprowadź niezbędne zmiany i kliknij `Zatwierdź`{.action}.

> [!warning]
>
> Każda zmiana wymaga restartu serwera baz danych.
> 

#### Instancja PostgreSQL

Nie można zmienić konfiguracji instancji PostgreSQL. 

Możesz jednak aktywować rozszerzenia Twoich baz danych. W tym celu przejdź do zakładki `Bazy danych`, kliknij ikonę tabeli bazy danych w kolumnie **"Rozszerzenia"**

![clouddb](images/private-sql-config03.png){.thumbnail}

### Zmiana wersji MySQL, PostgreSQL lub MariaDB serwera baz danych

Aby poznać wersję MySQL, PostgreSQL lub MariaDB Twojego serwera baz danych, przejdź do zakładki **"Informacje ogólne"** po wybraniu serwera baz danych.

Aktualna wersja pojawia się w wierszu **"Wersja"**.

Aby zmienić tę wersję, kliknij `Zmień wersję`{.action}.

![clouddb](images/private-sql-config04.png){.thumbnail}


#### **Jak poznać dokładną wersję PostgreSQL, której używam?**

Wprowadź to polecenie w phpPgAdmin klikając na **bazę danych**, sekcja **"SQL"**, a następnie klikając `Uruchom`{.action}:

```
select version();
```

####  **Jak poznać dokładną wersję mySQL lub MariaDB, której używam?**

W tym celu wprowadź komendę w phpMyAdmin, w rubryce **"SQL"**, następnie kliknij `Uruchom`{.action}:

```
show variables jak "version";
```

> [!primary]
>
> - Przed migracją do wyższej wersji upewnij się, że Twoja baza danych jest kompatybilna z wybraną wersją.
> - Zmiana zostanie wykonana w ciągu kilku minut.
>

> [!warning]
>
> Nie można przejść bezpośrednio z najstarszej wersji do najnowszej. Korzystanie z wszystkich wersji pośrednich jest obowiązkowe.
> 

### Logi i metryki

#### Statystyki czasu wykonywania zapytań

Dzięki temu możesz wyświetlić czas wykonywania zapytań na serwerze baz danych w ciągu ostatnich 24 godzin.

Przejdź do Panelu [klienta OVHcloud](https://www.ovh.com/auth/?action=gotomanager&from=https://www.ovh.pl/&ovhSubsidiary=pl){.external}. Kliknij kartę `Web Cloud`, a następnie `Baza danych`{.action} w panelu po lewej stronie. Wybierz nazwę serwera baz danych. 

Przejdź do karty `Metryki` serwera baz danych. Wykres **"Statystyki czasu wykonywania zapytań"**.

![clouddb](images/private-sql-metrics01.png){.thumbnail}

#### Dostęp do logów "Slow Query"

> **Definicja "slow query log"**
> 
> Są to nieoptymalne zapytania, które trwają dłużej. Wartość jest ustawiona na 1 sekundę dla serwerów baz danych w zmiennej **"long_query_time"**.

Logi te, nazywane **"slow-query.log"**, mogą zostać odzyskane z katalogu głównego przestrzeni SFTP Twojego serwera baz danych. 

Przejdź do Panelu [klienta OVHcloud](https://www.ovh.com/auth/?action=gotomanager&from=https://www.ovh.pl/&ovhSubsidiary=pl){.external}. Kliknij kartę `Web Cloud`, a następnie `Baza danych`{.action} w panelu po lewej stronie. Wybierz nazwę serwera baz danych. 

W zakładce `informacje ogólne` sekcja **"SFTP"** w polu **"Informacje o logowaniu"**

![clouddb](images/private-sql-SFTP01.png){.thumbnail}

Aby zalogować się przez **SFTP**, możesz skorzystać z programu Filezilla i z niniejszego przewodnika: [ "Korzystanie z programu FileZilla na Twoim hostingu"]( ../hosting_www_przewodnik_dotyczacy_korzystania_z_programu_filezilla/){.external}.

Jeśli ten plik jest pusty, to znaczy, że nie masz żadnych nieoptymalnych zapytań.


#### Monitoruj zużytą pamięć RAM

Przejdź do Panelu [klienta OVHcloud](https://www.ovh.com/auth/?action=gotomanager&from=https://www.ovh.pl/&ovhSubsidiary=pl){.external}. Kliknij kartę `Web Cloud`, a następnie `Baza danych`{.action} w panelu po lewej stronie. Wybierz nazwę serwera baz danych. 

Przejdź do karty `Metryki` w Panelu klienta. Wykres **"Statystyki pamięci RAM"**.

![clouddb](images/private-sql-metrics02.png){.thumbnail}

#### Monitorowanie liczby połączeń na minutę

Wykres ten pozwala na śledzenie, w ciągu ostatnich 24 godzin, obciążenia połączeń na minutę na serwerze bazy danych.

Przejdź do Panelu [klienta OVHcloud](https://www.ovh.com/auth/?action=gotomanager&from=https://www.ovh.pl/&ovhSubsidiary=pl){.external}. Kliknij kartę `Web Cloud`, a następnie `Baza danych`{.action} w panelu po lewej stronie. Wybierz nazwę serwera baz danych. 

Przejdź do karty `Metryki` w Panelu klienta. Wykres **"Statystyki całkowitej liczby połączeń na minutę"**.

![clouddb](images/private-sql-metrics03.png){.thumbnail}

### Optymalizacja bazy danych

 Zalecamy optymalizację bazy danych w celu zapewnienia jej wysokiej wydajności. Wydajność polega na tym, że informacje zawarte w bazie danych są zwracane do skryptu, który je wzywa. Wymaga to ustrukturyzowanej i zoptymalizowanej bazy danych.

#### **Indeksowanie bazy danych**

Aby przyspieszyć wyszukiwanie podczas zapytania, należy dodać indeks do pól używanych w klauzulach WHERE.

Przykład: regularnie wyszukujesz osób w danym mieście. Zaindeksuj pole "miasto" za pomocą następującego zapytania:

```bash
ALTER TABLE `test` ADD INDEX ( `miasto` );
```
#### **Czyszczenie bazy danych**

Niektóre z Twoich danych nie są już dostępne? Poprzez ich archiwizację, Twoje tabele będą mniej wypełnione, a wyszukiwania będą trwały krócej.

#### **Ograniczenie wyświetlania**

Ogranicz wyświetlanie rekordów do ustalonej liczby (np. 10 na stronę), korzystając z limitowanej części zapytania SQL.

#### **Łączenie zapytań**

Zbierz wszystkie zapytania na początku skryptu w poniższy sposób:

```bash
connexion_base
zapytanie1
zapytanie2
...
odłączenie_bazy
Wyświetlanie
Przetwarzanie danych
Boucles ...
Wyświetlanie
...
```
#### **Pobieranie tylko użytecznych danych**

W zapytaniach SQL sprawdź, czy wybierasz tylko to, czego potrzebujesz, a przede wszystkim czy pamiętasz o połączeniach między tabelami.

Przykład:

```bash
(where table1.pole = tabela2.pole2)
```

#### **Unikanie opcji zużywających zbyt dużo zasobów**

Unikanie na przykład stosowania **"HAVING"**. Zwiększa to liczbę twoich zapytań. Podobnie należy unikać korzystania z **"GROUP BY"**, chyba że jest to bezwzględnie konieczne.

## Sprawdź również

[Lista adresów IP klastrów i hostingów](../lista-adresow-ip-klastrow-i-hostingow-www/){.external}

Dołącz do społeczności naszych użytkowników na stronie <https://community.ovh.com>.
