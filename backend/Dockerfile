# بنستخدم نسخة خفيفة من Node.js (أو اللغة اللي تحبها)
FROM node:18-alpine

# تحديد الفولدر اللي هنشتغل فيه جوه الـ Container
WORKDIR /app

# نسخ ملفات التعريف وتنزيل المكتبات
COPY package*.json ./
RUN npm install

# نسخ باقي الكود
COPY . .

# البورت اللي الـ Backend هيشتغل عليه (زي ما في الرسمة)
EXPOSE 3000

CMD ["npm", "start"]
