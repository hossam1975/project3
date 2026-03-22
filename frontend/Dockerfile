# المرحلة الأولى: Build للكود
FROM node:18-alpine AS build
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

# المرحلة الثانية: تشغيل الكود على Nginx
FROM nginx:stable-alpine
# بنسخ الملفات اللي طلعت من الـ build لفولدر Nginx
COPY --from=build /app/dist /usr/share/nginx/html
# نسخ إعدادات Nginx الخاصة بينا لو محتاجين
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
