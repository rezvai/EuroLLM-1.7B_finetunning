# LLM Training Environment

## Установка и запуск

1. Клонируй репозиторий и перейди в директорию проекта:
   ```bash
   git clone <URL>
   cd <папка_проекта>

2. Создай `.env` из примера:

   ```bash
   cp .env.example .env
   ```

3. Собери образ:

   ```bash
   docker build -t llm_training .
   ```

4. Запусти контейнер (с доступом к GPU):

   ```bash
   docker run --gpus all -it -v "$(pwd)":/app -w /app llm_training bash
   ```

5. Проверь, что GPU доступен:

   ```bash
   python3 -c "import torch; print(torch.cuda.is_available())"
   ```

6. Для работы с ноутбуком:

   ```bash
   jupyter notebook --ip=0.0.0.0 --port=8888 --allow-root --no-browser
   ```

   Перейди по ссылке из вывода в браузере.

   Или используй VS code и Dev Containers

```
