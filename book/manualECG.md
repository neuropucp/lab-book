# Manual ECG
## 2.1.	Introducción
El _Shimmer3 ECG Unit_ (ECG) pertenece a la familia de dispositivos Shimmer, utilizados en el monitoreo de mediciones fisiológicas. 

### 2.1.1. Función de la unidad 
El ECG es un tipo de electrocardiograma que se utiliza para medir señales eléctricas del corazón y registrar su actividad. Para obtener esta información, el ECG recolecta las señales de la piel mediante cinco cables externos conectados al equipo, a los cuales deben adherirse electrodos desechables convencionales. Estos datos pueden registrarse tanto en sujetos en reposo como ambulatorios, e incluso durante el ejercicio o movimiento, proporcionando información sobre la respuesta cardíaca ante la actividad física.

### 2.1.2. Hardware 
La unidad de procesamiento central (CPU) del shimmer es el microprocesador low-power MSP430F5437A que configura y controla placas de adquisición de datos, a través de pines input/output que se emplean para acoplar conectores de expansión interna y externa (i.e. la base). La CPU tiene integrado un convertidor analógico-digital (ADC) de 16 canales y 12 bits que se utiliza para capturar los datos de los sensores o las expansiones de sensores.

El shimmer tiene un puerto para tarjetas microSD Flash a modo de almacenamiento adicional externo, para asegurar su compatibilidad la tarjeta debe implementar el modo SPI de 1 bit. Asimismo, tiene 5 diodos emisores de luz LED, un interruptor de encendido/apagado y un botón de usuario definido por el software. 

Para la transmisión inalámbrica de datos, el shimmer está equipado con una antena de 2.4GHz conectada a un módulo bluetooth de clase 2 RN-42 para comunicarse. El rango de RN-42 es de más de 10 metros. 

La unidad shimmer se ha fabricado con una batería de litio recargable de 3,7V y 450mAh con alimentación de CA, es importante proteger la polaridad de la batería, supervisar la carga y los límites de sobretensión/subtensión; además de la sobredescarga. El tiempo de duración de la batería depende de cuánto tiempo lleva operando el dispositivo, si la radio está activada, qué sensores se están usando y con qué frecuencia de muestreo. Idealmente fue fabricada para que la batería dure de 1 a 14 días adquiriendo datos de varios canales con transmisión periódica por radio. 

Los estados de alimentación de la placa (encendido y apagado) son controlados por un interruptor deslizante. Mientras que él módulo de radio bluetooth es controlado con el software Consensys, mientras que la expansión FFC (radio periférica), el oscilador de cristal con compensación de temperatura y el puerto microSD disponen de conmutación suave de la alimentación. Incluso otros módulos tienen integradas funciones de apagado. 

## 2.2.	Medidas de bioseguridad 
1. Es neceasario utilizar equipo de protección personal (EPP) (ej. guantes desechables, batas o delantales). 
2. Emplear agua destilada para limpiar la superficie de la piel de la persona antes de aplicar los electrodos. 
3. Los electrodos del equipo no deben aplicarse al cuerpo del sujeto mientras la unidad Shimmer esté en la base o, por defecto, conectado externamente (puerto USB, cargador múltiple). Debe desconectarlo. 
4. Evitar la exposición del equipo al calor excesivo o a una llama abierta. 
5. Mantener el equipo alejado de personas menores de edad. 

## 2.3. Componentes
### _2.3.1. Componentes del Equipo Shimmer_ 
* Cable de poder: conecta al estabilizador con la corriente eléctrica. 
* Estabilizador: se conecta al cable de conexión del equipo. 
* Enchufe principal de la base (enchufe del estabilizador). 
* Cable USB: conecta la base con la computadora. 
* El shimmer ECG se conecta a la base.	

Una vez realizado el ensamblaje de los componentes, proceder al encendido del equipo.

### _2.3.2. Componentes del Equipo Shimmer ECG_
* Unidades de sensor shimmer3 ECG. 
* Cables biofísicos (5 por unidad de sensor). 
* Electrodos desechables ECG (medición estándar 4 medidas de referencia y 1 para medición).
* Correa (1 se posiciona en el pecho). 

