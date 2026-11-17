<p align="center">
  <img src="assets/logo-kampu.png" alt="Kampu Tour Manager" width="300" />
</p>

<h3 align="center">Plataforma integral de gestión operativa y comercial<br />para agencias de turismo y operadores de viajes</h3>
<p align="center">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@v2.16.0/icons/angular/angular-original.svg" alt="Angular" height="40" />
  &nbsp;&nbsp;&nbsp;&nbsp;
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@v2.16.0/icons/java/java-original.svg" alt="Java" height="40" />
  &nbsp;&nbsp;&nbsp;&nbsp;
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@v2.16.0/icons/spring/spring-original.svg" alt="Spring Boot" height="40" />
  &nbsp;&nbsp;&nbsp;&nbsp;
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@v2.16.0/icons/oracle/oracle-original.svg" alt="Oracle" height="40" />

</p>

<p align="center">
  <a href="#descripción-general">Descripción</a> &nbsp;·&nbsp;
  <a href="#módulos-principales">Módulos</a> &nbsp;·&nbsp;
  <a href="#arquitectura">Arquitectura</a> &nbsp;·&nbsp;
  <a href="#instalación">Instalación</a> &nbsp;·&nbsp;
  <a href="#equipo">Equipo</a>
</p>

---

## Descripción general

**Kampu** es una solución *Full Stack* que centraliza, estandariza y automatiza los flujos de trabajo de una agencia de viajes. Cubre todo el ciclo operativo: desde la estructuración de paquetes turísticos y la programación de salidas, hasta la gestión de reservas, la asignación de recursos logísticos y el control financiero multimoneda.

---

## Módulos principales

<details>
<summary><b>Panel de control (Dashboard)</b></summary>
<br />
Resumen ejecutivo de métricas operativas, ocupación y estado general de la agencia.
</details>

<details>
<summary><b>Catálogo de paquetes turísticos</b></summary>
<br />
Administración de tours, itinerarios, tarifas base y material multimedia.
</details>

<details>
<summary><b>Programación de salidas</b></summary>
<br />
Control de fechas, disponibilidad de cupos y asignación de recursos por salida.
</details>

<details>
<summary><b>Gestión de reservas y pasajeros</b></summary>
<br />
Flujo completo de registro, seguimiento detallado de pasajeros y procesamiento de anulaciones.
</details>

<details>
<summary><b>Directorio de clientes</b></summary>
<br />
Registro centralizado e historial comercial de clientes.
</details>

<details>
<summary><b>Recursos operativos</b></summary>
<br />
Administración de guías turísticos y flota de transporte asignada.
</details>

<details>
<summary><b>Pagos y multimoneda</b></summary>
<br />
Registro de abonos, liquidación de pagos y conversión de divisas integrada.
</details>

<details>
<summary><b>Autenticación y seguridad</b></summary>
<br />
Control de sesiones mediante interceptores, validación de acceso y gestión de roles de usuario.
</details>

---

## Arquitectura

Monorepo desacoplado en dos aplicaciones principales:

<details open>
<summary><b>Estructura del proyecto</b></summary>

```text
kampu-app/
├── assets/                    # Identidad visual y recursos estáticos
├── kampu-frontend/            # Single Page Application (Angular)
│   └── src/app/
│       ├── core/              # Modelos, servicios HTTP, autenticación y utilidades
│       ├── features/          # Módulos funcionales (dashboard, paquetes, salidas, reservas, pagos...)
│       ├── layout/            # Contenedor principal y navegación
│       └── shared/            # Componentes reutilizables
│
└── kampu-backend/             # API RESTful (Java / Spring Boot)
    └── src/main/
        ├── java/.../lp2_gp2/
        │   ├── config/        # Seguridad, CORS, interceptores y OpenAPI
        │   ├── controller/    # Controladores REST
        │   ├── dto/           # Objetos de transferencia y validaciones
        │   ├── entity/        # Entidades JPA
        │   ├── exception/     # Manejador global de excepciones
        │   ├── repository/    # Persistencia (Spring Data JPA)
        │   └── services/      # Lógica de negocio, archivos y conversión de moneda
        └── resources/
            └── db/            # 01_schema.sql (esquema) y 02_data.sql (datos iniciales)
```

</details>

---

## Instalación

### Requisitos previos

* **Java JDK 17** o superior
* **Node.js 18+** y **npm**
* **Angular CLI**
* Motor de base de datos relacional configurado según `application.yaml`

### 1. Clonar el repositorio

```bash
git clone https://github.com/soforee/kampu-app.git
cd kampu-app
```

### 2. Backend

<details>
<summary><b>Ver pasos del backend</b></summary>
<br />

1. Edita `kampu-backend/src/main/resources/application.yaml` con las credenciales de tu base de datos local.
2. Ejecuta los scripts de `kampu-backend/src/main/resources/db/` (`01_schema.sql` y luego `02_data.sql`) para cargar la estructura y los datos de prueba.
3. Inicia el servidor:

```bash
cd kampu-backend
./mvnw spring-boot:run
```

La documentación interactiva de los endpoints queda disponible en Swagger / OpenAPI una vez iniciado el servicio.

</details>

### 3. Frontend

<details>
<summary><b>Ver pasos del frontend</b></summary>
<br />

En una nueva terminal:

```bash
cd kampu-frontend
npm install
npm start
```

Abre la aplicación en **http://localhost:4200**

</details>

---

## Equipo

<div align="center">
<table>
  <tr>
    <td align="center" width="200">
      <a href="https://github.com/soforee">
        <img src="https://github.com/soforee.png?size=100" width="90" alt="Russell Diaz Nuñez" /><br />
        <sub><b>Russell Diaz Nuñez</b></sub>
      </a><br />
      <sub>@soforee</sub>
    </td>
    <td align="center" width="200">
      <a href="https://github.com/stardolllar">
        <img src="https://github.com/stardolllar.png?size=100" width="90" alt="Doriann Gonzales Navarro" /><br />
        <sub><b>Doriann Gonzales Navarro</b></sub>
      </a><br />
      <sub>@stardolllar</sub>
    </td>
    <td align="center" width="200">
      <a href="https://github.com/ssh4123">
        <img src="https://github.com/ssh4123.png?size=100" width="90" alt="Rodrigo Usuriaga Salas" /><br />
        <sub><b>Rodrigo Usuriaga Salas</b></sub>
      </a><br />
      <sub>@ssh4123</sub>
    </td>
  </tr>
</table>
</div>
