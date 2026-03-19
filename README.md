# GiveSync Frontend

Aplicación web frontend para facilitar donaciones monetarias a instituciones benéficas.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![React Version](https://img.shields.io/badge/react-19.1.0-blue)](https://reactjs.org/)
[![Vite](https://img.shields.io/badge/vite-6.3.5-orange)](https://vitejs.dev/)

## Tabla de Contenidos

- [Descripción](#descripción)
- [Vista de la aplicación](#vista-de-la-aplicación)
- [Características Principales](#características-principales)
- [Tecnologías Utilizadas](#tecnologías-utilizadas)
- [Requisitos Previos](#requisitos-previos)
- [Instalación](#instalación)
- [Configuración de Variables de Entorno](#configuración-de-variables-de-entorno)
- [Uso de la Aplicación](#uso-de-la-aplicación)
- [Estructura del Proyecto](#estructura-del-proyecto)
- [Componentes Principales](#componentes-principales)
- [Licencia](#licencia)
- [Autores](#autores)

## Descripción

GiveSync Frontend es una aplicación web moderna desarrollada en React que proporciona una interfaz intuitiva para la plataforma de donaciones solidarias. La aplicación permite a los usuarios explorar instituciones benéficas, realizar donaciones monetarias, y gestionar sus perfiles, mientras que las instituciones pueden publicar actualizaciones sobre sus actividades y los administradores pueden supervisar toda la plataforma.

La interfaz está diseñada con una experiencia de usuario optimizada, incluyendo navegación fluida que facilita el acceso a todas las funcionalidades de la plataforma de donaciones.

## Vista de la aplicación

![3WithoutLogin](./docs/img/screenshots/general/3WithoutLogin.png)

### Panel de Usuario
![5InstitutionDetails](./docs/img/screenshots/general/5InstitutionDetails.png)
![6Donation](./docs/img/screenshots/general/6Donation.png)

### Panel de Institución
![1.1MyInstitution](./docs/img/screenshots/userWithInstitution/1.1MyInstitution.png)
![4ConfigurationPublication](./docs/img/screenshots/userWithInstitution/4ConfigurationPublication.png)

### Panel de Administrador
![2.1RequestFromInstitutions](./docs/img/screenshots/admin/2.1RequestFromInstitutions.png)

> **Nota:** Puede visualizar todas las imágenes de la aplicación en [Screenshots](docs/screenshots.md).

## Características Principales

- **Interfaz Moderna**: Diseño responsive y atractivo con Bootstrap
- **Navegación Intuitiva**: Sistema de rutas bien estructurado con React Router
- **Gestión de Estado**: Context API y hooks personalizados para manejo de estado
- **Notificaciones en Tiempo Real**: Sistema de notificaciones con Socket.IO
- **Formularios Optimizados**: Validación y manejo de formularios con react-hook-form
- **Autenticación Segura**: Integración con JWT del backend
- **Gestión de Instituciones**: Registro y validación de instituciones benéficas
- **Sistema de Donaciones**: Procesamiento seguro de donaciones monetarias
- **Publicaciones Multimedia**: Soporte para imágenes y texto en publicaciones
- **Panel Administrativo**: Gestión completa de usuarios e instituciones
- **Sistema de Comentarios**: Interacción entre usuarios e instituciones
- **Exportación de Datos**: Generación de reportes en Excel

## Tecnologías Utilizadas

### Frontend Core
- **React 19** - Biblioteca principal para la interfaz de usuario
- **Vite 6** - Herramienta de construcción y desarrollo
- **React Router DOM** - Gestión de rutas y navegación
- **Bootstrap 5** - Framework de CSS para estilos

### Estado y Datos
- **Context API** - Manejo de estado global
- **Axios** - Cliente HTTP para comunicación con la API
- **React Hook Form** - Manejo de formularios y validación

### UI/UX
- **React Bootstrap** - Componentes de Bootstrap para React
- **React Icons** - Biblioteca de iconos
- **Font Awesome** - Iconos adicionales
- **Lucide React** - Conjunto de iconos modernos
- **React Hot Toast** - Sistema de notificaciones
- **React Slick** - Componentes de carrusel

### Comunicación en Tiempo Real
- **Socket.IO Client** - Cliente para comunicación en tiempo real

### Desarrollo
- **ESLint** - Linting y calidad de código
- **Prop Types** - Validación de tipos de props

## Requisitos Previos

- Node.js >= 18.0.0
- npm >= 8.0.0
- Git
- Navegador web

## Instalación

Sigue estos pasos para configurar el proyecto en tu entorno local:

### 1. Clonar el repositorio
```bash
git clone https://github.com/gabrielpinula/GiveSync_Frontend.git
cd GiveSync_Frontend
```

### 2. Instalar dependencias
```bash
npm install
```

### 3. Configurar variables de entorno
Crea un archivo `.env` en la raíz del proyecto:

```bash
# Si no existe .env.example, créalo manualmente
touch .env
```

Edita el archivo `.env` con tu configuración (ver en la sección de configuración).

### 4. Asegurar que el backend esté corriendo

La aplicación frontend requiere que el backend esté funcionando en `http://localhost:3000` por defecto.

> Nota: Este frontend consume la API REST del backend.  
> Repositorio del backend: [GiveSync Backend](https://github.com/gabrielpinula/GiveSync_Backend)

### 5. Ejecutar la aplicación
```bash
# Modo desarrollo con recarga
npm run dev

# Modo producción después de construir
npm run preview
```

La aplicación se iniciará en `http://localhost:5173` por defecto.

## Configuración de Variables de Entorno

Crea un archivo `.env` en la raíz del proyecto con las siguientes variables:

```env
# API URL
VITE_API_URL=http://localhost:3000
```

> Nota: Las variables de entorno en Vite deben comenzar con `VITE_` para ser accesibles en el frontend.

## Uso de la Aplicación

### Iniciar el servidor de desarrollo
```bash
npm run dev
```

### Construir para producción
```bash
npm run build
```

### Previsualizar la construcción
```bash
npm run preview
```

### Verificar el linting
```bash
npm run lint
```

### Flujo de uso típico

1. **Exploración**: Los usuarios no registrados pueden explorar instituciones y ver publicaciones
2. **Registro/Login**: Los usuarios se registran o inician sesión para acceder a funcionalidades completas
3. **Donaciones**: Usuarios autenticados pueden realizar donaciones a instituciones
4. **Solicitud de Institución**: Usuarios pueden solicitar el registro de nuevas instituciones
5. **Publicaciones**: Las instituciones pueden compartir actualizaciones sobre sus actividades
6. **Administración**: Los administradores gestionan usuarios, instituciones y donaciones

## Estructura del Proyecto

```
GiveSync_Frontend/
├── public/                     # Archivos estáticos
├── src/                        # Código fuente principal
│   ├── components/             # Componentes reutilizables
│   │   ├── Login/              # Componentes de login
│   │   ├── Register/           # Componentes de registro
│   │   ├── comments/           # Sistema de comentarios
│   │   ├── layout/             # Componentes de estructura
│   │   ├── publication/        # Componentes de publicaciones
│   │   ├── ServiceUnavailable/ # Página de servicio no disponible
│   │   └── underConstruction/  # Páginas en construcción
│   ├── pages/                  # Páginas principales
│   │   ├── AdminPage/          # Página de administrador
│   │   ├── Auth/               # Página de autenticación
│   │   ├── MainPage/           # Página principal
│   │   ├── SectionInstitutionPage/ # Gestión de instituciones
│   │   ├── UserSettingsPage/   # Configuración de usuario
│   │   ├── CommentsPage/       # Página de comentarios
│   │   └── NotFound/           # Página 404
│   ├── services/               # Servicios de API
│   │   └── api.js              # Configuración y servicios HTTP
│   ├── shared/                 # Componentes y utilidades compartidas
│   │   ├── hooks/              # Hooks personalizados
│   │   ├── utils/              # Funciones utilitarias
│   │   └── validators/         # Validaciones de formularios
│   ├── context/                # Contextos de React
│   ├── assets/                 # Recursos estáticos
│   ├── routes.jsx              # Configuración de rutas
│   ├── App.jsx                 # Componente principal
│   ├── main.jsx                # Punto de entrada
│   ├── App.css                 # Estilos globales
│   └── index.css               # Estilos de la aplicación
├── docs/                       # Documentación
│   └── img/screenshots/         # Capturas de pantalla
├── .env                        # Variables de entorno (no versionado)
├── .gitignore                  # Archivos ignorados por Git
├── eslint.config.js            # Configuración de ESLint
├── index.html                  # Plantilla HTML
├── package.json                # Dependencias y scripts
├── vite.config.js              # Configuración de Vite
└── README.md                   # Documentación del proyecto
```

## Componentes Principales

### Autenticación
- **AuthPage**: Página principal de autenticación (login/registro)
- **Login**: Componente de inicio de sesión
- **Register**: Componente de registro de usuarios

### Páginas Principales
- **WelcomePage**: Página de bienvenida y landing
- **HomePage**: Página principal con lista de instituciones
- **InstitutionDetail**: Vista detallada de instituciones
- **AddDonationPage**: Formulario para realizar donaciones
- **CommentsPage**: Página de comentarios de publicaciones

### Administración
- **AdminPage**: Panel de administración principal
- **AllDonationsMade**: Historial de donaciones realizadas
- **ListOfInstitutions**: Gestión de instituciones
- **RegisteredUsers**: Gestión de usuarios registrados
- **RequestFromInstitutions**: Solicitudes de registro de instituciones

### Gestión de Instituciones
- **SectionInstitutionPage**: Panel principal para instituciones
- **MyInstitution**: Vista de información de la institución
- **ConfigurationOfTheInstitution**: Configuración de datos de institución
- **DonationsToMyInstitution**: Donaciones recibidas
- **ConfigurationPublication**: Gestión de publicaciones

### Configuración de Usuario
- **UserSettingsPage**: Panel de configuración de usuario
- **UserInformation**: Información personal del usuario
- **DonationHistory**: Historial de donaciones realizadas
- **RequestToRegisterAnInstitution**: Solicitud para registrar institución

### Componentes UI Comunes
- **Input.jsx**: Componente de entrada reutilizable
- **layout/**: Componentes de estructura general (navbar, footer, sidebar, etc.)
- **comments/**: Componentes para sistema de comentarios
- **publication/**: Componentes para gestión de publicaciones

### Servicios y Utilidades
- **api.js**: Configuración base de Axios y todos los servicios HTTP
- **shared/hooks/**: Hooks personalizados de React
- **shared/utils/**: Funciones utilitarias (decodeToken, ProtectedRoute)
- **shared/validators/**: Validaciones de formularios

### Rutas Protegidas
- **ProtectedRoute**: Protección para usuarios autenticados
- **ProtectedRouteAdmin**: Protección para administradores
- **ProtectedRouteInstitution**: Protección para instituciones

## Licencia

Este proyecto está licenciado bajo la Licencia MIT. Consulta el archivo [LICENSE](LICENSE) para más detalles.

## Autores

- **Gabriel Pinula (GP)** - Desarrollo Principal - [gabrielpinula](https://github.com/gabrielpinula)
- **Marcos Pamal (MP)** - Desarrollo y Colaboración - [mpamal-2023046](https://github.com/mpamal-2023046)
- **Kenny Terraza (KT)** - Desarrollo y Colaboración - [kterraza-2023022](https://github.com/kterraza-2023022)
- **Dylan Julian (DJ)** - Desarrollo y Colaboración - [djulian-2023098](https://github.com/djulian-2023098)
- **Andre Figueroa (AF)** - Desarrollo y Colaboración - [afigueroa-2023106](https://github.com/afigueroa-2023106)

## Contacto

Si tienes alguna pregunta o sugerencia, no dudes en contactarnos:

- **Email**: gpinula-2020433@kinal.edu.gt
- **GitHub Issues**: [Issues del Proyecto](https://github.com/gabrielpinula/GiveSync_Frontend/issues)

Gracias por tu interés en este proyecto y por contribuir a hacer del mundo un lugar mejor a través de las donaciones solidarias.