### 2.3.3.	ECG Leads 
**_Consideraciones:_**

```{note} Diferencia entre wire (cable) y lead (conductor)
a. Lead o conductor: se refiere a la señal de voltaje proveniente de la diferencia entre dos electrodos. 

b. Wires: el cable biofísico que conecta físicamente los electrodos con el ECG. Hay 4 electrodos que se colocan a manera de referencia (siempre se ponen), la posición del quinto electrodo se ubica sobre el pecho en la región del corazón, depende de qué se busque medir exactamente. 
```

Electrodos de derivación de miembros bipolares:

* LA (Left arm o Brazo izquierdo). 
* RA (Right arm o Brazo derecho). 
* LL (Left leg o Pierna izquierda). 
* RL (Right leg o Pierna derecha). 

Posiciones de electrodos de derivación unipolar: 
* Vx (V1, V2, V3, V4, V5 o V6): El Vx puede ser puesto en cualquiera de las 6 posiciones. 

El ECG presenta 4 leads (conductores) que se recomiendan que sigan la siguiente configuración: 

__1. Leads bipolares__ (capturan actividad eléctrica del corazón desde dos ubicaciones diferentes, outcome: diferencia de voltaje).

	Lead 1 (LA-RA): señal vector del ECG medida desde el RA (brazo derecho) hasta el LA (brazo izquierdo) 
	
	Lead 2 (LL-RA) señal vector del ECG medida desde el RA (brazo derecho) hasta el LL (pierna izquierda) 
	
	Lead 3 (LL-LA) señal vector del ECG medida desde el LA (brazo izquierdo) hasta el LL (pierna izquierda). Se deriva de sustrayendo el Lead 1 y el Lead 2. 

__2. Lead unipolar__ (captura actividad eléctrica del corazón desde un solo punto de referencia). Vx-WCT es la señal vector del ECG del voltaje WCT que se posiciona en la posición Vx (en el pecho). 

Localización de electrodos: 

<div align="center">
  <img src="https://raw.githubusercontent.com/neuropucp/lab-book/main/book/res/manualECG_Localizacion_de_electrodos.png" alt="Localización de electrodos ECG" width="auto" height="auto">
  <p><em><strong> Figura 15 </strong>Posicionamiento de electrodos para medición con 9 leads (derecha) y con 18 leads (izquierda). Se representan las derivaciones estándar utilizadas en el registro de señales ECG. Elaboración propia.</em></p>
</div>

Cada electrodo debe estar localizado en el cuerpo, alejado del corazón y en la dirección de la articulación de la extremidad relevante (pierna, brazo). Todos los electrodos también pueden ser colocados en el pecho.

```{tip} __Buenas prácticas de cómo adquirir una buena señal__

__Preparación de la piel:__ 
* No es esencial, pero ayuda a mejorar la señal y minimizar la interferencia. 

__Recomendaciones:__
* Colocar en zonas con poco o sin pelo 
* Limpiar la piel con agua destilada 

__Frecuencia de Sampleo:__ 
* Frecuencia de sampleo de 512 HZ 

__Cables:__
* Utilizar los cables más cortos posibles, a mayor longitud, mayor probabilidad de interferencia 

```

## 2.4. Hardware y Software
__Instalación de Software__ 
Contiene 3 secciones: 
1. Instalación de drivers 
2. Instalación del Consensys Pro 
3. Instalación del Bluetooth (solo si tu computadora no cuenta con bluetooth).

### 2.4.1	Instalación de Drivers 
__Paso 1:__ Descarga el software de Consensys V1.6.0 (64 o 32bits)* desde el sitio web, pero no lo instales: https://shimmersensing.com/support/wireless-sensor-networks-download/ 

Para verificar y elegir qué versión (32 o 64bits) es compatible a la PC, seguir la siguiente ruta: 
1. _Panel de control_ 
2. _Sistema y seguridad_ 
3. _Sistema_ 

