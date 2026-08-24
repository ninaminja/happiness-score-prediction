# happiness-score-prediction
predikcija happiness score-a na osnovu informacija iz dataseta
# World Happiness Score Prediction

Projekat rađen za predmet **Veštačka inteligencija**. Cilj je analiza faktora koji utiču na indeks sreće (Happiness Score) u različitim zemljama sveta i predviđanje tog indeksa na osnovu ekonomskih, socijalnih i političkih faktora.

## Dataset

**World Happiness Report 2015** (`2015.csv`) — podaci o indeksu sreće za 158 zemalja, sa faktorima:
- Ekonomski indikatori (BDP po stanovniku)
- Socijalni faktori (porodična podrška, očekivani životni vek)
- Politički faktori (sloboda, korupcija)
- Ostali (velikodušnost, dystopia residual)

Ciljna promenljiva: `Happiness Score`.

## Metodologija

1. **Eksplorativna analiza podataka** — distribucija po regionima, uticaj porodice i slobode na sreću, korelaciona matrica.
2. **Predobrada podataka**:
   - Frequency encoding za `Region`
   - Target encoding za `Country` (prosečan Happiness Score po zemlji)
3. **Modeli mašinskog učenja** (baseline za poređenje):
   - Random Forest Regressor
   - XGBoost Regressor
   - Linear Regression
4. **Neuronska mreža (MLP)** — dodatni model specifičan za predmet VI, sa standardizacijom ulaza i poređenjem performansi sa modelima iz koraka 3.
5. Evaluacija: MSE, MAE, RMSE, R² score, scatter plot stvarnih vs. predviđenih vrednosti.

## Rezultati

Modeli su upoređeni po MSE/MAE/R² metrikama; Random Forest i XGBoost daju najbolje rezultate, dok MLP služi kao poređenje sa klasičnim tehnikama veštačke inteligencije. Detalji u notebook-u.

## Struktura repozitorijuma

```
├── 2015.csv
├── projectAi.ipynb
├── requirements2.txt
└── README.md
```

## Pokretanje

```bash
pip install -r requirements.txt
jupyter notebook projectAi.ipynb
```

## Korišćene biblioteke

pandas, numpy, matplotlib, seaborn, scikit-learn, statsmodels, xgboost, pydot

## Moguća proširenja

- Genetski algoritam za feature selection ili tuning hiperparametara
- Vremenska analiza kroz World Happiness Report 2015–2023
- Feature importance i SHAP objašnjivost modela
- Klasterovanje zemalja (K-Means) po profilu sreće
