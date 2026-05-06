
# Implementación de la Carga Automática (Autoload) PSR-4 con Composer
## 1. Información General
* **Institución:** Universidad Tecnológica de Panamá 
* **Facultad:** Facultad de Ingeniería de Sistemas Computacionales 
* **Departamento:** Departamento de Programación 
* **Asignatura:** Desarrollo de Software VII 
* **Estudiante:** Aaron Ortiz
* **Instructor:** Ing. Irina Fong
* **Semestre:** I Semestre 2026 


## 2. Descripción del Laboratorio
Este laboratorio consiste en la implementación del estándar **PSR-4** para la gestión de dependencias y organización de Namespaces en aplicaciones PHP. El objetivo principal es eliminar el uso manual de `include` y `require`, optimizando la estructura del proyecto mediante el uso de **Composer Autoload**.

## 3. Guía de Instalación
Para ejecutar este proyecto localmente, siga estas instrucciones:

1. **Clonar el repositorio:**
   ```bash
   git clone <URL_DE_TU_REPOSITORIO>
   cd AutoCargaEjemplo
   ```

2. **Generar la carga automática:**
   Ejecute el siguiente comando para crear la carpeta `vendor/` y el mapa de clases:
   ```bash
   composer install
   ```
   O, si solo necesita regenerar el autoloader:
   ```bash
   composer dump-autoload
   ```

## 4. Estructura de Archivos y Namespaces
La organización del proyecto sigue el estándar PSR-4, vinculando los Namespaces a carpetas físicas de la siguiente manera:

| Estructura Global | ProductModel.php | User.php |
| :---: | :---: | :---: |
| <img width="178" src="https://github.com/user-attachments/assets/cdfa2aea-3225-4860-aa14-31d520c4f4f8" /> | <img width="261" src="https://github.com/user-attachments/assets/7f168f78-fd29-4be3-9a2b-826f8f9b27af" /> | <img width="306" src="https://github.com/user-attachments/assets/98ca6017-7ee7-41f8-9065-3486ccb7fce6" /> |


**Ejemplo de implementación:**
```php
<?php
// Sustitución de include_once por el autoloader de Composer
require_once 'vendor/autoload.php';

use App\Models\Ejemplo;

$objeto = new Ejemplo();

?>
```

## 6. Conclusiones Técnicas
Durante el desarrollo de este laboratorio, se observaron las siguientes ventajas críticas:

* **Mantenibilidad:** Se pueden agregar nuevas clases de forma inmediata sin necesidad de tocar archivos de configuración globales, siempre que se respete la estructura de carpetas y Namespaces.
* **Eficiencia de Memoria:** El sistema utiliza *Lazy Loading* (carga bajo demanda), lo que reduce el consumo de recursos al cargar solo las clases que el servidor realmente necesita procesar.
* **Estandarización:** Seguir el estándar PSR-4 facilita el trabajo colaborativo y asegura que el código sea compatible con las mejores prácticas de la comunidad PHP moderna.

## 7. Higiene del Repositorio
El repositorio incluye un archivo **.gitignore** configurado para excluir la carpeta `vendor/`. Esto garantiza que el repositorio sea ligero y obliga a que la carga automática se genere localmente mediante Composer, manteniendo el estándar de entrega profesional solicitado.
```

---
# Dependencias de Composer 
/vendor/

# Archivos de entorno 
.env
.env.local

# Logs y temporales
*.log
---
