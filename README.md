import pandas as pd
import numpy as np
import datetime as dt
import matplotlib.pyplot as plt


planea = pd.read_csv('fplanea.csv')

#print(planea.dtypes)


 print('planea-  mexico - Año: 2000 al 2019')
border = planea["calificar"] == "mexico"
fecha = fronteras["Date"].dt.strftime("%Y").isin(["2000","2001","2002","2003","2004","2005","2006","2007","2008","2009","2010","2011","2012","2013","2014","2015","2016","2017","2018","2019"])
brow = planea["mexico"] == "calificaciones"
ejer1 = fronteras[border & fecha & brow]
print(ejer1)

desejer1 = ejer1.describe()
print(desejer1)

#eje x, detalle del paso del tiempo 
x=ejer1['Date']
#eje y, valores
y=ejer1['Value']
#Función para graficar en línea
plt.plot(x,y)
#plt.show()

#Se guarda la grafica como imagen con formato png, pero si se desea guardar
#se debe comentar plot.show()
plt.savefig('fugure.png'
