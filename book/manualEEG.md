# Manual EEG

## Verificación de adquisición de señal con Emotiv Pro

El electroencefalograma que utilizamos es el Emotiv EPOC Flex saline de 32 canales. Este dispositivo cuenta con un casco de electrodos adaptable, batería recargable y conexión vía bluetooth.

Las computadoras del laboratorio están equipadas con el instalador Emotiv Launcher. Este permite la conexión del caso de electrodos con otras aplicaciones de Emotiv como EmotivPro, EmotivAnalyzer, entre otros, además de otras aplicaciones de terceros.

El laboratorio cuenta con una licencia de EmotivPro. Esta interfaz nos ofrece diversas funciones para visualizar, adquirir y analizar la actividad cerebral recopilada por el EEG. Entre las principales funciones de EmotivPro se incluyen:

* Grabación y almacenamiento de los datos del EEG.
* Exportación de datos en formatos compatibles.
* Monitoreo de la calidad de la señal de los electrodos.
* Personalización de la configuración de los experimentos, permitiendo crear, aplicar y guardar
configuraciones específicas para cada estudio.

**Aspectos generales sobre el uso del EEG**

**Preparación inicial:**

* Hidratar los filtros con el suero fisiológico y colocarlos en los sensores a utilizar, incluyendo los **sensores de referencia**.
* Encender el Flex Control Box (caja negra ubicada en el casco).
* Conectar el receptor bluetooth al ordenador.
* Abrir Emotiv Launcher y establecer la conexión con el EEG. En el launcher puedes revisar la batería y cargarla de ser necesario.

**Visualización de actividad cerebral:**

EmotivPro nos permite visualizar la actividad cerebral en vivo. Para verificar que efectivamente estamos registrando actividad en el EEG, podemos hacer algunas pruebas colocando 2 o 3 filtros e los sensores ubicados en el lóbulo prefrontal. Así podemos hacer algunos movimientos (p.e parpadear o morder repetidas veces), y observar variaciones en la señal.

**Electrode setup:**

Podemos revisar y configurar mediante EmotivPro los electrodos que se van a utilizar. Cada
experimento tiene una distribución diferente de electrodos, y esta interfaz nos permite guardar el setup de electrodos deseado, además de verificar la ubicación adecuada de los electrodos.

**¿Cómo puedo asegurarme de que la señal adquirida es de calidad?**

Se puede verificar la calidad de nuestra señal mediante dos indicadores presentes en EmotivPro: Contact Quality y EEG Quality:

**A. Contact Quality:**

Indica si la señal eléctrica pasa a través de los filtros hacia los sensores del EEG. Cuenta con 4 indicadores: 1. No hay contacto (negro), 2. Malo (rojo), 3. Medio/ok (naranja) y 4. Bueno (verde).

En esta etapa se busca un 100% de conectividad, de no ser así, hay algunas medidas que se
pueden realizar:

* Revisar si el casco está puesto correctamente.
* Verificar el manejo adecuado del cabello del/la participante (Ver Anexo 1).
* Humedecer los filtros de referencias y en los electrodos colocados.

**B. EEG Quality:**

Indica la calidad de señal que capta y registra el EEG. Esta se recopila en cuestión de
segundos y presenta 4 indicadores: Muy mala (negro), Mala (rojo), Medio a bueno (verde
claro) y Bueno (verde oscuro).

En este apartado, lo ideal es alcanzar un 100%. Al igual que en el apartado anterior, de no ser posible, hay algunas recomendaciones que se pueden seguir para alcanzar la conectividad deseada:

1. Humedecer un poco más los electrodos con baja conectividad (negro o rojo)
2. Instruir al participante que realice lo siguiente:
     * Minimizar el parpadeo u otros movimientos oculares.
     * Evitar realizar movimientos bruscos de cabeza, rostro o cuerpo.
     * Mantener una postura adecuada y relajada.
     * Respiración regular y estable para evitar artefactos.
