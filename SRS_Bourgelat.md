# Especificación de Requisitos del Software (SRS)

**Proyecto:** Bourgelat – Sistema SaaS para Gestión Veterinaria

**Aprendices:**
- Román Alberto Bolaños Cerquera
- Stiven Ferreira Espinosa
- Elmer Julian Rosas Manjarres

**Instructor:** Karol Daniela Correa Trujillo

**Programa:** Tecnología en Desarrollo de Software

**Ficha:** 3239137

**SENA – Centro de la Industria, la Empresa y los Servicios (CIES), Sede Neiva**

**Año:** 2026

---

Aprendices:

SERVICIO NACIONAL DE APRENDIZAJE – SENA
 Centro de la Industria, la Empresa y los Servicios (CIES)
 Sede Neiva – Jornada Nocturna

Programa: Tecnología en Desarrollo de Software
 Ficha: 3239137

Neiva – Huila
 2026

Tabla de contenido:

## 1. Introducción

En la actualidad, la digitalización de los servicios se ha convertido en un factor determinante para la optimización de procesos administrativos y operativos en diversas organizaciones. La adopción de soluciones tecnológicas permite mejorar la eficiencia, reducir errores humanos y garantizar un mejor control de la información.

En el sector veterinario, muchas clínicas aún gestionan procesos como el registro de pacientes, historial clínico, facturación y programación de citas de manera manual o mediante herramientas no integradas, lo que genera pérdida de tiempo, desorganización y riesgos en el manejo de la información.

Con el propósito de abordar esta problemática, se propone el desarrollo del sistema Bourgelat, una plataforma web bajo el modelo Software as a Service (SaaS), diseñada para ofrecer una solución integral de gestión veterinaria. El sistema operará bajo una arquitectura Multi-Tenant, permitiendo que múltiples clínicas veterinarias accedan a la plataforma mediante suscripción, garantizando seguridad, escalabilidad y aislamiento de datos.

El presente documento especifica los requisitos funcionales y no funcionales del sistema, estableciendo de manera clara y formal el comportamiento esperado de la plataforma.

### 1.1 Propósito

El propósito del presente documento es especificar de manera clara, estructurada y verificable los requisitos funcionales y no funcionales del sistema Bourgelat. Este documento servirá como referencia formal para el equipo de desarrollo, evaluadores académicos y demás partes interesadas, estableciendo el comportamiento esperado del sistema y delimitando su alcance.

### 1.2 Alcance

El sistema Bourgelat será una plataforma web orientada a la gestión integral de clínicas veterinarias bajo el modelo Software as a Service (SaaS). La solución permitirá que múltiples clínicas accedan al sistema mediante suscripción, garantizando aislamiento lógico de la información entre cada organización a través de una arquitectura Multi-Tenant.

En su versión inicial (1.0), el sistema incluirá los siguientes módulos principales:

Registro y gestión de clínicas veterinarias.

Gestión de usuarios con control de acceso basado en roles.

Registro y administración de pacientes y propietarios.

Gestión de historial clínico.

Programación y control de citas.

Gestión básica de inventario.

Generación de facturación interna.

Generación de reportes administrativos básicos.

Gestión de estado de suscripción de cada clínica.

El sistema será accesible a través de navegadores web modernos y requerirá conexión a internet para su funcionamiento. La plataforma estará diseñada bajo una arquitectura cliente-servidor, permitiendo escalabilidad para futuras ampliaciones.

No se incluye en la versión 1.0 la integración directa con sistemas externos de facturación electrónica, tales como los requeridos por la Dirección de Impuestos y Aduanas Nacionales
 (DIAN). Sin embargo, el sistema será diseñado considerando la posibilidad de integración futura conforme a la normativa vigente en Colombia.

Asimismo, funcionalidades como pasarelas de pago en línea, aplicación móvil nativa y soporte multi-sede avanzado podrán ser contempladas en versiones posteriores del sistema.

### 1.3 Definiciones, Acrónimos y Abreviaturas

Para efectos del presente documento, se establecen las siguientes definiciones y acrónimos:

SRS (Software Requirements Specification): Documento formal que describe los requisitos funcionales y no funcionales de un sistema de software.

SaaS (Software as a Service): Modelo de distribución de software en el cual la aplicación es alojada en servidores externos y ofrecida a los usuarios mediante suscripción a través de internet.

Multi-Tenant: Arquitectura en la cual múltiples organizaciones (clientes) comparten la misma infraestructura tecnológica, garantizando el aislamiento lógico de la información entre ellas.

API (Application Programming Interface): Conjunto de reglas y protocolos que permiten la comunicación entre diferentes sistemas o componentes de software.

HTTPS (HyperText Transfer Protocol Secure): Protocolo de comunicación segura utilizado para la transmisión de datos cifrados en aplicaciones web.

