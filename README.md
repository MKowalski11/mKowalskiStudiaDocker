# mKowalskiStudiaDocker

stronka:            interfejs do obsługi webapi
webApi_2.1:         pliki projektu 2, .NET Core 2.1
webApi_3.1:         webApi, .NET Core 3.1
webApi_3.1 - Copy:  kopia zapasowa webApi

W celu uruchomienia:

Gdy w katalogu WebApi_3.1:

    docker build -t webapi_test .
    docker run --network host --publish 15000:8000 -d --name webapi webapi_test
    
Gdy w katalogu stronka

    docker build -t interfejs:v1 .
    docker run --network host --publish 80:80 -d --name interfejs interfejs:v1
    
Dostęp poprzez adres domyślny maszyny wirtualnej Dockera:

    192.168.99.100               - interfejs
    192.168.99.100:8000/api/...  - dostęp do web api na porcie 8000
    
 
