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

### Modelo de Datos (ERD)

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
