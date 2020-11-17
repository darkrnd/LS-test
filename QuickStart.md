# Установка Label Studio, руководствуясь разделом [Quickstart](https://labelstud.io/guide/#Quickstart)

Operating System: Windows 10 Home 64-bit (10.0, Build 19041) (19041.vb_release.191206-1406)
Screen Resolution: 1920x1080 
Label Studio Version: 0.8.0.post0-py3


1.  Попытка установки, используя последнюю доступную версию Python 3.9.0 (на момент 17.11.2020)(Неудачно)
    
* По указанной в [https://labelstud.io/guide/#Prerequisites](https://labelstud.io/guide/#Prerequisites) ссылке [(https://www.lfd.uci.edu/~gohlke/pythonlibs/#lxml)](https://www.lfd.uci.edu/~gohlke/pythonlibs/#lxml)) был скачан пакет lxml‑4.6.1‑cp39‑cp39‑win_amd64.whl
	```
	pip install lxml‑4.6.1‑cp39‑cp39‑win_amd64.whl
	pip install label-studio
	```

![](https://lh4.googleusercontent.com/VGnPlKOtTRnGqSmbaN4epYKsYVnId07UkLd29155Nr0W2SZrkieZ2f6jr6mUteyryo5gmHbBafoetSYQH4wLk0KbdbPNdnHCoSmSCr4QJEwt9afn1XTkcVXXqjlePSdvtYhGUTgy)

  

* Требует Microsoft Visual C++ 14.0  
* Было бы неплохо указать в инструкции данное требование и разместить ссылку.
* По ссылке, указанной в ошибке найти именно Build Tools, а не весь Visual Studio оказалось неочевидным, пришлось искать решение в Google.
* Установщик был взят с [https://visualstudio.microsoft.com/visual-cpp-build-tools/](https://visualstudio.microsoft.com/visual-cpp-build-tools/)
* При установке пакет требует выбрать необходимый состав, что на первый взгляд
* выглядит непросто:

![](https://lh6.googleusercontent.com/p3VtUVtdD2sp-l-vwJph8DsWjl7kbx6LjfJhzsmemO2zP3shtPNrStoxk2Z7bMDqUriT2caKSS-zwpthiqGyvMxDYsnHiiTazicRuEA8FGiXXzVsbiVmLJm0h7g6fPx-Yn-Xh8ym)

* Установил только Build Tools, оставив все галочки по умолчанию. Стоит отметить, что необходимое пространство - около 6.5 Гб (не много, но и не мало).
	```
	pip install label-studio
	```

* На выходе множественные ошибки, невозможность собрать Pillow
	```
	python -m pip install --upgrade pip
	python -m pip install --upgrade Pillow
	pip install label-studio
	```
  
	```
	Building wheel for blis (setup.py) ... error
	ERROR: Command errored out with exit status 1

	...

	Building wheel for cymem (setup.py) ... error
	ERROR: Command errored out with exit status 1:
	...
	Building wheel for Pillow (setup.py) ... error
	ERROR: Command errored out with exit status 1:
	```

* Поиски решения проблемы в Google не принесли результатов. Установка разных версий библиотек так же не принесла результатов.

* Установка всегда падала. Пришел к выводу, что Label Studio требуются более старые версии библиотек, установка которых уже невозможна на Python, версии 3.9
