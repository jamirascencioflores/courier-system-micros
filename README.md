## Sistema de Gestión Courier (Microservicios) 📦

Plataforma escalable para la gestión logística y seguimiento de envíos en tiempo real. Este proyecto demuestra el uso de arquitecturas modernas distribuidas y comunicación asíncrona entre servicios.

---

### 🛠️ Stack Tecnológico
***Frontend***

 - **Angular:** Framework principal para la interfaz de usuario.

 - **TypeScript:** Lenguaje base para un desarrollo tipado y seguro.

***Backend (Microservicios con Spring Boot)***

- **Spring Cloud Gateway:** Enrutamiento centralizado y manejo de CORS.

- **Netflix Eureka:** Service Discovery para el registro dinámico de instancias.

- **Spring Security & JWT:** Autenticación y autorización centralizada (MS-AUTH).

- **RabbitMQ:** Comunicación asíncrona y mensajería entre microservicios (Event-Driven).

- **PostgreSQL:** Base de datos relacional (una instancia independiente por microservicio).
  
---
### 🏗️ Arquitectura del Sistema
El sistema se divide en varios componentes especializados:

1. **API Gateway:** Punto de entrada único que gestiona la seguridad y redirige el tráfico.

2. **Discovery Server:** Permite que los servicios se encuentren entre sí sin configurar IPs estáticas.

3. **MS-Auth:** Gestiona usuarios, roles y generación de tokens JWT.

4. **MS-Orders:** Controla el ciclo de vida de los pedidos y órdenes.

5. **MS-Shipping:** Lógica de logística, cálculo de costos y rutas.

6. **MS-Notifications:** Envío de alertas mediante RabbitMQ al ocurrir eventos en el sistema.

---

### 🚀 Configuración y Ejecución

***Requisitos***
- Java 17+ y Node.js.

- PostgreSQL corriendo en el puerto `5432`.

- RabbitMQ activo en el puerto `5672`.
---

**Pasos para levantar el ecosistema**

1. **Infraestructura:** Crear las bases de datos `db_auth`, `db_orders` y `db_shipping`.

2. **Servidor de Descubrimiento:** Ejecutar `discovery-server` (Puerto 8761).

3. **Puerta de Enlace:** Ejecutar `api-gateway` (Puerto 8080).
   
4. **Servicios de Negocio:** Levantar los microservicios restantes en cualquier orden.
   
5. **Frontend:** Dentro de `courier-frontend`, ejecutar `npm install` y luego `ng serve`.
