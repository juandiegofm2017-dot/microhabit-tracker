# Frontend - MicroHabit Tracker

## Descripción

Aplicación web desarrollada con React que proporciona la interfaz de usuario para MicroHabit Tracker. Permite a estudiantes universitarios registrar, monitorear y visualizar el progreso de sus micro-hábitos.

## Estructura del Proyecto

```
src/
├── components/          # Componentes reutilizables
│   ├── Header/
│   ├── Sidebar/
│   ├── HabitCard/
│   ├── HabitForm/
│   ├── ProgressChart/
│   ├── NotificationBadge/
│   └── Modal/
├── pages/               # Páginas/vistas principales
│   ├── LoginPage.jsx
│   ├── RegisterPage.jsx
│   ├── DashboardPage.jsx
│   ├── HabitDetailPage.jsx
│   ├── ProgressPage.jsx
│   ├── HistoryPage.jsx
│   └── AdminDashboardPage.jsx
├── hooks/               # Custom React Hooks
│   ├── useAuth.js
│   ├── useHabits.js
│   ├── useLocalStorage.js
│   └── useSocket.js
├── services/            # Servicios (API calls, WebSocket)
│   ├── api.js           # Configuración Axios
│   ├── authService.js
│   ├── habitService.js
│   ├── socketService.js
│   └── metricsService.js
├── utils/               # Funciones utilitarias
│   ├── helpers.js
│   ├── dateUtils.js
│   ├── validators.js
│   └── constants.js
├── assets/              # Recursos estáticos
│   ├── images/
│   ├── icons/
│   └── styles/
│       └── global.css
├── App.jsx              # Componente raíz
├── main.jsx             # Punto de entrada
└── index.css            # Estilos globales
```

## Instalación

```bash
cd frontend
npm install
```

## Ejecución en Desarrollo

```bash
npm run dev
```

La aplicación estará disponible en [http://localhost:5173](http://localhost:5173)

## Construcción para Producción

```bash
npm run build
```

Los archivos de construcción estarán en la carpeta `dist/`

## Vista Previa de Construcción

```bash
npm run preview
```

## Linting

```bash
npm run lint
```

## Estructura de Capas

### 1. Pages (Páginas)
Componentes principales que representan vistas/rutas de la aplicación

### 2. Components (Componentes)
Componentes reutilizables que se componen en las páginas

### 3. Services (Servicios)
Manejan comunicación con API backend y WebSockets

### 4. Hooks (Custom Hooks)
Lógica reutilizable específica de React (estado, efectos)

### 5. Utils (Utilidades)
Funciones auxiliares: formateo, validación, constantes

## Tecnologías Principales

- **React 18**: Librería de UI
- **React Router**: Enrutamiento
- **Axios**: Cliente HTTP
- **Socket.io Client**: Comunicación en tiempo real
- **Vite**: Build tool y dev server
- **CSS/Tailwind** (recomendado): Estilos

## Flujo de Datos Recomendado

1. **Componentes** disparan acciones del usuario
2. **Custom Hooks** manejan estado y efectos
3. **Services** comunican con el backend
4. **State Management** (useState/useContext) distribuye datos
5. **Componentes** se re-renderizan con nuevos datos

## Notas de Desarrollo

- Mantener componentes pequeños y reutilizables
- Usar hooks para lógica compartida
- Centralizar llamadas API en servicios
- Implementar manejo de errores en componentes
- Usar constantes para URLs, mensajes, etc.
- Documentar props complejos en componentes
- Preferir funciones puras en utils