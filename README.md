# Tutorial-Web — Formulario de Registro con Supabase

Proyecto web moderno con formulario de registro conectado a Supabase.

---

## 📁 Estructura del proyecto

```
Tutorial-Web/
├── frontend/           ← 👁️  Visual + Funcionalidades del cliente
│   ├── index.html      ← Página con el formulario
│   ├── styles.css      ← Diseño oscuro moderno (CSS puro)
│   └── app.js          ← Validaciones + conexión a Supabase (JS puro)
│
├── backend/            ← 🗄️  Base de datos
│   └── schema.sql      ← SQL para crear la tabla con permisos públicos
│
├── package.json
└── README.md
```

---

## 🗄️ PASO 1 — Crear la tabla en Supabase

1. Abre tu proyecto → [SQL Editor](https://supabase.com/dashboard/project/cvvallodsetqersupfia/sql/new)
2. Copia el contenido de `backend/schema.sql`
3. Pégalo y presiona **Run ▶️**

Esto crea la tabla `registro_usuarios` con:
- ✅ RLS habilitado
- ✅ Política pública de INSERT (rol `anon`)
- ✅ Política pública de SELECT (rol `anon`)

---

## 🚀 PASO 2 — Ejecutar el proyecto

Abre CMD en la carpeta del proyecto:

```cmd
npm install
npm run dev
```

Luego abre en el navegador:

```
http://localhost:3000/frontend/index.html
```

> ⚠️ **No abras el HTML directamente** haciendo doble clic. Usa el servidor para que los módulos ES funcionen.

---

## 📋 Campos del formulario

| Campo           | Tipo     | Obligatorio |
|-----------------|----------|-------------|
| Nombre completo | Texto    | ✅ Sí       |
| Teléfono        | Tel      | ✅ Sí       |
| Correo          | Email    | ✅ Sí (único) |
| Ciudad          | Texto    | ❌ No       |
| Mensaje         | Textarea | ❌ No       |
| Aceptar términos | Checkbox | ✅ Sí      |

---

## 🔑 Credenciales Supabase (en `frontend/app.js`)

| Variable   | Valor |
|------------|-------|
| URL        | `https://cvvallodsetqersupfia.supabase.co` |
| Anon Key   | Ya configurada en el archivo |

---

## 🔍 Verificar conexión

Al abrir la página, la consola del navegador (`F12 → Console`) mostrará:

- ✅ `[Supabase] Conexión exitosa` → todo ok
- ⚠️ Si aparece un error → revisa que el schema SQL fue ejecutado en Supabase