<div align="right">
  <img src="https://raw.githubusercontent.com/neuropucp/lab-book/main/book/res/manualECG_Especificaciones_del_dispositivo.png" alt="Especificaciones dispositivo ECG" width="500px" height="auto">
  <p><em><strong> Figura 16 </strong>Detalle de las especificaciones del equipo utilizado para los registros. Elaboración propia.</em></p>
</div>

__Paso 2:__ Windows instalará ahora los controladores (drivers) para la Base. Se proporcionará retroalimentación del estado en la bandeja del sistema de Windows; esquina inferior derecha de la 
pantalla. 

<div align="center">
  <img src="https://raw.githubusercontent.com/neuropucp/lab-book/main/book/res/manualECG_Instalacion_controladores.png" alt="Instalación controladores" width="auto" height="auto">
  <p><em><strong> Figura 17 </strong>Mensajes del sistema durante la instalación exitosa del controlador del dispositivo. Elaboración propia.</em></p>
</div>

__Paso 3:__ Conectar la base con la computadora, aparecerá una ventana emergente que menciona que el equipo está instalado. Para revisar que se haya instalado correctamente ubicarse en “Administrador de dispositivos” (si sale alguna ventana emergente, solo ciérrala) y desplegar “Controladores de bus serie universal” donde deberían encontrarse 4 USB Serial Converters (A, B, C, D).

<div align="center">
  <img src="https://raw.githubusercontent.com/neuropucp/lab-book/main/book/res/manualECG_Acceso_administrador_y_verificacion_de_instalacion.png" alt="Administrador y verificación instalación" width="900px" height="auto">
  <p><em><strong> Figura 18 </strong>Acceso al Administrador de dispositivos (A) y verificación de la instalación de los convertidores USB Serial para el dispositivo Shimmer (B). Elaboración propia.</em></p>
</div>

<div align="center">
  <img src="https://raw.githubusercontent.com/neuropucp/lab-book/main/book/res/manualECG_Verificacion_de_instalacion.png" alt="Verificación instalación" width="900px" height="auto">
  <p><em><strong> Figura 19 </strong>Verificación de la instalación del controlador USB Serial: acceso a propiedades del dispositivo (C), revisión de versión del driver (D) y configuración de nombre del puerto (E). Elaboración propia.</em></p>
</div>

```{Advertencia} En caso los procedimientos anteriores no resulten, proceder a la instalación manual de Drivers. 
* Paso A: En caso no se haya instalado, ir al siguiente enlace: https://ftdichip.com/drivers/vcp-drivers/ 
* Paso B: Descargar el archivo “WHQL Certified” dando click en setup.executable. 
* Paso C: Ejecutar el archivo con permisos de administrador y seguir las instrucciones del ejecutable. 
* Paso D: Una vez instalado, revisar si los drivers se instalaron como en el paso 3. 
* Paso E: Si se encuentran instalados, ya estaría listo para instalar el programa Consenys.
```

### _2.4.2. Instalación del ConsensysPRO_ 
Es un software que trabaja con todos los sensores Shimmer3 y la Base. Se emplea para grabar y retransmitir información, aplicar algoritmos, aplicar el firmware, y configurar y calibrar los sensores. Para la instalación realizar lo siguiente:

1. Ir al apartado de descargas en la página de Shimmer3 o ir al siguiente enlace: Downloads - Shimmer Wearable Sensor Technology (shimmersensing.com). 

2. Dependiendo de las especificaciones de tu computadora, descargar la versión de x32 o de x64 bits. 
3. Una vez descargado, extraer el archivo en tu computadora. 
4. Ejecutar el archivo ejecutable .exe 
5. Seguir las instrucciones e instalarlo. 
6. Darle doble clic al ícono que aparece en el escritorio.

### _2.4.3. Instalación de Bluetooth_
Para la retransmisión en vivo de las señales de los sensores al programa ConsensysPRO se necesita que su computadora cuente Bluetooth, caso contrario realice los siguientes pasos:

