# ESNext

В 2015 году вышел новый стандарт JS, который описывает огромное
количество нововведений. Большая часть нововведений не концептуально
новые вещи, а различный синтаксический сахар.
Также сменился принцип именования версий и появился явный порядок
появления каких-то новых вещей:
- Каждый год выходить новая версия спецификации, которая содержит
  определенный набор фич. Версия именуется годом выпуска
  (например, ES6 — это старое именование, по новому — ES2015.
  Также уже вышла версия ES2016 и так далее);
- Stage-4 — предложение готово для включения в стандарт;
- Stage-3 — предложение почти готово, для попадания в stage-4
  необходимо несколько независимых реализаций;
- Stage-2 — черновик предложения, первая версия того, что будет в стандарте;
- Stage-1 — должна быть описана решаемая проблема,
  идея приобретает формальную форму;
- Stage-0 — какие-то идеи в свободной форме.
[Подробнее о статусах](http://www.2ality.com/2015/11/tc39-process.html)
Чем меньше число, тем больше шансов, что в будущем может в спецификации
что-то поменяться и будут изменения в синтаксисе.
Поэтому стоит задумываться об этом при выборе фич, которые будут использоваться.

Так как еще не весь функционал новых стандартов поддерживается браузерами,
то для написания кода необходим инструмент, который преобразует код по новому
стандарту в «старый» код (этот процесс называется транспайлингом).
Это возможно лишь для тех вещей, которые являются синтаксическим сахаром.
Но в стандартах бывают вещи, которые без нативной поддержки целиком
воссоздать невозможно.
Таким инструментом является [Babel](https://babeljs.io/).
В его настройках можно указать версии языка или номера stage,
которые поддерживать. Или просто отдельные возможности.
Стоит учитывать, что Babel транспайлит только синтаксические конструкции,
но не полифилит различные методы объектов. Например, даже при
подключенном ES2016 вызвать метод `Array.prototype.includes`,
то его не будет в старых браузерах.
Для полифилинга есть отдельный модуль [babel-polyfill](https://babeljs.io/docs/usage/polyfill/)
