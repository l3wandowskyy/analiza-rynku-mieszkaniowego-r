# Analiza rynku mieszkaniowego w Polsce (R)

> Analiza ofert sprzedaży mieszkań w 15 największych miastach Polski na podstawie danych z sierpnia 2023 roku.  
> Projekt zrealizowany w języku **R** z wykorzystaniem publicznie dostępnych danych z Kaggle.

---

## Cel projektu

Celem głównym projektu była **analiza struktury ofert sprzedaży mieszkań w Polsce** w sierpniu 2023 roku,  
ze szczególnym uwzględnieniem różnic pomiędzy 15 największymi miastami.

---

## Pytania badawcze

1. Jak kształtują się podstawowe cechy ofert sprzedaży mieszkań w Polsce?  
2. Które miasta w Polsce charakteryzują się najwyższą średnią ceną za m²?  
3. Czy typ budynku ma wpływ na cenę za m² mieszkania?  
4. Czy istnieje zależność między ceną mieszkania a jego odległością od centrum miasta?  
5. Czy liczba punktów POI (Point of Interest) w pobliżu mieszkania wpływa na jego cenę?  
6. Które punkty POI (np. szkoła, restauracja, apteka) mają największą korelację z ceną za m²?  
7. Jak przedstawia się przestrzenny rozkład cen mieszkań na terenie Poznania?

---

## Zakres danych

Dane pochodzą z repozytorium **Kaggle**:  
**Apartment Prices in Poland (Pricing of apartments in 15 largest Polish cities)**  
Autor: *Krzysztof Jamroz*  
Data pobrania: 24.06.2025  
[Link do zbioru danych](https://www.kaggle.com/datasets/krzysztofjamroz/apartment-prices-inpoland)

Zbiór obejmuje dane z sierpnia 2023 r. dla 15 największych miast Polski:  
Warszawa, Łódź, Kraków, Wrocław, Poznań, Gdańsk, Szczecin, Bydgoszcz, Lublin, Katowice, Białystok, Częstochowa, Gdynia, Rzeszów, Toruń.

---

## Opis danych

Dane zawierają informacje m.in. o:
- cenie (`Price`), powierzchni (`SquareMeters`), liczbie pokoi (`Rooms`),  
- typie budynku (`Type`), piętrze (`Floor`), roku budowy (`buildYear`),  
- współrzędnych (`Latitude`, `Longitude`),  
- odległości od centrum (`centreDistance`),  
- liczbie punktów POI (`poiCount`) i ich typach,  
- udogodnieniach (`HasBalcony`, `HasParking`, `HasElevator`, `HasSecurity`).

Na potrzeby analizy utworzono zmienne:
- `Price_per_m2` – cena za metr kwadratowy,  
- `Has[poiName]` – binarne zmienne informujące o obecności wybranych punktów POI w promieniu 500 m.

---

## Metody i narzędzia

- **R**, **tidyverse**, **ggplot2**, **dplyr**, **sf**, **readr**  
- Wykorzystane techniki:
  - analiza statystyczna (miary opisowe, korelacje),
  - wizualizacja danych (histogramy, boxploty, mapy cieplne, scatterploty),
  - analiza przestrzenna (mapa ofert mieszkań w Poznaniu),
  - eksploracja zależności między ceną, lokalizacją i punktami POI.

---

## Kluczowe wyniki

- Średnia cena ofertowa: **12 127 zł/m²**, mediana: **11 429 zł/m²**.  
- Najwyższe średnie ceny: **Warszawa (15 612 zł/m²)**, **Kraków (13 583 zł/m²)**, **Gdańsk (13 246 zł/m²)**.  
- Najniższe ceny: **Szczecin (8 049 zł/m²)** i **Białystok (8 421 zł/m²)**.  
- Dominują mieszkania **2- i 3-pokojowe**, o metrażu ok. **50–55 m²**, położone na niskich piętrach.  
- **Typ budynku wpływa na cenę** — najwyższe ceny w apartamentowcach, najniższe w blokach.  
- **Odległość od centrum** nie koreluje istotnie z ceną (r ≈ 0,01).  
- **Liczba POI** wykazuje słabą dodatnią korelację z ceną (r ≈ 0,27).  
- **Obecność konkretnych POI** (np. szkół, uczelni, restauracji) nie ma istotnego wpływu na cenę.  
- W **Poznaniu** najwyższe ceny koncentrują się w centrum i na nowych osiedlach (Łacina, Grunwald).

---

## Zastosowane wizualizacje

- Histogramy i boxploty dla ceny, powierzchni, liczby pokoi i piętra  
- Heatmapa korelacji między ceną a obecnością POI  
- Scatterploty ceny względem odległości i liczby POI  
- Mapa punktowa ofert w Poznaniu z kolorową skalą cen  
- Wykresy porównawcze cen między miastami

---

## Zawartość repozytorium

| Plik / folder | Opis |
|----------------|------|
| `README.md` | Opis projektu i dokumentacja repozytorium |
| `Raport - Analiza ofert sprzedaży mieszkań w 15 największych miastach Polski (sierpień 2023).pdf` | Pełny raport z analizy – szczegółowe wyniki, wizualizacje i wnioski |
| `apartments_analysis.R` | Główny skrypt analizy danych w języku R |
| `apartments_analysis.Rmd` | Skrypt RMarkdown generujący raport PDF |
| `project.Rproj` | Plik projektu RStudio |
| `apartments_pl_2023_08.csv` | Dane źródłowe – oferty sprzedaży mieszkań |
| `city_comparison.csv` | Zestawienie średnich cen za m² między miastami |
| `summary_stats.csv` | Podstawowe statystyki opisowe zmiennych |
| `boxplot_typ_budynku.png` | Wykres pudełkowy – ceny za m² w zależności od typu budynku |
| `heatmap_cena_poi.png` | Mapa cieplna – korelacja ceny z punktami POI |
| `histogram_ceny_za_m2.png` | Histogram rozkładu cen za metr kwadratowy |
| `histogram_powierzchni.png` | Histogram rozkładu powierzchni mieszkań |
| `histogram_liczby_pokoi.png` | Histogram rozkładu liczby pokoi |
| `histogram_pietro.png` | Histogram rozkładu pięter |
| `scatterplot_cena_liczba_poi.png` | Wykres punktowy – zależność między ceną a liczbą POI |
| `scatterplot_cena_odleglosc_centrum.png` | Wykres punktowy – zależność między ceną a odległością od centrum miasta |

---

**Szczegółowa analiza wyników** – wraz z opisem metod, wnioskami i pełnym zestawem wizualizacji –  
została zaprezentowana w raporcie:  
[**Raport – Analiza ofert sprzedaży mieszkań w 15 największych miastach Polski (sierpień 2023)**](https://github.com/l3wandowskyy/analiza-rynku-mieszkaniowego-r/blob/main/Raport%20-%20Analiza%20ofert%20sprzedaży%20mieszkań%20w%2015%20największych%20miastach%20Polski%20(sierpień%202023).pdf)

---

## Licencja

Projekt dostępny na licencji **MIT**.  
Dane wykorzystano wyłącznie w celach edukacyjnych i badawczych.

---

## Autor

**Jakub Lewandowski**  
[jakub.lewandowski865@gmail.com](mailto:jakub.lewandowski865@gmail.com)  
[![GitHub](https://img.shields.io/badge/GitHub-000000?style=flat&logo=github&logoColor=white)](https://github.com/l3wandowskyy)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/jakub-lewandowski-poznań)
