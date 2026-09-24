# Enanos Backend

API REST hecha con **Express + TypeScript + Prisma (SQLite)** para gestionar Enanos (nombre y edad).

Parte del trabajo práctico de la materia Aplicaciones Móviles, basado en el ejemplo
[prisma-examples/orm/express](https://github.com/prisma/prisma-examples/tree/latest/orm/express),
adaptado de PostgreSQL a SQLite.

## Cómo correrlo

1. Clonar el repositorio:
```bash
   git clone https://github.com/Edgardo0510/enanos-backend.git
   cd enanos-backend
```

2. Instalar las dependencias:
```bash
   npm install
```

3. Crear un archivo `.env` en la raíz del proyecto con:

DATABASE_URL="file:./dev.db"

4. Generar el cliente de Prisma y aplicar las migraciones:
```bash
   npx prisma generate
   npx prisma migrate dev
```

5. Levantar el servidor:
```bash
   npm run dev
```

El servidor queda corriendo en `http://localhost:3000`.

## Endpoints de Enano

| Método | Ruta            | Descripción                          |
|--------|-----------------|---------------------------------------|
| GET    | `/enanos`       | Lista todos los Enanos                |
| POST   | `/enanos`       | Crea un Enano (`nombre`, `edad`)      |
| DELETE | `/enanos/:id`   | Elimina un Enano por su `id`          |

### Ejemplo con curl

```bash
curl -X POST http://localhost:3000/enanos \
  -H "Content-Type: application/json" \
  -d '{"nombre":"Gruñón","edad":250}'

curl http://localhost:3000/enanos

curl -X DELETE http://localhost:3000/enanos/1
```
