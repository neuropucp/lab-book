# Manual EDA
## __3.1. Introducción__

El *Shimmer3 GSR+ Unit* (GSR) pertenece a la familia de dispositivos *Shimmer*, utilizados en el monitoreo de mediciones fisiológicas. 

### *__3.1.1. Función de la unidad__*

La unidad GSR+ se utiliza para medir la respuesta galvánica de la piel, también conocida como resistencia o actividad electrodérmica de dos electrodos adjuntos a dos dedos de una mano. En respuesta a un estímulo, las glándulas sudoríparas se vuelven más activas, incrementando la humedad de la piel y permitiendo que la corriente eléctrica fluya más fácilmente al cambiar el equilibrio de iones positivos y negativos en el líquido secretado. 

### *__3.1.2. Hardware__*

La unidad de procesamiento central (CPU) del shimmer es el microprocesador low-power MSP430F5437A que configura y controla placas de adquisición de datos, a través de pines input/output que se emplean para acoplar conectores de expansión interna y externa (i.e. la base). La CPU tiene integrado un convertidor analógico-digital (ADC) de 16 canales y 12 bits que se utiliza para capturar los datos de los sensores o las expansiones de sensores. 

El Shimmer tiene un puerto para tarjetas microSD Flash a modo de almacenamiento adicional externo, para asegurar su compatibilidad la tarjeta debe implementar el modo SPI de 1 bit. Asimismo, tiene 5 diodos emisores de luz LED, un interruptor de encendido/apagado y un botón de usuario definido por el software. Para la transmisión inalámbrica de datos, el Shimmer está equipado con una antena de 2.4GHz conectada a un módulo bluetooth de clase 2 RN-42 para comunicarse. El rango de RN-42 es de más de 10 metros. 

La unidad shimmer se ha fabricado con una batería de litio recargable de 3,7V y 450mAh con alimentación de CA, es importante proteger la polaridad de la batería, supervisar la carga y los límites de sobretensión/subtensión; además de la sobredescarga. El tiempo de duración de la batería depende de cuánto tiempo lleva operando el dispositivo, si la radio está activada, qué sensores se están usando y con qué frecuencia de muestreo. Idealmente fue fabricada para que la batería dure de 1 a 14 días adquiriendo datos de varios canales con transmisión periódica por radio. 

Los estados de alimentación de la placa (encendido y apagado) son controlados por un interruptor deslizante. Mientras que él módulo de radio bluetooth es controlado con el software Consensys, mientras que la expansión FFC (radio periférica), el oscilador de cristal con compensación de temperatura y el puerto microSD disponen de conmutación suave de la alimentación. Incluso otros módulos tienen integradas funciones de apagado. 

## __3.2. Medidas de bioseguridad__

1. Es necesario utilizar equipo de protección personal (EPP) (ej. guantes desechables, batas o delantales). 

2. Emplear agua destilada para limpiar la superficie de la piel de la persona antes de aplicar los electrodos. 

3. Los electrodos del equipo no deben aplicarse al cuerpo del sujeto mientras la unidad Shimmer esté en la base o, por defecto, conectado externamente (puerto USB, cargador múltiple). Debe desconectarlo. 

4. Evitar la exposición del equipo al calor excesivo o a una llama abierta. 

5. Mantener el equipo alejado de personas menores de edad. 

6. Limpiar la superficie donde se colocarán los sensores, de esta forma evitamos interferencias 7. Al culminar las mediciones, retirar cuidadosamente los electrodos y desinfectarlos 

## __3.3. Componentes__

### *__3.3.1. Componentes del Equipo Shimmer__*

* Base: se conecta al cable de conexión del equipo. 
* Cable de poder: conecta la base con la corriente eléctrica. 
* Cable USB: conecta la base con la computadora. 
* El shimmer GSR+ se conecta a la base. 

Una vez realizado el ensamblaje de los componentes, proceder al encendido del equipo.              

### *__3.3.2. Componentes del Equipo Shimmer GSR+__*
* Unidades de sensor Shimmer3 GSR+ unit. 
* Cables biofísicos (2 por unidad de sensor). 
* Velcro (2 se posiciona alrededor de cada dedo). 
* Sensor de pulso óptico 

## __3.4. Midiendo señales GSR__


*__Consideraciones:__*
 
