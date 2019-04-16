GithubApi
Сервіс по роботі з Github пошуком. Надає інформацію(логін,ім'я, прізвище, bio,електронну адресу та місце знаходження) про 10 користувачів,що мають найбільше фоловерів.

http://localhost:3001/api/users/test - по цьому посиланню доступна інформація. Відображення з бази даних

http://localhost:3001/api/users/auth/github - для авторизації

Express.js Характерною особливістю цього фреймворка - не великий об'єм базового функціоналу. Якщо постає питання у збільшенні кількості функцій - слід встановлювати додатові модулі. При цьому важливо, що вибір модулів для Express не пов'язаний ні з якими обмеженнями: ні з кількісними, ні з функціональними. В результаті, цей фреймворк забезпечує можливість вирішувати будь-які завдання, не обмежуючи при цьому у виборі засобів.

Недоліки: великий обсяг ручної роботи використовується застарілий підхід callback функцій

Спосіб зберігання даних: Існують два основних напрямів баз даних SQL and NOSQL. Було вибрано MongoDB(NOSQL). Чесно кажучи тут я не можу сказати щоб було ліпше вибрати. Має досвіт і з MongoDB і з MySQL. Сказати що певна з них була б ліпша в цьому випадку не можу.

(додаткова інформація) Для доступу до електронної адреси потрібно пройти авторизацію. Її я пройшов створивши OAuth Apps. З приводу додавання найбільш популярних користувачів. З часом людина яка була в ретингу 11(наприклад) може стати 1. В моїй реалізації все буде коректно відображатися,але вже в базі даних буде 11 користувачів. А беручи до уваги,що кожну годину буде йти повторне звернення,то кількість записів буде зростати. Слід було реалізувати наступний алгоритм роботи з базою даних: get запрос для отримання інфорації. Використовуючи метод findOneAndUpdate оновлюємо інформацію. Якщо такого користувача немає,то видаляємо запис з найменшою кількістю фоловерів і вставляємо в БД. Таким чином в БД завжди 10 записів

P.S.якщо я правильно зрозумів перше додаткове завдання то я його частково викнав
