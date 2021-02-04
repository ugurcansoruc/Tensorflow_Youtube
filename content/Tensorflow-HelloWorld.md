# Tensorflow - "Hello World" #1

İnsanlar adına görevleri gerçekleştirmek için bilgisayarı kullanmak söz konusu olduğunda, bilgisayara her zaman bir bilgisayar programı şeklinde talimatlar vermeliyiz. Çoğu programlama çerçevesi, ana görevi birleştirilebilir problemlere ayırmakla ilgilidir.

Geleneksel programlama dilleri genellikle veri ve (iş veya çözüm) kurallarını girdi olarak alır ve cevapları çıktı olarak bulmak için kuralları verilere uygular.

Öte yandan, makine öğrenimi paradigmasında, veriler ve cevaplar (veya etiketler) girdi olarak girer ve öğrenilen kurallar (modeller) çıktı olarak ortaya çıkar. Makine öğrenimi paradigması benzersiz bir şekilde değerlidir, çünkü bilgisayarın karmaşık ve çok boyutlu uzayda yeni kurallar öğrenmesine izin verir.

![traditional_programming](https://github.com/ugurcansoruc/Tensorflow_Youtube/blob/master/images/traditional_programming.png)

Şimdi geleneksel programlama ve makine öğrenmi arasındaki farkı daha iyi anlayabileceğimiz ve makine öğrenimine bir giriş yapabileceğimiz hello_world uygulumamızı gerçekleştirelim.

```python
#Kutuphanelerin import edilmesi

import tensorflow as tf
from tensorflow import keras
import numpy as np
```

Geleneksel programlama mantığı ile ilgili örnek bir yapı.

```python
xs = np.array([1,2,3,4,5])

def function(x):
    return 2 * x + 1

print(function(xs))
```

Geleneksel programlama mantığı ile oluşturulmuş örneğin makine öğrenimine uyarlanması, modelin oluşturulması ve tahminlerin yapılması.

```python
xs = np.array([1,2,3,4,5])
xy = np.array([3,5,7,9,11])

model = tf.keras.Sequential([
    keras.layers.Dense(1,input_shape=[xs.ndim])
])

model.compile(loss=tf.losses.mean_squared_error, optimizer=tf.optimizers.SGD())
history = model.fit(xs, xy, epochs=1000)

prediction = model.predict(np.array([23, 43, 19]))
print(prediction)

print(function(np.array([23, 43, 19])))
```
> Notebook dosyasına [Tensorflow-HelloWorld.ipynb](https://github.com/ugurcansoruc/Tensorflow_Youtube/blob/master/notebooks/Tensorflow-HelloWorld.ipynb) bağlantısı üzerinden ulaşabilirsiniz.
