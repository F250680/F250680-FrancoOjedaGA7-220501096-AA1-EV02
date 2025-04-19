# 🚀 Estándares de Codificación 🚀

## 📋 Índice
- [Introducción](#introducción)
- [Estándares Generales](#estándares-generales)
- [Estándares por Plataforma](#estándares-por-plataforma)
  - [Frontend](#frontend)
  - [Backend](#backend)
  - [Mobile](#mobile)
- [Comandos Básicos](#comandos-básicos)
- [Flujo de Trabajo Git](#flujo-de-trabajo-git)
- [Recursos Adicionales](#recursos-adicionales)

## 🌟 Introducción

Este documento define los estándares de codificación que deberán seguirse en todos los proyectos de nuestro equipo. Mantener un código limpio y consistente nos permite:

- ✅ Mejorar la legibilidad
- ✅ Facilitar el mantenimiento
- ✅ Reducir errores
- ✅ Optimizar la colaboración

## 🧰 Estándares Generales

### 📝 Nomenclatura

- **Variables y funciones**: camelCase (`nombreUsuario`, `calcularTotal`)
- **Clases**: PascalCase (`UsuarioController`, `ProductoServicio`)
- **Constantes**: UPPER_SNAKE_CASE (`API_KEY`, `MAX_INTENTOS`)
- **Archivos**: kebab-case (`usuario-service.js`, `producto-modelo.php`)

### 🔍 Indentación y Formato

- Utilizar **2 espacios** para la indentación (no tabs)
- Líneas de máximo **80 caracteres**
- Siempre usar llaves `{}` incluso en bloques de una sola línea
- Insertar una línea en blanco al final de cada archivo

### 💬 Comentarios

- Usar JSDoc/PHPDoc para documentar funciones y clases
- Comentarios breves y descriptivos
- Evitar comentarios obvios
- Documentar decisiones no evidentes

## 💻 Estándares por Plataforma

### Frontend

#### 🎨 React

```jsx
// Componentes en archivos separados
// Nombres de componentes en PascalCase
const BotonPrimario = ({ texto, onClick }) => {
  return (
    <button 
      className="btn btn-primary" 
      onClick={onClick}
    >
      {texto}
    </button>
  );
};

// Hooks personalizados con prefijo 'use'
const useFormulario = (valoresIniciales) => {
  const [valores, setValores] = useState(valoresIniciales);
  // Lógica del hook...
  return { valores, setValores };
};
```

#### 🎭 CSS/SCSS

- Usar metodología BEM para clases CSS
- Preferir SCSS sobre CSS plano
- Variables para colores, espaciados y tamaños de fuente

### Backend

#### 🔧 Node.js/Express

```javascript
// Estructura de carpetas por funcionalidad
// /controllers, /models, /routes, /services, /middlewares

// Rutas expresivas
router.get('/usuarios/:id', usuarioController.obtenerPorId);

// Middleware en archivos separados
const autenticar = require('../middlewares/autenticar');
```

#### 🐘 PHP/Laravel

```php
// Convenciones de Laravel
// Modelos en singular, controladores en plural
class Usuario extends Model
{
    protected $fillable = ['nombre', 'email', 'contraseña'];
    
    public function publicaciones()
    {
        return $this->hasMany(Publicacion::class);
    }
}
```

### Mobile

#### 📱 React Native

- Mismas convenciones que React
- Separar estilos en objetos StyleSheet
- Organizar componentes por pantallas

#### 🤖 Android (Java/Kotlin)

```kotlin
// Kotlin preferido sobre Java
// Nombres de clases descriptivos
class UsuarioRepositorio(private val api: ApiService) {
    suspend fun obtenerTodos(): List<Usuario> {
        return api.obtenerUsuarios()
    }
}
```

## ⌨️ Comandos Básicos

| Comando | Descripción | Ejemplo |
|---------|-------------|---------|
| 📦 `npm install` | Instala dependencias del proyecto | `npm install` |
| 🏃‍♂️ `npm start` | Inicia el servidor de desarrollo | `npm start` |
| 🧪 `npm test` | Ejecuta las pruebas | `npm test` |
| 🏗️ `npm run build` | Compila el proyecto para producción | `npm run build` |
| 📊 `npm run lint` | Verifica el estilo del código | `npm run lint` |
| 🧹 `npm run lint:fix` | Corrige problemas de estilo automáticamente | `npm run lint:fix` |

## 🌿 Flujo de Trabajo Git

### 🔄 Ramas

- `main`: Código en producción
- `develop`: Código de desarrollo integrado
- `feature/nombre-feature`: Para nuevas funcionalidades
- `bugfix/nombre-bug`: Para correcciones
- `release/x.y.z`: Para preparar versiones

### 📝 Commits

Formato: `tipo(alcance): descripción`

Tipos:
- ✨ `feat`: Nueva funcionalidad
- 🐛 `fix`: Corrección de errores
- 📚 `docs`: Documentación
- 💄 `style`: Cambios de formato/estilo
- ♻️ `refactor`: Refactorización de código
- 🧪 `test`: Añadir/modificar pruebas
- 🔧 `chore`: Tareas de mantenimiento

Ejemplo: `feat(auth): implementar autenticación con Google`

## 📚 Recursos Adicionales

- [Guía de estilo de Airbnb para JavaScript](https://github.com/airbnb/javascript)
- [Guía de estilo de Google para Python](https://google.github.io/styleguide/pyguide.html)
- [Convenciones de Laravel](https://laravel.com/docs/master/contributions#coding-style)
- [Guía de estilo de React](https://reactjs.org/docs/code-style.html)

---

⭐ **¡Recuerda que un código limpio es un código feliz!** ⭐

Ante cualquier duda, consulta con el equipo de desarrollo o abre un issue en este repositorio.
