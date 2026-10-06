# Harmoniq

![Головна сторінка Harmoniq](assets/harmoniq-preview.webp)

**Harmoniq** — командний full-stack вебзастосунок, створений у межах навчальної програми GoIT. Це платформа для читання й публікації статей, пошуку авторів та взаємодії зі спільнотою.

[🌐 Демо](https://project-webcrafters-03-frontend.vercel.app) · [📦 Основний репозиторій](https://github.com/vitaliypolets/project-webcrafters-03)

> Цей репозиторій є fork оригінального командного проєкту.

---

## ✨ Основні можливості

- перегляд популярних статей і повного каталогу публікацій;
- сторінки окремих статей та авторів;
- реєстрація, авторизація і керування сесією;
- створення, редагування та видалення власних статей;
- додавання публікацій до закладок;
- перегляд профілю та керування даними користувача;
- завантаження зображень через Cloudinary;
- адаптивний інтерфейс для мобільних пристроїв, планшетів і десктопів.

---

## 👩‍💻 Мій внесок

На цьому проєкті моєю зоною відповідальності були **AuthorsPage та загальні дані окремого автора**.

### Frontend

- реалізувала сторінку списку авторів за маршрутом `/authors`;
- створила сторінку профілю автора `/authors/[userId]`;
- розробила компоненти списку й картки автора, типи та API-сервіси;
- реалізувала посторінкове завантаження авторів через `useInfiniteQuery`;
- додала кешування та попереднє завантаження наступної сторінки за допомогою TanStack Query;
- реалізувала кнопку **Load More**, стани завантаження й помилок та плавний перехід до нової порції даних;
- використала `next/image` для аватарів і створила адаптивне оформлення сторінок;
- додала Next.js Route Handler `/api/users/[userId]`, який працює як BFF-проксі до Express API.

### Backend

- реалізувала публічний endpoint `GET /api/users/:userId`;
- створила окремий модуль `users/details` із route, controller, service і validation;
- додала перевірку валідності MongoDB ObjectId;
- реалізувала отримання основних даних користувача та підрахунок кількості його статей;
- передбачила контрольовані відповіді для невалідного ID і відсутнього користувача.

> Моя зона відповідальності охоплювала загальні дані автора. Список статей автора реалізовував інший учасник команди.

---

## 🧰 Технологічний стек

| Частина | Технології |
| --- | --- |
| Frontend | Next.js 16, React 19, TypeScript, CSS Modules |
| Робота з API | Axios, TanStack Query, Next.js Route Handlers |
| Global State | Zustand |
| Форми та валідація | Formik, Yup |
| Backend | Node.js, Express 5, JavaScript |
| База даних | MongoDB, Mongoose |
| Авторизація | JWT, bcrypt |
| Робота із зображеннями | Multer, Cloudinary, Next/Image |
| Документація API | Swagger / OpenAPI |
| Якість коду | ESLint, Prettier |
| Деплой | Vercel, Render |

---

## 🏗️ Архітектура

Проєкт організований як monorepo з npm workspaces:

- `frontend/` — застосунок на Next.js App Router;
- `backend/` — окремий REST API на Node.js та Express.

Клієнтська частина надсилає запити до `/api/...` через Axios. Next.js Route Handlers виконують роль proxy/BFF і передають запити до Express Backend. Сервер відповідає за бізнес-логіку, авторизацію та взаємодію з MongoDB через Mongoose.

TanStack Query використовується для server state, кешування й мутацій, а Zustand — для глобального client state.

---

## 📚 Документація

- [API Contract](docs/API_CONTRACT.md)
- [API Conventions](docs/API_CONVENTIONS.md)
- [Ownership Map](docs/OWNERSHIP_MAP.md)
- [Frontend Layout Guide](docs/FRONTEND_LAYOUT_GUIDE.md)
- [Git Workflow](docs/GIT_WORKFLOW.md)
- [Team Rules](docs/TEAM_RULES.md)

---

## 🚀 Локальний запуск

1. Клонуйте репозиторій:

```bash
git clone https://github.com/Anastasiia-Kosh/Garmoniq.git
cd Garmoniq
```

2. Встановіть залежності:

```bash
npm install
```

3. Створіть локальні файли змінних середовища на основі:

- `frontend/.env.example`;
- `backend/.env.example`.

4. Запустіть frontend і backend одночасно:

```bash
npm run dev
```

Окремий запуск:

```bash
npm run dev:frontend
npm run dev:backend
```

# Макет

[Figma](https://www.figma.com/design/tWO4RvXS2zFhL9keRcNJtb/Harmoniq?node-id=6-39&p=f&t=FNQA1ISKPXym9aTV-0)
