# Arquitectura de la Aplicación Cafrilosa MVP

## Estructura de Componentes

### Layout Principal
- **App.jsx**: Componente principal que maneja el routing y estado global
- **Layout.jsx**: Layout principal con menú lateral y área de contenido
- **Sidebar.jsx**: Menú lateral con navegación entre módulos

### Módulos Principales
1. **PedidosVendedores**: Gestión de pedidos de vendedores internos
2. **PedidosEcommerce**: Gestión de pedidos de eCommerce
3. **CuentasPorCobrar**: Gestión de cuentas por cobrar

### Componentes Compartidos
- **TablaBase.jsx**: Componente base para todas las tablas
- **BotonAccion.jsx**: Botones de acción (✔️ y ➕)
- **FormularioInline.jsx**: Formulario desplegable para comentarios
- **NotificacionToast.jsx**: Notificaciones de éxito/error

## Estado de la Aplicación

### Context API
- **AppContext**: Estado global de la aplicación
- **PedidosContext**: Estado específico de pedidos
- **NotificacionesContext**: Manejo de notificaciones

### Estructura de Datos

#### Pedido
```javascript
{
  id: string,
  fecha: Date,
  vendedor: string, // o plataforma para eCommerce
  cliente: string,
  detalle: string,
  total: number,
  estado: 'pendiente' | 'enviado_produccion' | 'despachado',
  comentarios?: string,
  timestamp_accion?: Date
}
```

#### Cuenta por Cobrar
```javascript
{
  id: string,
  factura: string,
  cliente: string,
  monto: number,
  vence: Date,
  estado_pago: 'pendiente' | 'pagado' | 'vencido'
}
```

## Integración con Webhooks

### URLs de Webhooks
- Pedidos Vendedores: `https://hook.us2.make.com/8wwvk7oe6nj94dn8hr9tvza25nddtgc7`
- eCommerce: `https://hook.us2.make.com/8qosk7cy7bplf5xohybiadittwg6ug7s`
- Órdenes de Producción: `https://hook.us2.make.com/hb2a48aimuoltrjrx91mdew4fvy5hleq`

### Servicio de API
- **webhookService.js**: Manejo de llamadas a webhooks
- **dataService.js**: Simulación de datos y polling

## Funcionalidades Clave

### Acciones de Un Solo Clic
- Botón ✔️: Marcar como "Enviado a Producción"
- Botón ➕: Abrir formulario inline para comentarios

### Actualizaciones en Tiempo Real
- Polling ligero cada 30 segundos
- Animaciones suaves para cambios de estado
- Feedback visual inmediato

### Responsive Design
- Diseño adaptable para desktop y tablet
- Menú lateral colapsable en móviles

## Tecnologías Utilizadas
- React 18 con Hooks
- Tailwind CSS para estilos
- shadcn/ui para componentes
- Lucide React para iconos
- Framer Motion para animaciones
- React Router para navegación

