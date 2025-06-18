# Cafrilosa - Dashboard de Ventas MVP

![Cafrilosa Logo](src/assets/CAFRILOSA_logo.png)

## Descripción

Dashboard CRM desarrollado para potenciar el equipo de ventas de Cafrilosa desde oficina, centralizando pedidos de vendedores, seguimiento de ventas de eCommerce, gestión de despachos y cuentas por cobrar.

## Características Principales

### 🎯 Módulos Implementados

1. **Pedidos de Vendedores**
   - Visualización de pedidos del equipo de ventas interno
   - Acciones de un solo clic para envío a producción
   - Estadísticas de pedidos pendientes y en producción

2. **Pedidos eCommerce**
   - Gestión de pedidos de plataformas online
   - Análisis por plataforma (Tienda Online, Marketplace)
   - Cálculo de ticket promedio

3. **Cuentas por Cobrar**
   - Seguimiento de facturas y pagos
   - Alertas de cuentas vencidas
   - Gestión de estados de pago

### ⚡ Funcionalidades Clave

- **Acciones de Un Solo Clic**: Botones ✔️ y ➕ para confirmar pedidos o agregar comentarios
- **Integración con Make.com**: Webhooks configurados para sincronización automática
- **Notificaciones en Tiempo Real**: Sistema de toast para feedback inmediato
- **Diseño Responsive**: Adaptable a desktop, tablet y móvil
- **Estadísticas Dinámicas**: Contadores y métricas que se actualizan automáticamente

## Tecnologías Utilizadas

- **Frontend**: React 18 + Vite
- **Estilos**: Tailwind CSS + shadcn/ui
- **Iconos**: Lucide React
- **Animaciones**: Framer Motion
- **Integración**: Webhooks de Make.com

## Instalación y Configuración

### Prerrequisitos

- Node.js 18+ 
- npm o pnpm

### Pasos de Instalación

1. **Clonar o descargar el proyecto**
   ```bash
   cd cafrilosa-mvp
   ```

2. **Instalar dependencias**
   ```bash
   npm install
   # o
   pnpm install
   ```

3. **Iniciar servidor de desarrollo**
   ```bash
   npm run dev
   # o
   pnpm run dev
   ```

4. **Abrir en navegador**
   ```
   http://localhost:5173
   ```

## Configuración de Webhooks

Los webhooks de Make.com están preconfigurados en `src/lib/webhookService.js`:

- **Pedidos Vendedores**: `https://hook.us2.make.com/8wwvk7oe6nj94dn8hr9tvza25nddtgc7`
- **eCommerce**: `https://hook.us2.make.com/8qosk7cy7bplf5xohybiadittwg6ug7s`
- **Órdenes de Producción**: `https://hook.us2.make.com/hb2a48aimuoltrjrx91mdew4fvy5hleq`

## Estructura del Proyecto

```
cafrilosa-mvp/
├── src/
│   ├── assets/              # Recursos estáticos (logo, imágenes)
│   ├── components/          # Componentes React
│   │   ├── Sidebar.jsx      # Menú lateral de navegación
│   │   ├── TablaBase.jsx    # Componente base para tablas
│   │   ├── BotonAccion.jsx  # Botones de acción (✔️ ➕)
│   │   ├── PedidosVendedores.jsx
│   │   ├── PedidosEcommerce.jsx
│   │   ├── CuentasPorCobrar.jsx
│   │   └── NotificacionToast.jsx
│   ├── hooks/               # Hooks personalizados
│   │   └── useApp.jsx       # Context y estado global
│   ├── lib/                 # Servicios y utilidades
│   │   ├── webhookService.js # Integración con Make.com
│   │   └── dataService.js   # Manejo de datos y formateo
│   ├── App.jsx              # Componente principal
│   └── main.jsx             # Punto de entrada
├── public/                  # Archivos públicos
├── package.json             # Dependencias y scripts
└── README.md               # Este archivo
```

## Uso de la Aplicación

### Navegación

Utiliza el menú lateral para navegar entre los tres módulos principales:

1. **Pedidos Vendedores** 🛒
2. **Pedidos eCommerce** 🌐  
3. **Cuentas por Cobrar** 💳

### Acciones Principales

#### En Pedidos (Vendedores y eCommerce)

- **Botón ✔️**: Envía el pedido a producción con un solo clic
- **Botón ➕**: Abre formulario para agregar comentarios antes del envío

#### En Cuentas por Cobrar

- **Botón ✔️**: Marca la factura como pagada

### Notificaciones

El sistema muestra notificaciones automáticas para:
- ✅ Acciones exitosas
- ❌ Errores en la integración
- ℹ️ Información relevante

## Datos de Prueba

La aplicación incluye datos simulados para demostración:

- 3 pedidos de vendedores
- 3 pedidos de eCommerce  
- 3 cuentas por cobrar

En producción, estos datos se reemplazarán por información real desde Google Sheets via Make.com.

## Despliegue

### Construcción para Producción

```bash
npm run build
```

### Despliegue

Los archivos generados en `dist/` pueden desplegarse en cualquier servidor web estático o plataforma como:

- Vercel
- Netlify  
- GitHub Pages
- Servidor web tradicional

## Soporte y Mantenimiento

### Logs y Debugging

- Abrir DevTools del navegador (F12)
- Revisar la consola para logs de webhooks
- Verificar la pestaña Network para llamadas HTTP

### Personalización

#### Cambiar Colores o Estilos

Editar `src/App.css` y las clases de Tailwind en los componentes.

#### Agregar Nuevos Módulos

1. Crear componente en `src/components/`
2. Agregar ruta en `src/App.jsx`
3. Actualizar menú en `src/components/Sidebar.jsx`

#### Modificar Webhooks

Editar URLs en `src/lib/webhookService.js`

## Contacto y Soporte

Para soporte técnico o consultas sobre la aplicación, contactar al equipo de desarrollo.

---

**Versión**: 1.0.0  
**Fecha**: Diciembre 2024  
**Estado**: Listo para Producción ✅

