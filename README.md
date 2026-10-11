# Aplicación Móvil de Gestión Operativa y Control Financiero para Estilistas

**Autor:** Jesus Abadia  
**Programa:** Ciencias Computacionales con especialización en Ciberseguridad  
**Curso:** COM-437ES Desarrollo de Aplicaciones Móviles  
**Módulo / Término Académico:** Módulo 4  
**Repositorio GitHub:** [app_estilistas](https://github.com/Jesus1234455/app_estilistas)  

## 1. Descripción del Proyecto
El presente proyecto abarca la concepción, arquitectura y diseño inicial de una aplicación móvil nativa multiplataforma orientada a optimizar el registro operativo y control financiero para profesionales del estilismo. La herramienta responde a la necesidad de registrar servicios en tiempo real (menos de 15 segundos) y automatiza el cálculo de deducciones y tarifas. El desarrollo se estructura bajo metodologías de planificación por etapas para garantizar entregables funcionales (GanttPRO, 2024).

## 2. Exposición del Problema
En salones de belleza, la remuneración variable de los estilistas está sujeta a múltiples factores (retenciones, costo de insumos, tipo de cliente). La alta intensidad operativa dificulta el registro manual, generando pérdida de transacciones e incertidumbre. Además, desde el perfil de ciberseguridad, se contempla la protección local de la información financiera del usuario.

## 3. Plataforma y Arquitectura Tecnológica
Se define una arquitectura por capas basada en las guías oficiales de desarrollo móvil (Android Developers, 2024):
* **Plataforma:** Flutter (Dart) para despliegue nativo multiplataforma.
* **Patrón:** Separación de UI Layer y Data Layer.
* **Base de Datos:** SQLite / Hive (Offline-First).
* **Seguridad:** Autenticación biométrica y cifrado local.

## 4. Justificación del Enfoque de Desarrollo
Para alcanzar el actual avance del proyecto, se tomó la decisión estratégica de priorizar la maquetación visual de la interfaz de usuario (UI) mediante Visual Studio Code. Este enfoque metodológico permite validar la intuición y la usabilidad de la aplicación antes de codificar la lógica interna en Dart. La prioridad es garantizar que el propósito central de la herramienta —un registro de servicios sin fricciones— se cumpla desde la primera interacción visual. Una vez confirmada la fluidez del diseño frontal, se procederá con la integración transaccional.

## 5. Changelog (Registro de Cambios)

**Pasado (Módulos 1 al 3) - [Versiones 0.1.0 a 0.4.0]**
* **Concepción y Requerimientos:** Definición del problema operativo y establecimiento de funcionalidades clave (F-01 a F-05).
* **Arquitectura de Software:** Selección de Flutter y SQLite/Hive para persistencia local.
* **Prototipado:** Estructuración del flujo de navegación y wireframes de la pantalla principal.

**Presente (Avance al 50%) - [Versión 0.5.0]**
* **Inicialización y Arquitectura:** Creación del proyecto en Flutter e implementación de la estructura base (separación UI/Lógica).
* **Maquetación UI Inicial:** Desarrollo del punto de entrada (`main.dart`) bajo el enfoque visual.

**Futuro (Módulos 5 al 8) - [Versiones 0.6.0 a 1.0.0]**
* **Lógica Operativa y Persistencia:** Integración de la base de datos local (SQLite) y motor de cálculo financiero.
* **Seguridad y Analítica:** Despliegue de autenticación biométrica y construcción gráfica del Dashboard de conciliación.

<img width="1104" height="1130" alt="image" src="https://github.com/user-attachments/assets/2985eaff-305e-4a87-8909-e0fc8814b4ca" />
<img width="1066" height="1039" alt="image" src="https://github.com/user-attachments/assets/2454fc80-4565-4098-ae57-4da5137a7d2b" />
<img width="629" height="1127" alt="image" src="https://github.com/user-attachments/assets/5285a4b8-5b1e-43c6-998b-afb728c4f134" />




## Referencias

Android Developers. (2024). *Guía de arquitectura de la app*. Google. https://developer.android.com/topic/architecture?hl=es-419

GanttPRO. (2024). *Programas de control de obra y gestión de proyectos*. GanttPRO Blog. https://blog.ganttpro.com/es/programas-de-control-de-obra-construccion/
