# Jenkins Docker Demo

Учебный проект Jenkins Pipeline.

## Pipeline

1. Build
2. Test
3. Docker Build
4. Run Container
5. Package
6. Deploy

## Docker

Образ собирается командой:

docker build -t demo-app:15 .

Запуск:

docker run --rm demo-app:15

Результат:

Hello Jenkins v3