__Paso 1:__ Ir al siguiente enlace: 
https://www.intel.la/content/www/xl/es/download/18649/intel-wireless-bluetooth-for-windows-10-and-windows-11.html 

__Paso 2:__ Dependiendo de las especificaciones de tu ordenador descargar la versión de 32 o de 64 bits. Ejecutar el archivo .exe y seguir las instrucciones para la instalación.

```{Nota}
Asegurarse de que el ordenador tenga integrada una antena de bluetooth, de no ser así adquirir uno de manera externa.
```

### _2.4.4.	Activación de Licencia y Workspace_
Para la activación de la licencia realizar lo siguiente: 
1. Abrir el programa ConsensysPro.

2. En el apartado de “ConsensysPRO”, darle click a “Enter License Key”. 

3. Introducir la información de la licencia PRO. 

Finalmente, aparecerá la opción para establecer un “Workspace”, donde se guardarán todos los archivos que se quieren grabar. 

Para transmitir la información por Bluetooth asegurarse lo siguiente: 

1. Tener el controlador de Bluetooth instalado. 

2. Contar con un dispositivo de Bluetooth instalado de manera interna, de no ser así conseguir uno de forma externa USB. 

3. Emparejar el sensor con el programa Consensys 
	1. En la computadora ir al apartado de “Configuración de Bluetooth y otros dispositivos” darle a insertar un nuevo dispositivo. 
	2. Darle a “Bluetooth” y buscar el Shimmer 
	3. Asegurarse de que el sensor esté prendido 
	4. Deberían aparecer los sensores para emparejarlos 
	5. Darle click 
	6. Introducir la contraseña “1234”

Una vez realizado estos pasos se podrá ir a la sección de “LIVE DATA”, para iniciar con la transmisión en Bluetooth. Asimismo, tras una grabación de información, se podrá ir a la sección de “MANAGE DATA”.

Culminada la instalación del programa Consensys, aparecerá una ventana emergente que solicitará la ubicación de almacenamiento. Se sugiere guardar los archivos en una carpeta de preferencia en el escritorio. *CAD (software aid computer).

### _2.4.5	Configuración de Firmware_
Para asegurar la conexión entre el Shimmer y Consensys realizar lo siguiente: 
1. Prender los sensores.

2. Conectar los sensores en la Base. 

3. Ir a “Manage Devices”, aparecerán los sensores y otros datos de estos como su nombre, el estado de carga, el tipo de sensor y el tamaño de espacio almacenado en las tarjetas SD. 

4. Seleccionar el sensor que se requiera configurar. 

5. Darle click a “FIRMWARE”. 

6. Dependiendo de cómo se quiere grabar la información, darle click a “SDLog_Shimmer3” o “LogAndStream_Shimmer3”. 

	* __SDLog_Shimmer3:__ solo para grabar información de forma directa a la tarjeta SD. Este se emplea principalmente cuando mides el parámetro alejado del equipo (PC). 
	
	* __LogAndStream_Shimmer3:__ para grabar y retransmitir información al mismo tiempo mediante el Bluetooth. Este se emplea cuando mides el parámetro cerca del equipo principal (PC). 
7. Darle clic a programar. 
8. Esperar a que termine de programar. 
9. Al finalizar darle click a “DONE”. 

<div align="center">
  <img src="https://raw.githubusercontent.com/neuropucp/lab-book/main/book/res/manualECG_Dispositivo_Shimmer.png" alt="Dispositivo Shimmer" width="300px" height="auto">
  <p><em><strong> Figura 20 </strong>Vista del dispositivo Shimmer para configuración de muestreo, algoritmos y calibración mediante la opción “CONFIGURE”. Elaboración propia.</em></p>
</div>

<div align="center">
  <img src="https://raw.githubusercontent.com/neuropucp/lab-book/main/book/res/manualECG_Dispositivo_Shimmer_softwareConsensys.png" alt="Dispositivo Shimmer softwareConsensys" width="900px" height="auto">
  <p><em><strong> Figura 21 </strong>Vista del dispositivo Shimmer en el software Consensys con la opción “Configure” resaltada. Elaboración propia.</em></p>
