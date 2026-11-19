# TVORIBOX

Интернет-магазин наборов для творчества одного продавца (Алматы, Астана; интерфейс на русском и казахском).

**Статус:** этап проектирования — архитектура готова, код ещё не написан.

Подробное описание (роли, правила, база данных, API, страницы): [docs/architecture.md](docs/architecture.md).

## Стек

| Часть | Технологии |
|---|---|
| Клиент (`client/`) | React (Vite) |
| Сервер (`server/`) | Node.js, Express |
| База данных | PostgreSQL, Prisma |

## Как запустить (когда появится код)

Нужны Node.js и PostgreSQL.

```bash
# сервер
cd server
npm install
cp .env.example .env      # заполнить значения
npx prisma migrate dev    # создать таблицы
npx prisma db seed        # категории и первый администратор
npm run dev

# клиент (в другом терминале)
cd client
npm install
npm run dev
```

## Переменные окружения (`server/.env`)

| Переменная | Что это |
|---|---|
| `DATABASE_URL` | адрес базы данных PostgreSQL |
| `JWT_SECRET` | секретный ключ для токенов входа |
| `PORT` | порт сервера |
| `CLIENT_URL` | адрес клиента (для CORS) |
| `DELIVERY_PRICE_ALMATY` | стоимость курьера по Алматы, ₸ |
| `DELIVERY_PRICE_ASTANA` | стоимость курьера по Астане, ₸ |
| `FREE_DELIVERY_FROM` | сумма товаров, от которой доставка бесплатна, ₸ |
| `PICKUP_ADDRESS_ALMATY` | адрес самовывоза (только Алматы) |

Файл `.env` нельзя публиковать в git. В репозитории хранится только `.env.example`.
