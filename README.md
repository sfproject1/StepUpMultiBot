# StepUpMultiBot
Бот для алгоритмической торговли на бирже Huobi. Пока только спотовый рынок и USDT пары.
В период тестирования, бот работает бесплатно. Так же, все участники тестирования получат большие бонусы на использование коммерческой версии программы.
В работе робота используется стратегия усреднения. 
Алгоритм:
1. Бот покупает актив на заданную сумму.
2. Если стоимость актива падает ниже заданного процента, происходит усреднение, робот докупает актив и средняя цена покупки увеличивается.
3. Если стоимость актива растет выше заданного уровня, включается режим трейлинга. Робот следит за движением цены от максимума и продает актив, при падении на заданный процент от максимума.

Для работы требуется Telegram. Необходимо:
1. Создать бота через https://t.me/BotFather . Записать Api ключ.
2. Создать канал, добавить туда бота, в качестве администратора. Написать в канале любое сообщение и переслать его в https://t.me/userinfobot . Вы получите ID канала (начинается с минуса).

Настройки:
1. Минимальный баланс.
Задается в процентах. Ниже этого остатка свободных средств, робот не открывает новые позиции и не усредняется
2. Размер начального ордера
Задается в десятичной доле доллара. Робот открывает позицию на эту сумму (0.5 = 5 долларов)
3. Запрет покупки при падении
Робот не открывает позицию, если суточное изменение цены ниже этого уровня в процентах
4. Запрет покупки при росте
Робот не открывает позицию, если суточное изменение цены выше этого уровня в процентах
5. Пауза между покупками
Робот не открывает заново торговлю по этой же паре, пока не истечет этот таймер в секундах
6. Минимальный торговый объем
Робот не открывает позицию по паре, если суточный объем в USD меньше этого значения
7. Тейк профит
Процент дохода, при котором робот закрывает сделку, либо включает трейлинг
8. Уровень усреднения
Процент убытков, при котором робот усредняется
9. Максимальное количество усреднений
Максимальное количество усреднений по паре
10. Объем усреднения
Множитель объема для усреднения. Усредняясь, робот берет весь купленный объем и умножает на этот коэффициент.
11. Максимальное количество торговых пар
Максимальное количество одновременно торгующихся пар. Если 0 , то робот не открывает новые пары. Если -1, то автоматически подбирает количество, основываясь на текущем остатке средств, учитывая усреднения. 
12. Активность трейлинга
Определяет, включен ли трейлинг. При значении YES, робот достигая тейк профита, не продает, а ожидает падения цены от максимального профита на заданный процент.
13. Уровень закрытия при трейлинге
Уровень от максимума в процентах, при котором робот закрывает позицию
14. Уровень запрета усреднения
Робот не усредняется, если суточное изменение цены меньше этого процентного значения. Полезно на сильно падающем рынке

![1](https://github.com/sfproject1/StepUpMultiBot/blob/main/1.png)
![2](https://github.com/sfproject1/StepUpMultiBot/blob/main/2.png)
![3](https://github.com/sfproject1/StepUpMultiBot/blob/main/3.png)