La unidad se puede configurar a distintos valores predeterminados para permitir resultados precisos (Tabla 1). Los ajustes 2 y 3 proporcionan la mejor combinación para los valores típicos de conductancia tónica de la piel. También existe una opción automática (Auto-Range) en la que se establecerá el rango al valor más adecuado para la lectura actual basándose en puntos de transición predeterminados. 

*__Tabla 1__*
*Ajustes predeterminados del GSR+.B*

Range
Setting	Full Scale Range
	Resistance	Conductance
0	8 kΩ a 63 kΩ	125 μS a 15.9μS
1	63 kΩ a 220 kΩ	15.9 μS a 4.5 μS
2	220 kΩ a 680 kΩ	4.5 μS a 1.5 μS
3	680 kΩ a 4.7 MΩ	1.5 μS a 0.2 μS
4	Auto-Range
Nota: Valores en kΩ y μS. Auto-Range ajusta el rango automáticamente.

__Sugerencias para la frecuencia de sampleo:__
Se sugiere utilizar frecuencias de 0-5 Hz para medidas tónicas, siendo las frecuencias 0.03-5 Hz adecuadas para mediciones fásicas 

__Posición de los electródos:__
Un electrodo debe colocarse en la superficie palmar de la falange medial y el otro en la superficie palmar de la falange distal (Figura 1): 

<div align="center">
  <img src="https://raw.githubusercontent.com/neuropucp/lab-book/main/book/res/manualEDA_Posicionamiento_de_electrodos_del_GSR+.png" alt="Localización de electrodos ECG" width="auto" height="auto">
  <p><em><strong> Figura 1 </strong>Ejemplo de posicionamiento de los electrodos del GSR+.</em></p>
</div>

__Sonda de pulso óptico:__

La sonda de pulso óptico suele colocarse en el lóbulo de la oreja, una zona ideal para medir la fotopletismografía (PPG) debido a su baja interferencia con el movimiento. Esto disminuye el ruido y minimiza la variabilidad en la conexión entre la piel y el sensor. Además, al no haber actividad muscular en esta área, el flujo sanguíneo no es alterado. 

Para obtener mejores resultados, se recomienda colocar el sensor en la parte inferior de la porción blanda del lóbulo de la oreja, ya que estudios han demostrado que la señal PPG obtenida es más débil en la parte superior del lóbulo. Esta diferencia en la ubicación podría dificultar la extracción de información sobre la frecuencia cardíaca. 

### *__3.4.1. La señal GSR__*

La señal GSR está compuesta de componentes tónicos y fásicos. Por un lado, el componente tónico, también conocido como nivel de conductancia de la piel, vendría a ser la señal base que varía lentamente. Por otro lado, el componente fásico es la parte que cambia rápido ante la aparición de estímulos o activación no especificada. 

__Línea base:__

El GSR mide la conductancia de la piel y esta dependerá de qué tanto la persona suda. Mientras más sude, mayor será la conductancia de la piel y menor su resistencia. Algunos factores que pueden afectar esta línea base son la temperatura, la sequedad de la piel u otros factores fisiológicos individuales. Las respuestas ante estímulos provocan un rápido incremento de la conductividad seguido de un retorno lento a la línea base. 

__Ruido y movimiento del artefacto:__
El movimiento puede traducirse en forma de onda de alta frecuencia. Esto puede ocurrir si los electrodos no están ajustados apropiadamente y pierden contacto con la piel. Por ello, se recomienda ajustar los electrodos a la piel para evitar este tipo de ruido. Asimismo, se recomienda aplicar un *low pass filter* para remover ruido de frecuencia alta que pueden atribuirse al movimiento del artefacto. 

## __3.5. Analizando e interpretando las señales GSR para medir excitación emocional__

Para ello se sugiere separar el componente tónico del fásico. A mayor variación del componente fásico, más excitado estará el sujeto. 

### *__3.5.1. Software__*
* __Instalación de Software__
Contiene 3 secciones: 
1. Instalación de drivers 
2. Instalación del Consensys Pro 
3. Instalación del Bluetooth (solo si tu computadora no cuenta con bluetooth). 
* __Instalación de Drivers__
__Paso 1:__ Descarga el software de Consensys V1.6.0 (64 o 32bits) * desde el sitio web, pero aún no debe ser instalado: https://shimmersensing.com/support/wireless-sensor-networks-download/ 

