# Convert old legacy system balances ending with '-' to negative values

Here's a way to convert a figure from an old legacy file (ex. 5,009-) 

`import pandas as pd`

`mask = df['Amount'].str.endswith('-')`

`df.loc[mask, 'Amount'] = '-' + df.loc[mask, 'Amount'].str[:-1]`

`df['Amount']=df['Amount'].str.replace(',','')`

`df['Amount']=df['Amount'].astype(float)`

Output:
`-5009`