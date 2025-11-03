# Interaktív Alkalmazások Python Segítségével

## Áttekintés

A projekt egy oktatási segédanyag, ami egy alkalmazás iteratív felépítésén keresztül mutatja be a Plotly Dash Python keretrendszert és a működését. Az alkalmazások a Világbank szegénységi és egyenlőségi adatbázisát használják, különböző interaktív diagramokat, térképeket és analitikai eszközöket demonstrálva.

## Követelmények

### Python verzió
- Python 3.12 vagy újabb

### Függőségek
A projekt a következő fő könyvtárakat használja:
- `dash>=2.18.1` - Webes alkalmazás keretrendszer
- `dash-bootstrap-components>=1.6.0` - Bootstrap komponensek Dash-hez
- `plotly>=5.24.1` - Interaktív diagramok
- `pandas>=2.2.2` - Adatkezelés
- `pandas-datareader>=0.10.0` - Adatok letöltése külső forrásokból
- `scikit-learn>=1.5.2` - Gépi tanulási algoritmusok
- `numpy>=2.1.1` - Numerikus számítások

A teljes függőségi lista a `requirements.txt` fájlban található.

## Telepítés

### 1. Anaconda környezet létrehozása
```bash
conda create --name dash python=3.12
conda activate dash
```

### 2. Repository klónozása
```bash
git clone https://github.com/basictask/Adatbanyaszat.git
cd Adatbanyaszat
```

### 3. Függőségek telepítése
```bash
pip install -r requirements.txt
```

## Alkalmazás Verziók

A projekt több verzióban érhető el, amelyek fokozatosan bővülő funkcionalitást kínálnak:

### Alapvető Verziók (v1.x)

- **app_v1_1.py** - Egyszerű "Hello, World!" alkalmazás
- **app_v1_2.py** - HTML komponensek hozzáadása
- **app_v1_3.py** - Témák használata (Bootstrap)
- **app_v1_4.py** - Bootstrap komponensek (Tabs)
- **app_v1_5.py** - Első callback függvény implementálása

### Diagramok (v2.x)

- **app_v2_1.py** - Plotly diagramok integrálása
- **app_v2_2.py** - Gini index vizualizáció
- **app_v2_3.py** - Komponensek újrafelhasználása
- **app_v2_4.py** - Jövedelmi megoszlás diagramok
- **app_v2_5.py** - Teljes alkalmazás finomított megjelenéssel

### Pontdiagramok és Térképek (v3.x)

- **app_v3_1.py** - Szegénységi szintek csúszkákkal
- **app_v3_2.py** - Teljes alkalmazás pontdiagramokkal
- **app_v3_3.py** - Tematikus térképek és Markdown komponensek

### Gyakorisági Adatok és Klaszterezés (v4.x)

- **app_v4_1.py** - Hisztogramok hozzáadása
- **app_v4_2.py** - K-közép klaszterezés implementálása

## Alkalmazás Futtatása

### Egyszerű futtatás
```bash
python app_v4_2.py
```

### Debug módban
```bash
# A debug mód alapértelmezetten be van kapcsolva
# Az alkalmazás elérhető lesz: http://127.0.0.1:8050/
```

## Főbb Funkciók

### 1. Adatvizualizáció
- **Oszlopdiagramok**: Legnépesebb országok megjelenítése
- **Vonaldiagramok**: Időbeli változások követése
- **Pontdiagramok**: Szegénységi szintek összehasonlítása
- **Hisztogramok**: Indikátorok eloszlásának vizsgálata

### 2. Tematikus Térképek
- Világbank adatok térképes megjelenítése
- Különböző projekciók támogatása
- Animációs réteg időbeli változásokhoz
- Interaktív hover információk

### 3. Interaktív Komponensek
- **Dropdown menük**: Ország és indikátor kiválasztás
- **Csúszkák**: Év és paraméter beállítás
- **Rádiógombok**: Adatkészlet kiválasztás
- **Tartomány csúszkák**: Időintervallum kiválasztás

### 4. Gépi Tanulás
- **K-közép klaszterezés**: Országok csoportosítása indikátorok alapján
- **Adatelőkészítés**: Hiányzó értékek kezelése, standardizálás
- **Vizualizáció**: Klaszterek megjelenítése térképen

### 5. Adattárolás
- **Session Storage**: Adatok ideiglenes tárolása
- **Interval Components**: Automatikus adatfrissítés
- **Store Components**: Kliens oldali adatkezelés

