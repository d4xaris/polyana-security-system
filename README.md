<img width="1281" height="239" alt="1 (1)" src="https://github.com/user-attachments/assets/56091c75-8928-441d-b344-bfe3127d2ca7" />
<img width="1281" height="157" alt="1 (3)" src="https://github.com/user-attachments/assets/95c1dc86-cfd3-49cb-91a8-520b72b90c34" />

---

<div align="center">
   
✨ **Made by**  
   
[@d4xaris](https://github.com/d4xaris) · [@setlors](https://github.com/setlors) · [@tevarindol](https://github.com/tevarindol)

</div>

## Огляд

Цей репозиторій надає готове до використання середовище бази даних з використанням Docker контейнерів.  
Середовище включає:

- Сервер бази даних PostgreSQL
- Веб-інтерфейс pgAdmin для управління базою даних

## Передумови

Перед початком роботи переконайтеся, що встановлено наступні інструменти:

- [Docker](https://www.docker.com/get-started)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Початок роботи

### Налаштування середовища

1. Клонуйте цей репозиторій:
   ```bash
   git clone https://github.com/ZheniaTrochun/db-intro-course.git
   cd db-intro-course
   ```

2. Запустіть контейнери:
   ```bash
   docker-compose up -d
   ```

3. Щоб зупинити контейнери виконайте:
   ```bash
   docker-compose down
   ```

## Сервіси

### PostgreSQL

- **Порт**: 5432
- **Ім'я користувача**: postgres
- **Пароль**: password123
- **Скрипти ініціалізації**: Розмістіть ваші SQL-скрипти в директорії `init-scripts`, щоб вони виконувалися при запуску контейнера

### pgAdmin

- **URL**: http://localhost:8080
- **Електронна пошта**: root@kpi.edu
- **Пароль**: password123

## Підключення до бази даних

### Використання pgAdmin

1. Відкрийте http://localhost:8080 у вашому браузері
2. Увійдіть, використовуючи вказані вище облікові дані
3. Додайте новий сервер з наступними налаштуваннями:
   - Назва: Будь-яка назва на ваш вибір
   - Хост: postgres
   - Порт: 5432
   - Ім'я користувача: postgres
   - Пароль: password123

### Використання командного рядка

```bash
docker exec -it db-intro-course_postgres_1 psql -U postgres
```
---

<img width="1281" height="157" alt="1 (2)" src="https://github.com/user-attachments/assets/f7a9d5d3-b45a-4932-a56c-f996b2f4893e" />

## Лабораторні
- [Лабораторна 1 - ER діаграми](labs/1%20-%20ER%20Diagram/lab_1.md)
- [Лабораторна 2 - DDL](labs/2%20-%20DDL/lab_2.md)
- [Лабораторна 3 - OLTP](labs/3%20-%20OLTP/lab_3.md)
- [Лабораторна 4 - OLAP](labs/4%20-%20OLAP/lab_4.md)
- [Лабораторна 5 - Нормалізація](labs/5%20-%20Normalization/lab_5.md)
- [Лабораторна 6 - Міграції](labs/6%20-%20Migrations/lab_6.md)

[Коротенький довідник по матеріалам](./sql-cheat-sheet.md)  
[Словничок термінів](./glossary.md)



## Збереження даних

Дані бази даних зберігаються в Docker volume:
- `postgres_data`: Дані PostgreSQL
- `pgadmin_data`: Конфігурація pgAdmin
