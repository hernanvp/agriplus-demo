# 🚀 Cómo Publicar en GitHub Pages

## 📋 Opción 1: Usando la Interfaz Web (Más Fácil)

### Paso 1: Crear Repositorio
1. Ve a [github.com/new](https://github.com/new)
2. **Repository name**: `agriplus-demo`
3. **Description**: "Dashboard interactivo de análisis de cosecha - Agriplus"
4. ✅ Marcar como **Public**
5. ❌ NO marcar "Add README" (ya tienes uno)
6. Click **"Create repository"**

### Paso 2: Subir Archivos
1. En la página del repositorio nuevo, click **"uploading an existing file"**
2. Arrastra los archivos:
   - `index.html`
   - `README.md`
3. En "Commit message" escribe: `Initial commit - Agriplus Dashboard`
4. Click **"Commit changes"**

### Paso 3: Activar GitHub Pages
1. En tu repositorio, click **Settings** (arriba)
2. En el menú izquierdo, click **Pages**
3. En **Source**, selecciona: `main` branch
4. Click **Save**
5. ⏳ Espera 1-2 minutos

### Paso 4: Obtener tu URL
Tu sitio estará en:
```
https://TU-USUARIO.github.io/agriplus-demo/
```

Ejemplo si tu usuario es "hernanvp":
```
https://hernanvp.github.io/agriplus-demo/
```

---

## 📋 Opción 2: Usando Git (Terminal)

### Requisitos
- Git instalado
- Cuenta de GitHub configurada

### Comandos

```bash
# 1. Ir a la carpeta del proyecto
cd /ruta/a/Agriplus/agriplus-demo

# 2. Inicializar Git
git init

# 3. Agregar archivos
git add .

# 4. Primer commit
git commit -m "Initial commit - Agriplus Dashboard"

# 5. Configurar rama principal
git branch -M main

# 6. Conectar con GitHub (REEMPLAZA 'TU-USUARIO')
git remote add origin https://github.com/TU-USUARIO/agriplus-demo.git

# 7. Subir código
git push -u origin main
```

Luego sigue **Paso 3** de la Opción 1 para activar Pages.

---

## ✅ Verificación

Una vez publicado:

1. **Verifica que funcione**:
   - Abre tu URL en el navegador
   - Comprueba que el mapa cargue
   - Prueba los filtros y gráficos

2. **Comparte el link**:
   - Copia la URL de GitHub Pages
   - Puedes compartirla públicamente
   - Funciona en cualquier dispositivo

---

## 🔄 Actualizar el Dashboard

Cuando quieras actualizar el sitio:

### Opción Web:
1. Ve al repositorio en GitHub
2. Click en el archivo que quieras editar
3. Click en el ícono del lápiz ✏️
4. Haz tus cambios
5. Click "Commit changes"
6. GitHub Pages se actualiza automáticamente en 1-2 minutos

### Opción Git:
```bash
git add .
git commit -m "Descripción de los cambios"
git push
```

---

## 🎨 Personalización Opcional

### Cambiar el nombre del sitio

Por defecto: `agriplus-demo.github.io`

Para usar dominio personalizado:
1. Settings → Pages → Custom domain
2. Ingresa tu dominio (ej: `dashboard.agriplus.com`)
3. Configura DNS según instrucciones

### Mejorar el README

El README.md es lo primero que ven en GitHub. Ya incluí uno completo, pero puedes:
- Agregar screenshots
- Incluir logo de Agriplus
- Añadir badges (status, versión, etc.)

---

## 🆘 Solución de Problemas

### El sitio no carga
- ⏳ Espera 2-3 minutos después de activar Pages
- 🔄 Refresca con Ctrl+F5 (limpia caché)
- ✅ Verifica que Source esté en `main` branch

### Error 404
- Verifica que el archivo se llame exactamente `index.html`
- Debe estar en la raíz del repositorio, no en subcarpeta

### Mapa no aparece
- Abre consola del navegador (F12)
- Si hay errores, pueden ser por:
  - Bloqueador de anuncios
  - Conexión a internet
  - CDN externo bloqueado

---

## 📞 ¿Necesitas Ayuda?

Si tienes problemas:
1. Revisa la [documentación oficial](https://docs.github.com/en/pages)
2. Verifica el status de GitHub: [githubstatus.com](https://www.githubstatus.com)
3. Contacta: hvp@icodriver.com

---

🎉 **¡Listo! Tu dashboard estará público y accesible desde cualquier lugar.**
