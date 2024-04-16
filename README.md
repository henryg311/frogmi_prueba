# Visualizador de Datos Sísmicos

Este proyecto es una aplicación web para visualizar información actualizada sobre eventos sísmicos a nivel mundial, facilitando el acceso y la interacción con datos sismológicos. La aplicación se compone de un backend desarrollado en Ruby on Rails que se encarga de la gestión de datos y un frontend implementado en React que permite la visualización y la interacción con los usuarios.

## Backend (Ruby on Rails)

El backend es responsable de obtener, almacenar y servir datos sismológicos, además de gestionar comentarios sobre dichos eventos.

### Tecnologías Utilizadas

- **Ruby on Rails**: Framework utilizado para crear la lógica del servidor y la API RESTful.
- **PostgreSQL**: Sistema de gestión de bases de datos relacional para el almacenamiento de datos.
- **Faraday**: Librería para realizar solicitudes HTTP a APIs externas.
- **Active Model Serializers**: Utilizado para serializar objetos en JSON de manera organizada para el frontend.

### Modelos

- **Feature**: Representa cada evento sísmico, almacenando atributos como magnitud, lugar, tipo de magnitud, entre otros.
- **Comment**: Almacena comentarios que los usuarios pueden hacer referentes a cada evento sísmico.

### Controladores

- **FeaturesController**: Controla las acciones de listar eventos sísmicos y filtrarlos según tipo de magnitud.
- **CommentsController**: Maneja la creación de comentarios asociados a eventos sísmicos.

### Endpoints Principales

- `GET /api/features`: Devuelve una lista de eventos sísmicos. Admite paginación y filtrado por tipo de magnitud.
- `POST /api/features/:feature_id/comments`: Permite crear un comentario para un evento sísmico específico.

### Tareas Programadas

- **fetch_and_save_data**: Esta tarea se ejecuta regularmente para obtener los datos más recientes de eventos sísmicos desde la API de USGS y actualizar la base de datos.

## Frontend (React)

El frontend proporciona la interfaz de usuario, permitiendo a los usuarios visualizar y interactuar con los datos sismológicos y enviar comentarios.

### Tecnologías Utilizadas

- **React**: Biblioteca de JavaScript para construir la interfaz de usuario.
- **Axios**: Utilizado para realizar solicitudes HTTP desde el frontend al backend.
- **CSS**: Estilos personalizados para mejorar la interfaz de usuario.

### Componentes Principales

- **FeaturesList**: Muestra la lista de eventos sísmicos disponibles.
- **CommentForm**: Permite a los usuarios enviar comentarios sobre un evento sísmico específico.

### Funcionalidades

- **Visualización de eventos sísmicos**: Los usuarios pueden ver una lista de eventos recientes con detalles como magnitud, ubicación y hora.
- **Envío de comentarios**: Los usuarios pueden añadir comentarios a eventos específicos directamente desde la lista.

