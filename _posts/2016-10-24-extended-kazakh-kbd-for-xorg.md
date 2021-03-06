---
layout: post
title: "Казахская клавиатура в Linux"
description: ""
categories:
- news
tags: [keyboard]
---

Недавно я поправил две вещи, которые доставляли неудобства при наборе казахского текста в системах с X.org, то есть в Linux. Во-первых, по каким-то историческим причинам (кажется, стандарт), двойная кавычка в казахской раскладке была не ```"``` а ```„``` то есть нижняя, видимо, скопированная с раскладки для пишущих машинок (не застал). В то же время, в Windows раскладке кавычки - нормальные ```"```. В новом релизе **xkeyboard-config** это [поправлено](https://cgit.freedesktop.org/xkeyboard-config/commit/?id=70813f1d10f593f0eb910164cd4aa922b830d622).

Вторая проблема заключалась в том, что для набора спецсимволов с английской раскладки, или даже для банального дефиса или цифр, приходилось переключать раскладку на английскую или русскую (у меня настроено три раскладки), особенно актуально для клавиатур ноутбуков, где нет расширенной цифровой части клавиатуры справа. Это также [поправлено](https://cgit.freedesktop.org/xkeyboard-config/commit/?id=26fc21c2ba957c0d2481ccf633e4111b6fec60c7) путем добавления этих самых спецсимволов на расширенный ряд, доступный по клавише-модификатору. Прилагаю поясняющий скриншот, менять надо пункт "Alternative Characters Key", в моём случае - выставлено в **Right Alt**.

![Клавиша в настройках](http://baurzhan.info/wp-content/uploads/lnx-gnome-3.14-kbd.PNG)

То есть, при удержании нажатой этой клавиши, в казахской раскладке можно набирать цифры, а при удержании этой клавиши+Shift - спецсимволы с английской раскладки.

Замечу только, что нужно выбрать вариант клавиатурной раскладки **Kazakh (extended)**, и только при наличии в системе пакета xkeyboard-config 2.19 или новее. В Fedora 25, ~~будущем релизе, этого пакета не будет, так что скомпилировал сам и теперь пользуюсь~~ этот пакет уже пришел в обновлениях.