Para verificar y elegir qué versión (32 o 64bits) es compatible a la PC, seguir la siguiente ruta: 
1. *Panel de control*
2. *Sistema y seguridad* 
3. *Sistema* 

__Paso 2:__ Windows instalará ahora los controladores (drivers) para la Base. 

<div align="center">
  <img src="https://raw.githubusercontent.com/neuropucp/lab-book/main/book/res/manualEDA_Especificaciones_de_compatibilidad_del_dispositivo.png" alt="Localización de electrodos ECG" width="auto" height="auto">
  <p><em><strong> Figura 2 </strong>Especificaciones de compatibilidad del dispositivo.</em></p>
</div>  

_Paso 3:_ Al conectar la base con la computadora, aparecerá una ventana emergente que menciona que el equipo está instalado. Para revisar que se haya instalado correctamente ubicarse en “Administrador de dispositivos” (si sale alguna ventana emergente, solo ciérrala) y desplegar “Controladores de USB serie universal” donde deberían encontrarse 4 USB Serial Converters (A, B, C, D). 

<div align="center">
  <img src="https://raw.githubusercontent.com/neuropucp/lab-book/main/book/res/manualEDA_Visualizacion_de_los_controladores_de_USB_serie_universal.png" alt="Localización de electrodos ECG" width="auto" height="auto">
  <p><em><strong> Figura 3 </strong>Visualización de los controladores de USB serie universal.</em></p>
</div>  


<div align="center">
  <img src="https://raw.githubusercontent.com/neuropucp/lab-book/main/book/res/manualEDA_Verificacion_manual_de la_instalacion_de_los_drivers.png" alt="Localización de electrodos ECG" width="auto" height="auto">
  <p><em><strong> Figura 4 </strong>Verificación manual de la instalación de los drivers.</em></p>
</div>  

```{warning} Advertencia
En caso los procedimientos anteriores no resulten, proceder a la instalación manual de Drivers....
```

```{figure} ../images/cool.jpg (CAMBIAR A GUÍA DE IMAGEN)
---
scale: 100%
align: center
---
*Verificación manual de la instalación de los drivers.*
```
* Paso A: En caso no se haya instalado, ir al siguiente enlace: https://ftdichip.com/drivers/vcp-drivers/ 
* Paso B: Descargar el archivo “WHQL Certified” dando click en setup.executable 
* Paso C: Ejecutar el archivo con permisos de administrador y seguir las instrucciones del ejecutable. 
* Paso D: Una vez instalado, revisar si los drivers se instalaron como en el paso 3.
* Paso E: Si se encuentran instalados, ya estaría listo para instalar el programa Consenys. 

## __3.6. Instalación del ConsensysPRO__

Es un software que trabaja con todos los sensores Shimmer3 y la Base. Se emplea para grabar y retransmitir información, aplicar algoritmos, aplicar el firmware, y configurar y calibrar los sensores. Para la instalación realizar lo siguiente:
 
1. Ir al apartado de descargas en la página de Shimmer3 o ir al siguiente enlace: Downloads - Shimmer Wearable Sensor Technology (shimmersensing.com). 
2. Dependiendo de las especificaciones de tu computadora, descargar la versión de x32 o de x64 bits. 
3. Una vez descargado, extraer el archivo en tu computadora. 
4. Ejecutar el archivo ejecutable .exe 
5. Seguir las instrucciones e instalarlo. 
6. Darle doble clic al ícono que aparece en el escritorio.

### *__3.6.1. Instalación de Bluetooth__*
Para la retransmisión en vivo de las señales de los sensores al programa ConsensysPRO se necesita que su computadora cuente Bluetooth, caso contrario realice los siguientes pasos: 

__Paso 1:__ Ir al siguiente enlace: 
	https://www.intel.la/content/www/xl/es/download/18649/intel-wireless-bluetooth-for-windows-10-and-wi ndows-11.html 

__Paso 2:__Dependiendo de las especificaciones de tu ordenador descargar la versión de 32 o de 64 bits. Ejecutar el archivo .exe y seguir las instrucciones para la instalación. 

```{note} Nota
Asegurarse de que el ordenador tenga integrada una antena de bluetooth, de no ser así adquirir uno de manera externa.
```

