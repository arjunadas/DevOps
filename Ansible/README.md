# ✅ Ansible Best Practices — Чеклист

## 📁 1. Структура и организация
- [ ] Используется структура с ролями (`roles/`), инвентори разделён по средам.
- [ ] В каждой роли есть стандартные каталоги: `tasks/`, `handlers/`, `vars/`, `defaults/`, `templates/`, `files/`.
- [ ] Переменные вынесены в `group_vars/`, `host_vars/` или `defaults/main.yml` в ролях.

## 🔧 2. Переменные и секреты
- [ ] Нет жестко захардкоженных значений в плейбуках.
- [ ] Используется `ansible-vault` для секретных данных.
- [ ] Имена переменных понятные и последовательные.

## 🧩 3. Задачи и модули
- [ ] Используются стандартные модули Ansible, а не `shell` или `command` без нужды.
- [ ] Все задачи имеют осмысленное описание `name`.
- [ ] Задачи идемпотентны (их можно запускать многократно без вреда).
- [ ] Для перезапуска сервисов используются `handlers`.

## 🔍 4. Логика и условности
- [ ] Используются условия (`when`) для проверки необходимости выполнения задачи.
- [ ] Используются параметры модулей, гарантирующие выполнение только при необходимости (`creates`, `removes` и т.п.).

## 📝 5. Шаблоны и конфигурация
- [ ] Используются шаблоны Jinja2 для конфигурационных файлов.
- [ ] Нет жестко прописанных путей и значений — все через переменные.

## 🔐 6. Безопасность и доступ
- [ ] Используются безопасные методы хранения и передачи паролей (vault, ssh-ключи).
- [ ] В инвентори нет лишних открытых данных.

## 📦 7. Управление ролями и зависимостями
- [ ] Роли используют `meta/main.yml` для описания зависимостей.
- [ ] Используется Ansible Galaxy для установки сторонних ролей.

## 🧪 8. Тестирование и отладка
- [ ] Запуск плейбуков с флагами `-v` или `-vvv` для детального вывода.
- [ ] Плейбуки проходят проверку в тестовом окружении перед продом.

## 📚 9. Документация
- [ ] Есть комментарии и описания для сложных задач.
- [ ] В README ролей описаны назначение, переменные и пример использования.

## 🔁 10. Контроль версий и CI/CD
- [ ] Плейбуки и роли хранятся в Git или другой системе контроля версий.
- [ ] Автоматизировано тестирование и деплой через CI/CD pipeline.