3. Si se observan artefactos musculares. Ajusta el casco y pide al participante que relaje
los músculos faciales y del cuello.

**Tip:** Para identificar artefactos musculares en EmotivPro, busca picos rápidos y de
alta frecuencia en los electrodos frontales (AF3, AF4, F7, F8) o temporales (T7, T8),
que aparecen de manera irregular. Los artefactos tienen mayor amplitud y están asociados con movimientos faciales, parpadeos o tensión en el cuello.

**Nota:** Ten en cuenta que la conectividad en el EEG Quality depende mucho de la persona y sus características (tipo de piel, la cantidad de cabello, la humedad), por lo que el tiempo de verificación de este apartado puede variar entre cada aplicación.

**EEG data adquisition**
Permite la devolución de datos tras el registro de cualquier grabación de actividad cerebral. El software EmotivPro almacena las grabación de todos los registros, los cuales nos permite descargar y guardar los registros realizados con el EEG. Este nos devuelve la información captada en tres archivos dependiendo del formato que se haya deseado descargar: CSV, EDF, EDF+ y BDF+.

## **Implementación de marcadores EMOTIV en Psychopy**

Los marcadores nos permiten delimitar el rango de tiempo en el que el EEG graba la actividad neuronal. Psychopy nos permite interactuar directamente con el software y hardware de Emotiv mediante los componentes presentes y así grabar la actividad neuronal o los ERPs deseados para la investigación a realizar.

**Componentes Emotiv-Psychopy** En versiones más actuales de Psychopy (2023.1.0 en adelante), los componentes de emotiv no están disponibles de manera automática, por lo que se tienen que añadir de manera manual. Para ello,tenemos dos rutas disponibles:

**Builder en Psychopy:** Para añadir los componentes de Emotiv en versiones actuales del
Psychopy siga la siguiente ruta:

Components → Get more → Plugins → Buscar “Emotiv EEG” → Instalar

<div align="center">
  <img src="https://github.com/neuropucp/lab-book/blob/main/book/res/manualEEG_Componentes _Emotiv_Psychopy.png" alt="Localización de electrodos ECG" width="auto" height="auto">
</div> 


**Comando de código:** Documentación para instalar en Psychopy para agregar soporte a
distintos hardwares de emotiv, como en añadir ambos componentes:
https://github.com/psychopy/psychopy-emotiv

Al realizar esto, ya se habrán añadido los 2 componentes de
Emotiv dentro de la pestaña de EEG en Psychopy, los cuales
son el **Emotiv Recording y Emotiv Marking.**

<div align="center">
  <img src="https://github.com/neuropucp/lab-book/blob/main/book/res/manualEEG_Emotiv_Recording _y_ Emotiv_Marking..png" alt="Localización de electrodos ECG" width="auto" height="auto">
</div> 

**Emotiv Recording:**

Este componente genera una conexión entre Psychopy y permite que los marcadores se envíen al software de Emotiv para iniciar el registro general del EEG.

**Recomendaciones:**

* Debe añadirse en una rutina previa a la presentación de estímulos.
* Se recomienda dejar los valores default de los parámetros del propio componente al añadirlo en la rutina (start y stop time).

Para mayor información acerca del emotiv record, revisar la siguente documentación:
https://www.psychopy.org/builder/components/emotiv_record.html

**Emotiv Marking:**
Este componente permite enviar los marcadores de Psychopy al EEG cuando se presentan los
estímulos.
* Parámetros del componente:
    * Name, start y stop time, stop marker.
    * Marker label: tag del marcador (string).
    * Marker value: valor asignado al marcador (String o Interger).
* Se recomienda coordinar el inicio y duración del marcador con el estímulo de interés.
Para mayor información acerca del emotiv marking, revisar la siguente documentación:
https://www.psychopy.org/builder/components/emotiv_marking.html

