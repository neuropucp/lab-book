# Ficha técnica EEG
## Introducción a FLEX
FLEX es una caja de control inalámbrica (controlador FLEX) que se integra con el sistema Flex Cap de EMOTIV. Utiliza la tecnología inalámbrica de los auriculares EPOC X de EMOTIV, combinada con la colocación flexible y de alta densidad de sensores típica de los sistemas de gorros EEG tradicionales. Los sensores pueden ubicarse en cualquiera de las 74 aberturas del gorro, en las posiciones estándar 10-20, permitiendo configuraciones personalizadas para diferentes experimentos o características de los participantes.
### 1.2 Características de FLEX 2
* Tipos de Kits de Sensores: Opción entre kits de sensores basados en gel o solución salina, optimizados para una conductividad y calidad de señal superiores.
* Canales EEG: Hasta 32 canales para una cobertura EEG de alta densidad.
* Sensores de Clip para la Oreja (solo gel): Utilizados para obtener señales de referencia.
* Bluetooth 5.2: Capacidad para transmitir datos sin comprimir de 16 bits a una velocidad de hasta 256 SPS por canal.
* Conectividad Inalámbrica: Fácil conexión con PC o Mac.
* Batería Recargable: Duración de hasta 6 horas por carga.
* Flex Cap: Opciones de gorros preconfigurados (solo solución salina) o configurables para una instalación y posicionamiento flexibles.
* Tamaños del Flex Cap: Variedad de tamaños disponibles para mejor adaptación y comodidad
 ### 1.3 Especificaciones Técnicas
