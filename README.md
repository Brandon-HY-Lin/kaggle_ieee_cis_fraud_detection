# kaggle_ieee_cis_fraud_detection
Kaggle contest: IEEE-CIS Fraud Detection


# Common Used APIs:
- Search Digits
  ```re.findall('d+\.d+')```
- Data Manupulation
  - Unique Features
    - pandas.DataFrame.unique()
    
  - Select Multiple Features
    - df_train[['P_emaildomain', 'R_emaildomain']]
  - NAN
    - Select Not Nan
      ```
      train_identity[train_identity['DeviceInfo'].notnull()]['DeviceInfo']
      ```
    - Count With NAN
      - pandas.DataFrame.isnull().sum()
    - Without NAN
      - pandas.Series.dropna()
  - Crosstab
    ```
    pandas.crosstab(df_train[index],
                      df_train['isFraud'])
    ```
      
- Plotting
  - Count Numbers
    - seaborn.countplot(data)
  - Pair Plot
    ```
    seaborn.pairplot(data=df,
                      hue='isFraud',
                      vars=['TransactionDT', 'TransactionAmt'],
                      plot_kws={'alpha':0.2})
    ```
  - Twin Axis
    ```
    ax = sns.countplot(data=df_train, x=index, hue='isFraud')
    new_ax = ax.twinx()
    new_ax.plot(tmp['Fraud'])
    ```
