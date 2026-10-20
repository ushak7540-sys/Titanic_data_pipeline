# Titanic Data Preparation Pipeline

Modular Python pipeline that prepares the Titanic dataset for any ML model.

## Steps
1. load_data: load from Seaborn
2. validate_data: check required columns (custom exception)
3. clean_text: normalize text columns
4. drop_useless: drop leaking and duplicate columns
5. handle_missing: median for numeric, mode for categorical
6. encode_categoricals: binary, ordinal and one-hot encoding
7. split_data: stratified 80/20 split
8. scale_features: StandardScaler fit on train only

## Run
pip install pandas seaborn scikit-learn
python titanic_pipeline.py

## Key decisions
- Dropped `alive` to avoid target leakage
- Stratified split keeps the survival ratio equal in train and test
- Scaler fit on train only to avoid data leakage