Para la activación de la licencia realizar lo siguiente: 
	1. Abrir el programa ConsensysPro. 
	2. En el apartado de “ConsensysPRO”, darle click a “Enter License Key”. 
	3. Introducir la información de la licencia PRO. 

Finalmente, aparecerá la opción para establecer un “Workspace”, donde se guardarán todos los archivos que se quieren grabar. 

Para transmitir la información por Bluetooth asegurarse lo siguiente: 
	1. Tener el controlador de Bluetooth instalado. 
	2. Contar con un dispositivo de Bluetooth instalado de manera interna, de no ser así conseguir uno de forma externa USB. 
	3. Emparejar el sensor con el programa Consensys 
		a. En la computadora ir al apartado de “Configuración de Bluetooth y otros dispositivos” darle a insertar un nuevo dispositivo. 
		b. Darle a “Bluetooth” y buscar el Shimmer 
		c. Asegurarse de que el sensor esté prendido 
		d. Deberían aparecer los sensores para emparejarlos 
		e. Darle click 
		f. Introducir la contraseña “1234” 

Una vez realizado estos pasos se podrá ir a la sección de “LIVE DATA”, para iniciar con la transmisión en Bluetooth. Asimismo, tras una grabación de información, se podrá ir a la sección de “MANAGE DATA”. 

Culminada la instalación del programa Consensys, aparecerá una ventana emergente que solicitará la ubicación de almacenamiento. Se sugiere guardar los archivos en una carpeta de preferencia en el escritorio. 

## *__3.6.2. Firmware__*
Para asegurar la conexión entre el Shimmer y Consensys realizar lo siguiente: 
1. Prender los sensores. 
2. Conectar los sensores en la Base. 
3. Ir a “Manage Devices”, aparecerán los sensores y otros datos de estos como su nombre, el estado de carga, el tipo de sensor y el tamaño de espacio almacenado en las tarjetas SD. 4. Seleccionar el sensor que se requiera configurar. 
5. Darle click a “FIRMWARE”. 
6. Dependiendo de cómo se quiere grabar la información, darle click a “SDLog_Shimmer3” o “LogAndStream_Shimmer3”. 
	* __SDLog_Shimmer3:__ solo para grabar información de forma directa a la tarjeta SD. Este se emplea principalmente cuando mides el parámetro alejado del equipo (PC). 
	* __LogAndStream_Shimmer3:__ para grabar y retransmitir información al mismo tiempo mediante el Bluetooth. Este se emplea cuando mides el parámetro cerca del equipo principal (PC). 
7. Darle clic a programar. 
8. Esperar a que termine de programar. 
9. Al finalizar darle click a “DONE”. 
 

<div align="center">
  <img src="https://raw.githubusercontent.com/neuropucp/lab-book/main/book/res/manualEDA_Shimmer3_GSR+_conectada.png" alt="Localización de electrodos ECG" width="auto" height="auto">
  <p><em><strong> Figura 5 </strong>Unidad Shimmer3 GSR+ conectada a la base y correctamente reconocida por el software Consensys.</em></p>
</div> 


Para realizar configuraciones como el muestreo, algoritmos y la calibración ir   “CONFIGURE”.


<div align="center">
  <img src="https://raw.githubusercontent.com/neuropucp/lab-book/main/book/res/manualEDA_Ventana_del_programa_Consensys.png" alt="Localización de electrodos ECG" width="auto" height="auto">
  <p><em><strong> Figura 6 </strong>Ventana del programa Consensys.</em></p>
</div> 


## __3.7. Programar los parámetros para el Shimmer__

### *__3.7.1. Sensores y Algoritmos__*

1. Elegir la ratio de muestreo. Este dato se coloca y se ingresa en la zona SAMPLING RATE (Hz) presionando “enter”. 

<div align="center">
  <img src="https://raw.githubusercontent.com/neuropucp/lab-book/main/book/res/manualEDA_Ventana_de_parametros(sensores).png" alt="Localización de electrodos ECG" width="auto" height="auto">
  <p><em><strong> Figura 7 </strong>Ventana de parámetros (sensores) de configuración del dispositivo.</em></p>
</div> 

