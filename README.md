# EDA-on-stock-marketing-adaniports-
sns.histplot(df.Trades, log_scale=True)
Trades_count=df.Trades.value_counts()
len(Trades_count)
high_trades=df.Trades[df.Trades>=70000]
low_trades=df.Trades[df.Trades<10000]
len(high_trades)/len(Trades_count)
len(low_trades)/len(Trades_count)

#visualization of turnover of the company

sns.histplot(df.Turnover, log_scale=True)
highest_turnover=df.Trades.max()
highest_turnover
lowest_turnover=df.Trades.min()
lowest_turnover
df['Date'] = pd.to_datetime(df['Date'])
df['Month'] = df['Date'].dt.month
df['Year'] = df['Date'].dt.year
df['Weekdays'] = df['Date'].dt.dayofweek
df['Months'] = df['Date'].dt.strftime('%b')
sns.histplot(df.Months, bins=12, kde=False)

#volumes vs years chart

sns.barplot(df.Year,df.Volume)

#volumes vs months chart

sns.barplot(df.Months,df.Volume)

#Trades vs years chart

sns.barplot(df.Year,df.Trades)

#Trades vs months chart

sns.barplot(df.Months,df.Trades)

#Trades vs weekdays chart

sns.barplot(df.Weekdays,df.Trades)
#highest opening price of day over year analysis
sns.barplot(df.Year,df.High)
#lowest opening price of day over year analysis
sns.barplot(df.Year,df.Low)
