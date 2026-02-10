# Promociones App (Ionic React + Vue)

Este proyecto consiste en dos aplicaciones:

## Descripción del Proyecto

### Aplicación Ionic React (Cliente)
- Muestra las promociones de productos o servicios en **tarjetas dinámicas**.
- Las tarjetas se actualizan en tiempo real utilizando Firestore y el patrón **Observer**.

### Aplicación Vue (Administrador)
- Administra las promociones, usuarios y categorías.

## Arquitectura del Proyecto

### Diagrama de Arquitectura
### [Diagrama ER](doc/ER.jpg)

## Reglas de Seguridad en Firebase

## Estructura de las Colecciones y Subcolecciones

### Colección Promociones
- **Campos**:
  - `id_promocion` (PK)
  - `titulo`

### Colección Usuarios
- **Campos**:
  - `id_usuario` (PK)
  - `email`

### Colección Categorías
- **Campos**:
  - `id_categoria` (PK)
  - `nombre`

## Instalación y Uso

### Frontend (Ionic React)

### Frontend (Vue.js)

graph TD
    subgraph "Client Side (Consumer)"
        A[Ionic React App] -->|Subscribes| B[Promotion Repository]
        B -->|Observer Pattern| C{Firestore SDK}
    end

    subgraph "Admin Side (Management)"
        D[Vue.js Admin Panel] -->|Writes/Updates| E[Admin Repository]
        E -->|Auth & CRUD| C
    end

    subgraph "Google Cloud / Firebase"
        C --> F[(Firestore DB)]
        C --> G[Firebase Auth]
        C --> H[Firebase Storage]
        F -->|Real-time Update| B
    end

    subgraph "Data Model"
        F --- I[Promociones]
        F --- J[Usuarios]
        F --- K[Categorías]
    end
sequenceDiagram
    participant Admin as Vue Admin App
    participant FS as Firestore Cloud
    participant Repo as Repository (Ionic)
    participant UI as Ionic React UI

    Admin->>FS: Actualiza Promoción (Estado/Descuento)
    FS-->>FS: Valida Reglas de Seguridad
    FS-->>Repo: Notifica cambio (Real-time Stream)
    Repo->>Repo: Mapea Documento a Interfaz TS
    Repo-->>UI: Notifica suscriptores (Observer)
    UI->>UI: Renderiza Card Dinámica con nuevos datos