**Algunos ejemplos para la implementación de marcadores**
Estos ejemplos nos dan una idea general de como colocar los marcadores en Psychopy. Ten en cuenta que este proceso varía dependiendo del diseño experimental que se desee realizar. Por lo que se recomienda revisar documentación específica que ayude a programar los marcadores adecuados para el diseño experimental deseado.

Ejemplo 1: https://www.youtube.com/watch?v=RRXs55ZScFg

Ejemplo 2: https://www.youtube.com/watch?v=rRoqGa4PoN8

**Pasos para la implementación y verificación de marcadores Emotiv**
1. Agregar los componentes de Emotiv en la interfaz Psychopy.
2. Elaborar el experimento deseado en Psychopy.
3. Utilizar componentes de Emotiv en las rutinas deseadas en Psychopy.
    * a. Agregar el componente Emotiv Recording en una rutina anterior al estímulo a registrar.
    * b. Agregar el componente Emotiv Marking en la rutina con el estímulo deseado: Buscar acomodar el tiempo de inicio, tiempo final, valores, etc. del marcador con las especificaciones del estímulo deseado.

4. Revisar conexión con EmotivPro.

    * a. Conectar USB bluetooth de Emotiv en la computadora.
    * b. Abrir la interfaz de EmotivPro y conectar con el headset EEG.
    * c. Configurar el setup de electrodos deseados.
    * d. Abrir el visualizador de grabación de EEG a tiempo real.

5. Correr el experimento de Psychopy y observar el registro de marcadores en el visualizador.
Observar imagen de referencia:
https://www.emotiv.com/cdn/shop/files/PRO_Acquire-Data-Cover_690x515_crop_center.png?v=1704704656

**Manejo del tiempo en estudios con EEG**

La precisión temporal es fundamental al medir ERPs. Cuando investigamos con múltiples fuentes de información, la gestión del tiempo se vuelve crucial. Realizar grabaciones sin una sincronización adecuada entre el estímulo y el registro de la señal puede ser perjudicial y hacer que los datos que recojamos sean inútiles. Es fundamental realizar una segmentación adecuada de la actividad cerebral para establecer correlaciones precisas entre causas y efectos. Para más información sobre la sincronización de tiempos, ingresa al siguiente link: https://www.bitbrain.com/blog/eeg-synchronization

Existen soluciones de tipo hardware (Emotiv Extender, etc) y software que pueden garantizar que el experimento tenga un timing adecuado. La solución usada en el laboratorio es el Lab Streaming
Layer.

**Lab Streaming Layer (LSL):**

Este es un software de código abierto que permite capturar y sincronizar una serie de medidas temporales a través de múltiples dispositivos y aplicaciones (como EEG, MEG, FMRI, etc). Está diseñado para experimentos que requieren una precisión temporal de hasta sub milisegundos y para establecer una comunicación bidireccional entre Emotiv Pro Flex y Psychopy. 

La función LSL de EmotivPro permite a los usuarios sincronizar flujos de datos entre varios
dispositivos y procesar en tiempo real datos EEG sin procesar en aplicaciones de terceros. LSL también facilita el envío de marcadores distintos en diferentes dispositivos y sincroniza los marcadores entre los dispositivos y las aplicaciones. Esta función cuenta con dos indicadores:

* Inlet: Usamos el Inlet para insertar marcadores desde un tercer software al flujo de datos de EEG mediante EmotivPro. Para mayor información, revisar la siguiente documentación: https://emotiv.gitbook.io/emotivpro-v3/lab-streaming-layer-lsl/lsl-inlet

* Outlet: Usamos el Outlet para configurar flujos de datos Emotiv que puedan comunicarse con otros dispositivos o software de terceros. Para mayor información, revisar la siguiente
documentación: https://emotiv.gitbook.io/emotivpro-v3/lab-streaming-layer-lsl/lsl-outlet

Antes de utilizar LSL, debemos asegurarnos de cumplir ciertos requisitos:

* Instalar Python (se recomienda la versión 3.8).

