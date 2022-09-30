# View data as an image

Use `imshow` to view your data as a 2-D image.

```python
import numpy as np
import matplotlib.pyplot as plt
%matplotlib inline  # for jupyter notebook

tmp = np.random.rand(3, 2)
print(tmp)
plt.imshow(tmp)

#   [[0.01424035 0.67437124]
#    [0.26121813 0.68051496]
#    [0.55202248 0.49235785]]
```

<img src='https://user-images.githubusercontent.com/67592868/193312379-f762c5c0-5cfd-46a0-a1c6-cca684715967.png' alt='Data shown as 2-D image' width='300' height='300'>

