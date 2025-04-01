# api-cli-fetche
zadanie 2 z dnia 01.04.2025 z zajęć Narzędzia Programistyczne
@ -1,2 +1,75 @@
# api-cli-fetche
zadanie 2 z dnia 01.04.2025 z zajęć Narzędzia Programistyczne
 # api-cli-fetcher

## Opis projektu
**api-cli-fetcher** to narzędzie wiersza poleceń (CLI), które pobiera dane z podanego API i zapisuje je do pliku JSON. Aplikacja umożliwia szybkie i łatwe pobieranie danych z różnych źródeł internetowych oraz ich przechowywanie lokalnie. Projekt został zaprojektowany z myślą o elastyczności i możliwościach rozbudowy.

## Instalacja
Aby korzystać z aplikacji, wykonaj następujące kroki:

### Wymagania
- Python 3.7+
- Moduł `requests` (można zainstalować za pomocą `pip`)

### Instalacja
1. Sklonuj repozytorium:
   ```sh
   git clone https://github.com/xBestia2004/api-cli-fetcher.git
   cd api-cli-fetcher
   ```
2. Zainstaluj wymagane zależności:
   ```sh
   pip install -r requirements.txt
   ```
3. Nadaj plikowi wykonywalnemu uprawnienia (opcjonalnie, dla systemów Unix):
   ```sh
   chmod +x cli_fetcher.py
   ```

## Sposób uruchomienia
Aby pobrać dane z API i zapisać je do pliku JSON, użyj następującej komendy:

```sh
python cli_fetcher.py --fetch --url https://api.example.com/data --output data.json
```

### Przykłady komend
- Pobranie danych z API i zapisanie ich do pliku `data.json`:
  ```sh
  python cli_fetcher.py --fetch --url https://api.example.com/data --output data.json
  ```
- Pobranie danych i zapisanie ich do domyślnego pliku (`output.json`):
  ```sh
  python cli_fetcher.py --fetch --url https://api.example.com/data
  ```
- Wyświetlenie pomocy:
  ```sh
  python cli_fetcher.py --help
  ```

## Rozszerzanie aplikacji
Aplikacja została zaprojektowana w sposób umożliwiający łatwe dodawanie nowych źródeł danych. Aby dodać obsługę nowych typów API lub zmienić sposób przetwarzania danych:

1. Otwórz plik `cli_fetcher.py`.
2. Dodaj nową funkcję do obsługi dodatkowego formatu danych lub nowego API.
3. Zmodyfikuj obsługę argumentów CLI, aby uwzględniała nowe opcje.
4. Przetestuj działanie i upewnij się, że aplikacja działa zgodnie z oczekiwaniami.

Przykładowy fragment kodu do obsługi nowego formatu:
```python
import requests
import json

def fetch_data(url):
    response = requests.get(url)
    return response.json()

def save_to_file(data, filename="output.json"):
    with open(filename, "w") as f:
        json.dump(data, f, indent=4)
```

## Licencja
Ten projekt jest dostępny na licencji MIT.
