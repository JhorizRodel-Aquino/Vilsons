FROM node:18-alpine

WORKDIR /app

# 1. FIRST copy ONLY package files
COPY package*.json ./

# 2. Copy Prisma schema BEFORE npm install
COPY prisma ./prisma/

# 3. NOW install dependencies (prisma generate will work)
RUN npm install

# 4. Generate Prisma Client (optional, already done in postinstall)
RUN npx prisma generate

# 5. Copy the rest of the application
COPY . .

EXPOSE 3000

CMD ["npm", "run", "dev"]