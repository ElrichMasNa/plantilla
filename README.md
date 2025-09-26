# Proyecto <nombre-proyecto>

## Creación del proyecto

> [!CAUTION]
> **En el caso de estar en un equipo MAC:**
> - Debe anteceder el comando `sudo` al ejecutar las instrucciones: `ng` y `chown`, y luego ingresar la contraseña del Administrador (`d3v3l0p3rUPC`).
> - Debe ubicarse en la carpeta `/Users/alumnos/IdeaProjects/1asi0729/2025-20` o en otra de su preferencia.

> [!CAUTION]
> **En el caso de estar en un equipo Windows:**
> - Debe ubicarse en la carpeta `IdeaProjects/` o en otra de su preferencia.

A continuación se detallan las instrucciones para crear un nuevo `workspace` e `initial starter app` de Angular. Más información en: https://angular.dev/tools/cli/setup-local

### Creación de un workspace y un initial application

**Ejecutar** el siguiente CLI command en la carpeta de su preferencia:

```bash
ng new <nombre-proyecto>
```
**OPCIONES**
```bash
CSS
N
Y
(*) GitHub Copilot
(*) JetBrains AI Assistant
```
## Instalación de Angular Material
```bash
cd <nombre-proyecto>
ng add @angular/material
```
**OPCIONES**
```bash
Y
```
```bash
Azure/Blue
```
## Instalación de Internationalization en/es
```bash
npm install @ngx-translate/core @ngx-translate/http-loader --save
```
Cambio de propietario (Solo MAC)
```bash
cd ..
sudo chown -R alumnos ./<nombre-proyecto>
ls -l
```

Desarrollo del proyecto

Ejecutar en el IDE:
```bash
ng serve --port 4200
```

Creación de archivos de idiomas

Estructura de carpetas:
- 📂 public
  - 📁 assets
    - 📁 i18n

Archivos de idioma:

📄 en.json

```bash
{
  "app": { "title": "<titulo-en-inglés>" },
  "<modulo-dominio>": { "title": "List of <EntidadPlural>" },
  "<entidad>": {
    "field1": "Field 1",
    "field2": "Field 2",
    "field3": "Field 3"
  },
  "footer": {
    "rights": "Copyright © 2025 <origen-datos>, All rights reserved",
    "intro": "Powered by <api-nombre>",
    "author": "Developed by {{ team }}"
  }
}
```

📄 es.json
```bash
{
  "app": { "title": "<titulo-en-español>" },
  "<modulo-dominio>": { "title": "Lista de <EntidadPlural>" },
  "<entidad>": {
    "field1": "Campo 1",
    "field2": "Campo 2",
    "field3": "Campo 3"
  },
  "footer": {
    "rights": "Derechos de autor © 2025 <origen-datos>, Todos los derechos reservados",
    "intro": "Desarrollado con <api-nombre>",
    "author": "Desarrollado por {{ team }}"
  }
}
```
Reemplaza <entidad>, <EntidadPlural>, <api-nombre>, <team> y los campos según tu proyecto.



Configuración de JSON Server

Estructura de carpetas:

- 📂 <nombre-proyecto>
  - 📁 server

📄 <modulo-dominio>.json
```bash
{
  "<EntidadPlural>": [
    { "id": 1, "field1": "valor1", "field2": "valor2", "field3": "valor3" },
    { "id": 2, "field1": "valorX", "field2": "valorY", "field3": "valorZ" }
  ]
}
```
Ejecutar JSON Server:
```bash
json-server --watch server/<modulo-dominio>.json --port 3000
```

Probar en navegador:

http://localhost:3000/
<EntidadPlural>

Configuración de environments
```bash
ng generate environments
```
📄 environment.development.ts
```bash
export const environment = {
  production: false,
  apiBaseUrl: 'http://localhost:3000',
  api<EntidadPlural>Endpoint: '/<EntidadPlural>'
};
```

📄environment.ts

```bash
export const environment = {
  production: true,
  apiBaseUrl: '<apiBaseUrl>',
  api<EntidadPlural>Endpoint: '/<EntidadPlural>'
};
```
⚠️ Modifica <apiBaseUrl> si tu API es distinta.

## Estructura de carpetas DDD


- 📂 src
  - 📂 app
    - 📂 <modulo-dominio>
      - 📁 application
      - 📁 domain
        - 📁 model
      - 📁 infrastructure
      - 📁 presentation
        - 📁 components
    - 📂 shared
      - 📁 infrastructure
      - 📁 presentation
        - 📁 components
## Creación de componentes
```bash
ng generate component shared/presentation/components/footer --skip-tests=true
```
```bash
ng generate component shared/presentation/components/language-switcher --skip-tests=true
```
```bash
ng generate component shared/presentation/components/layout --skip-tests=true
```
```bash
ng generate component <modulo-dominio>/presentation/components/<entidad>-card --skip-tests=true
```
```bash
ng generate component <modulo-dominio>/presentation/components/<entidad>-list --skip-tests=true
```
Reemplaza <modulo-dominio> y <entidad> según corresponda (ejemplo: cities, products, users).


Personaliza con:

<nombre-proyecto> → nombre de tu proyecto

<modulo-dominio> → carpeta de dominio (ej. cities, products)

<entidad> / <EntidadPlural> → nombre de la entidad (ej. city / cities)

<apiBaseUrl> → endpoint real de la API

<team> → tu nombre o el del equipo


Actividad

Agregar todos los campos del endpoint en el front.

Agregar el funcionamiento de los demás endpoints.


---

🔥 Con esta versión ya tienes una **plantilla reutilizable**:  
- Para *Cities* → `<modulo-dominio>` = `cities`, `<entidad>` = `city`.  
- Para *FakeStore* → `<modulo-dominio>` = `products`, `<entidad>` = `product`.  

¿Quieres que te prepare además un **ejemplo resuelto** (rellenando los `<placeholders>`) para un caso concreto como `products` o `cities` para que compares?