SSL/TLS (Secure Sockets Layer / Transport Layer Security): Protocolos criptográficos utilizados para establecer conexiones seguras en internet.

## 2. Descripción General

Esta sección presenta una visión general del sistema Bourgelat, describiendo su contexto, funciones principales, características de los usuarios, restricciones y supuestos operativos.

### 2.1 Perspectiva del Producto

Bourgelat será una plataforma web desarrollada bajo una arquitectura cliente-servidor, implementada bajo el modelo Software as a Service (SaaS). El sistema permitirá que múltiples clínicas veterinarias accedan a la plataforma mediante suscripción, compartiendo la misma infraestructura tecnológica bajo un esquema Multi-Tenant.

La aplicación será accesible a través de navegadores web modernos y requerirá conexión a internet para su funcionamiento. La arquitectura del sistema estará compuesta por:

Capa de presentación (Frontend), desarrollada mediante un framework moderno como Angular o React.

Capa de lógica de negocio (Backend), implementada mediante una API REST.

Capa de persistencia de datos (Base de datos centralizada).

El sistema garantizará el aislamiento lógico de la información mediante la identificación única de cada clínica dentro de la base de datos, evitando el acceso cruzado entre organizaciones.

La plataforma será diseñada con capacidad de escalabilidad horizontal, permitiendo el crecimiento progresivo en número de clínicas suscritas sin afectar el rendimiento general del sistema.

### 2.2 Funciones Generales del Sistema

Bourgelat permitirá realizar, de manera general, las siguientes funciones:

Registro y gestión de clínicas veterinarias.

Administración de usuarios y asignación de roles.

Registro y administración de pacientes y propietarios.

Gestión de historial clínico digital.

Programación, modificación y cancelación de citas.

Gestión básica de inventario de productos y servicios.

Generación de facturación interna.

Generación de reportes administrativos.

Gestión de suscripciones y estado de pago.

### 2.3 Características de los Usuarios

El sistema estará dirigido a los siguientes tipos de usuarios:

Super Administrador

Responsable de la gestión global de la plataforma. Tendrá permisos para administrar clínicas registradas, supervisar suscripciones y gestionar configuraciones generales del sistema.

Nivel técnico esperado: Medio – Alto.

Administrador de Clínica

Responsable de la gestión interna de su clínica dentro de la plataforma. Podrá administrar usuarios, consultar reportes y supervisar operaciones administrativas.

Nivel técnico esperado: Medio.

Veterinario

Encargado del registro de consultas, actualización del historial clínico y gestión de citas médicas.

Nivel técnico esperado: Básico – Medio.

Recepcionista

Encargado del registro de pacientes, programación de citas y generación de facturación interna.

Nivel técnico esperado: Básico.

### 2.4 Restricciones del sistema

El sistema estará sujeto a las siguientes restricciones:

Dependencia de conexión a internet para su funcionamiento.

Uso obligatorio del protocolo HTTPS para la transmisión de datos.

La integración con sistemas de facturación electrónica regulados por la Dirección de Impuestos y Aduanas Nacionales (DIAN) no será implementada en la versión 1.0.

El desarrollo se realizará en un entorno académico con recursos limitados.

Compatibilidad con navegadores modernos (Chrome, Edge, Firefox, Brave, etc).

### 2.5 Suposiciones y Dependencias

Se asume que las clínicas cuentan con acceso estable a internet.

Se asume que los usuarios poseen conocimientos básicos en el manejo de sistemas web.

El crecimiento del sistema dependerá de la infraestructura de despliegue seleccionada.

La integración futura con servicios externos dependerá del cumplimiento de requisitos regulatorios y técnicos.

## Requerimientos no funcionales

## Requisitos funcionales

| Código | Módulo / Requisito | Descripción |
|---|---|---|
| RF-01 | Módulo 1: Gestión Multi-Tenant | Registro de nuevas clínicas en modalidad SaaS |
| RF-02 |  | Generación automática de espacio aislado de datos por clínica |
| RF-03 |  | Activación y desactivación de clínicas por superadministrador |
| RF-04 |  | Asociación de suscripción activa a cada clínica |
| RF-05 |  | Bloqueo de acceso a clínicas con suscripción vencida |

| Código | Módulo / Requisito | Descripción |
|---|---|---|
| RF-06 | Módulo 2: Gestión de Usuarios y Roles | Registro de usuarios dentro de cada clínica |
| RF-07 |  | Asignación de roles (Administrador, Veterinario, Recepcionista) |
| RF-08a |  | Edición de información de usuario |
| RF-09 |  | Desactivación de usuarios |
| RF-10 |  | Validación de credenciales mediante autenticación segura |

