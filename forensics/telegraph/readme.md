# Bad developer 1
forensics, 200 points

> Разработчики UPML CTF, наверное, не очень шарят в безопасности. Кажется, они оставляют заметки о тасках на telegra.ph. Да ещё и называют их UPML CTF.
>
> Посмотри, что они там слили, пока они сами не узнали и не удалили!

## Write-up

Зайдем на telegra.ph и создадим любую статью (лучше с названием, не равным UPML CTF). Видим, что URL-статьи имеет вид
`http://telegra.ph/Title-with-dashes-MM-DD`, где `MM` — месяц, `DD` — день, а `Title-with-dashes` — заголовок, в котором
пробелы заменены на тире.

Если за день публикуется больше одной статьи с одинаковым названием (пример — UPML CTF, вы создали 68 статей с таким
названием за 11 ноября), то будет URL `http://telegra.ph/Title-with-dashes-MM-DD-ID`, где `ID` — порядковый номер.

В любом случае, если переберем без `ID`, то найдем для каждого дня, были в этот день статьи, или нет (если первой не 
существует, остальных, очевидно тоже). Статья находится от [15 октября](http://telegra.ph/UPML-CTF-10-15). Там видим
флаг от первого задания категории forensics.

Флаг: **uctf_y0u_f0und_t3l3gra_ph_s3cr3t**