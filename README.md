# WorkForge

**Project, Production & Inventory Management System**

WorkForge es un sistema web orientado a la gestión integral de proyectos empresariales, diseñado para centralizar y controlar el flujo de trabajo desde la generación de una cotización hasta la finalización del proyecto, incluyendo diseño, fabricación, inventario, documentación y facturación.

El sistema busca proporcionar **trazabilidad completa de los proyectos**, permitiendo conocer qué actividad se realizó, quién la realizó, cuándo comenzó, cuándo terminó y cuál es el estado actual del proceso.

---

## 🎯 Objetivo del proyecto

Desarrollar una plataforma web que permita a los diferentes departamentos de una empresa trabajar sobre un mismo sistema, manteniendo centralizada la información relacionada con:

* Clientes.
* Cotizaciones.
* Proyectos.
* Órdenes de diseño.
* Diseño y documentación.
* Fabricación.
* Inventario de materiales.
* Solicitudes de materiales.
* Facturación y pagos.
* Historial y trazabilidad.
* Estadísticas y reportes.

El sistema será desarrollado inicialmente como un proyecto independiente para establecer una arquitectura escalable y posteriormente adaptarlo a las necesidades específicas de un cliente.

---

# 🗺️ Roadmap

El desarrollo de WorkForge estará dividido en las siguientes fases:

```text
FASE 1  → Análisis y especificación
   ↓
FASE 2  → Arquitectura y base de datos
   ↓
FASE 3  → Autenticación y usuarios
   ↓
FASE 4  → Clientes y cotizaciones
   ↓
FASE 5  → Gestión de proyectos y órdenes
   ↓
FASE 6  → Diseño
   ↓
FASE 7  → Fabricación
   ↓
FASE 8  → Inventario
   ↓
FASE 9  → Facturación y pagos
   ↓
FASE 10 → Dashboard y reportes
   ↓
FASE 11 → Auditoría y trazabilidad
   ↓
FASE 12 → Seguridad, pruebas y despliegue
```

---

# 1. 🔎 Análisis y especificación

### Objetivo

Definir completamente el funcionamiento del sistema antes de comenzar el desarrollo.

### Características

* Identificación de los procesos de la empresa.
* Definición de departamentos.
* Definición de roles y permisos.
* Identificación de actores del sistema.
* Definición de estados de cada proceso.
* Definición de reglas de negocio.
* Definición de flujos de trabajo.
* Identificación de documentos generados.
* Definición de información obligatoria y opcional.
* Definición de eventos que deben quedar registrados.

### Resultado esperado

Documento de especificación funcional que describa cómo debe comportarse WorkForge.

---

# 2. 🏗️ Arquitectura y base de datos

### Objetivo

Diseñar la estructura técnica sobre la cual funcionará el sistema.

### Características

* Arquitectura frontend/backend.
* Diseño de API REST.
* Modelo entidad-relación.
* Diseño de base de datos.
* Relaciones entre entidades.
* Normalización de datos.
* Sistema de migraciones.
* Gestión de archivos.
* Estructura del proyecto.
* Variables de entorno.
* Configuración para desarrollo y producción.

### Tecnologías previstas

* **Frontend:** React + TypeScript.
* **Backend:** Python + FastAPI.
* **Base de datos:** PostgreSQL.
* **Control de versiones:** Git + GitHub.
* **Contenedores:** Docker.

---

# 3. 🔐 Autenticación y usuarios

### Objetivo

Permitir que los integrantes de la empresa accedan al sistema mediante sus credenciales.

### Características

* Inicio de sesión.
* Cierre de sesión.
* Gestión de usuarios.
* Roles.
* Departamentos.
* Permisos.
* Protección de rutas.
* Control de acceso.
* Gestión segura de contraseñas.
* Sesiones/autenticación mediante tokens.
* Registro del usuario responsable de cada acción.

### Roles iniciales

* Administrador.
* Gerencia.
* Comercial.
* Diseño.
* Fabricación.
* Inventario.
* Contabilidad.

Los roles podrán modificarse posteriormente según las necesidades reales de la empresa.

---

# 4. 💼 Clientes y cotizaciones

### Objetivo

Gestionar el proceso comercial previo al inicio de un proyecto.

### Características

### Clientes

* Crear clientes.
* Editar clientes.
* Consultar clientes.
* Historial de proyectos.
* Información de contacto.
* Estado del cliente.

### Cotizaciones

* Crear cotizaciones.
* Asociar cotización a un cliente.
* Agregar productos o servicios.
* Registrar cantidades.
* Registrar precios.
* Calcular subtotales.
* Calcular impuestos.
* Calcular total.
* Adjuntar diseños preliminares.
* Adjuntar documentos.
* Registrar fecha de creación.
* Registrar fecha de modificación.
* Estados de cotización.

### Estados previstos

```text
BORRADOR
   ↓
ENVIADA
   ↓
ACEPTADA
   ↓
ORDEN DE DISEÑO

          o

RECHAZADA
```

---