| Código | Módulo / Requisito | Descripción |
|---|---|---|
| RF-11a | Módulo 3: Gestión de Clientes (Propietarios) | Registro de propietarios de mascotas |
| RF-12 |  | Edición de información del propietario |
| RF-13 |  | Consulta de propietarios mediante filtros |
| RF-14 |  | Asociación de múltiples mascotas a un propietario |
| RF-15 |  | Prevención de duplicidad de propietarios por número de identificación |

| Código | Módulo / Requisito | Descripción |
|---|---|---|
| RF-16 | Módulo 4: Gestión de Pacientes (Mascotas) | Registro de mascotas asociadas a propietario |
| RF-17 |  | Almacenamiento de especie, raza, edad y peso del paciente |
| RF-18 |  | Edición de datos del paciente |
| RF-19 |  | Consulta de historial clínico del paciente |
| RF-20 |  | Carga de imagen del paciente |

| Código | Módulo / Requisito | Descripción |
|---|---|---|
| RF-21a | Módulo 5: Gestión de Citas | Agendamiento de citas médicas |
| RF-22 |  | Reprogramación de citas |
| RF-23a |  | Cancelación de citas |
| RF-24 |  | Visualización de calendario de citas |
| RF-25 |  | Prevención de solapamiento de citas por veterinario |

| Código | Módulo / Requisito | Descripción |
|---|---|---|
| RF-26 | Módulo 6: Historia Clínica | Registro de consultas médicas |
| RF-27 |  | Registro de diagnóstico |
| RF-28 |  | Registro de tratamiento |
| RF-29 |  | Registro de medicamentos formulados |
| RF-30 |  | Historial clínico inalterable |
| RF-31 |  | Adjuntar documentos clínicos a la historia |

| Código | Módulo / Requisito | Descripción |
|---|---|---|
| RF-32 | Módulo 7: Inventario | Registro de productos en inventario |
| RF-33 |  | Actualización automática de stock |
| RF-34 |  | Alertas de bajo stock |
| RF-35 |  | Registro de entradas y salidas de inventario |
| RF-36 |  | Reporte de inventario |

| Código | Módulo / Requisito | Descripción |
|---|---|---|
| RF-37 | Módulo 8: Servicios | Registro de servicios veterinarios |
| RF-38 |  | Modificación de precios de servicios |
| RF-39 |  | Asociación de servicios a facturación |

| Código | Módulo / Requisito | Descripción |
|---|---|---|
| RF-40 | Módulo 9: Facturación | Generación de facturas electrónicas internas |
| RF-41 |  | Asociación de productos y servicios a factura |
| RF-42 |  | Cálculo automático de impuestos |
| RF-43 |  | Generación de comprobante en PDF |
| RF-44 |  | Registro de métodos de pago |
| RF-45 |  | Historial de facturación |
| RF-46 |  | Anulación de factura |
| RF-47 |  | Contemplar futura integración con DIAN |

| Código | Módulo / Requisito | Descripción |
|---|---|---|
| RF-48 | Módulo 10: Reportes | Reporte de ventas |
| RF-49 |  | Reporte de citas |
| RF-50 |  | Reporte de ingresos mensuales |
| RF-51 |  | Reporte de servicios más solicitados |
| RF-52 |  | Exportación de reportes en PDF |

| Código | Módulo / Requisito | Descripción |
|---|---|---|
| RF-53 | Módulo 11: Suscripciones SaaS | Selección de plan de suscripción |
| RF-54 |  | Registro de pagos de suscripción |
| RF-55 |  | Alertas de vencimiento de suscripción |
| RF-56 |  | Limitación de funcionalidades según plan contratado |

| Código | Módulo / Requisito | Descripción |
|---|---|---|
| RF-57 | Módulo 12: Seguridad | Registro de auditoría de acciones |
| RF-58 |  | Cierre de sesión por inactividad |
| RF-59a |  | Recuperación de contraseña |
| RF-60 |  | Cifrado de contraseñas |

## Requisitos funcionales — RF