* Número de Canales: 32 (más referencias CMS/DRL).
* Nombres de Canales: Configurable en las 72 ubicaciones estándar internacionales 10-20.
* Método de Muestreo: Muestreo secuencial con conversores analógico-digitales duales.
* Frecuencia de Muestreo: Configurable entre 128/256 SPS (hasta 2048 Hz internamente
## Instalación
### 2.1 Contenido del paquete FLEX:
El paquete FLEX contiene 16 elementos:
1. **Estuche FLEX** (protege y organiza el equipo EEG durante el transporte y almacenamiento)
2. **Guía de inicio rápido** (instrucciones breves para configurar y usar el sistema)
3. **Gorra FLEX** (se utiliza para colocar y asegurar los electrodos en la cabeza del usuario)
4. **Controlador FLEX** (recolecta y transmite los datos de los electrodos y sensores)
5. **daptador Bluetooth** (conecta el sistema de forma inalámbrica a otros dispositivos)
6. **Cables - extensión** (para ampliar el alcance de las conexiones eléctricas)
7. **Cable de carga USB-C** (para cargar el controlador FLEX)
8. **Adaptador de USB-A a USB-C** (permite conectar dispositivos USB-C a puertos USB- A)
9. **Soporte de electrodos** (fijan los electrodos en su lugar para asegurar un buen contacto con la piel)
10. **50 Pines** (establecen conexiones eléctricas entre el controlador FLEX y los electrodos)
11. **1 Herramienta** (facilita la instalación o ajuste de los componentes del controlador FLEX y los electrodos)
12. **2 bolsas de cable** (organizan y protegen los cables del controlador FLEX y los electrodos)
13. **80 Filtros de longitud estándar** (solo salinos) (conectan electrodos salinos al controlador FLEX)
14. **20 Filtros de longitud larga** (solo salinos) (conectan electrodos salinos al controlador FLEX, ofrecen mayor alcance)

<div align="center">
  <img src="https://raw.githubusercontent.com/neuropucp/lab-book/main/book/res/manualEEG_Contenido_del_paquete_FLEX_P1.png" alt="Localización de electrodos ECG" width="auto" height="auto">
  <p><em><strong> Figura 1 </strong>Contenido del paquete FLEX. Imagen basada en EMOTIV (2023).</em></p>
</div>
<div align="center">
  <img src="https://raw.githubusercontent.com/neuropucp/lab-book/main/book/res/manualEEG_Contenido_del_paquete_FLEX_P2.png" alt="Localización de electrodos ECG" width="auto" height="auto">
  <p><em><strong> Figura 2 </strong>Contenido del paquete FLEX. Imagen basada en EMOTIV (2023).</em></p>
</div>
Existen 3 tipos de cabezales (medidas del Flex cap): pequeño (54 cm), mediano (56 cm) y grande (58 cm).

```{Nota} Se recomienda usar el gorro flex pequeño para mujeres y niños y el gorro mediano para hombres. Sin embargo, es importante calcular el tamaño del gorro en función de las características individuales de cada usuario para asegurar un ajuste óptimo.```

También existen 2 diferentes tipos de configuraciones
- Kit de solución salina flexible: Contiene electrodos salinos, adecuado para aplicaciones que requieren este tipo de conductividad.
- Kit preconfigurado Flex Saline: Listo para usar con electrodos salinos, sin necesidad de configuración.

**Controlador Flex**

El FLEX tiene 16 canales en el lado izquierdo con una entrada CMS* y 16 canales a la derecha + salida DRL (se conectan a los electrodos para captar señales eléctricas).

La entrada CMS (Common Mode Signal) y la salida DRL (Driven Right Leg) son parte de un sistema de referencia y estabilización, mejorando la calidad de las señales captadas, minimizando interferencias.

### 2.2 Controles e Indicadores del FLEX Controller
- Interruptor de Encendido: Ubicado junto al conector USB, este interruptor se desliza hacia la derecha para encender el controlador y hacia la izquierda para apagarlo.
- Indicador de Encendido: Un LED debajo del logotipo que indica si el dispositivo está encendido (luz encendida) o apagado (luz apagada).
- Estado de Carga: Un LED, situado junto al conector USB-C, muestra el nivel de batería del controlador. Indica si el dispositivo necesita ser cargado o si está completamente cargado.
### 2.3 Carga Flex
Para aprovechar al máximo el controlador FLEX, debe cargarse completamente antes de usarlo. Si el LED de encendido no está azul al encender el dispositivo, significa que necesita cargarse.

Para cargar la batería:
1. Conecte el cable de carga USB-C al puerto USB-C.
2. Luego, conecta el otro extremo del cable de carga USB-C a una toma de corriente o a tu PC/Mac.

El tiempo de carga de la batería depende de cuán descargada esté la batería del controlador FLEX. Puede tardar hasta cuatro horas en recargarse por completo, y la carga es más rápida si se conecta a un puerto USB dedicado.

Si no usa el FLEX por un tiempo prolongado, la batería puede descargarse por completo. En ese caso, puede necesitar cargarlo durante 24 horas.

Si tiene problemas al cargar el FLEX, comunicarse con el soporte de EMOTIV. 

Comportamiento de carga FLEX

| Cargando                                     | Carga completa                                                  |
|---------------------------------------------|------------------------------------------------------------------|
| Cuando FLEX se está cargando, se muestra el LED naranja. | Cuando FLEX está completamente cargado, el LED se vuelve verde. |

### 2.4 Activación de FLEX

| **Apagado** | **Encender** |
|------------|--------------|
| Cuando el controlador FLEX esté apagado, el LED no se iluminará. | Para encender FLEX, mueva el botón de encendido hacia la derecha. El LED de encendido se iluminará y mostrará el estado de carga de la batería. |

### 2.5 Cables y sensores Flex
**Cables flex**

El kit Flex incluye 34 sensores conectados a 16 cables azules, 16 cables rojos y 2 cables negros. Estos colores sirven como una guía de identificación de los canales (azul = izquierda, rojo = derecha, negro = canales de referecia). Asimismo, cada cable esta etiquetado con la letra del canal

**Longitud de los cables**

La longitud de los cables es distinta dependiendo de los canales, esto nos permite que no haya un excedente de cables y a su vez nos permite configurar cualquier distribución deseada. Los cables de sensores vienen en 2 largos distintos, aquellos que estan en zonas más frontales, como los canales desde la A a la G, tienen un largo de 300mm. Mientras que aquellos canales desde la J hasta la Q son de 150mm.

**Saline Sensor Kit y proceso de hidratación**

El epoch Flex Saline Kit incluye 34 sensores recubiertos de plata y cuentan con 3 puntas para sujetar los filtros del sensor. Siguiendo esta línea, para utilizar el gorro EEG tenemos que seguir un proceso de hidratación de los filtros que se ubicaran posteriormente dentro de los sensores. Para ello se necesitan los filtros, un frasco de vidrio y solución salina, para posteriormente seguir los siguientes pasos:

1. Deje lo filtros en el frasco
2. Cubrir con solución salina y dejar reposar 5 minutos aproximadamente.
3. Cuando estén completamente hidratados, retirar los filtros del frasco y retirar el exceso. 

Tras esto, los filtros estarían listos para ubicar en los sensores deseados.

**Hidratación de los sensores durante el experimento**

Debido a que las sesiones de EEG suelen durar bastante tiempo, es probable que los filtros empiecen a secarse durante la sesión, lo cual depende de diversos factores (contacto con el cabello, temperatura ambiental, etc.). Por lo que, para mantener una buena conectividad, es necesario mantenerlos hidratados. Para ello, puedes añadir un poco de solución salina de maneraindividual a través de de la abertura superior que tiene cada sensor durante la calibración del EEG.

### 2.6 Gorra Flex
La gorra flex sigue el sistema 10-20 y tiene 74 aberturas para posicionar electrodos. Adicionalmente cuenta con 2 espacios para asegurar el controlador flex: uno en la parte superior del gorro (debajo del electrodo Cz) y el otro en la parte posterior (debajo del Iz). Asimismo, la gorra flex está elaborada con un material elástico y viene en tres tamaños de acuerdo con su circunferencia: 54cm, 56cm y 58cm.
### 2.7 Configuración de flex Cap.
**Insertar sensores**

Para insertar los sensores en el gorro FLEX tienes que seguir los siguientes pasos:

1. Sostén el gorro FLEX, luego estirar un poco la tela del agujero en el que desees insertar el sensor.
2. Empuje el sensor hacía arriba a través del agujero, luego libere la tensión del material del gorro para que encaje alrededor de la parte baja del sensor. Otra forma de realizarlo es, desde la parte interior del caso, estira el agujero deseado y deja que el material se retraiga alrededor de la ranura de plástico.
3. Ajusta el material del gorro en el sensor hasta que esté ubicado correctamente.

<div align="center">
  <img src="https://raw.githubusercontent.com/neuropucp/lab-book/main/book/res/manualEEG_Inserta_sensores_en_gorro_FLEX.png" alt="Localización de electrodos ECG" width="auto" height="auto">
  <p><em><strong> Figura 3 </strong>Insertar sensores en gorro FLEX. Elaboración propia.</em></p>
</div>

| **Recomendaciones** |
|---------------------|
- Asegúrate que los sensores estén orientados hacia adentro del gorro antes de insertarlos.
- La mayor parte del sensor tiene que estar en la parte exterior del gorro, mientras que la abertura con la almohadilla tiene que estar hacia el cabello del participante.
- No fuerces los sensores a través de las aberturas.

**_Nota:_** Realizar este paso con anticipación antes de iniciar la aplicación del experimento porque puede demorar este proceso. |

**Posicionamiento del controlador FLEX**

Hay dos lugares en el gorro FLEX para colocar el controlador FLEX: en la parte superior (Cz) o en la parte inferior (Iz)

El lugar en el cual configurar la ubicación del controlador FLEX no es problemático, sin embargo, este dependerá de dos factores:

- Si el sobrante de los cables es corto, es probable que el único lugar en el que puedas posicionarlo es en la parte superior.
- Si estás realizando un estudio en el que el participante deba apoyar su cabeza por la parte trasera, se recomienda posicionar el controlador FLEX en la parte superior.
  
<div align="center">
  <img src="https://raw.githubusercontent.com/neuropucp/lab-book/main/book/res/manualEEG_Ubicacion_controlador.png" alt="Localización de electrodos ECG" width="auto" height="auto">
  <p><em><strong> Figura 4 </strong>Ubicaciones controlador. Elaboración propia.</em></p>
</div>

**Como colocar el controlador FLEX**
1. Escoger la posición en la que deseas ubicar el controlador usando la app de EMOTIV.
2. Colocar el controlador FLEX en el bolsillo adecuado, asegurando que tenga el logotipo de EMOTIV hacía el frente, con el interruptor de on/off y el puerto USB en el borde inferior.
3. Estire el bolsillo del gorro FLEX sobre el controlador y a su vez alrededor de la ranura de la parte circular con el logotipo de EMOTIV.

<div align="center">
  <img src="https://raw.githubusercontent.com/neuropucp/lab-book/main/book/res/manualEEG_Colocacion_del_controlador_FLEX.png">
  <p><em><strong> Figura 5 </strong>Cómo colocar el controlador FLEX. Elaboración propia.</em></p>
</div>

**Conectar los sensores al controlador FLEX**
Para conectar los sensores al controlador FLEX, se tiene que conectar el extremo blanco de los cables rojos y conectarlo en el lado derecho del controlador. Como a su vez, conectar el extremo blanco de los cables azules en el lado izquierdo.
<div align="center">
  <img src="https://raw.githubusercontent.com/neuropucp/lab-book/main/book/res/manualEEG_Conexion_de_sensores_al_controlador_FLEX.png">
  <p><em><strong> Figura 5 </strong>Cómo colocar el controlador FLEX. Elaboración propia.</em></p>
</div>

**_Nota:_** 
Asegúrate de manipular los cables desde el conector blanco para desconectar y conectar al controlador FLEX, ya que aplicar fuerza desde los cables puede hacer que se salgan de la base blanca. Conectar los conectores blancos hasta que sientas cierta “presión” en el controlador.

**Colocar el gorro FLEX en los participantes**

Colocar el gorro FLEX es similar a colocarse un gorro de natación, por lo que podría seguir las siguientes indicaciones:

1.	Coloca el gorro FLEX sobre la frente del participante, teniendo en cuenta que el bolsillo para el controlador FLEX esté en la parte posterior de la cabeza.
2.	Estire la gorra FLEX hacia la parte posterior de la cabeza.
3.	Asegura que los oídos estén colocados en los agujeros.

| **Recomendaciones** |
|---------------------|
* El participante debería sentir cierta presión de los sensores en el cuero cabelludo. Si no es así, trata de ajustar un poco más el gorro con la correa de la mandíbula o cambiar a una talla más pequeña.
*	Revisa si la posición del sensor “Cz” se ubica en el centro del gorro FLEX y que los sensores estén posicionados de manera simétrica.
*	La posición de los sensores Fp1/Fp2 del gorro deben estar encima de las cejas.
*	Las líneas del gorro, dos laterales y una central, deberían estar en una distancia que coincida con los ojos del participante como con el centro del rostro, respectivamente.| 

**Cómo conseguir una señal de EEG de alta calidad con los Sensores salinos**

Para conseguir una mejor calidad de señal, es necesario minimizar la impedancia entre los sensores salinos y el cuero cabelludo. A continuación, se ofrecen algunos consejos que le ayudarán a conseguir la mejor calidad de señal:

*	Asegúrese de que el participante se haya lavado el cabello antes del experimento. No se debería utilizar acondicionador ni otros productos antes del experimento, ya que pueden provocar impedancias.

*	Cuando limpies los sensores o añadas la solución salina a los sensores, asegúrate de que tienes suficiente luz para ver lo que estás haciendo.

## 3. Limpieza y almacenamiento

**Limpieza de gorro FLEX**

Puedes limpiar el gorro FLEX a mano o en lavadora a 30°c / 86°F con un detergente delicado, como podría ser con shampoo de bebe. Tras ello, remover el exceso de agua con papel toalla y dejar secar al aire libre.

Para mantener la vida útil del gorro FLEX, ten en cuenta las siguientes precauciones:

*	No poner el gorro en la secadora.

*	No planchar el gorro.

*	No usar o verter desinfectante o lejía.

**Limpiar sensores FLEX**

Los sensores solo deberían tener contacto con solución salina o suero fisiológico durante la sesión del experimento. Para mantener la vida útil de los sensores, enjuagar los sensores con agua para remover los residuos después de cada uso, posteriormente, seque los sensores con una toalla o pañuelos.

**Advertencia**: No deje los filtros húmedos dentro de los sensores, debido a que esto puede corroer el material.

**Almacenar gorro FLEX**

Cuando el gorro FLEX no esté en uso, remueva los sensores del gorro y asegúrese que todo esté limpio y seco antes de guardar.

## **Anexos**

*	Figura 1. Contenido del paquete FLEX

*	Figura 2. Contenido del paquete FLEX

*	Figura 3. Insertar sensores en gorro FLEX

*	Figura 4. Ubicaciones controlador FLEX

*	Figura 5. Como colocar controlador FLEX

*	Figura 6. Ordenar los cables y minimizar el movimiento de artefactos.

*	Figura 7. Conectar sensores a controlador FLEX

**Referencias Bibliográficas**

*	EMOTIV. (2023). Flex 2.0 user manual. https://emotiv.gitbook.io/flex-2.0-user-manual

*	EPOC FLEX User Manual | EPOC Flex User Manual. (2020). https://emotiv.gitbook.io/epoc-flex-user-manual