# 5. 📋 Gestión de proyectos y órdenes

### Objetivo

Convertir una cotización aceptada en un proyecto gestionable dentro del sistema.

### Características

* Crear proyecto desde una cotización aceptada.
* Generar número único de proyecto.
* Crear orden de diseño.
* Definir fecha de entrega.
* Definir prioridad.
* Asociar documentos.
* Registrar observaciones.
* Consultar estado general.
* Historial del proyecto.
* Seguimiento de actividades.

### Sistema de prioridades

```text
🔴 Alta
🟡 Media
🟢 Baja
```

### Lista de espera

Las órdenes pendientes estarán disponibles para los usuarios autorizados.

Un diseñador podrá seleccionar una orden disponible y el sistema registrará automáticamente:

* Usuario que tomó la orden.
* Fecha de aceptación.
* Hora de aceptación.

Esto permitirá medir el tiempo que una orden permanece en espera.

---

# 6. 🎨 Gestión de diseño

### Objetivo

Gestionar las actividades relacionadas con el diseño y preparación técnica de un proyecto.

### Características

* Lista de órdenes pendientes.
* Filtrado por prioridad.
* Filtrado por fecha de entrega.
* Asignación de diseñadores.
* Aceptación de órdenes.
* Registro automático de fecha/hora de inicio.
* Carga de archivos.
* Versionamiento de documentos.
* Observaciones.
* Finalización de tareas.
* Registro automático de fecha/hora de finalización.

### Medición de tiempo

El sistema permitirá determinar:

```text
Tiempo en espera
+
Tiempo de diseño
=
Tiempo total de preparación
```

---

# 7. ⚙️ Gestión de fabricación

### Objetivo

Gestionar la fabricación de los elementos que componen un proyecto.

Una característica fundamental será permitir dividir un proyecto en múltiples piezas.

```text
Proyecto
│
├── Pieza 1
├── Pieza 2
├── Pieza 3
├── Pieza 4
└── Pieza N
```

### Características

* Crear piezas.
* Asociar piezas a proyectos.
* Definir información de fabricación.
* Asignar responsables.
* Registrar inicio de fabricación.
* Registrar finalización.
* Estado individual de cada pieza.
* Observaciones.
* Archivos asociados.
* Seguimiento individual.

### Fabricación paralela

Las piezas podrán ser procesadas independientemente.

Por ejemplo:

```text
Diseño
   │
   ├── Pieza 1 → Fabricación ──→ ✓
   ├── Pieza 2 → Fabricación ──→ ✓
   ├── Pieza 3 → Fabricación ──→ En proceso
   └── Pieza 4 → Fabricación ──→ ✓
```

El proyecto podrá considerarse terminado únicamente cuando todas las tareas requeridas hayan sido completadas.

---

# 8. 📦 Gestión de inventario

### Objetivo

Controlar exclusivamente el inventario de materiales utilizados por la empresa.

### Características

* Registro de materiales.
* Código de material.
* Nombre.
* Descripción.
* Unidad de medida.
* Stock disponible.
* Stock mínimo.
* Proveedores.
* Entradas.
* Salidas.
* Movimientos.
* Historial de movimientos.

### Solicitudes de materiales

Cualquier usuario autorizado podrá realizar una solicitud.

```text
Solicitud
│
├── Usuario
├── Proyecto
├── Material
├── Cantidad
├── Motivo
└── Fecha
```

La solicitud podrá pasar por estados:

```text
PENDIENTE
   ↓
APROBADA
   ↓
ENTREGADA
```

o:

```text
PENDIENTE
   ↓
RECHAZADA
```

### Entradas de inventario

Se podrán registrar:

* Material.
* Cantidad.
* Precio unitario.
* Precio total.
* Proveedor.
* Fecha.
* Número de factura.
* Observaciones.

---

# 9. 💰 Facturación y pagos

### Objetivo

Gestionar el valor económico de los proyectos y determinar el saldo pendiente.

### Características

* Valor total del proyecto.
* Anticipos.
* Pagos.
* Saldos pendientes.
* Registro de facturas.
* Estado de pago.
* Documentos asociados.
* Historial de pagos.

### Ejemplo

```text
Valor del proyecto       $10.000.000
Anticipo                  $3.000.000
Pago adicional            $1.000.000
------------------------------------
Saldo pendiente           $6.000.000
```

El sistema deberá considerar automáticamente los pagos realizados para determinar el saldo restante.

---

# 10. 📊 Dashboard y reportes

### Objetivo

Proporcionar una visión general del funcionamiento de la empresa.

### Indicadores

* Cotizaciones realizadas.
* Cotizaciones aceptadas.
* Cotizaciones rechazadas.
* Proyectos recibidos.
* Proyectos en proceso.
* Proyectos completados.
* Órdenes pendientes.
* Órdenes en diseño.
* Órdenes en fabricación.
* Materiales utilizados.
* Materiales ingresados.
* Ingresos.
* Pagos pendientes.

### Filtros

Los reportes podrán filtrarse por:

