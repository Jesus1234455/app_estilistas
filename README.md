# Borrador del Proyecto: Aplicación Móvil de Gestión Operativa y Control Financiero para Estilistas

**Autor:** Jesus Abadia  
**Programa:** Ciencias Computacionales con especialización en Ciberseguridad  
**Curso:** COM-437ES Desarrollo de Aplicaciones Móviles  
**Módulo / Término Académico:** Módulo 2  
**Repositorio GitHub:** https://github.com/Jesus1234455/app_estilistas  

---

## 1. Descripción del Proyecto

El presente proyecto abarca la concepción, arquitectura y diseño inicial de una **aplicación móvil nativa multiplataforma (Android e iOS)** orientada a optimizar el registro operativo, cálculo transaccional y control analítico de ingresos para profesionales independientes del sector de la estética y estilismo. 

La herramienta responde a la necesidad de registrar en tiempo real (en menos de 15 segundos entre cliente y cliente) cada servicio prestado (cortes, tintes, maquillajes). El sistema automatiza el cálculo de deducciones variables (porcentaje retenido por el club/empresa, costo de productos utilizados y tarifas diferenciadas según tipo de cliente, como accionistas o clientes generales) y genera reportes analíticos para la conciliación de ingresos quincenales. El desarrollo del proyecto se estructura bajo metodologías de control de tiempos y planificación por etapas para garantizar entregables funcionales (GanttPRO, 2024).

---

## 2. Exposición del Problema

En salones de belleza y clubes sociales, la compensación de los estilistas opera bajo un esquema de remuneración variable sujeto a múltiples variables financieras:
* Retención de un porcentaje sobre el servicio por parte del club o salón.
* Deducción por el costo de productos e insumos aplicados (tintes, decolorantes, ampolletas, queratinas).
* Diferenciación de tarifas según la categoría del cliente (socios/accionistas vs. clientes externos).

**El problema central** radica en la alta intensidad operativa durante jornadas de gran flujo de clientes, lo que dificulta el registro manual detallado. Esto genera pérdida de transacciones e incertidumbre al comparar la liquidación quincenal entregada por la administración con los servicios reales prestados. Desde el perfil de ciberseguridad, se contempla además la protección del almacenamiento local en el smartphone frente a accesos no autorizados a la información financiera del usuario.

---

## 3. Plataforma y Arquitectura Tecnológica

Para garantizar el funcionamiento fluido en smartphones y la disponibilidad en zonas con cobertura inestable dentro de las instalaciones, se define una arquitectura por capas basada en las guías oficiales de desarrollo móvil (Android Developers, 2024):

* **Plataforma y Framework:** **Flutter** (lenguaje **Dart**) para despliegue multiplataforma nativo (Android e iOS) desde un único código base.
* **Patrón de Arquitectura:** Capa de Interfaz de Usuario (UI Layer) separada de la Capa de Datos (Data Layer) con gestión de estado reactiva (Android Developers, 2024).
* **Entorno de Desarrollo (IDE):** Visual Studio Code acoplado con Android SDK y emulador **Pixel 8 (android-x64)**.
* **Base de Datos Local (Offline-First):** SQLite / Hive para la persistencia transaccional local sin necesidad de conexión continua a Internet.
* **Seguridad Móvil:** Autenticación biométrica (Face ID / Huella dactilar) e integración de buenas prácticas de cifrado en almacenamiento local.

---

## 4. Interfaz de Usuario (UI Móvil) e Interfaz de Administrador

### 4.1. Interfaz de Usuario Móvil (Estilista)
* **Pantalla de Registro Rápido (Home):** Botones de gran tamaño (*thumb-friendly*) para selección rápida de servicios (Corte, Tinte, Maquillaje), interruptor para tipo de cliente (Accionista / General) y selector táctil de insumos.
* **Gestor Móvil de Tarifas:** Módulo para actualizar la tabla de precios y costos de productos de manera dinámica directamente en el teléfono.
* **Panel de Control Quincenal (Dashboard):** Visualización del balance acumulado de la quincena (ingresos brutos, retención del club y costo de insumos).
* **Módulo de Analítica y Tendencias:** Gráficos estadísticos para comparar el rendimiento financiero e histórico mes a mes.

### 4.2. Interfaz de Administrador (Configuración de Parámetros)
* **Módulo de Reglas Financieras:** Configuración del porcentaje de comisión aplicable según el contrato o salón.
* **Catálogo Maestro de Insumos:** Lista actualizable de precios de productos y materiales.
* **Exportador de Reportes:** Generación de resúmenes consolidados en PDF/Excel para conciliación quincenal.

---

## 5. Funcionalidad

| Módulo | Funcionalidad Clave | Descripción del Requerimiento Móvil |
| :--- | :--- | :--- |
| **F-01** | Captura Táctil Rápida | Registro de servicio en < 15 segundos mediante componentes optimizados para smartphones. |
| **F-02** | Motor de Cálculo Financiero | Cálculo automático: `Ingreso Neto = (Precio Servicio - Descuento Accionista) * % Comisión - Costo Insumos`. |
| **F-03** | Modo Offline (Sin Red) | Permite registrar servicios en el teléfono sin conexión y sincroniza al detectar red. |
| **F-04** | Gestión Dinámica de Tarifas | Modificación de precios de lista e insumos sin alterar el historial acumulado. |
| **F-05** | Dashboard Analítico Móvil | Gráficos visuales de rendimiento quincenal e historial comparativo de ingresos. |

---

## 6. Diseño (Wireframes y Esquemas de Pantalla Móvil)

### 6.1. Flujo de Navegación Móvil

```mermaid
graph TD
    A[main.dart / MyApp] --> B[Autenticación Biométrica]
    B --> C[Dashboard Principal: MyHomePage]
    C --> D[+ Nuevo Registro Rápido]
    C --> E[Resumen Quincenal / Conciliación]
    C --> F[Analítica Comparativa Mensual]
    C --> G[Configurar Tarifas / Insumos]
    
    D --> D1[Seleccionar Servicio: Corte/Color/Maquillaje]
    D1 --> D2[Tipo Cliente: Accionista / General]
    D2 --> D3[Añadir Insumos Utilizados]
    D3 --> D4[Guardar en el Celular]


+-----------------------------------+
|  [≡] App Estilista      [Face ID] |
+-----------------------------------+
|  NUEVO REGISTRO (00:12 s)         |
|                                   |
|  [ SERVICIO ]                     |
|  ( ) Corte   (*) Tinte   ( ) Maq. |
|                                   |
|  [ CLIENTE ]                      |
|  (*) ACCIONISTA       ( ) GENERAL |
|                                   |
|  [ INSUMOS CONSUMIDOS ]           |
|  [+] Tinte Matiz (#405)  $15.000  |
|  [+] Decolorante 50g     $ 8.000  |
|                                   |
|  -------------------------------  |
|  Valor Bruto:           $180.000  |
|  Comisión Empresa (40%):-$ 72.000  |
|  Insumos:               -$ 23.000  |
|  -------------------------------  |
|  INGRESO NETO:          $ 85.000  |
|                                   |
|  [        GUARDAR EN APP       ]  |
+-----------------------------------+

Referencias
Android Developers. (2024). Guía de arquitectura de la app. Google. https://developer.android.com/topic/architecture?hl=es-419

GanttPRO. (2024). Programas de control de obra y gestión de proyectos. GanttPRO Blog. https://blog.ganttpro.com/es/programas-de-control-de-obra-construccion/
