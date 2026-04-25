# Backend - MicroHabit Tracker

## Descripción

API REST desarrollada con Node.js y Express para MicroHabit Tracker. Gestiona la autenticación, operaciones CRUD de hábitos, lógica de negocio y comunicación en tiempo real mediante WebSockets.

## Estructura del Proyecto

```
src/
├── config/             # Configuraciones globales
│   ├── database.js     # Conexión MongoDB
│   ├── socket.js       # Configuración Socket.io
│   └── constants.js    # Constantes de la aplicación
├── controllers/        # Controladores (lógica de rutas)
│   ├── authController.js
│   ├── habitController.js
│   ├── habitCheckInController.js
│   ├── userController.js
│   └── adminController.js
├── routes/             # Definición de rutas
│   ├── authRoutes.js
│   ├── habitRoutes.js
│   ├── userRoutes.js
│   ├── adminRoutes.js
│   └── index.js
├── models/             # Modelos Mongoose
│   ├── User.js
│   ├── Habit.js
│   ├── HabitCheckIn.js
│   └── Notification.js
├── services/           # Lógica de negocio
│   ├── authService.js
│   ├── habitService.js
│   ├── notificationService.js
│   └── metricsService.js
├── middlewares/        # Middlewares Express
│   ├── authMiddleware.js
│   ├── errorHandler.js
│   ├── validator.js
│   └── corsMiddleware.js
├── utils/              # Funciones utilitarias
│   ├── helpers.js
│   ├── logger.js
│   └── errorMessages.js
├── index.js            # Punto de entrada
└── .env.example        # Ejemplo de variables de entorno
```

## Instalación

```bash
cd backend
npm install
```

## Configuración

1. Crear archivo `.env` basándose en `.env.example`
2. Configurar variables de entorno:
   - `MONGODB_URI`: Conexión a MongoDB
   - `JWT_SECRET`: Secreto para JWT
   - `PORT`: Puerto del servidor (default: 5000)
   - `NODE_ENV`: Ambiente (development/production)

## Ejecución en Desarrollo

```bash
npm run dev
```

El servidor estará disponible en [http://localhost:5000](http://localhost:5000)

## Ejecución en Producción

```bash
npm start
```

## Linting

```bash
npm run lint
```

## Estructura de Capas

### 1. Routes (Rutas)
Define los endpoints de la API y mapea con controladores

### 2. Controllers (Controladores)
Recibe solicitudes HTTP, valida datos y delega a servicios

### 3. Services (Servicios)
Contiene lógica de negocio principal

### 4. Models (Modelos)
Define esquemas y estructura de datos en MongoDB

### 5. Middlewares
Funciones que procesan solicitudes (autenticación, validación, etc)

## Tecnologías Principales

- **Express**: Framework web
- **MongoDB + Mongoose**: Base de datos y ODM
- **JWT**: Autenticación segura
- **Socket.io**: WebSockets en tiempo real
- **bcryptjs**: Hash de contraseñas
- **express-validator**: Validación de datos

## Notas de Desarrollo

- Separar lógica de negocio en servicios
- Usar middlewares para concerns transversales
- Implementar manejo de errores consistente
- Documentar endpoints en comentarios
- Seguir patrón RESTful para rutas
- Validar entrada en controladores y servicios