# 22491a4491
import pandas as pd
import matplotlib.pyplot as plt

lr=pd.read_csv("/content/energy.csv")
print(lr)

srh=lr[lr['State']=='Andhra']
rcb=lr[lr['State']=='Karnataka']

fig,diag=plt.subplots(2)
diag[0].plot(srh['Date'],srh['Consumption'])
diag[1].plot(rcb['Date'],rcb['Consumption'])


srh=lr[lr['State']=='Telengana']
rcb=lr[lr['State']=='Tripura']

fig,diag=plt.subplots(2)
diag[0].bar(srh['Date'],srh['Consumption'],color='red')
diag[1].bar(rcb['Date'],rcb['Consumption'],color='green')


csds='Kerala'
cse='Delhi'
ece=[csds,cse]

# Calculate total consumptions separately and store in a list
tdp = [
    lr[lr['State']=='Kerala']['Consumption'].sum(),
    lr[lr['State']=='Delhi']['Consumption'].sum()
]

fig,diag=plt.subplots(1) # Create a single subplot for the pie chart
diag.pie(tdp,labels=ece,autopct='%1.1f%%') # Use the list of total consumptions

plt.show() # Display the charts
