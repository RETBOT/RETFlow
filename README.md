# RETFlow CRM

> **Estructura y control para tu operación comercial**

Sistema de gestión de relaciones con clientes (CRM) desarrollado para **RETEX** - Relationship Execution & Tracking Excellence.

[![License](https://img.shields.io/badge/license-ISC-blue.svg)](LICENSE)
[![React](https://img.shields.io/badge/React-19.0-61DAFB?logo=react)](https://reactjs.org)
[![Node.js](https://img.shields.io/badge/Node.js-20+-339933?logo=node.js)](https://nodejs.org)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.9-3178C6?logo=typescript)](https://www.typescriptlang.org)
[![SQL Server](https://img.shields.io/badge/SQL_Server-CC2927?logo=microsoftsqlserver)](https://www.microsoft.com/sql-server)

---

## Acerca del Proyecto

RETFlow es un sistema CRM completo diseñado para gestionar la operación comercial de equipos de ventas. Permite administrar clientes, prospectos, actividades, oportunidades y generar reportes ejecutivos en tiempo real.

El sistema fue construido con un enfoque moderno, utilizando **agentes de inteligencia artificial** como herramienta de desarrollo para acelerar la implementación manteniendo alta calidad de código.

> Los repositorios con el código fuente (frontend y backend) son privados. Este repositorio es un showcase del proyecto.

**RETEX** = Relationship Execution & Tracking Excellence  
**RETFlow** = Relationship Execution & Tracking Flow

---

## Metodología de Desarrollo

Este proyecto fue desarrollado utilizando **agentes de inteligencia artificial** como herramienta principal de desarrollo. El flujo de trabajo permitió:

- **Planificación automatizada**: Los agentes analizaron requisitos y crearon roadmaps de implementación
- **Código estructurado**: Generación de módulos siguiendo patrones consistentes (controllers, services, routes)
- **Documentación integrada**: Actualización simultánea de README y CHANGELOG
- **Validación continua**: Verificación de código y consistencia entre frontend y backend
- **Iteración rápida**: Múltiples funcionalidades implementadas en ciclos cortos

### Stack Tecnológico

#### Frontend
| Tecnología | Versión | Propósito |
|------------|---------|-----------|
| React | 19.0 | Framework de UI |
| Vite | 7.0 | Bundler y dev server |
| Tailwind CSS | 3.3 | Framework de estilos |
| React Router | 6.30 | Navegación |
| Material Tailwind | 2.1.4 | Componentes UI |
| Recharts | 3.1.0 | Gráficos estadísticos |
| Leaflet | 1.9.4 | Mapas interactivos |
| React Big Calendar | 1.19.4 | Calendario de actividades |

#### Backend
| Tecnología | Versión | Propósito |
|------------|---------|-----------|
| Node.js | 20+ | Runtime de JavaScript |
| Express | 5.2 | Framework web |
| TypeScript | 5.9 | Lenguaje tipado |
| SQL Server | - | Base de datos |
| JWT | 9.0 | Autenticación |
| Zod | 4.3.6 | Validación de datos |
| ExcelJS | 4.4.0 | Exportación a Excel |
| PDFKit | 0.18.0 | Generación de PDFs |
| Nodemailer | 8.0 | Envío de emails |
| Google APIs | 171.4 | Integración Google |

---

## Arquitectura

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                              FRONTEND (React)                                │
│                                                                              │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐     │
│  │Dashboard │  │ Clientes │  │ Prospectos│  │ Contactos│  │   Mapa   │     │
│  └────┬─────┘  └────┬─────┘  └────┬─────┘  └────┬─────┘  └────┬─────┘     │
│       └──────────────┼─────────────┼─────────────┼─────────────┘           │
│                      └──────────────┼─────────────┘                          │
│  ┌──────────┐  ┌──────────┐  ┌─────┴──────┐  ┌──────────┐  ┌──────────┐  │
│  │Oportunida│  │Productos │  │Actividades │  │ Reportes │  │  Admin   │  │
│  │   des    │  │          │  │            │  │          │  │          │  │
│  └────┬─────┘  └────┬─────┘  └─────┬──────┘  └────┬─────┘  └────┬─────┘   │
│       └──────────────┼─────────────┼─────────────┼─────────────┘          │
│                      └──────────────┼─────────────┘                         │
│                                     │                                        │
│                            API REST (JWT Bearer)                             │
└─────────────────────────────────────┼────────────────────────────────────────┘
                                      │
┌─────────────────────────────────────┼────────────────────────────────────────┐
│                             BACKEND (Express)                                │
│                                                                              │
│  ┌──────────┐  ┌──────────┐  ┌─────┴──────┐  ┌──────────┐  ┌──────────┐  │
│  │   Auth   │  │  Admin   │  │ Customers  │  │ Activities│  │Opportunit│  │
│  │  Module  │  │  Module  │  │  Module    │  │  Module   │  │  Module  │  │
│  └──────────┘  └──────────┘  └────────────┘  └───────────┘  └──────────┘  │
│                                                                              │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐    │
│  │ Reports  │  │ Products  │  │  Email    │  │ Calendar │  │  Scope   │    │
│  │  Module  │  │  Module   │  │  Module   │  │  Module  │  │  Module  │    │
│  └──────────┘  └──────────┘  └──────────┘  └──────────┘  └──────────┘    │
│                                                                              │
│                                     │                                        │
│                              ┌──────┴──────┐                                 │
│                              │ SQL Server  │                                 │
│                              │  crm_core   │                                 │
│                              └─────────────┘                                 │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## Funcionalidades

### 1. Autenticación y Seguridad

El sistema implementa un flujo de autenticación robusto con las siguientes características:

**Inicio de Sesión**
- Formulario profesional con logo RETEX
- Validación de credenciales en backend
- Generación de JWT (access token) y refresh token
- Almacenamiento seguro de tokens en el cliente
- Protección de rutas por autenticación

**Recuperación de Contraseña**
- Solicitud de recuperación por email
- Generación de token único con hash SHA-256
- Enlace de recuperación válido por 1 hora
- Restablecimiento de contraseña con validación de token
- Tokens de un solo uso

**Seguridad**
- Middleware de autenticación JWT en todos los endpoints
- Rate limiting para prevenir ataques de fuerza bruta
- Validación de esquemas con Zod
- Sanitización de inputs contra XSS
- CORS configurado para producción

---

### 2. Dashboard Ejecutivo

El panel de control proporciona una visión completa del estado del negocio:

**KPIs en Tiempo Real**
- Ventas del mes actual
- Porcentaje de meta alcanzada
- Oportunidades ganadas en el período
- Nuevos clientes registrados

**Gráficos Interactivos**
- Tendencia de ventas (línea temporal)
- Distribución de oportunidades por etapa (donut)
- Actividades por estatus (barras)
- Top vendedores del período

**Widgets de Alerta**
- Contador de actividades vencidas
- Lista resumida de actividades pendientes
- Notificaciones del sistema

**Tablas de Resumen**
- Últimas 5 oportunidades activas
- Clientes con cartera vencida

---

### 3. Gestión de Clientes y Prospectos

El sistema permite administrar tanto clientes como prospectos con funcionalidades completas:

**Listado de Clientes/Prospectos**
- Tabla con columnas: Nombre, RFC, Estatus, Sucursal, Venta Neta
- Búsqueda con debounce de 400ms
- Filtros por estatus, sucursal, ruta
- Paginación de resultados
- Botón para crear nuevo cliente/prospecto

**Formulario de Cliente/Prospecto**
- Datos básicos: nombre, RFC, email, teléfono
- Información fiscal y dirección
- Geolocalización con mapa integrado (Leaflet + Nominatim)
- Sucursal y ruta asignadas
- Análisis financiero: venta neta, margen, línea de crédito, cartera vencida
- Badges de estado: Activo, Inactivo, Hold, Cartera Vencida

**Detalle del Cliente (5 tabs)**
1. **Detalles**: Información completa del cliente
2. **Análisis**: Métricas financieras y KPIs
3. **Contactos**: Lista de contactos asociados
4. **Oportunidades**: Pipeline del cliente
5. **Actividades**: Historial de actividades

**Conversión de Prospecto a Cliente**
- Un clic para convertir prospecto a cliente
- Preserva todo el historial
- Mantiene los contactos asociados

---

### 4. Gestión de Contactos

Cada cliente/prospecto puede tener múltiples contactos asociados:

**CRUD de Contactos**
- Nombre, puesto, departamento
- Teléfono, extensión, WhatsApp
- Email
- Comentarios adicionales

**Búsqueda**
- Por nombre o puesto
- Filtrado por cliente

**Integración**
- Click-to-call para teléfonos
- Click-to-email para enviar correos
- Asociación automática a actividades

---

### 5. Mapa Interactivo

Visualización geográfica de todos los clientes en un mapa interactivo:

**Visualización**
- Mapa con OpenStreetMap como base
- Marcadores de clientes con clustering automático
- Colores por estatus: verde (activo), gris (inactivo)
- Popups con información resumida al hacer clic

**Navegación**
- Botón "Mi ubicación" para centrar en posición GPS
- Búsqueda de direcciones con Nominatim
- Zoom y paneo fluido

**Optimización de Rutas**
- Seleccionar múltiples clientes en el mapa
- Cálculo de ruta optimizada con OSRM
- Polilínea siguiendo calles reales
- Marcadores numerados en cada parada
- Panel con distancias y tiempos estimados
- Botón para iniciar navegación externa

**Filtros**
- Por estatus (activo/inactivo)
- Por sucursal
- Por ruta/vendedor
- Búsqueda por nombre

**Persistencia de Estado**
- Posición del mapa, zoom y filtros guardados en URL
- Compartir enlaces del mapa con estado

---

### 6. Pipeline de Oportunidades

Gestión visual del embudo de ventas:

**Vista Kanban**
- 4 columnas: Prospecto, Calificado, Propuesta, Ganada
- Cards con nombre de oportunidad y monto
- Totales visibles arriba de cada columna
- Drag & drop para mover entre etapas

**Gestión de Oportunidades**
- Nombre, descripción, fecha de cierre
- Monto total y probabilidad
- Cliente asociado
- Vendedor responsable

**Items de Oportunidad**
- Agregar productos a la oportunidad
- Editar cantidades y precios
- Cálculo automático de totales
- Control de precios con permisos

**Filtros**
- Por etapa del pipeline
- Por vendedor
- Por rango de fechas

---

### 7. Actividades con GPS

Sistema completo de gestión de actividades comerciales:

**Tipos de Actividad**
- Llamada
- Correo
- Visita
- Reunión
- Tarea

**Creación de Actividades**
- Selector de cliente y contacto
- Tipo de actividad
- Fecha y hora
- Notas descriptivas
- Asignación a usuario

**Completar/Cancelar**
- Marcar como completada o cancelada
- Agregar notas de resultado
- **Check-in GPS**: para Visitas y Reuniones
  - Captura de coordenadas
  - Nota mínima de 10 caracteres
  - Advertencia si precisión GPS > 150m
  - Append al historial de notas

**Estados**
- Pendiente
- Programada (cuando tiene fecha asignada)
- Completada
- Cancelada
- Vencida (automático si fecha pasó sin completar)

**Alertas Visuales**
- Borde rojo para vencidas
- Fecha en color rojo
- Badge con días de retraso

**Filtros**
- Por estatus
- Por tipo
- Por vendedor
- Búsqueda por texto

---

### 8. Catálogo de Productos

Gestión del catálogo de productos:

**Listado**
- Código, nombre, descripción
- Categoría
- Precio actual
- Stock

**CRUD de Productos**
- Crear productos con toda la información
- Editar detalles y precios
- Categorización por tipo
- Historial de cambios de precio

**Control de Precios**
- Permiso especial para editar precios
- Historial de modificaciones

---

### 9. Reportes y Exportación

Centro de reportes completo con múltiples vistas:

**Tipos de Reporte**
1. **Dashboard**: KPIs ejecutivos, tendencias, distribución
2. **Ventas**: Por período, vendedor, producto
3. **Clientes**: Nuevos clientes, recurrentes, actividad
4. **Actividades**: Por estatus, tipo, vendedor, tendencia
5. **Oportunidades**: Pipeline, tasa de éxito, por vendedor
6. **Productos**: Por categoría, stock, precios

**Filtros**
- Rango de fechas
- Vendedor
- Sucursal
- Otros criterios según tipo de reporte

**Exportación**
- **Excel**: Multi-hoja con portada profesional, formato MXN
- **PDF**: Portada corporativa, tabla de contenido, secciones
- **CSV**: UTF-8 con BOM para Excel

**Vistas Guardadas**
- Guardar configuraciones de filtros con nombre
- Cargar vistas previamente guardadas
- Eliminar vistas que no se necesitan

**Reportes Programados**
- Programar envío automático por email
- Frecuencias: diaria, semanal, mensual
- Múltiples destinatarios
- Activar/desactivar sin eliminar

---

### 10. Email y Calendario

**Integración con Email**
- Conexión via OAuth2 (Gmail/Outlook)
- Envío de correos desde el CRM
- Historial de correos enviados
- Plantillas de correo personalizables
- Tracking de aperturas y clics
- Firmas de correo por usuario

**Calendario**
- Sincronización con Google Calendar y Outlook
- Vista unificada de eventos + actividades CRM
- Crear actividad desde evento externo
- Sincronización bidireccional

---

### 11. Administración

Panel completo para gestionar usuarios, roles y permisos:

**Gestión de Usuarios**
- Crear usuarios
- Editar nombre, email, sucursal
- Activar/inactivar usuarios
- Resetear contraseña manualmente
- Enviar enlace de recuperación por email

**Roles**
- Crear y eliminar roles
- Asignar permisos a roles
- Roles predefinidos: Admin, Vendedor, Solo lectura

**Permisos (31 en total)**
- **Administración**: users.manage, roles.manage, scope.manage
- **Clientes**: read, create, update, delete
- **Prospectos**: read, create, update, delete, convert
- **Actividades**: create, update, complete, assign
- **Oportunidades**: create, update, delete, price.edit, items.*
- **Productos**: create, update, delete, price.edit
- **Reportes**: view, export, scheduled, saved_views

**Alcance de Datos**
- **ALL**: Ve todos los datos
- **BRANCH**: Solo datos de su sucursal
- **ROUTE**: Solo datos de su ruta/vendedor
- Configurable por usuario

---

### 12. Notificaciones

Sistema de notificaciones en tiempo real:

- Notificaciones del sistema
- Marcar como leídas
- Marcar todas como leídas
- Badge en navbar con contador

---

## Endpoints de la API

### Autenticación
| Método | Ruta | Descripción |
|--------|------|-------------|
| POST | `/api/login/access` | Iniciar sesión |
| POST | `/api/login/refresh_token` | Renovar token |
| POST | `/api/login/forgotpwd` | Solicitar recuperación |
| POST | `/api/login/reset-password` | Restablecer contraseña |

### Dashboard
| Método | Ruta | Permiso | Descripción |
|--------|------|---------|-------------|
| GET | `/api/dashboard/home` | Auth | Panel de control |
| GET | `/api/dashboard/overdue` | Auth | Actividades vencidas |

### Clientes y Prospectos
| Método | Ruta | Permiso | Descripción |
|--------|------|---------|-------------|
| POST | `/api/cn/clientes` | Auth | Listar clientes/prospectos |
| POST | `/api/cn/clientes_abc` | Auth | Crear/editar cliente |
| POST | `/api/cn/contactos` | Auth | Listar contactos |
| POST | `/api/cn/contactos_abc` | Auth | Crear/editar contacto |
| POST | `/api/cn/convertir_prospecto` | Auth | Convertir a cliente |

### Actividades
| Método | Ruta | Permiso | Descripción |
|--------|------|---------|-------------|
| POST | `/api/cn/actividades` | Auth | Listar actividades |
| POST | `/api/cn/actividades_crear` | Auth | Crear actividad |
| POST | `/api/cn/actividades_actualizar` | Auth | Actualizar actividad |
| POST | `/api/cn/actividades_completar` | Auth | Completar/cancelar |
| POST | `/api/cn/actividades_asignar` | Auth | Asignar actividad |
| POST | `/api/cn/actividades_checkins` | Auth | Listar check-ins |

### Oportunidades
| Método | Ruta | Permiso | Descripción |
|--------|------|---------|-------------|
| POST | `/api/cn/oportunidades` | Auth | Listar oportunidades |
| POST | `/api/cn/oportunidades_abc` | Auth | CRUD oportunidades |
| POST | `/api/cn/oportunidades_items` | Auth | Gestionar items |

### Reportes
| Método | Ruta | Permiso | Descripción |
|--------|------|---------|-------------|
| POST | `/api/reports/*` | Auth | Generación de reportes |
| POST | `/api/reports/export` | Auth | Exportar datos |
| GET/POST | `/api/reports/saved-views` | Auth | Vistas guardadas |
| GET/POST | `/api/reports/scheduled` | Auth | Reportes programados |

### Email
| Método | Ruta | Permiso | Descripción |
|--------|------|---------|-------------|
| POST | `/api/email/connect` | Auth | Conectar cuenta OAuth |
| POST | `/api/email/send` | Auth | Enviar correo |
| GET | `/api/email/history` | Auth | Historial de correos |
| GET | `/api/email-advanced/templates` | Auth | Plantillas de correo |

### Administración
| Método | Ruta | Permiso | Descripción |
|--------|------|---------|-------------|
| GET/POST | `/api/admin/users` | Auth | Gestión de usuarios |
| GET/POST | `/api/admin/roles` | Auth | Gestión de roles |
| GET/POST | `/api/admin/permissions` | Auth | Gestión de permisos |
| GET/PUT | `/api/admin/users/:id/scope` | Auth | Alcance de datos |

---

## Modelo de Datos

### Tablas Principales

```
┌─────────────────┐     ┌─────────────────┐
│     users       │     │     roles       │
├─────────────────┤     ├─────────────────┤
│ user_id (PK)    │     │ role_id (PK)    │
│ company_id (FK) │     │ role_name       │
│ username        │     │ permissions     │
│ email           │     │ is_active       │
│ password_hash   │     └────────┬────────┘
│ is_active      │              │
└────────┬────────┘              │
         │                       │
         │              ┌────────┴────────┐
         │              │ role_permissions│
         │              ├─────────────────┤
         │              │ role_id (FK)    │
         │              │ permission_id   │
         │              └─────────────────┘
         │
┌────────┴────────┐
│    customers     │
├─────────────────┤
│ customer_id (PK) │
│ company_id (FK) │
│ customer_type    │──► CLIENTE / PROSPECTO
│ customer_code   │
│ customer_name   │
│ rfc             │
│ email           │
│ phone           │
│ latitude        │
│ longitude       │
│ status          │──► ACTIVO / INACTIVO
│ branch_id (FK)  │
│ route_id (FK)   │
│ venta_neta      │
│ margen          │
│ linea_credito   │
│ cartera_vencida │
└────────┬────────┘
         │
┌────────┴────────┐
│    contacts     │
├─────────────────┤
│ contact_id (PK) │
│ customer_id(FK) │
│ contact_name    │
│ position        │
│ phone           │
│ extension       │
│ whatsapp        │
│ email           │
└─────────────────┘

┌─────────────────┐     ┌─────────────────┐
│  opportunities  │     │  opportunity    │
├─────────────────┤     │     _items      │
├─────────────────┤     ├─────────────────┤
│ opp_id (PK)     │     │ opp_id (FK)    │
│ customer_id(FK) │◄────│ product_id(FK) │
│ opp_name        │     │ quantity        │
│ stage           │     │ unit_price     │
│ amount          │     │ total          │
│ probability     │     └─────────────────┘
│ close_date      │
│ vendedor_id(FK) │
└─────────────────┘

┌─────────────────┐
│  activities     │
├─────────────────┤
│ activity_id (PK)│
│ customer_id(FK) │
│ contact_id (FK)│
│ activity_type  │──► LLAMADA/CORREO/VISITA/REUNION/TAREA
│ title           │
│ description     │
│ status          │──► PENDIENTE/PROGRAMADA/COMPLETADA/CANCELADA
│ due_date        │
│ assigned_to(FK) │
│ completed_at    │
│ checkin_lat     │
│ checkin_lng     │
│ checkin_notes   │
└─────────────────┘

┌─────────────────┐
│   branches      │
├─────────────────┤
│ branch_id (PK)  │
│ company_id (FK) │
│ branch_name     │
│ branch_code     │
│ address         │
│ status          │
└─────────────────┘

┌─────────────────┐
│   vendedores    │
├─────────────────┤
│ vendedor_id(PK) │
│ company_id (FK) │
│ branch_id (FK)  │
│ vendedor_code   │
│ vendedor_name   │
│ status          │
└─────────────────┘
```

---

## Sistema de Permisos

El sistema cuenta con **31 permisos** organizados por dominio:

### Administración
| Permiso | Controla |
|---------|----------|
| `users.manage` | Crear y gestionar usuarios |
| `roles.manage` | Crear/editar/eliminar roles y permisos |
| `scope.manage` | Configurar alcance de datos |

### Clientes
| Permiso | Controla |
|---------|----------|
| `customers.read` | Ver lista de clientes |
| `customers.create` | Crear nuevos clientes |
| `customers.update` | Editar clientes y contactos |
| `customers.delete` | Inactivar clientes |

### Prospectos
| Permiso | Controla |
|---------|----------|
| `prospects.read` | Ver lista de prospectos |
| `prospects.create` | Crear prospectos |
| `prospects.update` | Editar prospectos |
| `prospects.delete` | Inactivar prospectos |
| `prospects.convert` | Convertir prospecto a cliente |

### Actividades
| Permiso | Controla |
|---------|----------|
| `activities.create` | Crear actividades |
| `activities.update` | Editar actividades |
| `activities.complete` | Completar/cancelar |
| `activities.assign` | Asignar a usuarios |

### Oportunidades
| Permiso | Controla |
|---------|----------|
| `opportunities.create` | Crear oportunidades |
| `opportunities.update` | Editar oportunidades |
| `opportunities.delete` | Eliminar oportunidades |
| `opportunities.price.edit` | Editar precios |
| `opportunities.items.create` | Agregar items |
| `opportunities.items.update` | Editar items |
| `opportunities.items.delete` | Eliminar items |

### Productos
| Permiso | Controla |
|---------|----------|
| `products.create` | Crear productos |
| `products.update` | Editar productos |
| `products.delete` | Eliminar productos |
| `products.price.edit` | Editar precios |

### Reportes
| Permiso | Controla |
|---------|----------|
| `reports.view` | Ver reportes |
| `reports.export` | Exportar datos |
| `reports.scheduled` | Programar reportes |
| `reports.saved_views` | Guardar vistas |

---

## Screenshots

A continuación se presentan las capturas de pantalla del sistema RETFlow CRM, organizadas por módulo:

---

### Autenticación

**Formulario de inicio de sesión con campos para email y contraseña**
<br>

![Formulario de inicio de sesión](assets/screenshots/0.%20Login/Login.png)

**Formulario de login adaptado para dispositivos móviles**
<br>

![Login en móvil](assets/screenshots/0.%20Login/Login%20Movil.png)

**Formulario para solicitar recuperación de contraseña**
<br>

![Recuperar contraseña](assets/screenshots/0.%20Login/Recuperar%20Contraseña.png)

**Confirmación de envío de enlace de recuperación al correo**
<br>

![Envío de correo de recuperación](assets/screenshots/0.%20Login/Envio%20de%20Correo%20-%20Recuperar%20Contraseña.png)

**Formulario para establecer nueva contraseña con token**
<br>

![Nueva contraseña](assets/screenshots/0.%20Login/Nueva%20Contraseña.png)

**Mensaje de error cuando el enlace de recuperación ya fue usado**
<br>

![Error por link expirado](assets/screenshots/0.%20Login/Nueva%20Contraseña%20-%20Error%20por%20intentar%20con%20el%20mismo%20link.png)

---

### Menú

**Menú lateral completo visible en escritorio con todas las opciones**
<br>

![Menú en PC](assets/screenshots/0.%20Menu/En%20PC.png)

**Menú hamburguesa adaptable a pantallas pequeñas**
<br>

![Menú en teléfono](assets/screenshots/0.%20Menu/En%20Telefono.png)

---

### Dashboard / Panel de Control

**Vista principal del dashboard con KPIs, gráficos y alertas**
<br>

![Panel de control en PC](assets/screenshots/1.%20Home/Panel%20de%20control%20-%20PC.png)

**Dashboard adaptado para visualización móvil**
<br>

![Panel de control en móvil](assets/screenshots/1.%20Home/Panel%20de%20control%20-%20Movil.png)

---

### Clientes

**Listado completo de clientes con tabla, búsqueda y filtros**
<br>

![Listado de clientes](assets/screenshots/2.%20Cliente/Clientes.png)

**Vista de detalle del cliente con tabs de información**
<br>

![Detalle del cliente](assets/screenshots/2.%20Cliente/Clientes%20-%20Detalle.png)

**Pestaña de análisis financiero: venta neta, margen, línea de crédito**
<br>

![Análisis financiero del cliente](assets/screenshots/2.%20Cliente/Clientes%20-%20Analisis.png)

**Lista de contactos asociados al cliente**
<br>

![Contactos del cliente](assets/screenshots/2.%20Cliente/Clientes%20-%20Contactos.png)

**Oportunidades de venta asociadas al cliente**
<br>

![Oportunidades del cliente](assets/screenshots/2.%20Cliente/Clientes%20-%20Oportunidades.png)

**Historial de actividades realizadas con el cliente**
<br>

![Actividades del cliente](assets/screenshots/2.%20Cliente/Clientes%20-%20Actividades.png)

**Formulario para crear un nuevo cliente**
<br>

![Nuevo cliente](assets/screenshots/2.%20Cliente/Clientes%20-%20Nuevo.png)

**Formulario para editar información del cliente**
<br>

![Editar cliente](assets/screenshots/2.%20Cliente/Clientes%20-%20Editar.png)

**Ventana para enviar correo electrónico al cliente**
<br>

![Correo al cliente](assets/screenshots/2.%20Cliente/Clientes%20-%20Correo.png)

**Formulario de composición de correo**
<br>

![Nuevo correo](assets/screenshots/2.%20Cliente/Clientes%20-%20Nuevo%20Correo.png)

---

### Prospectos

**Listado de prospectos con tabla y opciones de filtrado**
<br>

![Listado de prospectos](assets/screenshots/3.%20Prospecto/Prospectos.png)

**Vista de detalle del prospecto**
<br>

![Detalles del prospecto](assets/screenshots/3.%20Prospecto/Prospectos%20-%20Detalles.png)

**Análisis financiero del prospecto**
<br>

![Análisis del prospecto](assets/screenshots/3.%20Prospecto/Prospectos%20Analisis.png)

**Contactos asociados al prospecto**
<br>

![Contactos del prospecto](assets/screenshots/3.%20Prospecto/Prospectos%20-%20Contactos.png)

**Oportunidades del prospecto**
<br>

![Oportunidades del prospecto](assets/screenshots/3.%20Prospecto/Prospectos%20-%20Oportunidades.png)

**Actividades registradas con el prospecto**
<br>

![Actividades del prospecto](assets/screenshots/3.%20Prospecto/Prospectos%20-%20Actividades.png)

**Formulario para crear nuevo prospecto**
<br>

![Nuevo prospecto](assets/screenshots/3.%20Prospecto/Prospectos%20-%20Nuevo.png)

**Formulario para editar prospecto existente**
<br>

![Editar prospecto](assets/screenshots/3.%20Prospecto/Prospectos%20-%20Editar.png)

---

### Mapa

**Mapa interactivo con marcadores de todos los clientes**
<br>

![Mapa interactivo](assets/screenshots/4.%20Mapa/Mapa.png)

**Selección de clientes para calcular ruta optimizada**
<br>

![Clientes con ruta óptima](assets/screenshots/4.%20Mapa/Mapa%20-%20Clientes%20Ruta%20Optima.png)

**Ruta optimizada incluyendo ubicación del usuario**
<br>

![Ruta óptima con usuario](assets/screenshots/4.%20Mapa/Mapa%20-%20Cliente%20+%20usuario%20Ruta%20Optima.png)

**Visualización de check-ins de visitas en el mapa**
<br>

![Check-ins en mapa](assets/screenshots/4.%20Mapa/Mapa%20-%20Checkins.png)

---

### Actividades

**Listado de todas las actividades con filtros**
<br>

![Listado de actividades](assets/screenshots/5.%20Actividad/Actividades.png)

**Panel de filtros avanzados por estatus y tipo**
<br>

![Filtros de actividades](assets/screenshots/5.%20Actividad/Actividades%20-%20Filtros.png)

**Formulario para crear nueva actividad**
<br>

![Nueva actividad](assets/screenshots/5.%20Actividad/Actividades%20-Nueva.png)

**Formulario para editar actividad existente**
<br>

![Editar actividad](assets/screenshots/5.%20Actividad/Actividades%20-Editar.png)

**Vista detallada de una actividad**
<br>

![Detalle de actividad](assets/screenshots/5.%20Actividad/Actividades%20-Detalle.png)

**Alerta de actividad vencida en el dashboard**
<br>

![Alerta de actividad vencida](assets/screenshots/5.%20Actividad/Actividades%20-Mensaje%20vencida%20en%20panel%20de%20control.png)

---

### Calendario

**Vista mensual del calendario con actividades**
<br>

![Vista mensual del calendario](assets/screenshots/6.%20Calendario/Calendario.png)

**Vista de agenda por día específico**
<br>

![Calendario por día](assets/screenshots/6.%20Calendario/Calendario%20-%20Por%20Dia.png)

**Vista semanal del calendario**
<br>

![Calendario por semana](assets/screenshots/6.%20Calendario/Calendario%20-%20Por%20semana.png)

**Lista de actividades en formato agenda**
<br>

![Agenda](assets/screenshots/6.%20Calendario/Calendario%20-%20Agenda.png)

**Detalle de un evento o actividad**
<br>

![Detalle del calendario](assets/screenshots/6.%20Calendario/Calendario%20-%20Detalle.png)

---

### Contactos

**Listado de todos los contactos del sistema**
<br>

![Listado de contactos](assets/screenshots/7.%20Contactos/Contactos.png)

**Formulario para crear nuevo contacto**
<br>

![Nuevo contacto](assets/screenshots/7.%20Contactos/Contactos%20-%20Nueva.png)

**Formulario para editar contacto existente**
<br>

![Editar contacto](assets/screenshots/7.%20Contactos/Contactos%20-%20Editar.png)

**Información detallada del contacto**
<br>

![Detalle del contacto](assets/screenshots/7.%20Contactos/Contactos%20-%20Detalle.png)

**Crear actividad asociada al contacto**
<br>

![Nueva actividad desde contacto](assets/screenshots/7.%20Contactos/Contactos%20-%20Nueva%20Actividad.png)

---

### Oportunidades

**Vista en lista de oportunidades**
<br>

![Lista de oportunidades](assets/screenshots/8.%20Oportunidades/Oportunidades%20-%20Lista.png)

**Pipeline kanban con columnas por etapa de venta**
<br>

![Pipeline Kanban](assets/screenshots/8.%20Oportunidades/Oportunidades%20-%20Kanban.png)

**Formulario para crear nueva oportunidad**
<br>

![Nueva oportunidad](assets/screenshots/8.%20Oportunidades/Oportunidades%20-%20Nueva.png)

**Formulario para editar oportunidad**
<br>

![Editar oportunidad](assets/screenshots/8.%20Oportunidades/Oportunidades%20-%20Editar.png)

**Vista detallada de oportunidad con productos**
<br>

![Detalle de oportunidad](assets/screenshots/8.%20Oportunidades/Oportunidades%20-%20Detalle.png)

---

### Productos

**Catálogo de productos con tabla y búsqueda**
<br>

![Catálogo de productos](assets/screenshots/9.%20Productos/Productos.png)

**Formulario para crear nuevo producto**
<br>

![Nuevo producto](assets/screenshots/9.%20Productos/Productos%20-%20Nuevo.png)

**Formulario para editar producto existente**
<br>

![Editar producto](assets/screenshots/9.%20Productos/Productos%20-%20Editar.png)

---

### Reportes

**Centro de reportes con todos los tipos disponibles**
<br>

![Centro de reportes](assets/screenshots/10.%20Reportes/Reportes.png)

**Gestión de filtros guardados**
<br>

![Filtros guardados](assets/screenshots/10.%20Reportes/Reportes%20-%20Filtros%20Guardados.png)

**Guardar configuración actual de filtros**
<br>

![Guardar filtros](assets/screenshots/10.%20Reportes/Reportes%20-%20Guardar%20filtros.png)

**Configurar envío programado de reportes**
<br>

![Programar envío](assets/screenshots/10.%20Reportes/Reportes%20-%20Programar%20envio%20de%20reportes.png)

**Lista de reportes programados activos**
<br>

![Reportes programados](assets/screenshots/10.%20Reportes/Reportes%20-%20Reportes%20Programados.png)

---

### Mi Perfil

**Información del perfil del usuario**
<br>

![Mi perfil](assets/screenshots/11.%20Mi%20Perfil/Mi%20perfil.png)

**Formulario para editar datos personales**
<br>

![Editar perfil](assets/screenshots/11.%20Mi%20Perfil/Mi%20perfil%20-%20Editar.png)

**Gestión de cuenta de correo conectada**
<br>

![Correo conectado](assets/screenshots/11.%20Mi%20Perfil/Mi%20perfil%20-%20Correo.png)

**Configuración de seguridad y contraseña**
<br>

![Seguridad](assets/screenshots/11.%20Mi%20Perfil/Mi%20perfil%20-%20Seguridad.png)

---

### Plantillas de Correo

**Administrador de plantillas de correo**
<br>

![Plantillas de correo](assets/screenshots/12.%20Plantillas%20de%20Correo/Plantillas.png)

---

### Administración

**Panel principal de administración**
<br>

![Panel de administración](assets/screenshots/13.%20Administracion/Admin.png)

**Formulario para crear nuevo usuario**
<br>

![Crear usuario](assets/screenshots/13.%20Administracion/Admin%20-%20Crear%20usuario.png)

**Editar información del usuario**
<br>

![Editar usuario](assets/screenshots/13.%20Administracion/Admin%20-%20Editar%20usuario.png)

**Asignar roles a usuario**
<br>

![Asignar roles](assets/screenshots/13.%20Administracion/Admin%20-%20Editar%20usuario%20roles.png)

**Resetear contraseña de usuario**
<br>

![Resetear contraseña](assets/screenshots/13.%20Administracion/Admin%20-%20Editar%20Contraseña%20usuario.png)

**Lista de roles del sistema**
<br>

![Lista de roles](assets/screenshots/13.%20Administracion/Admin%20-%20Roles.png)

**Crear nuevo rol**
<br>

![Nuevo rol](assets/screenshots/13.%20Administracion/Admin%20-%20Roles%20Nuevo.png)

**Editar permisos de rol**
<br>

![Editar rol](assets/screenshots/13.%20Administracion/Admin%20-%20Roles%20Editar.png)

**Gestión de permisos del sistema**
<br>

![Gestión de permisos](assets/screenshots/13.%20Administracion/Admin%20-%20Permisos.png)

**Configurar alcance de datos (ALL/BRANCH/ROUTE)**
<br>

![Editar alcance](assets/screenshots/13.%20Administracion/Admin%20-%20Editar%20Alcance.png)

---

## Repositorios

El código fuente se encuentra en repositorios privados:

- **Frontend:** [crm-frontend](https://github.com/RETBOT/crm-frontend) *(privado)*
- **Backend:** [crm-backend](https://github.com/RETBOT/crm-backend) *(privado)*

---

## Colaboración

¿Te gustaría contribuir o colaborar en este proyecto? ¡Contáctame! Toda la información está disponible en mi perfil de GitHub.

---

## Licencia

Este proyecto es propiedad de **RETEX**. Todos los derechos reservados.

---

*Desarrollado con agentes de inteligencia artificial para máxima eficiencia y calidad.*