2. Hacer click en los cuadrados para activar y configurar los sensores: En la ventana sensores (resaltador amarillo), en ella se determina que señales se desea medir para el ensayo experimental. Por ejemplo, en la imagen se muestran los sensores que están habilitados (en color blanco): GSR+. En caso, se encuentre coloreado de gris significa que son señales desactivadas. 

El equipo cuenta con los siguientes sensores: Acelerómetro de bajo ruido, Acelerómetro de amplio rango (Varshney, 2021), Giroscopio (Sieciński et al., 2020), Magnetómetro (Brisinda et al., 2023), Temperatura y presión (Marathe et al., 2019), Voltaje de batería (Lee & Seo, 2019), Convertidores Anlógico-Digitales de expansión externa e interna y GSR/PPG. 

3. Posteriormente, de click en la ventana algoritmos. 

<div align="center">
  <img src="https://raw.githubusercontent.com/neuropucp/lab-book/main/book/res/manualEDA_Ventana_de_parametros(algoritmos).png" alt="Localización de electrodos ECG" width="auto" height="auto">
  <p><em><strong> Figura 8 </strong>Ventana de parámetros (algoritmos) de configuración del dispositivo.</em></p>
</div> 


El equipo cuenta con los siguientes algoritmos: Calibración del giroscopio “sobre la marcha”, 9DOF (Lüken et al., 2015) , 6DOF (Lüken et al., 2015), PPG to HR y Activity (Muhlsteff et al., 2004).

4. Seguidamente pasar a la ventana de calibración, en el cual se debe cerciorar que los bordes de los cuadros sean de color naranja como indica en la imagen referencial. Lo anterior indica una adecuada calibración 

<div align="center">
  <img src="https://github.com/neuropucp/lab-book/blob/main/book/res/manualEDA_Ventana_de_parametros (calibración).png" alt="Localización de electrodos ECG" width="auto" height="auto">
  <p><em><strong> Figura 9 </strong>Ventana de parámetros (calibración) de configuración del dispositivo.</em></p>
</div> 


5. Finalmente, confirmar la configuración y hacer click en “Write Config”. La ventana emergente indica que la unidad está en proceso o lista para recoger información (Configuration progress). 

<div align="center">
  <img src="https://raw.githubusercontent.com/neuropucp/lab-book/main/book/res/manualEDA_Ventana_del_estado_de_confirmacion.png" alt="Localización de electrodos ECG" width="auto" height="auto">
  <p><em><strong> Figura 10 </strong>Ventana del estado de confirmación de la configuración del dispositivo.</em></p>
</div> 

Enseguida, seguir las instrucciones de la imagen inferior:
1. Retirar el shimmer de la base 
2. Tener cuidado de no apagarlo. 
3. Presiona el botón naranja  para empezar el registro. 
4. Verificar que la luz verde esté intermitente cuando se graban los datos. 
5. Presionar el botón naranja para detener el registro.

<div align="center">
  <img src="https://raw.githubusercontent.com/neuropucp/lab-book/main/book/res/manualEDA_Ventana_con_instrucciones_para_registro_datos.png" alt="Localización de electrodos ECG" width="auto" height="auto">
  <p><em><strong> Figura 11 </strong>Ventana con instrucciones para el registro de datos.</em></p>
</div> 

## *__3.7.2. Visualización de la data__*
1. Dirigirse a la pestaña “Live Data” para visualizar la señal. Verificar previamente que el dispositivo bluetooth esté conectado a la computadora, luego dar click en el ícono de antena (encendido de azul). 


<div align="center">
  <img src="https://raw.githubusercontent.com/neuropucp/lab-book/main/book/res/manualEDA_Ventana_de_visualizacion_data.png" alt="Localización de electrodos ECG" width="auto" height="auto">
  <p><em><strong> Figura 12 </strong>Ventana para la visualización de la data.</em></p>
</div> 

<div align="center">
  <img src="https://raw.githubusercontent.com/neuropucp/lab-book/main/book/res/manualEDA_Ventana_conectado_correccto_bluetooth.png" alt="Localización de electrodos ECG" width="auto" height="auto">
  <p><em><strong> Figura 13 </strong>Visualización del Shimmer correctamente conectado a la señal bluetooth.</em></p>
</div> 

2. Finalmente, Dar click a “Stream” para visualizar la data


