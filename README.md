# job4j_di

## Описание проекта
Этот проект создан для изучения концепции внедрения зависимостей (Dependency Injection, DI) в Java с использованием рефлексии.

DI позволяет упростить создание объектов с множеством зависимостей, <br/>
автоматически инициализируя их через специальное контекстное хранилище объектов.

Приложение упаковано в Docker контейнер.

## Технологии
Проект использует:
- Java 21
- Maven
- Checkstyle
- Docker

## Запуск

1. Установите и запустите Docker.<br><br>

2. Склонируйте репозиторий
```
git clone https://github.com/hrodvar-one/job4j_di
```

3. Перейдите в папку куда склонировали проект
```
cd job4j_di
```

4. В командной строке выполните команду:
```
docker build -t job4j_di . && docker run job4j_di
```

5. Ждём сборку и запуск контейнера с приложением.
6. При успешном запуске контейнера в консоль выведет результат работы упакованного приложения:
```
Petr Arsentev
Ivan ivanov
```

## Архитектура
### Основные классы:
1. **`Store`** — хранилище данных.
2. **`StartUI`** — класс, управляющий взаимодействием с пользователем.
3. **`Context`** — DI-контейнер, который управляет зависимостями между объектами.
4. **`ConsoleInput`** — ввод данных с консоли.
5. **`Main`** — точка входа в программу.

### Принцип работы DI:
1. В **Context** регистрируются классы `Store`, `StartUI`, `ConsoleInput`.
2. **Context** создает объекты, анализируя их зависимости.
3. **StartUI** получает зависимости (`Store`, `ConsoleInput`) автоматически.
4. **Программист** извлекает готовый объект `StartUI` из **Context** и использует его.

