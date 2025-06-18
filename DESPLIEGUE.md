# Guía de Despliegue - Cafrilosa MVP

## Opciones de Despliegue

### 1. Despliegue Rápido con Vercel (Recomendado)

1. **Subir código a GitHub**
   ```bash
   git init
   git add .
   git commit -m "Initial commit - Cafrilosa MVP"
   git remote add origin [URL_DE_TU_REPO]
   git push -u origin main
   ```

2. **Conectar con Vercel**
   - Ir a [vercel.com](https://vercel.com)
   - Conectar repositorio de GitHub
   - Configuración automática detectada
   - Deploy en minutos

### 2. Despliegue con Netlify

1. **Build local**
   ```bash
   npm run build
   ```

2. **Subir carpeta dist/**
   - Ir a [netlify.com](https://netlify.com)
   - Arrastrar carpeta `dist/` al área de deploy
   - URL disponible inmediatamente

### 3. Servidor Web Tradicional

1. **Generar build**
   ```bash
   npm run build
   ```

2. **Subir archivos**
   - Copiar contenido de `dist/` al servidor
   - Configurar servidor web (Apache/Nginx)
   - Asegurar que todas las rutas apunten a `index.html`

## Configuración de Producción

### Variables de Entorno

Si necesitas configurar URLs diferentes para producción, crear archivo `.env`:

```env
VITE_WEBHOOK_VENDEDORES=https://hook.us2.make.com/8wwvk7oe6nj94dn8hr9tvza25nddtgc7
VITE_WEBHOOK_ECOMMERCE=https://hook.us2.make.com/8qosk7cy7bplf5xohybiadittwg6ug7s
VITE_WEBHOOK_PRODUCCION=https://hook.us2.make.com/hb2a48aimuoltrjrx91mdew4fvy5hleq
```

### Configuración de CORS

Asegurar que los webhooks de Make.com permitan requests desde el dominio de producción.

### Optimizaciones

- ✅ Minificación automática con Vite
- ✅ Tree shaking incluido
- ✅ Compresión de assets
- ✅ Lazy loading de componentes

## Monitoreo Post-Despliegue

### Métricas a Monitorear

1. **Tiempo de carga** de la aplicación
2. **Errores de webhooks** en la consola
3. **Uso en dispositivos móviles**
4. **Feedback de usuarios** sobre la interfaz

### Logs Importantes

- Errores de red en DevTools
- Respuestas de webhooks de Make.com
- Rendimiento de la aplicación

## Mantenimiento

### Actualizaciones

```bash
# Actualizar dependencias
npm update

# Rebuild y redeploy
npm run build
```

### Backup

- Código fuente en repositorio Git
- Configuración de webhooks documentada
- Datos en Google Sheets (respaldado por Make.com)

---

**¡La aplicación está lista para producción!** 🚀

