## Тема, Мета, Місце розташування

**Тема:** Адаптивний веб-застосунок ресторану швидкого харчування MacShnaknels

**Мета:** Мета лабораторної роботи — реалізувати REST API для вебзастосунку **MacShnaknels**, додати реєстрацію, авторизацію, валідацію даних, захищені маршрути, ролі користувачів, refresh token, logout, оновлення профілю, зміну та відновлення пароля, підтвердження email і підготовку Google OAuth.

**Місце розташування:**
- GitHub: [встав посилання](https://github.com/gervinn/IA-34_appWEB-VinnitskiyHerman-FIOT-2026)
- Live demo: ([встав посилання](https://gervinn.github.io/IA-34_appWEB-VinnitskiyHerman-FIOT-2026/))

---

## Постановка задачі

У якості основи використано проєкт лабораторної роботи №2 **MacShnaknels**, у якому вже було реалізовано:

- статичну клієнтську частину сайту ресторану швидкого харчування;
- адаптивний інтерфейс з головною сторінкою, меню, акціями, кошиком і блоком контактів;
- підключення Node.js до MySQL через пакет `mysql2`;
- використання ORM `Sequelize`;
- створення моделей `User` та `Post`;
- реалізацію зв’язку One-to-Many між користувачами та постами;
- базові SQL-запити `SELECT`, `INSERT`, `UPDATE`, `DELETE`;
- зберігання користувачів і постів у базі даних MySQL.

У лабораторній роботі №3 структура проєкту була збережена, а наявний backend розширено модулем автентифікації та авторизації користувачів. Таким чином, Lab 3 є продовженням Lab 2, а не окремим новим проєктом.

---

## Що повторно використано з Lab 2

У роботі без змін або з мінімальними змінами повторно використано:

- головну сторінку `index.html`;
- стилі сайту з папки `css`;
- JavaScript-логіку клієнтської частини з папки `js`;
- папку `assets/images` для графічних ресурсів;
- конфігурацію підключення до MySQL;
- модель `User`;
- модель `Post`;
- зв’язок One-to-Many між `User` та `Post`;
- маршрути для роботи з користувачами через `mysql2`;
- маршрути для роботи з моделями через `Sequelize`;
- загальну структуру Express-проєкту.

Це дозволило зберегти цілісність вебзастосунку та показати послідовний розвиток проєкту від лабораторної роботи №2 до лабораторної роботи №3.

---

## Нові можливості Lab 3

До проєкту було додано:

- реєстрацію користувача;
- авторизацію користувача;
- підтвердження пароля при реєстрації;
- валідацію введених даних;
- обробку помилок;
- access token;
- refresh token;
- logout;
- захищений маршрут профілю;
- оновлення профілю користувача;
- зміну пароля;
- ролі користувачів `user` та `admin`;
- middleware для перевірки JWT-токена;
- адміністративні маршрути;
- видалення користувача;
- відновлення пароля;
- підтвердження email;
- обмеження кількості спроб входу;
- логування помилок у файл;
- підготовку Google OAuth-авторизації.

---

## Структура проєкту після доопрацювання

```text
macshnaknels/
│
├── assets/
│   └── images/
│       └── зображення сайту
│
├── css/
│   ├── style.css
│   ├── auth.css
│   └── admin.css
│
├── js/
│   ├── script.js
│   ├── register.js
│   ├── login.js
│   └── admin.js
│
├── backend/
│   ├── src/
│   │   ├── config/
│   │   │   ├── mysql2.js
│   │   │   └── sequelize.js
│   │   │
│   │   ├── models/
│   │   │   ├── User.js
│   │   │   ├── Post.js
│   │   │   └── index.js
│   │   │
│   │   └── server.js
│   │
│   ├── logs/
│   │   ├── access.log
│   │   └── errors.log
│   │
│   ├── .env
│   ├── package.json
│   └── package-lock.json
│
├── index.html
├── register.html
├── login.html
├── admin.html
└── README.md
```

---

## Опис основних файлів

`index.html` — головна сторінка сайту MacShnaknels. Містить основні блоки інтерфейсу: header, hero-блок, меню, акції, інформацію про заклад, footer та кошик.

`register.html` — сторінка реєстрації користувача.

`login.html` — сторінка авторизації користувача.

`admin.html` — сторінка адміністративної панелі.

`css/style.css` — основні стилі сайту.

`css/auth.css` — стилі сторінок реєстрації та входу.

`css/admin.css` — стилі адміністративної панелі.

`js/script.js` — основна логіка frontend-частини: меню, кошик, відображення поточного акаунта, logout.

`js/register.js` — відправлення даних реєстрації на backend.

`js/login.js` — авторизація користувача та збереження токенів у `localStorage`.

`js/admin.js` — логіка адміністративної панелі.

`backend/src/server.js` — головний файл backend-сервера, у якому реалізовано REST API.

`backend/src/config/mysql2.js` — підключення до MySQL через пакет `mysql2`.

`backend/src/config/sequelize.js` — підключення до MySQL через ORM Sequelize.

`backend/src/models/User.js` — модель користувача.

`backend/src/models/Post.js` — модель поста або акції.

`backend/src/models/index.js` — опис зв’язків між моделями.

---

## Стек технологій

У проєкті використано:

- `HTML5` — створення структури сторінок;
- `CSS3` — стилізація інтерфейсу;
- `JavaScript` — клієнтська логіка сайту;
- `Node.js` — серверне середовище виконання JavaScript;
- `Express.js` — створення REST API;
- `MySQL` — база даних;
- `XAMPP` — запуск локального MySQL-сервера;
- `phpMyAdmin` — перегляд і керування базою даних;
- `mysql2` — пряме підключення Node.js до MySQL;
- `Sequelize` — ORM для роботи з базою даних через моделі;
- `bcryptjs` — хешування паролів;
- `jsonwebtoken` — створення access token і refresh token;
- `express-validator` — валідація даних;
- `express-rate-limit` — обмеження кількості спроб входу;
- `morgan` — логування HTTP-запитів;
- `nodemailer` — підготовка надсилання email;
- `passport` — підготовка OAuth-авторизації;
- `passport-google-oauth20` — підготовка Google login;
- `dotenv` — робота зі змінними середовища;
- `cors` — дозвіл запитів між frontend і backend.

---

## REST API маршрути

### Успадковані з Lab 2

```text
GET    /api/raw/users
POST   /api/raw/users
PUT    /api/raw/users/:id
DELETE /api/raw/users/:id

POST   /api/orm/users
POST   /api/orm/posts
GET    /api/orm/users-with-posts
```

Ці маршрути використовуються для демонстрації роботи з базою даних через `mysql2` та `Sequelize`.

### Додані в Lab 3

```text
POST   /api/auth/register
POST   /api/auth/login
POST   /api/auth/refresh
POST   /api/auth/logout
GET    /api/auth/me
PUT    /api/auth/profile
PUT    /api/auth/change-password
DELETE /api/auth/delete-account
POST   /api/auth/forgot-password
POST   /api/auth/reset-password
GET    /api/auth/confirm-email/:token
GET    /api/auth/google
GET    /api/auth/google/callback
```

### Адміністративні маршрути

```text
GET    /api/admin/users
PATCH  /api/admin/users/:id/role
DELETE /api/admin/users/:id

GET    /api/admin/posts
POST   /api/admin/posts
PUT    /api/admin/posts/:id
DELETE /api/admin/posts/:id
```

Адміністративні маршрути доступні тільки користувачам з роллю `admin`.

---

## Структура бази даних

У проєкті використовується база даних:

```text
macshnaknels_db
```

Основні таблиці:

- `users`;
- `posts`.

---

## Таблиця users

Таблиця `users` використовується для збереження користувачів системи.

Основні поля:

```text
id — унікальний ідентифікатор користувача;
name — ім’я користувача;
email — електронна пошта;
password — хешований пароль;
role — роль користувача: user або admin;
refreshToken — refresh token користувача;
emailConfirmed — статус підтвердження email;
emailConfirmToken — токен підтвердження email;
resetPasswordToken — токен відновлення пароля;
resetPasswordExpires — час дії токена відновлення пароля;
googleId — ідентифікатор Google-акаунта;
loginAttempts — кількість невдалих спроб входу;
lockUntil — час блокування акаунта після великої кількості невдалих спроб входу.
```

---

## Таблиця posts

Таблиця `posts` використовується для збереження постів, акцій або новин сайту.

Основні поля:

```text
id — унікальний ідентифікатор поста;
title — назва поста або акції;
content — текстовий опис;
user_id — зовнішній ключ, який посилається на користувача-автора.
```

---

## Зв’язок One-to-Many

Між таблицями `users` та `posts` реалізовано зв’язок **One-to-Many**.

Це означає, що один користувач може створювати багато постів або акцій, але кожен пост належить тільки одному користувачу.

У Sequelize цей зв’язок реалізовано так:

```js
User.hasMany(Post, {
  foreignKey: "user_id",
  as: "posts",
  onDelete: "CASCADE",
});

Post.belongsTo(User, {
  foreignKey: "user_id",
  as: "author",
});
```

Для перевірки зв’язку використовується маршрут:

```text
GET /api/orm/users-with-posts
```

---

## Валідація та безпека

У роботі реалізовано:

- перевірку формату email;
- перевірку мінімальної довжини пароля;
- підтвердження пароля під час реєстрації;
- перевірку старого пароля при зміні на новий;
- хешування паролів через `bcryptjs`;
- використання JWT для захисту маршрутів;
- access token для доступу до захищених ресурсів;
- refresh token для оновлення access token;
- перевірку ролей користувачів;
- middleware для перевірки токена;
- rate limit для обмеження кількості спроб входу;
- логування запитів та помилок у файли;
- обробку помилок через `try/catch` та глобальний middleware.

---

## Приклади запитів для тестування

### Реєстрація користувача

```bash
curl -X POST http://localhost:3000/api/auth/register ^
  -H "Content-Type: application/json" ^
  -d "{\"name\":\"Herman\",\"email\":\"herman@example.com\",\"password\":\"secret123\",\"confirmPassword\":\"secret123\"}"
```

### Авторизація користувача

```bash
curl -X POST http://localhost:3000/api/auth/login ^
  -H "Content-Type: application/json" ^
  -d "{\"email\":\"herman@example.com\",\"password\":\"secret123\"}"
```

### Отримання профілю користувача

```bash
curl http://localhost:3000/api/auth/me ^
  -H "Authorization: Bearer ACCESS_TOKEN"
```

### Оновлення профілю

```bash
curl -X PUT http://localhost:3000/api/auth/profile ^
  -H "Content-Type: application/json" ^
  -H "Authorization: Bearer ACCESS_TOKEN" ^
  -d "{\"name\":\"Updated Herman\",\"email\":\"updated@example.com\"}"
```

### Зміна пароля

```bash
curl -X PUT http://localhost:3000/api/auth/change-password ^
  -H "Content-Type: application/json" ^
  -H "Authorization: Bearer ACCESS_TOKEN" ^
  -d "{\"oldPassword\":\"secret123\",\"newPassword\":\"newpass123\",\"confirmNewPassword\":\"newpass123\"}"
```

### Refresh token

```bash
curl -X POST http://localhost:3000/api/auth/refresh ^
  -H "Content-Type: application/json" ^
  -d "{\"refreshToken\":\"REFRESH_TOKEN\"}"
```

### Logout

```bash
curl -X POST http://localhost:3000/api/auth/logout ^
  -H "Authorization: Bearer ACCESS_TOKEN"
```

### Відновлення пароля

```bash
curl -X POST http://localhost:3000/api/auth/forgot-password ^
  -H "Content-Type: application/json" ^
  -d "{\"email\":\"herman@example.com\"}"
```

### Скидання пароля

```bash
curl -X POST http://localhost:3000/api/auth/reset-password ^
  -H "Content-Type: application/json" ^
  -d "{\"token\":\"RESET_TOKEN\",\"newPassword\":\"reset123\",\"confirmNewPassword\":\"reset123\"}"
```

### Перевірка Google OAuth

```bash
curl http://localhost:3000/api/auth/google
```

Якщо `GOOGLE_CLIENT_ID` та `GOOGLE_CLIENT_SECRET` не налаштовані у файлі `.env`, API поверне повідомлення про те, що Google OAuth не налаштовано. Це означає, що інтеграцію підготовлено, але для повної роботи потрібно створити OAuth credentials у Google Cloud Console.

---

## Інструкція запуску проєкту

### 1. Запустити XAMPP

У XAMPP потрібно запустити:

```text
Apache
MySQL
```

### 2. Перейти в папку backend

```bash
cd backend
```

### 3. Встановити залежності

```bash
npm install
```

### 4. Запустити backend

```bash
npm run dev
```

Після запуску має з’явитися повідомлення:

```text
Підключення до MySQL через Sequelize успішне
Сервер працює на http://localhost:3000
```

### 5. Запустити frontend

Frontend-частину потрібно відкрити через Live Server у VS Code.

Основні сторінки:

```text
index.html
register.html
login.html
admin.html
```

---

## Файл .env

Приклад файлу `.env`:

```env
PORT=3000

DB_HOST=localhost
DB_PORT=3306
DB_USER=root
DB_PASSWORD=
DB_NAME=macshnaknels_db

ACCESS_TOKEN_SECRET=macshnaknels_access_secret
REFRESH_TOKEN_SECRET=macshnaknels_refresh_secret
JWT_SECRET=macshnaknels_secret_key

CLIENT_URL=http://127.0.0.1:5500

GOOGLE_CLIENT_ID=
GOOGLE_CLIENT_SECRET=
GOOGLE_CALLBACK_URL=http://localhost:3000/api/auth/google/callback

SMTP_HOST=
SMTP_PORT=587
SMTP_USER=
SMTP_PASS=
```

Файл `.env` не потрібно публікувати у GitHub, оскільки він може містити секретні ключі.

---

## Результат виконання

У ході лабораторної роботи було збережено архітектурну основу лабораторної роботи №2 та повторно використано наявну frontend- і backend-структуру вебзастосунку **MacShnaknels**. Серверну частину було розширено повноцінним REST API для роботи з користувачами.

Було реалізовано реєстрацію, авторизацію, валідацію даних, обробку помилок, захищені маршрути, ролі користувачів, access token, refresh token, logout, оновлення профілю, зміну пароля, видалення користувача, відновлення пароля, підтвердження email, логування помилок та обмеження кількості спроб входу.

Також було підготовлено інтеграцію Google OAuth. У разі додавання `GOOGLE_CLIENT_ID` та `GOOGLE_CLIENT_SECRET` у файл `.env` користувач зможе авторизуватися через Google-акаунт.

---

## Висновки

У лабораторній роботі №3 було виконано розвиток проєкту **MacShnaknels** без повної перебудови його структури. Клієнтську частину сайту було повторно використано, а серверну логіку доповнено засобами автентифікації та авторизації користувачів.

У результаті вебзастосунок отримав функціональний REST API, який підтримує реєстрацію, вхід, logout, оновлення профілю, зміну пароля, відновлення пароля, підтвердження email, перевірку токена та розмежування прав доступу за ролями `user` і `admin`.

Реалізована система є більш наближеною до реального вебсервісу, оскільки забезпечує захист маршрутів, перевірку введених даних, обробку помилок, збереження користувачів у базі даних MySQL та використання JWT-токенів для авторизації.
