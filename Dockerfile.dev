FROM node:20

# Set working directory
WORKDIR /app

# Copy dependency files
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy application source
COPY . .

# Copy wait-for-it script
COPY wait-for-it.sh /usr/local/bin/wait-for-it.sh
RUN chmod +x /usr/local/bin/wait-for-it.sh

# Expose port
EXPOSE 3000

# Wait for DB, then start app
ENTRYPOINT ["wait-for-it.sh", "blog-db:3306", "--"]
CMD ["npm", "run", "dev"]




# # docker build --platform platform-name --no-cache -t usr-name/image-name:version .