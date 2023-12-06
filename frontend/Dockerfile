# Используем официальный образ Node.js LTS
FROM node:14

# Устанавливаем рабочую директорию внутри контейнера
WORKDIR /app

# Копируем .dockerignore
COPY .dockerignore .

# Копируем файлы package.json и package-lock.json и устанавливаем зависимости
COPY package*.json ./
RUN npm install

# Копируем остальные файлы проекта (исключая те, которые указаны в .dockerignore)
COPY . .

# Собираем приложение
RUN npm run build

# Запускаем встроенный веб-сервер Node.js для раздачи статики
CMD ["npm", "start"]

# Экспонируем порт 8000
EXPOSE 8000

