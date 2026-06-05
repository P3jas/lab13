# lab13
### Kacper Kozlinski
### 101603

## Czesc Obowiazkowa

### Uzasadnienie przydzialu sieci dla phpMyAdmin
phpMyAdmin zostal podłączony wylacznie do sieci backend, poniewaz musi komunikowac się bezposrednio z kontenerem MySQL, ktory znajduje się w tej sieci. Dostep z zewnątrz jest zapewniony przez zmapowany port 6001, wiec podlczenie do sieci frontend byłoby zbedne.

### Uzyte polecenia
Do realizacji zadanie zostaly wykorzystane 2 polecenia

`docker compose up -d` - do uruchomienia wielokontenerowej aplikacji

wynik polecenia:
![Actions](screenshots/dockerCompose.png)

`docker compose ps` - do sprawdzenia poprawnosci dzialania
![Actions](screenshots/dockerPs.png)

### Dowod dzialania

### LEMP
dowodem dzialanie jest dzialajaca strona localhost:4001 ktora zostala zdefiniowana w pliku html/index.php i zostala wyswietlona funkcja phpinfo()
![Actions](screenshots/przegladarka.png)

### inicjacja testowej bazy danych

baza zostala zainicjalizowana poprawnie widac to na screenie ponizej
![Actions](screenshots/phpMyadmin.png)


## Czesc Nieobowiazkowa

Względem części obowiązkowej hasło roota MySQL zamiast być przechowywane jako zwykła zmienna środowiskowa zostało przeniesione do mechanizmu Docker Secrets. W tym celu został utworzony plik password.txt zawierający hasło. W pliku docker-compose.yml zmieniono MYSQL_ROOT_PASSWORD na MYSQL_ROOT_PASSWORD_FILE oraz dodano sekcję secrets dla serwisów mysql i phpmyadmin.

### Uzyte polecenia

![Actions](screenshots/logi2.png)

### Dowod dzialania

### LEMP
![Actions](screenshots/przegladarka2.png)

### inicjacja testowej bazy danych
By zalogowac sie na ta strone trzeba bylo uzyc hasla zdefiniowanego w pliku password.txt
![Actions](screenshots/bazaDod.png)
