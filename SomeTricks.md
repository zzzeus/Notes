## 1.play Sound in Jupyter

```python
from IPython.display import Audio
sound_file = './sound/beep.wav'

Audio(sound_file, autoplay=True)
```