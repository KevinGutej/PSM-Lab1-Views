# Zadanie 8. Porównanie obu podejść

## Tabela porównawcza

| Zagadnienie | Jetpack Compose (Kotlin) | Views (Java + XML) |
| :--- | :--- | :--- |
| **Opis interfejsu** | kod Kotlina, funkcje `@Composable` | plik XML + kod aktywności |
| **Liczba edytowanych plików** | **2** (`MainActivity.kt`, `strings.xml`) | **4** (`build.gradle.kts`, `activity_main.xml`, `strings.xml`, `MainActivity.java`) |
| **Czas kompilacji (pierwsze / kolejne)** | ok. 7 sekund / 2 sekundy | ok. 7 sekund / 2 sekundy |
| **Dostęp do kontrolek** | niepotrzebny - stan steruje widokiem | View Binding (dawniej `findViewById`) |
| **Ukrywanie elementu** | element nie powstaje (`if`) | atrybut `visibility: invisible / gone` |
| **Podgląd interfejsu** | `@Preview` w IDE | edytor układu (Design / Split) |
| **Reakcja na zmianę danych** | automatyczna rekompozycja | ręczna aktualizacja kontrolek |
| **Czytelność kodu** | Bardzo wysoka – cała logika, stan i wygląd zamknięte w jednym pliku Kotlina | Średnia – rozproszenie kodu pomiędzy pliki XML i klasę w Javie |

## Obserwacje i wniosek

W podejściu Views konieczna była edycja 4 plików (`build.gradle.kts` do włączenia ViewBinding, układu XML, `strings.xml` oraz `MainActivity.java`), podczas gdy w Jetpack Compose cały interfejs wraz z logiką zamknął się w 2 plikach (`MainActivity.kt` i `strings.xml`), przy niemal identycznym czasie kompilacji dla obu wariantów.

**Wniosek:** Podejście **Jetpack Compose** okazało się znacznie czytelniejsze, ponieważ pozwala deklaratywnie opisać cały interfejs użytkownika wraz z jego stanem i logiką w jednym pliku w języku Kotlin, eliminując potrzebę rozpraszania kodu na pliki XML oraz ręcznej manipulacji widokami za pomocą ViewBinding.
