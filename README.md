# Turbo-Kompres-r
Turbo Kompresör haritası
import numpy as np
import matplotlib.pyplot as plt

# Kompresör parametrelerini oluşturuyoruz
debi = np.linspace(0, 100, 100)  # Debi (m³/s)
basinc = np.linspace(0, 10, 100)  # Basınç (bar)

# Meshgrid ile 2D veri oluşturuyoruz
X, Y = np.meshgrid(debi, basinc)

# Verimlilik hesaplaması (örnek bir model, gerçek değerler veritabanından alınabilir)
# Bu hesaplama tamamen örnek olup, farklı debi ve basınca göre verimliliği simüle eder
Z = np.exp(-(X - 50)**2 / 200) * np.exp(-(Y - 5)**2 / 10)  # Basit bir örnek verimlilik fonksiyonu

# Grafik
plt.figure(figsize=(10, 7))
cp = plt.contourf(X, Y, Z, levels=4, cmap='viridis')  # 4 farklı renk seviyesiyle kontur çizimi
plt.colorbar(cp)  # Renk barı

# Eksen etiketleri ve başlık
plt.title('Kompresör Verimlilik Haritası')
plt.xlabel('Debi (m³/s)')
plt.ylabel('Basınç (bar)')

plt.show()
