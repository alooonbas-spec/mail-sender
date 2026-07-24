# Mail Sender - Программа для рассылки сообщений

Автоматическая программа для генерации почтовых адресов и рассылки сообщений на эти адреса.

## 📋 Возможности

- ✅ Генерация случайных email адресов
- ✅ Отправка сообщений через SMTP
- ✅ Массовая рассылка на несколько адресов
- ✅ Поддержка HTML и текстовых сообщений
- ✅ Логирование отправок

## 🚀 Быстрый старт

### Требования
- Python 3.7+ или Node.js 14+
- Аккаунт Gmail с включённой двухфакторной аутентификацией
- App Password для Gmail

### Установка Gmail App Password

1. Перейдите на [myaccount.google.com/apppassigns](https://myaccount.google.com/apppasswords)
2. Выберите "Mail" и "Windows Computer" (или ваше устройство)
3. Скопируйте сгенерированный пароль


Вот пошаговые инструкции для запуска проекта:

🐍 Запуск на Python
Шаг 1: Установка зависимостей
bash
pip install -r requirements.txt
Шаг 2: Подготовка Gmail
Откройте https://myaccount.google.com/apppasswords
Выберите Mail и Windows Computer (или ваше устройство)
Скопируйте 16-символьный пароль
Шаг 3: Конфигурация программы
Откройте mail_sender.py и измените строки:

Python
SENDER_EMAIL = "your_email@gmail.com"        # ← Ваша почта Gmail
SENDER_PASSWORD = "your_app_password"         # ← 16-символьный пароль из App Passwords
Например:

Python
SENDER_EMAIL = "example@gmail.com"
SENDER_PASSWORD = "abcd efgh ijkl mnop"
Шаг 4: Запуск программы
bash
python mail_sender.py
Результат:

Code
Начинаем рассылку на 3 адресов...

[1/3] Отправка на a1b2c3d4e5@gmail.com...
✓ Сообщение отправлено на a1b2c3d4e5@gmail.com

[2/3] Отправка на f6g7h8i9j0@yahoo.com...
✓ Сообщение отправлено на f6g7h8i9j0@yahoo.com

[3/3] Отправка на k1l2m3n4o5@outlook.com...
✓ Сообщение отправлено на k1l2m3n4o5@outlook.com


📦 Запуск на Node.js
Шаг 1: Установка зависимостей
bash
npm install

Шаг 2: Подготовка Gmail (как выше)

Шаг 3: Конфигурация в mail_sender.js
Найдите и измените:

JavaScript
auth: {
    user: 'your_email@gmail.com',      // ← Ваша почта Gmail
    pass: 'your_app_password'           // ← 16-символьный пароль
}

Шаг 4: Запуск программы
bash
npm start
или

bash
node mail_sender.js

🔧 Параметры рассылки
Вы можете изменить количество писем в коде:

Python:
Python
send_bulk_emails(SENDER_EMAIL, SENDER_PASSWORD, SUBJECT, BODY, recipient_count=5)
                                                                    # ↑ измените это число

Node.js:
JavaScript
sendBulkEmails(SUBJECT, BODY, 3);  // Отправит 3 письма
               # ↑ измените это число

⚠️ Возможные ошибки
Ошибка	Решение
AuthenticationError	Проверьте пароль App Password (он 16 символов)
SMTPAuthenticationError	Включите 2FA на аккаунте Gmail
SMTPException: SMTP AUTH extension	Используйте только пароль из App Passwords
[Errno -2] Name or service not known	Проверьте интернет соединение

💡 Советы
📧 Тестируйте сначала отправкой на одно письмо (recipient_count=1)
⏱️ Между письмами есть задержка в 1 сек (можно изменить)
🔒 Никогда не кладите пароль в код - используйте .env файл
✅ Проверьте папку "Спам" если письма не приходят
