
# Plataforma de Café Especial Colombiano

## Descripción

Plataforma e-commerce, diseñada para conectar productores de café especial colombiano (campesinos) directamente con compradores, eliminando intermediarios. Busca empoderar a los productores locales (por ejemplo, en Nariño) y promover venta justa, trazabilidad y prácticas sostenibles.

## Objetivos

- **Impacto social:** Aumentar ingresos de los campesinos ~20–30% al reducir comisiones e intermediación.
- **MVP:** Registro de usuarios (campesinos y compradores), listado de productos (fotos, descripciones, origen), recomendaciones básicas con APIs de IA, y deploy escalable en la nube.
- **Proyección:** Escalar nacional e internacionalmente; integrar pagos (Stripe), logística, IA avanzada (predicción de cosechas/demanda) y certificaciones (orgánico/especial).

## Tecnologías

- Backend: Spring Boot (Clean Architecture)
- Frontend: React / Next.js
- Infraestructura: AWS (S3, EC2, RDS), CI/CD con GitHub Actions
- Requisitos locales: Java 17+, Node.js 18+, Git

## Instalación (rápida)

Clona el repositorio (reemplaza <repo-url> por la URL real del repositorio):

```bash
git clone <repo-url>
cd cafiro
```

Backend (Spring Boot — Gradle wrapper incluido en este repo):

```bash
cd cafiro
./gradlew bootRun    # Linux/macOS
# o en Windows:
gradlew.bat bootRun
```

Si usas Maven en otro fork/proyecto:

```bash
mvn spring-boot:run
```

Configura variables de entorno en `application.properties` o via env vars (DB URL, credenciales AWS, keys de servicios de pago).

Frontend (Next.js — ejemplo):

```bash
cd frontend
npm install
npm run dev
# Abre http://localhost:3000
```

## Deploy inicial (sugerencia)

- Configura `aws` CLI y crea un bucket S3 para assets y backups.
- Para producción usa: RDS (DB), ECS/EC2 o AWS Elastic Beanstalk para el backend, y Vercel/Netlify para el frontend.
- Añade CI/CD con GitHub Actions para build/test/deploy.

## Uso (flujo básico)

- Como Campesino: regístrate, sube productos (origen, variedad, proceso, altura, fotos), gestiona stock y pedidos.
- Como Comprador: busca por origen/variedad, filtra por certificaciones, revisa perfil del productor y compra directo.

Ejemplo simple de API REST:

```
GET /api/products      # lista productos disponibles
GET /api/products/{id} # detalle de un café
POST /api/auth/register # registrar usuario
```

## Estructura propuesta (Clean Architecture)

- `/domain` — Entidades + reglas de negocio puras
- `/application` — Casos de uso / Interactors
- `/infrastructure` — Adaptadores (DB, AWS, servicios externos)
- `/presentation` — Controllers REST, seguridad

Frontend (features-based):

- `/src/features/products` — componentes, hooks, vistas de listing
- `/src/features/users` — registro, autenticación

## Recomendaciones iniciales de MVP

- Empezar local y validar con 1–2 comunidades productoras.
- Priorizar onboarding sencillo para campesinos (UX accesible, móvil-first).
- Implementar trazabilidad mínima: origen + fotos + fecha de cosecha.

## Contribuciones

1. Forkea el repo
2. Crea una rama: `git checkout -b feature/nombre-funcion`
3. Envía un PR describiendo el cambio

Prioridades: integraciones IA, pagos seguros, mejoras mobile.

## Licencia

MIT License — libre para usar y modificar, se agradece atribución.

## Contacto

Nicolás García — nikolasg12000@gmail.com

---

Este README se actualizará conforme avance el proyecto. ¡Manos a la obra para construir impacto real en las zonas cafeteras de Colombia!
