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
[Aqui iran las reglas de seguridad de firebase]

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

## Relaciones

Flujo de la app de promociones

    Admin->>FS: Actualiza Promoción (Estado/Descuento)
    FS-->>FS: Valida Reglas de Seguridad
    FS-->>Repo: Notifica cambio (Real-time Stream)
    Repo->>Repo: Mapea Documento a Interfaz TS
    Repo-->>UI: Notifica suscriptores (Observer)
    UI->>UI: Renderiza Card Dinámica con nuevos datos
