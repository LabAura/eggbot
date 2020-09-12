<html>
<head>
<!--<style type="text/css">
.tab { margin-left: 40px; }
</style>-->
</head>
<body>
                                                  <h2>Операционная система Windows 7,10</h2>
<p>1) Скачиваем Arduino IDE с оффициального сайта https://www.arduino.cc/en/Main/Software. 
<p style="margin-left: 40px;">В разделе "Download the Arduino IDE" выбираем "Windows installer ..."<br></p>
2) Устанавливаем "Arduino-#.#.#-windows.exe" (#-цифровое обозначение версии программы).<br>
<p style="margin-left: 40px;">В процессе установки будет установлен драйвер для Arduino.<br></p>
3) Подключаем Сферобота к компьютеру через кабель USB-B.<br>
4) Открываем "Диспетчер устройств" и проверяем, что драйвер установился корректно.<br>
<p style="margin-left: 40px;">Нажимаем клавишесочетание Win+R и вводим devmgmt.msc<br>
    Далее открываем пункт "Порты (COM и LPT)", в нём должно показаться устройство "Arduino Uno (COM3)" (Номер порта может быть другим).<br></p>
5) Обновление прошивки.<br>
<p style="margin-left: 40px;">Переходим по ссылке и скачиваем файл. https://github.com/ProbotXYZ/EggBot/blob/master/Firmware/Firmware.zip<br>
   	Теперь надо разархивировать архив.<br>
  	Открываем установленную программу Arduino IDE.<br>
   	Если открылась пустая программа, то нужно нажать вверху на вкладку "Файл->Открыть", выбрать место, куда сохранился файл прошивки и выбрать EggDuino.ino<br>
   	Далее нужно нажать на вкладку "Инструменты", выбрать во вкладке "Плата" пункт "Arduino/Genuino Uno" и во вкладке "Порт" выбрать устройство, которое совпадает с тем, что было открыто в "Диспетчере устройств".<br>
   	На последок нужно залить прошивку в сферобота нажав на стрелочку "->" в программе. Прошивка должна залиться успешно.<br></p>
6) Скачиваем векторный редактор "Inkscape" и плагин для работы с Eggbot.<br>
<p style="margin-left: 40px;">Скачиваем Inkscape с оффициального сайта https://inkscape.org/release/inkscape-0.92.4/ <br>
		Устанавливаем Inkscape.<br>
		Скачиваем по ссылке плагин. https://github.com/ProbotXYZ/EggBot/blob/master/Software/Inkscape_extension_only.zip <br>
		Разархивируем архив.<br>
		В папке "extensions" нужно отредактировать файл "ebb_serial.py", сделать это проще всего через редактор "Notepad++". Находим строчку с надписью "USB-SERIAL CH340" в скобках и меняем данные на "Arduino Uno (COM3)". (номер порта может отличаться)<br>
		Всё содержимое папки "extensions" нужно переместить в папку по пути C:\Program Files\Inkscape\share\extensions<br>
		Аналогично поступаем с содержимым папки "templates" в папку по пути C:\Program Files\Inkscape\share\templates<br></p>
7) Проверка работы Сферобота.<br>
<p style="margin-left: 40px;">Запускаем Inkscape.<br>
		Нажимаем на вкладку "Файл" и выбираем "Создать по шаблону...".<br>
		В открывшемся окне выбираем "EggBot".<br>
		Рисуем что-нибудь, что помещается на шаблон и не выходит за его рамки.<br>
		Нажимаем вверху на пункт меню "Расширения", наводим мышкой на "EggBot" и нажимаем на "EggBot Control".<br>
		Далее в появившемся окне выбираем "Применить". Сферобот должен начать двигаться.<br></p>
</p>
                                                  <h2>Операционная система Raspbian</h2>
<p>1) Установим Arduino IDE.<br>
	<p style="margin-left: 80px 0 0 0;">sudo apt install arduino -y<br></p>
2) Скачаем xarchiver.<br>
	<p style="margin-left: 80px 0 0 0;">sudo apt install xarchiver -y <br></p>
3) Скачаем прошивку с сайта https://github.com/ProbotXYZ/EggBot/blob/master/Firmware/Firmware.zip <br>
<p style="margin-left: 40px;">Разархивируем архив, нажав правой кнопкой мыши по нему и выбрав "Разархивировать в текущую папку".<br></p>
4) Заливаем прошивку в Сферобота. <br>
<p style="margin-left: 40px;">Захожим в папку "EggDuino" и нажав правой кнопкой мыши по файлу "EggDuino.ino" выбираем пункт "Arduino IDE"<br>
		Нажимаем на стрелочку "->", чтобы залить прошивку. Прошивка должна залиться успешно.<br></p>
5) Скачиваем Inkscape.<br>
	<p style="margin-left: 80px 0 0 0;">			sudo apt install inkscape -y<br></p>
6) Скачиваем расширение с сайта https://github.com/ProbotXYZ/EggBot/blob/master/Software/Inkscape_extension_only.zip<br>
<p style="margin-left: 40px;">Разархивируем архив.<br></p>
7) Отредактируем файл "ebb_serial.py"<br>
	<p style="margin-left: 40px;">Откроем файл.<br></p>
	<p style="margin-left: 80px 0 0 0;">			nano /home/pi/Загрузки/extensions/ebb_serial.py <br></p>
	<p style="margin-left: 40px;">Находим строчку с надписью "USB-SERIAL CH340" и меняем данные на "ttyACM0".<br>
		Нажимаем X, затем Y, затем Enter.<br></p>
8) Переместим файлы с плагинами.<br>
	<p style="margin-left: 80px 0 0 0;">sudo cp -r /home/pi/Загрузки/extensions/* /usr/share/inkscape/extensions/<br>
	sudo cp -r /home/pi/Загрузки/templates/* /usr/share/inkscape/templates/<br></p>
9) Выполняем пробный запуск.<br>
<p style="margin-left: 40px;">Запускаем Inkscape.<br>
		Нажимаем вверху на пункт меню "Файл" и выбираем "Создать по шаблону...".<br>
		Выбираем EggBot.<br>
		Рисуем что-нибудь, что не выходит за границы полей шаблона.<br>
		Нажимаем вверху на пункт меню "Расширения", наводим мышкой на "EggBot" и нажимаем на "EggBot Control".<br>
		По умолчанию мы находимся в меню "Начертить", поэтому нажимаем на "Применить". Сферобот должен начать двигаться.<br></p>
</p>
</body>
</html>
