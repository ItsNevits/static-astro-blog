# 🚀 Blog Astro

Un blog moderno construido con **Astro** y **Tailwind CSS**, diseñado para ser rápido, accesible y fácil de mantener.

## ✨ Características

- 🎯 **Astro** - Framework moderno para sitios web estáticos y dinámicos
- 🎨 **Tailwind CSS** - Framework de CSS utilitario para diseño rápido
- 📝 **MDX** - Soporte completo para Markdown con componentes React/Vue/Svelte
- � **Content Collections** - Sistema de gestión de contenido tipado
- 👥 **Sistema de Autores** - Perfiles de autores con avatares y redes sociales
- 📱 **Diseño Responsivo** - Optimizado para dispositivos móviles y escritorio
- 🔍 **SEO Optimizado** - Meta tags, Open Graph y estructura semántica
- 📡 **RSS Feed** - Feed RSS automático para suscriptores
- 🏷️ **Sistema de Etiquetas** - Organización de contenido por categorías
- ⚡ **Optimización de Imágenes** - Carga optimizada de imágenes

## 🛠️ Tecnologías Utilizadas

- **Astro** v5.13.5 - Framework principal
- **Tailwind CSS** v4.1.12 - Estilos y diseño
- **MDX** v4.3.4 - Contenido con componentes
- **RSS** v4.0.12 - Generación de feeds
- **TypeScript** - Tipado estático
- **PNPM** - Gestor de paquetes

## 📁 Estructura del Proyecto

```
├── public/                    # Archivos estáticos
│   ├── favicon.svg
│   ├── assets/images/         # Imágenes públicas
│   └── styles/rss.xsl        # Estilos para RSS
├── src/
│   ├── components/           # Componentes reutilizables
│   │   ├── AuthorCard.astro
│   │   ├── BlogPost.astro
│   │   └── TypedBlogPost.astro
│   ├── config/              # Configuración del sitio
│   │   └── site-config.ts
│   ├── content/             # Contenido del blog
│   │   ├── config.ts        # Esquemas de Content Collections
│   │   ├── author/          # Datos de autores
│   │   └── blog/            # Posts del blog
│   ├── layouts/             # Layouts de página
│   │   ├── BlogLayout.astro
│   │   └── MainLayout.astro
│   ├── pages/               # Páginas y rutas
│   │   ├── index.astro      # Página principal
│   │   ├── rss.xml.ts       # Feed RSS
│   │   ├── authors/         # Páginas de autores
│   │   ├── blog/            # Páginas de blog
│   │   └── posts/           # Posts individuales
│   ├── styles/              # Estilos CSS
│   └── utils/               # Utilidades
└── astro.config.mjs         # Configuración de Astro
```

## 🚀 Instalación y Configuración

### Prerequisitos

- Node.js 18+ o superior
- PNPM (recomendado) o NPM

### Instalación

1. **Clona el repositorio**

   ```bash
   git clone <tu-repositorio>
   cd 03-blog
   ```

2. **Instala las dependencias**

   ```bash
   pnpm install
   ```

3. **Configura el sitio**

   Edita `src/config/site-config.ts`:

   ```typescript
   export const SiteConfig = {
     title: "Tu Blog",
     description: "Descripción de tu blog",
   };
   ```

   Actualiza `astro.config.mjs`:

   ```javascript
   export default defineConfig({
     site: "https://tu-dominio.com",
     // ... resto de configuración
   });
   ```

## 🎯 Comandos Disponibles

| Comando        | Descripción                            |
| -------------- | -------------------------------------- |
| `pnpm dev`     | Inicia el servidor de desarrollo       |
| `pnpm build`   | Construye el proyecto para producción  |
| `pnpm preview` | Vista previa de la build de producción |
| `pnpm astro`   | Ejecuta comandos de Astro CLI          |

## 📝 Gestión de Contenido

### Creando un Nuevo Post

1. **Crea un archivo markdown** en `src/content/blog/`:

   ```markdown
   ---
   title: "Tu Título"
   date: 2024-01-01
   description: "Descripción del post"
   author: jane-doe
   image: "images/tu-imagen.png"
   tags: [JavaScript, Web Development]
   isDraft: false
   ---

   # Tu contenido aquí

   Escribe tu post usando Markdown o MDX.
   ```

2. **Agrega la imagen** en `src/content/blog/images/`

### Añadiendo un Autor

1. **Crea un archivo YAML** en `src/content/author/`:

   ```yaml
   name: "Tu Nombre"
   avatar: "./avatars/tu-avatar.webp"
   twitter: "@tu_twitter"
   linkedIn: "https://linkedin.com/in/tu-perfil"
   bio: "Tu biografía aquí"
   ```

2. **Agrega el avatar** en `src/content/author/avatars/`

## 🎨 Personalización

### Estilos

- **Tailwind CSS**: Modifica `src/styles/tailwind.css` para configuraciones globales
- **CSS Global**: Usa `src/styles/global.css` para estilos personalizados
- **CSS de Blog**: Personaliza `src/styles/blog.css` para estilos específicos del blog

### Componentes

Los componentes principales están en `src/components/`:

- `AuthorCard.astro` - Tarjeta de perfil del autor
- `BlogPost.astro` - Componente para mostrar posts
- `TypedBlogPost.astro` - Versión tipada del componente de post

### Layouts

- `MainLayout.astro` - Layout principal del sitio
- `BlogLayout.astro` - Layout específico para posts del blog

## 📡 RSS Feed

El feed RSS se genera automáticamente en `/rss.xml` y incluye:

- Todos los posts publicados (no drafts)
- Metadatos completos de cada post
- Imágenes y descripciones
- Información del autor

## 🔧 Content Collections

Este proyecto utiliza las Content Collections de Astro para:

- **Tipado automático** del contenido
- **Validación de esquemas** con Zod
- **Referencias entre contenido** (posts ↔ autores)
- **Optimización de imágenes** automática

## 📱 Características Responsive

- Diseño mobile-first
- Navegación adaptativa
- Imágenes optimizadas para diferentes pantallas
- Tipografía escalable

## 🚀 Despliegue

### Netlify

```bash
pnpm build
# Sube la carpeta 'dist' a Netlify
```

### Vercel

```bash
pnpm build
# Conecta tu repositorio con Vercel
```

### GitHub Pages

```bash
# Configura GitHub Actions con el workflow de Astro
pnpm build
```

## 🤝 Contribuciones

1. Fork el proyecto
2. Crea una rama para tu feature (`git checkout -b feature/AmazingFeature`)
3. Commit tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abre un Pull Request

## 📄 Licencia

Este proyecto está bajo la Licencia MIT. Ver el archivo `LICENSE` para más detalles.

## 🙏 Reconocimientos

- [Astro](https://astro.build/) - Por el increíble framework
- [Tailwind CSS](https://tailwindcss.com/) - Por el sistema de diseño
- [Heroicons](https://heroicons.com/) - Por los iconos

---

Hecho con ❤️ y [Astro](https://astro.build/)
