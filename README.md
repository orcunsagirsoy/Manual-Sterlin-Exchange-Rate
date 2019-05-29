# Manual-Sterlin-Exchange-Rate
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
raw_data = {'Banka': ['Akbank', 'Denizbank', 'QNB Finansbank', 'HSBC', 'İs Bankasi','Merkez Bankasi','Sekerbank','Vakifbank','Yapikredi'], 
        'Alis': [7.6379,7.5499,7.5707,7.6107,7.5961,7.5923,7.5995,7.6009,7.5930], 
        'Satis': [7.6420, 7.6705, 7.6772, 7.6324, 7.6570,7.6319,7.6449,7.6589,7.6537]}

df = pd.DataFrame(raw_data, columns = ['Banka', 'Alis', 'Satis'])



Alis = raw_data['Alis']
Satis = raw_data['Satis']
Banka = raw_data['Banka']
Colors = ['red','blue','yellow','pink','cyan','green','orange','brown','black']
plt.xlabel('Alış')
plt.ylabel('Satış')
plt.title('Bankaların Sterlin Kuru')
plt.tight_layout()

for i, type in enumerate(Banka):
    x = Alis[i]
    y = Satis[i]
    plt.scatter(x, y, marker='o', color=Colors[i])
    plt.text(x+0.001, y-0.002, type, fontsize=8)