* Instalar **pip y pylsl** (la versión de Python de LSL). Pueden hacerlo corriendo la siguiente
línea en el terminal de la computadora: **pip install pylsl.**

**Enviar marcadores desde Psychopy al Inlet de Emotiv LSL.**

Para enviar marcadores usando LSL, debemos incluir un Python script. Utilizaremos las funciones pylsl. Para mayor información, revisar la siguiente documentación: https://github.com/labstreaminglayer/liblsl-Python/blob/master/pylsl/pylsl.py

Adjuntamos un ejemplo de script:

<div align="center">
  <img src="https://github.com/neuropucp/lab-book/blob/main/book/res/manualEEG_Ejemplo_de_script.png" alt="Localización de electrodos ECG" width="auto" height="auto">
</div> 
A continuación, visualizaremos este script en el componente de código de PsychoPy.

<div align="center">
  <img src="https://github.com/neuropucp/lab-book/blob/main/book/res/manualEEG_Código_de _PsychoPy.png" alt="Localización de electrodos ECG" width="auto" height="auto">
</div> 

Aquí desglosamos cada parte del código para entender cómo funciona:

| **Descripción de los argumentos del código** |  |
|---------------------------------------------|--|
| **StreamInfo**: La función StreamInfo define la metadata sobre el stream que enviarás a través de LSL. |  |
| `name='my_stream_name'` | Este es el nombre del stream de datos. Es útil para identificar el stream cuando múltiples streams están siendo enviados. En este caso, el nombre es "my_stream_name", pero puedes elegir un nombre descriptivo de acuerdo con tu experimento. |
| `type='Markers'` | Define el tipo de datos que enviarás. En este caso, estás enviando marcadores, así que el tipo es "Markers". Otros ejemplos de tipos podrían ser "EEG" o "EMG" si estuvieras enviando datos de señales biológicas. |
| `channel_count=1` | Define cuántos canales o dimensiones de datos tiene este stream. Dado que estás enviando solo marcadores, que suelen ser eventos discretos, se usa 1 canal. |
| `channel_format='int32'` | Esta es una cadena única que identifica de manera exclusiva el stream. Es útil cuando hay varios dispositivos enviando datos para diferenciarlos. |
| `source_id='uniqueid12345'` | Es un identificador único para tu fuente de datos. Esto es útil cuando estás trabajando con múltiples streams y quieres diferenciarlos. Debe ser único en cada flujo de datos para evitar confusiones en la red de LSL. |
| **StreamOutlet(info)**: Esta línea crea un objeto StreamOutlet que usas para enviar datos a través del stream. Se basa en la información que proporcionaste en StreamInfo. El objeto outlet se utiliza para enviar los datos a los consumidores de LSL (como una aplicación EEG o software de análisis). |  |
| `outlet.push_sample(x=[100])` | Esta línea envía un "sample" o muestra al stream, en este caso, un marcador. |
| `x=[100]` | El argumento x=[100] es el valor que se envía como el marcador. Aquí, el marcador es el número 100. Este podría ser cualquier número que represente un evento, como el inicio de un estímulo, el final de una tarea, etc. |
| `x` | Es una lista porque, aunque solo hay un canal, LSL espera una lista o array de valores, lo que permite que el código sea extensible para enviar múltiples valores si aumentas el número de canales (`channel_count`). |

**Algunas recomendaciones:**
* Para establecer un marcador, recomendamos usar enteros como marcadores. También se
puede incluir nombres de marcadores dinámicos.
* Si estás utilizando un loop en PsychoPy, incluye valores de marcadores en una columna de lahoja de cálculo utilizada para el loop. Por ejemplo: si el encabezado de la columna es
"marker", el código sería ***outlet.push_sample([marker]).***

Para verificar que se envían adecuadamente los marcadores, ejecuta la tarea en Psychopy, y antes de continuar con el botón "ok", verifica en **EmotivPro/Settings/LabStreamingLayer/Inlet** que el marcador corresponda con el nombre que consignaste en tu código. Según el ejemplo: 'my_stream_name'.

