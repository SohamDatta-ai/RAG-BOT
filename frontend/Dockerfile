FROM node:20-alpine

WORKDIR /app

# Accept build arguments
ARG NEXT_PUBLIC_BACKEND_API_URL
ARG NEXT_PUBLIC_BACKEND_API_PREFIX
ARG NEXT_PUBLIC_API_PREFIX
ARG NEXT_PUBLIC_DOMAIN_URL

# Set environment variables for build
ENV NEXT_PUBLIC_BACKEND_API_URL=$NEXT_PUBLIC_BACKEND_API_URL
ENV NEXT_PUBLIC_BACKEND_API_PREFIX=$NEXT_PUBLIC_BACKEND_API_PREFIX
ENV NEXT_PUBLIC_API_PREFIX=$NEXT_PUBLIC_API_PREFIX
ENV NEXT_PUBLIC_DOMAIN_URL=$NEXT_PUBLIC_DOMAIN_URL

# Install pnpm
RUN npm install -g pnpm && apk add --no-cache dos2unix

# Copy package files
COPY package*.json ./
RUN pnpm install

# Copy source code
COPY . .

# Build the application
# RUN pnpm run build

# Expose port
EXPOSE 3001

# Start inline to avoid Windows line-ending issues with scripts
CMD ["/bin/sh", "-lc", "if [ \"$NODE_ENV\" = \"development\" ]; then pnpm run dev -- -p 3001 -H 0.0.0.0; else pnpm run build && pnpm run start -- -p 3001 -H 0.0.0.0; fi"]