| Código | Módulo | Requisito |
|---|---|---|
| RF-01 | Gestión Multi-Tenant | Registro de nuevas clínicas en modalidad SaaS |
| RF-02 | Gestión Multi-Tenant | Generación automática de espacio aislado de datos por clínica |
| RF-03 | Gestión Multi-Tenant | Activación y desactivación de clínicas por superadministrador |
| RF-04 | Gestión Multi-Tenant | Asociación de suscripción activa a cada clínica |
| RF-05 | Gestión Multi-Tenant | Bloqueo de acceso a clínicas con suscripción vencida |
| RF-06 | Gestión de Usuarios y Roles | Registro de usuarios dentro de cada clínica |
| RF-07 | Gestión de Usuarios y Roles | Asignación de roles (Administrador, Veterinario, Recepcionista) |
| RF-08a | Gestión de Usuarios y Roles | Edición de información de usuario |
| RF-09 | Gestión de Usuarios y Roles | Desactivación de usuarios |
| RF-10 | Gestión de Usuarios y Roles | Validación de credenciales mediante autenticación segura |
| RF-11a | Gestión de Clientes (Propietarios) | Registro de propietarios de mascotas |
| RF-12 | Gestión de Clientes (Propietarios) | Edición de información del propietario |
| RF-13 | Gestión de Clientes (Propietarios) | Consulta de propietarios mediante filtros |
| RF-14 | Gestión de Clientes (Propietarios) | Asociación de múltiples mascotas a un propietario |
| RF-15 | Gestión de Clientes (Propietarios) | Prevención de duplicidad de propietarios por número de identificación |
| RF-16 | Gestión de Pacientes (Mascotas) | Registro de mascotas asociadas a propietario |
| RF-17 | Gestión de Pacientes (Mascotas) | Almacenamiento de especie, raza, edad y peso del paciente |
| RF-18 | Gestión de Pacientes (Mascotas) | Edición de datos del paciente |
| RF-19 | Gestión de Pacientes (Mascotas) | Consulta de historial clínico del paciente |
| RF-20 | Gestión de Pacientes (Mascotas) | Carga de imagen del paciente |
| RF-21a | Gestión de Citas | Agendamiento de citas médicas |
| RF-22 | Gestión de Citas | Reprogramación de citas |
| RF-23a | Gestión de Citas | Cancelación de citas |
| RF-24 | Gestión de Citas | Visualización de calendario de citas |
| RF-25 | Gestión de Citas | Prevención de solapamiento de citas por veterinario |
| RF-26 | Historia Clínica | Registro de consultas médicas |
| RF-27 | Historia Clínica | Registro de diagnóstico |
| RF-28 | Historia Clínica | Registro de tratamiento |
| RF-29 | Historia Clínica | Registro de medicamentos formulados |
| RF-30 | Historia Clínica | Historial clínico inalterable |
| RF-31 | Historia Clínica | Adjuntar documentos clínicos a la historia |
| RF-32 | Inventario | Registro de productos en inventario |
| RF-33 | Inventario | Actualización automática de stock |
| RF-34 | Inventario | Alertas de bajo stock |
| RF-35 | Inventario | Registro de entradas y salidas de inventario |
| RF-36 | Inventario | Reporte de inventario |
| RF-37 | Servicios | Registro de servicios veterinarios |
| RF-38 | Servicios | Modificación de precios de servicios |
| RF-39 | Servicios | Asociación de servicios a facturación |
| RF-40 | Facturación | Generación de facturas electrónicas internas |
| RF-41 | Facturación | Asociación de productos y servicios a factura |
| RF-42 | Facturación | Cálculo automático de impuestos |
| RF-43 | Facturación | Generación de comprobante en PDF |
| RF-44 | Facturación | Registro de métodos de pago |
| RF-45 | Facturación | Historial de facturación |
| RF-46 | Facturación | Anulación de factura |
| RF-47 | Facturación | Contemplar futura integración con DIAN |
| RF-48 | Reportes | Reporte de ventas |
| RF-49 | Reportes | Reporte de citas |
| RF-50 | Reportes | Reporte de ingresos mensuales |
| RF-51 | Reportes | Reporte de servicios más solicitados |
| RF-52 | Reportes | Exportación de reportes en PDF |
| RF-53 | Suscripciones SaaS | Selección de plan de suscripción |
| RF-54 | Suscripciones SaaS | Registro de pagos de suscripción |
| RF-55 | Suscripciones SaaS | Alertas de vencimiento de suscripción |
| RF-56 | Suscripciones SaaS | Limitación de funcionalidades según plan contratado |
| RF-57 | Seguridad | Registro de auditoría de acciones |
| RF-58 | Seguridad | Cierre de sesión por inactividad |
| RF-59a | Seguridad | Recuperación de contraseña |
| RF-60 | Seguridad | Cifrado de contraseñas |

## Requerimientos no funcionales

| Código | Categoría | Requisito |
|---|---|---|
| RNF-01a | Seguridad | Cifrado de contraseñas con algoritmos de hashing seguro (bcrypt) |
| RNF-02 | Seguridad | Protocolo HTTPS mediante certificado SSL válido |
| RNF-03 | Seguridad | Autenticación basada en tokens JWT |
| RNF-04 | Seguridad | Control de acceso por roles (RBAC) |
| RNF-05 | Seguridad | Registro de logs de auditoría de acciones críticas |
| RNF-06 | Seguridad | Bloqueo de cuenta tras múltiples intentos fallidos |
| RNF-07 | Seguridad | Protección contra SQL Injection, XSS y CSRF |
| RNF-08 | Seguridad | Aislamiento de datos entre clínicas (Multi-Tenant seguro) |
ya entendí las nuevas cosas yo no se ni mrd ehhhhhhh
