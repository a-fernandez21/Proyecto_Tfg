# FisioMap – Gestión Inteligente para Centros de Fisioterapia

## Descripción General

**FisioMap** es una aplicación multiplataforma diseñada para optimizar la gestión de centros de fisioterapia y mejorar la experiencia tanto de fisioterapeutas como de pacientes. Esta solución integral está pensada para clínicas de fisioterapia y profesionales independientes.

## Características Principales

### Para Fisioterapeutas
- Gestión centralizada de citas con pacientes
- Administración de diagnósticos médicos
- Mantenimiento de historial clínico completo
- Sistema de pagos y facturación
- Gestión de servicios y tratamientos ofrecidos

### Para Pacientes (Modo Cliente)
- Reserva y gestión de citas en línea
- Realización de pagos de manera segura
- Comunicación con fisioterapeutas vía videollamada
- Acceso al historial de diagnósticos y tratamientos

## Funcionalidades con Inteligencia Artificial

La aplicación integra tecnologías de IA para mejorar la documentación clínica:

- **Grabación y transcripción automática**: Utiliza una grabadora integrada en el dispositivo móvil para registrar sesiones entre fisioterapeuta y paciente
- **Procesamiento inteligente**: El audio es transcrito automáticamente mediante IA
- **Clasificación de contenido**: El texto transcrito se clasifica en secciones relevantes para generar o complementar el diagnóstico clínico
- **Transcripción en tiempo real**: Visualización del texto mientras se realiza la grabación

## Tecnologías Utilizadas

- **Frontend**: Flutter & Dart
- **Arquitectura**: Modelo-Vista-Controlador (MVC)
- **Automatización**: n8n
- **IA**: Agente telefónico con inteligencia artificial

## Problemas Encontrados y Soluciones

### Transcripción en Vivo

#### Descripción del Problema
Al trabajar con Whisper, el cual fue liberado hace tiempo y no contempla la opción de streaming, no es posible crear la transcripción en vivo haciendo streaming del audio y recuperar un streaming de texto para mostrar.

#### Solución Propuesta
El flujo propuesto será el siguiente:

1. **Captura de audio**: El audio se envía a Whisper para transcribirlo a texto
2. **Corrección automática**: La transcripción pasa por el agente de corrección, que ajusta errores y formato
3. **Revisión del usuario**: El texto corregido se devuelve al usuario para su revisión
4. **Almacenamiento**: El audio se almacena en la base de datos (.mp3, 64 kbps)
5. **Generación de anamnesis**: Posteriormente, la transcripción se utilizará para generar y guardar la anamnesis correspondiente a la sesión con el cliente

### Agente Telefónico

#### Descripción del Problema
El agente de Vapi resultó ser demasiado costoso, puesto que cobran 0,17€ por minuto de llamada más una prima adicional por llamada, lo que hace inviable su implementación en el proyecto.

#### Solución Propuesta
Se desestimó el agente telefónico y no se va a implementar en la versión actual del proyecto debido a los altos costos operativos.

#### Feedback cliente 

#### Descripción del Problema 
En el prototipo actual de la aplicación todavía no están configurados los endpoints. Sin embargo, Chiu nos ha indicado que es necesario implementar una forma de notificar al cliente cuando su anamnesis haya sido subida correctamente.

#### Solución Propuesta
Actualmente, tras grabar el audio, el proceso de subida a la base de datos puede tardar unos segundos, por lo que es importante mostrar un indicador de estado —por ejemplo, un modal o una notificación— que informe al usuario cuando la subida se haya completado con éxito.


## Repositorios del Proyecto

- [Prototipo de grabación](https://github.com/a-fernandez21/prueba_boton_grabar)
- [Prototipos de pantallas](https://github.com/a-fernandez21/screens_fisiomap)

## Estado del Desarrollo

### Fase Actual: Desarrollo de MVP
**Fecha objetivo**: 5 de noviembre de 2025

### Equipo de Desarrollo
- **Total**: 4 desarrolladores
- **Frontend**: 2 desarrolladores
- **Backend**: 2 desarrolladores


### Octubre 2025

#### 7 de octubre
- Inicio del aprendizaje de Dart y Flutter
- Investigación de la herramienta n8n
- Inicio de la documentación del anteproyecto

#### 15 de octubre
- Finalización del agente telefónico con IA
- Presentación de prototipos de pantallas
- Investigación sobre transcripción en tiempo real
- Desarrollo de prototipo de botón de grabación con funcionalidad de audio

#### 21-28 de octubre
- Aprobación de prototipos por parte del equipo de supervisión
- Implementación de arquitectura MVC
- Refactorización del código según estándares del proyecto
- Incorporación como colaboradores en el repositorio principal
- Preparación para desarrollo del MVP
- **Prueba de transcripción con IA**: Se realizó una prueba de concepto transcribiendo un video utilizando inteligencia artificial para validar la funcionalidad de transcripción automática

### Recursos de Aprendizaje

- [Curso de Flutter & Dart](https://www.udemy.com/course/learn-flutter-dart-to-build-ios-android-apps/) y los proyectos del curso están, los estoy subiendo a github y te pondré los links cuando estén todos.
- Proyectos del Curso de flutter
- [primer_proyecto](https://github.com/a-fernandez21/primer_proyecto.git)
- [adv_basics](https://github.com/a-fernandez21/adv_basics.git)
- [app_ahorro](https://github.com/a-fernandez21/app_ahorro.git)
- [TODO'S](https://github.com/a-fernandez21/TODO-S.git)
- [meals](https://github.com/a-fernandez21/meals.git)
- [shopping_list](https://github.com/a-fernandez21/shopping_list.git)

---

### 28-04 de noviembre 
- Añadida la última prueba con la respuesta devuelta por n8n, ahora en formato HTML para permitir su almacenamiento según la solicitud de Erick.
- Integrada la librería flutter_html_editor_enhanced para visualizar y editar el documento HTML directamente desde la aplicación.
- Integración de la pantallas al proyecto final.
- A la espera de aprobación por parte de Brais (el que lleva fisiomap)
- Añadido los enlaces del curso de Flutter


### 04-11 de noviembre
- Creamos un widget desplegable que adapta su tamaño al scroll de la pantalla.
- Eliminar funcionalidades como tipo de curso clinico a la hora de grabar por petición de Chiu.
- Esperando a que configuren el archivo GoogleServices para poder probarlo en ios, ya que la grabadora donde más suele fallar es en IOS por temas de permiso y carpetas.
- Seguimos a la espera de la parte de Brais de hacer un mergue a la main para comprobar si tenemos que cambiar algo. 
- Actualizar los estilos de nuestras pantallas para que fuese lo más parecido al estilo propuesto por brais.
- Implementación de 3 wizards para explicar al usuario como utilizar la aplicación la primera vez que la instala.
- Hoy le pido a brais que te de acceso al repo del proyecto.
- Creada una lista con las preguntas claves para que la grabación sea de mayor calidad. 

### 11-17 de noviembre
- Brais te ha mandado invitación.
- Editado el Ante proyecto por las cosas que al final no se implementan. 
- He añadido un PDF con todas las librerías que se utilizan en Fisiomap, elaborado con la ayuda de la IA. Le pasé todo el archivo pubspec.yaml y le pedí: “Quiero que me expliques y me hagas una tabla con toda la información de estas librerías”. La IA reconoció correctamente cuáles son las librerías que hemos implementado nosotros, como las de reproducción de audio, visualización de HTML y pumpun_core, pero el resto me resultan totalmente nuevas.
- 