<div align="center">
  <img src="https://raw.githubusercontent.com/neuropucp/lab-book/main/book/res/manualEDA_Visualizacion_data_en_vivo.png" alt="Localización de electrodos ECG" width="auto" height="auto">
  <p><em><strong> Figura 14 </strong>Visualización de la data en vivo.</em></p>
</div> 

Consensys permite personalizar la visualización de los datos: 

* Elegir qué leads se desean visualizar de acuerdo con los parámetros escogidos como relevantes para el estudio. 
* Elegir el número de “plots” y el color de la señal que se desea tener en cada uno **el nombre de la señal del lead aparece en la parte inferior del plot correspondiente 
* Configurar las dimensiones del eje Y (en unidades mV) y eje X (en unidades de tiempo) de la señal transversal a todos los plots. 


## 3.8. Referencias Bibliográficas:
 
Ahmed, M. U., & Begum, S. (2010). Heart rate and inter-beat interval computation to diagnose stress using ECG sensor signal. https://www.es.mdh.se/pdf_publications/1929.pdf 

Heyat, M. B. B., et al. (2023). Recording of EEG, ECG, EMG signal. https://www.researchgate.net/profile/Md-Belal-Bin-Heyat/publication/366137968_Recording_of_EEG_ECG_EMG_Signal/links/6392ecd8e42faa7e75ab8f00/Recording-of-EEG-ECG-EMG-Sign al.pdf 

Lee, J., & Seo, D. (n.d.). Development of ECG monitoring system and implantable device with wireless charging. Micromachines, 10(1), 1-15. https://doi.org/10.3390/mi10010038 

Lüken, M., Misgeld, B. J. E., Rüschen, D., & Leonhardt, S. (2015). Multi-sensor calibration of low-cost magnetic, angular rate and gravity systems. Sensors, 15(10), 25919-25936. https://doi.org/10.3390/s151025919 

Marathe, S., Zeeshan, D., Thomas, T., & Vidhya, S. (2019). A Wireless Patient Monitoring System using Integrated ECG module, Pulse Oximeter, Blood Pressure and Temperature Sensor. 2019 International Conference on Vision Towards Emerging Trends in Communication and Networking (ViTECoN). https://doi.org/10.1109/vitecon.2019.8899541 

Muhlsteff, J., Such, O., Schmidt, R., Perkuhn, M., Reiter, H., Lauter, J., Thijs, G., & Harris, M. (2004). Wearable approach for continuous ECG and activity patient monitoring. The 26th Annual International Conference of the IEEE Engineering in Medicine and Biology Society. 

Richer, R., Blank, P., Schuldhaus, D., & Eskofier, B. M. (2014). Real-time ECG and EMG analysis for biking using Android-based mobile devices. 11th International Conference on Wearable and Implantable Body Sensor Networks. https://www.semanticscholar.org/paper/Real-Time-ECG-and-EMG-Analysis-for-Biking-Using-Ri cher-Blank/d7e647d978e6b4c4b0e922963ef8eab792f2da05 

Shimmer Research Ltd. (2023, September 26). Optical Pulse Probe | Shimmer3 GSR+ unit | Shimmer Sensing. Shimmer Wearable Sensor Technology. 
https://shimmersensing.com/product/optical-pulse-probe/ + 

Shimmer Research. (2016). Optical Pulse Sensor User Guide (Rev. 1.6). Shimmer Research. https://shimmersensing.com 

Shimmer Sensing. (n.d.). 9DOF Calibration Application User Manual Rev 2.10a. https://shimmersensing.com/wp-content/docs/support/documentation/Shimmer_9DOF_Calibratio n_User_Manual_rev2.10a.pdf 

Sieciński, S., Kostka, P. S. & Tkacz, E. J. (2020). Gyrocardiography: A Review of the Definition, History, Waveform Description, and Applications. Sensors, 20, 1-30. 

Varshney, N. (2021). Combining electrocardiogram signal with Accelerometer signals for Human Activity Recognition using Convolution neural network. Journal of Physics Conference Series, 1947(1), 012037. https://doi.org/10.1088/1742-6596/1947/1/012037 

Werner, J. (2014). Electrocardiography. En A. Brahme (Ed.), Comprehensive Biomedical Physics (pp. 25–45). Oxford: Elsevier. https://doi.org/10.1016/B978-0-444-53632-7.00507-4 