</div>

Configuración de ensayo de referencia (https://www.youtube.com/watch?v=1B9oz1ZluO0) 

### _2.4.6. Programar los parámetros para cada Shimmer._ 
1. Elegir la ratio de muestreo (512 Hz, parámetro recomendado para ensayos clínicos). Este dato se coloca y se ingresa en la zona señalizada presionando “enter”. 

<div align="center">
  <img src="https://raw.githubusercontent.com/neuropucp/lab-book/main/book/res/manualECG_Muestreo_de_software.png" alt="Muestreo de software" width="900px" height="auto">
  <p><em><strong> Figura 22 </strong>Selección de la ratio de muestreo en el software Consensys (512 Hz). Elaboración propia.</em></p>
</div>

2.   Hacer click en los cuadrados para activar y configurar los sensores: En la ventana sensores (resaltador amarillo), en ella se determina que señales se desea medir para el ensayo experimental. Por ejemplo, en la imagen se muestran los sensores que están habilitados (en color blanco): Wide- range Accelerometer, Gyroscope y ECG. En caso, se encuentre coloreado de gris significa que son señales desactivadas. Este dato se coloca y se ingresa en la zona señalizada presionando “enter”. Para mayor alcance acerca de los sensores, consultar la siguiente información:

## 2.5. Sensores y Algoritmos 
El equipo cuenta con los siguientes sensores: Acelerómetro de bajo ruido, Acelerómetro de amplio rango (Varshney, 2021), Giroscopio (Sieciński et al., 2020), Magnetómetro (Brisinda et al., 2023), Temperatura y presión (Marathe et al., 2019), Voltaje de batería (Lee & Seo, 2019), ECG/EMG (Heyat & Siddiqui, 2015).

<div align="center">
  <img src="https://raw.githubusercontent.com/neuropucp/lab-book/main/book/res/manualECG_Interfaz_softwareConsensysPRO.png" alt="Interfaz softwareConsensysPRO" width="900px" height="auto">
  <p><em><strong> Figura 23 </strong>Interfaz del software ConsensysPRO v1.6.0 mostrando la ventana de algoritmos resaltada para su configuración. Elaboración propia.</em></p>
</div>

3. Posteriormente, de click en la ventana algoritmos (resaltado). 

El equipo cuenta con los siguientes algoritmos: Calibración del giroscopio “sobre la marcha”, 9DOF (Lüken et al., 2015) , 6DOF (Lüken et al., 2015), ECG-to-HR (Ahmed & Begum, 2010), EMG Processing (Richer et al., 2014), Activity (Muhlsteff et al., 2004). 

1. Seguidamente pasar a la ventana calibración (resaltada), en el cual se debe cerciorar que los bordes de los cuadros sean de color naranja como indica en la imagen referencial. Lo anterior indica una adecuada calibración.
2. Luego, regresar a la ventana de sensores (resaltador amarillo) y hacer click en “Write Config”. La ventana emergente indica que la unidad está lista para recoger información (Configuration progress)

Enseguida, seguir las instrucciones de la imagen inferior: 

<div align="center">
  <img src="https://raw.githubusercontent.com/neuropucp/lab-book/main/book/res/manualECG_Confirmacion_configuracion_softwareConsensys.png" alt="Confirmación configuración software" width="900px" height="auto">
  <p><em><strong> Figura 24 </strong>Confirmación de la configuración en el software Consensys mediante la ventana “Configuration Progress”. Elaboración propia.</em></p>
</div>

1. Retirar el shimmer de la base.

2. Tener cuidado de no apagarlo. 

3. Presiona el botón naranja para empezar el registro. 

4. Verificar que la luz verde esté intermitente cuando se graban los datos. 

5. Presionar el botón naranja para detener el registro. 

<div align="center">
  <img src="https://raw.githubusercontent.com/neuropucp/lab-book/main/book/res/manualECG_Iniciar_y_detener_registro.png" alt="Iniciar y detener registro" width="900px" height="auto">
  <p><em><strong> Figura 25 </strong>Instrucciones para iniciar y detener el registro de datos en el dispositivo Shimmer mediante el botón naranja. Elaboración propia.</em></p>
</div>

6. Visualización de la data en vivo: 
Apretar el botón “Live Data” para visualizar la señal. Asegurarse que el dispositivo bluetooth esté conectado a la computadora, dar click en el ícono de antena (encendido de azul).

<div align="center">
  <img src="https://raw.githubusercontent.com/neuropucp/lab-book/main/book/res/manualECG_Visualizacion_se%C3%B1ales_registradas.png" alt="Visualizar Señales registradas" width="900px" height="auto">
  <p><em><strong> Figura 26 </strong>Visualización en vivo de las señales registradas por el dispositivo Shimmer en ConsensysPRO. Elaboración propia.</em></p>
</div>

Finalmente, se selecciona los instrumentos que se desea conectar al bluetooth. Dar click a “Stream” para visualizar la data.

<div align="center">
  <img src="https://raw.githubusercontent.com/neuropucp/lab-book/main/book/res/manualECG_Visualizador_dispositivos_tiempo_real.png" alt="Visualizar dispositivo tiempo real" width="900px" height="auto">
  <p><em><strong> Figura 27 </strong>Panel de ConsensysPRO mostrando dispositivo conectado y señales listas para visualizar en tiempo real. Elaboración propia.</em></p>
</div>

La siguiente imagen incluye la visualización de las ondas PQRST. 

<div align="center">
  <img src="https://raw.githubusercontent.com/neuropucp/lab-book/main/book/res/manualECG_Visualizacion_tiempo_real.png" alt="Visualizar dispositivo tiempo real" width="900px" height="auto">
  <p><em><strong> Figura 28 </strong>Visualización en tiempo real de la señal fisiológica registrada por el dispositivo Shimmer en ConsensysPRO. Elaboración propia.</em></p>
</div>

Consensys permite personalizar la visualización de los datos: 
* Elegir qué leads se desean visualizar de acuerdo con los parámetros escogidos como relevantes para el estudio.

* Elegir el número de “plots” y el color de la señal que se desea tener en cada uno **el nombre de la señal del lead aparece en la parte inferior del plot correspondiente. 

* Configurar las dimensiones del eje Y (en unidades mV) y eje X (en unidades de tiempo) de la señal transversal a todos los plots. 

A partir de una pequeña revisión de literatura en la cual se empleó el Shimmer3 ECG para el recojo de datos fisiológicos. Se recomienda establecer una tasa de muestreo que podría ser el valor por defecto de 512Hz, el cual se ha empleado en el recojo de data en reposo (Bossaerts et al., 2024). Además, se reporta el uso de una tasa de muestreo de 1024Hz para recojo de datos en movimiento (Ogden et al., 2024). Inclusive, se podría tomar en consideración las tasas de muestreo mínimas según la Asociación Americana del Corazón (Kligfield, 2007). De forma análoga, se debe evaluar la posición conveniente para la posición de los electrodos y leads (Miranda-Correa et al., 2018; Katsigiannis & Ramzan, 2017). 

## 2.6.	Referencias Bibliográficas
Ahmed, M.U., & Begum, S. (2010). Heart Rate and Inter-beat Interval Computation to Diagnose Stress Using ECG Sensor Signal. https://www.es.mdh.se/pdf_publications/1929.pdf 

Bossaerts, P., Fattinger, F., Rotaru, K., & Xu, K. (2024). Emotional engagement and trading performance. Management Science, 70(6), 3381-3397. https://doi.org/10.1287/mnsc.2023.4883 

Brisinda, D., Fenici, P., & Fenici, R. (2023). 

Clinical magnetocardiography: the unshielded bet-past, present, and future. Frontiers in cardiovascular medicine, 10, 1-24. https://doi.org/10.3389/fcvm.2023.1232882 

Heyat, B. M., & Siddiqui, M. M. (2015). Recording of EEG, ECG, EMG Signal. International Journal of Advanced Research in Computer Science and Software Engineering, 5(10), 813-815. Katsigiannis, S., & Ramzan, N. (2017). DREAMER: A database for emotion recognition through EEG and ECG signals from wireless low-cost off-the-shelf devices. IEEE journal of biomedical and health informatics, 22(1), 98-107. https://doi.org/10.1109/JBHI.2017.2688239 

Kligfield, P., Gettes, L. S., Bailey, J. J., Childers, R., Deal, B. J., Hancock, E. W., van Herpen, G., Kors, J. A., Macfarlane, P., Mirvis, D. M., Pahlm, O., Rautaharju, P., 

Wagner, G. S., Josephson, M., Mason, J. W., Okin, P., Surawicz, B., Wellens, H. (2007). Recommendations for the standardization and interpretation of the electrocardiogram: part I: the electrocardiogram and its technology a scientific statement from the American Heart Association Electrocardiography and Arrhythmias Committee, Council on Clinical Cardiology; the American College of Cardiology Foundation; and the Heart Rhythm Society endorsed by the International Society for Computerized Electrocardiology. Circulation, 115(10), 1306-1324. https://doi.org/10.1161/CIRCULATIONAHA.106.180200 

Lee, J., & Seo, D. (2019). Development of ECG Monitoring System and Implantable Device with Wireless Charging. Micromachines, 10(1), 1-15. https://doi.org/10.3390/mi10010038 Lüken M, Misgeld BJE, Rüschen D, Leonhardt S. (2015). Multi-Sensor Calibration of Low-Cost Magnetic, Angular Rate and Gravity Systems. Sensors, 15(10), 25919-25936. https://doi.org/10.3390/s151025919 

Marathe, S., Zeeshan, D., Thomas, T., & Vidhya, S. (2019). A Wireless Patient Monitoring System using Integrated ECG module, Pulse Oximeter, Blood Pressure and Temperature Sensor. Conference on Vision Towards Emerging Trends in Communication and Networking (ViTECoN), 1-4. https://doi.org/10.1109/ViTECoN.2019.8899541 

Miranda-Correa, J. A., Abadi, M. K., Sebe, N., & Patras, I. (2018). Amigos: A dataset for affect, personality and mood research on individuals and groups. IEEE transactions on af ective computing, 12(2), 479-493. https://doi.org/10.1109/TAFFC.2018.2884461 

Muhlsteff, J., Such, O., Schmidt, R., Perkuhn, M., Reiter, H., Lauter, J., Thijs, J., Musch, G., & Harris, M. (2004). Wearable approach for continuous ECG--and activity patient-monitoring. Conference proceedings: Annual International Conference of the IEEE Engineering in Medicine and Biology Society. IEEE Engineering in Medicine and Biology Society. Annual Conference, 2004, 2184–2187. https://doi.org/10.1109/IEMBS.2004.1403638 

Ogden, R. S., Dobbins, C., Slade, K., McIntyre, J., & Fairclough, S. (2022). The psychophysiological mechanisms of real-world time experience. Scientific reports, 12(1), 12890. https://doi.org/10.1038/s41598-022-16198-z 

Richer, R., Blank, P., Schuldhaus, D., & Eskofier, B. M. (2014). Real-Time ECG and EMG Analysis for Biking Using Android-Based Mobile Devices. 11th International Conference on Wearable and Implantable Body Sensor Networks. https://www.semanticscholar.org/paper/Real-Time-ECG-and-EMG-Analysis-for-Biking-Using-Richer Blank/d7e647d978e6b4c4b0e922963ef8eab792f2da05 

Sieciński, S., Kostka, P. S. & Tkacz, E. J. (2020). Gyrocardiography: A Review of the Definition, History, Waveform Description, and Applications. Sensors, 20, 1-30. https://doi.org/10.3390/s20226675 

Varshney, N. (2021). Combining electrocardiogram signal with Accelerometer signals for Human Activity Recognition using Convolution neural network. Journal of Physics: Conference Series, 1947, 1-5. https://dx.doi.org/10.1088/1742-6596/1947/1/012037 
