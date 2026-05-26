# Wielowymiarowa Analiza Danych – Hurtownia Sprzedaży (OLAP & Data Mining)

Projekt zrealizowany w ramach zaliczenia przedmiotu **Wielowymiarowa analiza danych**. Obejmuje on pełny proces budowy analitycznego środowiska bazodanowego: od implementacji wielowymiarowej kostki OLAP, poprzez zastosowanie algorytmów eksploracji danych (Data Mining), aż po interaktywną wizualizację wyników w środowisku Power BI.
---

## 🛠 Wykorzystane technologie

* **Silnik bazodanowy:** Microsoft SQL Server
* **Przetwarzanie analityczne (OLAP) i Data Mining:** SQL Server Analysis Services (SSAS Multidimensional)
* **Raportowanie i wizualizacja AI:** Power BI
* **Języki zapytań:** SQL, MDX (Multidimensional Expressions)

---

## 🏗 Struktura projektu i zrealizowane zadania

### 1. Wielowymiarowa Kostka OLAP
Zaprojektowano zoptymalizowaną kostkę analityczną opartą na schemacie gwiazdy (centralna tabela faktów `fact_Sales` otoczona tabelami wymiarów `dim_Location`, `dim_Item`).
* Wdrożono mechanizmy pre-agregacji danych w celu przyspieszenia zapytań.
* Zdefiniowano autorskie miary obliczeniowe w języku MDX (m.in. *Marża Zysku*, *Średnia Wartość Zamówienia*, *Średni Zysk z Transakcji*).
* Utworzono hierarchie nawigacyjne dla wymiarów pozwalające na operacje Drill-down oraz Roll-up.

### 2. Eksploracja Danych (Data Mining w SSAS)
W ramach analizy zaawansowanej (Predictive & Prescriptive Analytics) przetrenowano cztery modele uczenia maszynowego:
* **Microsoft Decision Trees:** Identyfikacja kluczowych atrybutów (np. kategoria produktu) bezpośrednio warunkujących końcową wartość generowanego zysku. Podział zbioru na uczący (70%) i testowy (30%).
* **Microsoft Time Series (Szeregi Czasowe):** Predykcja finansowa przyszłych przychodów. Wygenerowanie prognozy na 5 kolejnych okresów w oparciu o analizę historycznych wzorców w modelu regresyjnym (ARTXP).
* **Microsoft Clustering:** Nienadzorowana segmentacja danych. Autonomiczne pogrupowanie lokalizacji geograficznych w klastry na podstawie podobieństwa parametrów marżowych i wolumenowych.
* **Microsoft Naive Bayes:** Modelowanie probabilistyczne zależności między atrybutami dyskretnymi w celu wykrycia najsilniejszych powiązań rynkowych.

### 3. Wizualizacja kognitywna w Power BI
Kostka OLAP została podłączona do narzędzia Power BI w trybie *Live Connection*. Na dedykowanym pulpicie analitycznym zaimplementowano interaktywne wizualizacje wykorzystujące silniki sztucznej inteligencji:
* **Key Influencers (Kluczowe czynniki wpływające):** Zautomatyzowana detekcja asortymentu najbardziej stymulującego rentowność (np. przewaga kategorii *Household* i *Cosmetics*).
* **Decomposition Tree (Drzewo Dekompozycji):** Interaktywne rozbicie zagregowanej wartości całkowitego zysku w podziale na kanały dystrybucji (Online vs. Offline) oraz zyskowność poszczególnych rynków geograficznych.

---

## ⚙️ Uruchomienie lokalne

1. Odtwórz główną bazę danych (hurtownię) na lokalnej instancji **MS SQL Server**.
2. Otwórz projekt w **Visual Studio** (wymagane rozszerzenie SQL Server Data Tools).
3. Zaktualizuj poświadczenia w widoku *Data Source* do swojej instancji serwera.
4. Wykonaj operację **Deploy** oraz **Process Full** dla struktury kostki i modeli wydobywania danych na lokalny serwer SSAS.
5. Otwórz plik raportu w **Power BI Desktop** i odśwież połączenie z kostką OLAP.

**Autorzy projektu:** 
Paweł Górski
Mateusz Gałda
