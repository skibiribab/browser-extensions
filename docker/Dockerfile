# Multi-stage CI for skibiribab/browser-extensions — lint → unit → build

FROM skibiribab/cli:1.8.0-node AS lint

WORKDIR /workspace
COPY . .
RUN cli repo lint /workspace

FROM node:22-slim AS deps

WORKDIR /app
COPY package.json package-lock.json ./
RUN npm ci

COPY . .

FROM deps AS unit-test

RUN npm run test:coverage

FROM deps AS build

RUN npm run build
