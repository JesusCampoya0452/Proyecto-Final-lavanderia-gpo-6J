Te doy un ejemplo claro usando una base de datos tipo **NoSQL (MongoDB)**, que maneja **colecciones (collections)** y **documentos (documents)**. Ideal para algo como una lavandería 👇

---

## 🧺 Base de datos: `lavanderia`

### 📁 Colección: `clientes`

**Documento ejemplo:**

```json
{
  "_id": "ObjectId",
  "nombre": "Juan Pérez",
  "telefono": "6561234567",
  "email": "juan@gmail.com",
  "direccion": {
    "calle": "Av. Reforma",
    "numero": 123,
    "ciudad": "Ciudad Juárez"
  },
  "fecha_registro": "2026-04-27T10:00:00Z"
}
```

**Atributos y tipos:**

* `_id`: ObjectId
* `nombre`: String
* `telefono`: String
* `email`: String
* `direccion`: Objeto
* `fecha_registro`: Date

---

### 📁 Colección: `servicios`

**Documento ejemplo:**

```json
{
  "_id": "ObjectId",
  "tipo": "Lavado y secado",
  "precio": 80.50,
  "descripcion": "Incluye detergente y suavizante"
}
```

**Atributos:**

* `_id`: ObjectId
* `tipo`: String
* `precio`: Number (decimal)
* `descripcion`: String

---

### 📁 Colección: `ordenes`

**Documento ejemplo:**

```json
{
  "_id": "ObjectId",
  "cliente_id": "ObjectId",
  "servicios": [
    {
      "servicio_id": "ObjectId",
      "cantidad": 2,
      "subtotal": 161.00
    }
  ],
  "total": 161.00,
  "estado": "En proceso",
  "fecha_orden": "2026-04-27T11:00:00Z",
  "fecha_entrega": "2026-04-28T18:00:00Z"
}
```

**Atributos:**

* `_id`: ObjectId
* `cliente_id`: ObjectId (referencia)
* `servicios`: Array de objetos
* `total`: Number
* `estado`: String (Ej: "En proceso", "Listo", "Entregado")
* `fecha_orden`: Date
* `fecha_entrega`: Date

---

### 📁 Colección: `pagos`

**Documento ejemplo:**

```json
{
  "_id": "ObjectId",
  "orden_id": "ObjectId",
  "metodo_pago": "Efectivo",
  "monto": 161.00,
  "fecha_pago": "2026-04-27T12:00:00Z"
}
```

**Atributos:**

* `_id`: ObjectId
* `orden_id`: ObjectId
* `metodo_pago`: String
* `monto`: Number
* `fecha_pago`: Date

---

## 💡 Idea general

* **Clientes** → quién usa el servicio
* **Servicios** → qué ofrece la lavandería
* **Órdenes** → pedidos de los clientes
* **Pagos** → cómo se paga cada orden

---

Si quieres, también puedo darte el mismo ejemplo pero en **SQL (tablas)** o ayudarte a hacerlo directamente en **MongoDB Atlas o código** 👍
