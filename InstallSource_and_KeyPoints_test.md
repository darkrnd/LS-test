# Установка Label Studio под Windows из исходного кода и проверка производительности KeyPoints(>=400)

Python version 3.7.9
1. Установка
* Установка производится на основе [https://labelstud.io/guide/index.html#Running-from-source](https://labelstud.io/guide/index.html#Running-from-source)

	```
	git clone https://github.com/heartexlabs/label-studio.git
	cd label-studio
	python setup.py develop
	```
	Все успешно, никаких проблем
* Переключение ветки
	```
	git fetch origin release/0.8.2
	git checkout release/0.8.2
	```
* Запуск Label Studio
	```
	label-studio start my_project --init
	```
---
2. Проверка производительности KeyPoints (>=400)
* После установки примерно 100 шт, интерфейс начинает заметно подвисать. Использовался браузер Chrome(x64) на Core i7 2.8GHz (8 ядер), 4GB RAM
* Результат работы  можно увидеть на видео: [https://github.com/darkrnd/LS-test/blob/main/ls-keypoints400.mkv](https://github.com/darkrnd/LS-test/blob/main/ls-keypoints400.mkv?raw=true)
* Заметный лаг уже наступает примерно с 30-й секунды видео, с добавлением новых точек лаг усиливается - временно зависает вся вкладка браузера