Haz click en el botón "Connect", y ejecuta la tarea en Psychopy. Deberás observar los marcadores
como líneas rosadas en el registro.

<div align="center">
  <img src="https://github.com/neuropucp/lab-book/blob/main/book/res/manualEEG_Marcadores_Emotiv.png" alt="Localización de electrodos ECG" width="auto" height="auto">
</div> 

Para revisar otro ejemplo utilizando las funciones **pylsl**, puedes ingresar al siguiente enlace: https://github.com/Emotiv/labstreaminglayer/blob/master/examples/psychopy/readme.md

**Anexo 1**

**Guia para el manejo del cabello para el registro del EEG**

1. Preparación del participante: Antes de la sesión en el laboratorio, solicita al/la participante que se asegure de que su cabello esté **limpio y libre de productos como acondicionador, gel, spray o aceites**, ya que estos pueden interferir con los electrodos y la recepción de la señal. Si el/la participante tiene el cabello sucio o grasoso, considera la posibilidad de sugerir un lavado previo. Alternativamente, se puede hacer uso de alcohol o toallitas desmaquillantes para limpiar la piel en la posición de los electrodos.

2. Despejar el área de colocación: Se recomienda usar ganchos o pinzas para sujetar el cabello largo y evitar que interfiera con los electrodos. En el caso de pacientes con cabello muy rizado o voluminoso, puede ser útil trenzar o recoger el cabello en un moño bajo para facilitar el
acceso al cuero cabelludo.

<div align="center">
  <img src="https://github.com/neuropucp/lab-book/blob/main/book/res/manualEEG_Recomendación_sobre_el_ cabello.png" alt="Localización de electrodos ECG" width="auto" height="auto"> <p><em><strong> </strong>Imágenes extraídas de: https://hellobrainlab.com/research/eeg-hair-project/.</em></p>
</div>

3. Colocación de electrodos: Al colocar los electrodos, asegúrate de que el cabello no esté
entrelazado entre el electrodo y el cuero cabelludo, ya que esto puede afectar la calidad de la señal. Utiliza más agua salina para mejorar la conductividad y minimizar la interferencia.

4. Comodidad del participante: Informa al participante sobre el proceso y asegúrate de que se sienta cómodo/a con el manejo de su cabello. Pregunta si prefiere que se le recoja el cabello de alguna manera específica o si necesita ayuda con el mismo.

5. Instrucciones post-registro: Proporciona al/la participante instrucciones sobre cómo limpiar su cabello y cuero cabelludo después de la prueba. Se recomienda un suave lavado para eliminar cualquier resto de la solución, y añadir acondicionador para restaurar la hidratación.

**Referencias:**

Brain Products. (2022, May 18). Inclusivity in EEG research. Brain Products.
https://pressrelease.brainproducts.com/inclusivity-in-eeg-research/

Emotiv. (n.d.). EmotivPRO user manual (Version 3). Emotiv. https://emotiv.gitbook.ioemotivpro-v3

Kothe, C. (n.d.). Lab streaming layer (LSL) - Developer documentation. Labstreaminglayer.
https://labstreaminglayer.readthedocs.io/dev/lib_dev.html

Louis, C. C., Webster, C. T., Gloe, L. M., & Moser, J. S. (2022). Hair me out: Highlighting systematic exclusion in psychophysiological methods and recommendations to increase inclusion. Frontiers in human neuroscience, 16, 1058953. https://doi.org/10.3389/fnhum.2022.1058953

Richardson, L. (2021). A guide to hair preparation for EEG studies. Biomechanics, Rehabilitation and Interdisciplinary Neuroscience (BRaIN Lab). https://hellobrainlab.com/research/eeg-hair-project/

Scully Center. (n.d.). How to prepare for your EEG experiment. Princeton University.
https://scullycenter.princeton.edu/experiment-participation/how-to-prepare-for-your-eeg-experiment/

