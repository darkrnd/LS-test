

# Установка Label Studio, руководствуясь разделом [Quickstart](https://labelstud.io/guide/#Quickstart)

Operating System: Windows 10 Home 64-bit (10.0, Build 19041) (19041.vb_release.191206-1406)  
Screen Resolution: 1920x1080  
Label Studio Version: 0.8.0.post0-py3




1. Попытка установки, используя последнюю доступную версию Python 3.9.0 (на момент 17.11.2020) (Неудачно)
    
* По указанной в [https://labelstud.io/guide/#Prerequisites](https://labelstud.io/guide/#Prerequisites) ссылке [https://www.lfd.uci.edu/~gohlke/pythonlibs/#lxml](https://www.lfd.uci.edu/~gohlke/pythonlibs/#lxml) был скачан пакет lxml‑4.6.1‑cp39‑cp39‑win_amd64.whl
	```
	pip install lxml‑4.6.1‑cp39‑cp39‑win_amd64.whl
	pip install label-studio
	```

![](https://lh4.googleusercontent.com/VGnPlKOtTRnGqSmbaN4epYKsYVnId07UkLd29155Nr0W2SZrkieZ2f6jr6mUteyryo5gmHbBafoetSYQH4wLk0KbdbPNdnHCoSmSCr4QJEwt9afn1XTkcVXXqjlePSdvtYhGUTgy)

  

* Требует Microsoft Visual C++ 14.0  
* Было бы неплохо указать в инструкции данное требование и разместить ссылку.
* По ссылке, указанной в ошибке найти именно Build Tools, а не весь Visual Studio оказалось неочевидным, пришлось искать решение в Google.
* Установщик был взят с [https://visualstudio.microsoft.com/visual-cpp-build-tools/](https://visualstudio.microsoft.com/visual-cpp-build-tools/)
* При установке пакет требует выбрать необходимый состав, что на первый взгляд выглядит непросто:

![](https://lh6.googleusercontent.com/p3VtUVtdD2sp-l-vwJph8DsWjl7kbx6LjfJhzsmemO2zP3shtPNrStoxk2Z7bMDqUriT2caKSS-zwpthiqGyvMxDYsnHiiTazicRuEA8FGiXXzVsbiVmLJm0h7g6fPx-Yn-Xh8ym)

* Установил только Build Tools, оставив все галочки по умолчанию. Стоит отметить, что необходимое пространство - около 6.5 Гб (не много, но и не мало).
	```
	pip install label-studio
	```

* На выходе множественные ошибки, невозможность собрать blis, cymem, Pillow
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

* Установка всегда падала. Пришел к выводу, что Label Studio требуются более старые версии библиотек, установка которых уже невозможна на Python версии 3.9

---

2. Попытка установки, используя версию Python 3.7.9 (Удачно)

* При установке C++ Build Tools было внесено одно изменение - установлена галочка "MSVC v140 - VS 2015 C++ build tools (v14.0)":

![](https://lh3.googleusercontent.com/fife/ABSRlIr5y7Mdn4Q-vtQf8WUKCjrCWQEOYrSfHLYf1FliUtEV3Ljo-7aJZZKN4EvtVYS0KWxI87MjAWB-49JbXQaJTbMQ2Y2d8Lz3RlRUIQw_1QbyPYREmqX6ieWHQfp3hptxyTa5DdUrPpxG4HI4RIntbspK0-5udt2buE1y_wzBLZGfKLuU8AtVfkAutcfxcwHLiq5Fx9ZvEAepPpnDZMeAJeADFTioK2A7F0JZb25jsRd6FCBZOYqFyw2xl_4oa3pA5_bDVSZUCwmIvr-JNHGD1eCNhbsZN0k0LWEYlU--Yr_43iuVmrQ1-5IYvcxR3jZKKBdi5jHuFc8f9f1XC_xl9LiNdzz1UVso7K_1GQJsMHy898yAhpgIXrpDctUKEvJ1iXzd5WLOL-ozvLg2fK4DIgiNCu5EvQF2fAWbAdUOYNb-x0av252B2naXFVQAyy6TLA-1crfMqJ1g8ThoCp1QB78wLMa22Vm8e2CNbHteMJkUTnNXrOIkirBN1o5S3QqJZFH9rJVKPwYpKdayUU5FpUbGKsVDzAWFRZC2BWhX4CCx_h07S77MtZHb0TBFTeRA1yXe_HiB9nzb-7hTNeQ3lYlrrjvL65eYBJTO7ECvJ2sQqNenUwxKOKZxMJBELb5WS9GYbvweDQ5RCS0nH3wWKPgCgqw4Njn9_tHRyurqvIjBFCp7dR0SubSzQ-m-IVDryll5JPnME4n4Nlam1Xzkp0ZZSRXxAMiwDQ=w1437-h969-ft)

* Был скачан пакет lxml‑4.5.2‑cp37‑cp37m‑win_amd64.whl для Python 3.7

	```
	pip install —upgrade pip
	pip install lxml‑4.5.2‑cp37‑cp37m‑win_amd64.whl
	pip install label-studio
	```
* Успешный запуск

![](https://lh3.googleusercontent.com/fife/ABSRlIpvHgw3qNRo_wVk6d5w1KXUdMv2R_Rapb9n0Sh5ScOCrAFpqmUe2VGzww0QDSYF7sRBBx1UCr0QOWTDJVram6o_yie6k2HBG2g0tZbxuJcEXF1FKtszu7UZFqclGRzv2_D_nMC2xs9TTw_2NWTnNs4Q8pzdtULGFaITTg2RnjRYIurffVRLBbbu6LaLulKBr5NdrHBp58_qCMyyknt1NWFkZrIFUboVFzyFGsoiByrWvOTC2LQAmHgP9nser0pMsPFyNIaUM-xgsw0mkVxOdSk_DO4sxtfbzjRSwNLRXJvgvpf79Q4O7f_sj4uCk4xsImIoCoUEnSVLfDkvACxRqrOyJV4Qjy8HZIm4nG_MdyOKTGZkFJDNZWQYWAxtx44wHS7Eh9vDgntehjLOFj66YYXizkL4VSePAjHKpW16S2ERH5ZdDNr9U4ygLljDGttXvsLKITrdB1NZyWi4fFyv_1QS_TnNFLVAlUC9hANXYXECmKa0Rbk-E_94X5IO-f2mhX0eOZQKaYTIdogjXp-iWrZwDtGSk5cpVblsM7gl6Ak8OMUNf8-Sn1R7FOb7LlzR2lWNlGiX4mYuqZlcTyhrITNyhiZsMBJPURvdyi6Q7RDKmkJdB5C92-JvbiminxJjvSC0Qq8n1FQaSdwYuWrPouk_TesQ4p49fJNXfz3O7_Oy1qlJVB1YyE98YH_3GgRweTTVupJfnnP6TY_x19vl4-SXkVRr4ASn5Q=w10000-h10000-ft)

---

3. Попытка установки, используя версию Python 3.8.6 (Удачно)
* Установка производилась на другой машине с ОС Windows 7 Enterprise (x64)
* Все действия аналогичны предыдущей установке
* Незначительным и логичным отличием является лишь установка пакета lxml для Python 3.8

	```
	pip install —upgrade pip
	pip install lxml‑4.5.2‑cp38‑cp38m‑win_amd64.whl
	pip install label-studio
	```
* Успешный запуск