* Día.
* Semana.
* Mes.
* Rango de fechas.
* Cliente.
* Proyecto.
* Departamento.
* Usuario.
* Estado.

### Métricas de productividad

El sistema podrá calcular:

```text
Tiempo promedio en espera
Tiempo promedio de diseño
Tiempo promedio de fabricación
Tiempo total del proyecto
```

También podrá analizar el rendimiento por usuario o departamento.

---

# 11. 📝 Auditoría y trazabilidad

### Objetivo

Registrar las acciones importantes realizadas dentro del sistema.

Cada evento podrá almacenar:

```text
Usuario
Fecha
Hora
Proyecto
Acción
Descripción
```

### Ejemplo

```text
10/08/2026 09:14
Andrés
Tomó orden OD-0047

10/08/2026 14:37
Andrés
Finalizó diseño

11/08/2026 07:20
Carlos
Inició fabricación de pieza #3

11/08/2026 13:42
Carlos
Finalizó fabricación de pieza #3
```

Esto permitirá reconstruir la historia completa de un proyecto.

---

# 12. 🛡️ Seguridad, pruebas y despliegue

### Objetivo

Preparar el sistema para un entorno real de producción.

### Seguridad

* Contraseñas almacenadas de forma segura.
* Control de acceso basado en roles.
* Protección de endpoints.
* Validación de datos.
* Control de archivos.
* Protección contra accesos no autorizados.
* Gestión de sesiones.
* Variables sensibles mediante variables de entorno.

### Pruebas

* Pruebas unitarias.
* Pruebas de API.
* Pruebas de integración.
* Validación de permisos.
* Pruebas de flujo completo.

### Despliegue

* Docker.
* Configuración de producción.
* Base de datos PostgreSQL.
* HTTPS.
* Backups.
* Logs.
* Monitoreo básico.

---

# 🔄 Flujo general del sistema

El flujo principal previsto será:

```text
                    CLIENTE
                       │
                       ▼
                 COTIZACIÓN
                       │
              ┌────────┴────────┐
              │                 │
           ACEPTADA          RECHAZADA
              │
              ▼
        ORDEN DE DISEÑO
              │
              ▼
        LISTA DE ESPERA
              │
              ▼
           DISEÑO
              │
              ▼
      DIVISIÓN EN PIEZAS
              │
       ┌──────┼──────┐
       ▼      ▼      ▼
    PIEZA 1 PIEZA 2 PIEZA N
       │      │      │
       └──────┼──────┘
              ▼
         FABRICACIÓN
              │
              ▼
       CONTROL DE ESTADO
              │
              ▼
          FACTURACIÓN
              │
              ▼
       PROYECTO COMPLETO
```

---

# 📈 Trazabilidad del proyecto

Una de las características principales de WorkForge será mantener un registro cronológico de cada proyecto.

```text
Cotización creada
       ↓
Cotización enviada
       ↓
Cotización aceptada
       ↓
Orden de diseño creada
       ↓
Orden entra en espera
       ↓
Diseñador acepta
       ↓
Diseño iniciado
       ↓
Diseño terminado
       ↓
Piezas creadas
       ↓
Fabricación iniciada
       ↓
Piezas terminadas
       ↓
Factura generada
       ↓
Proyecto completado
```

Cada transición deberá conservar la fecha, hora y usuario responsable cuando corresponda.

---

# 🧰 Tecnologías

### Frontend

* React
* TypeScript
* HTML5
* CSS
* Tailwind CSS

### Backend

* Python
* FastAPI
* REST API

### Base de datos

* PostgreSQL

### Desarrollo

* Git
* GitHub
* Docker
* VS Code

### Documentación

* Markdown
* OpenAPI / Swagger

---

# 🚧 Estado del proyecto

> **Actualmente en fase de análisis y planificación.**

El desarrollo se realizará progresivamente siguiendo el roadmap establecido.

```text
[✓] Definición inicial del proyecto
[✓] Definición general del flujo
[ ] Análisis detallado
[ ] Modelo entidad-relación
[ ] Arquitectura
[ ] Backend
[ ] Frontend
[ ] Autenticación
[ ] Gestión de cotizaciones
[ ] Gestión de proyectos
[ ] Gestión de diseño
[ ] Gestión de fabricación
[ ] Gestión de inventario
[ ] Facturación
[ ] Dashboard
[ ] Auditoría
[ ] Pruebas
[ ] Despliegue
```

---

# 📌 Filosofía del proyecto

WorkForge busca centralizar los procesos de la empresa en una única plataforma, reduciendo la dependencia de registros manuales y permitiendo obtener información precisa sobre el estado y rendimiento de cada proyecto.

El sistema se diseñará bajo los principios de:

* **Trazabilidad**
* **Modularidad**
* **Escalabilidad**
* **Seguridad**
* **Automatización**
* **Mantenibilidad**
* **Separación de responsabilidades**

---

## 📄 Licencia

La licencia del proyecto será definida posteriormente de acuerdo con su evolución y posible uso comercial.