## Projekt Struktúra
```
├── requirements.txt           # Python függőségek
├── data/                      # Adatfájlok
├── doc/                       # Dokumentáció és források
│   ├── graphs/                # Generált grafikonok
│   └── images/                # Képek és ábrák
├── src/                       # Forráskód
│   └── code/                  # Programfájlok
└── tasks/                     # Feladatok és tesztek
```

## Használt Technológiák

### Frontend
- **Dash**: Python-alapú webes keretrendszer
- **Plotly**: Interaktív diagramkészítés
- **Bootstrap**: Reszponzív dizájn
- **HTML/CSS**: Alapvető megjelenés

### Backend
- **Flask**: Mikrokeretrendszer (Dash alatt)
- **Pandas**: Adatmanipuláció
- **NumPy**: Numerikus műveletek
- **Scikit-learn**: Gépi tanulás

### Adatforrások
- **Világbank API**: Élő adatok letöltése
- **CSV fájlok**: Helyi adattárolás

## Főbb Komponensek

### Dash Core Components
- `dcc.Dropdown`: Legördülő menük
- `dcc.Slider`: Csúszkák
- `dcc.Graph`: Diagramok
- `dcc.Markdown`: Markdown tartalom
- `dcc.Store`: Adattárolás
- `dcc.Interval`: Időzített frissítés

### Dash HTML Components
- `html.Div`: Konténerek
- `html.H1, H2`: Címsorok
- `html.Br`: Sortörés
- `html.Hr`: Vízszintes vonal

### Dash Bootstrap Components
- `dbc.Row, Col`: Rács elrendezés
- `dbc.Tabs, Tab`: Fülek
- `dbc.Label`: Címkék
- `dbc.Alert`: Értesítések

## Callback Függvények

A callback függvények az alkalmazás interaktivitásának alapját képezik:
```python
@app.callback(
    Output('component_id', 'property'),
    Input('trigger_component', 'property'),
    State('state_component', 'property')
)
def update_function(input_value, state_value):
    # Logika
    return output_value
```

## Stílusok és Témák

### Használt Témák
- `BOOTSTRAP`: Alapértelmezett Bootstrap téma
- `COSMO`: Modern, világos téma
- `SOLAR`: Sötét téma

### Színsémák
- **Cividis**: Folytonos színskála
- **Qualitative.T10**: Diszkrét színek klaszterezéshez
- **Sequential**: Szekvenciális színsémák

## Adatfeldolgozás

### Transzformációk
1. **Hiányzó értékek kezelése**: SimpleImputer (átlag stratégia)
2. **Standardizálás**: StandardScaler (z-score normalizálás)
3. **Szűrés**: Pandas query műveletek
4. **Aggregálás**: GroupBy műveletek

### K-közép Klaszterezés
```python
from sklearn.cluster import KMeans

kmeans = KMeans(n_clusters=5, random_state=42)
kmeans.fit(scaled_data)
labels = kmeans.labels_
```

## Hasznos Tippek

### Debug Mód
A debug mód automatikus újratöltést biztosít kódváltozások esetén:
```python
app.run_server(debug=True)
```

### Vizuális Debugger
A Dash beépített vizuális debugger eszköze segít a callback függvények nyomon követésében.

### Teljesítmény Optimalizálás
- Használj `PreventUpdate` kivételt, ha nincs szükség frissítésre
- Minimalizáld a callback függvények számát
- Használj `State` paramétereket, ahol lehetséges

## Gyakori Problémák

### Portfoglalás
Ha a 8050-es port foglalt:
```python
app.run_server(debug=True, port=8051)
```

### Adatbetöltési Hibák
Győződj meg róla, hogy az adatfájlok a megfelelő mappában vannak:
```python
current_dir = os.path.dirname(os.path.abspath(__file__))
poverty = pd.read_csv(os.path.join(current_dir, '../../data/poverty.csv'))
```

## Továbbfejlesztési Lehetőségek

1. **Több gépi tanulási algoritmus**: PCA, hierarchikus klaszterezés
2. **Felhasználói autentikáció**: Bejelentkezés, szerepkörök
3. **Adatbázis integráció**: PostgreSQL, MongoDB
4. **Export funkciók**: PDF, Excel exportálás
5. **Real-time adatok**: WebSocket kapcsolatok
6. **Mobiloptimalizálás**: Reszponzív dizájn fejlesztése

## Licenc

Ez a projekt oktatási célokat szolgál. Az adatok a Világbank tulajdonában vannak.

## Kapcsolat

- **GitHub Repository**: [https://github.com/basictask/Adatbanyaszat](https://github.com/basictask/Adatbanyaszat)
- **Világbank Adatok**: [https://datacatalog.worldbank.org/dataset/poverty-and-equity-database](https://datacatalog.worldbank.org/dataset/poverty-and-equity-database)

