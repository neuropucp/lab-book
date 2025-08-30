# Ficha EDA
## 3.9. Ficha Técnica Shimmer3 GSR+
### *__3.9.1. Introducción__* 

El Shimmer3 GSR+ es un dispositivo diseñado para medir la respuesta galvánica de la piel (GSR), proporcionando información sobre la conductancia y resistencia de la piel en respuesta a estímulos. Además, cuenta con capacidades para medir la frecuencia cardíaca mediante fotopletismografía (PPG). Su versatilidad lo hace ideal para aplicaciones en investigación fisiológica, monitoreo emocional y estudios de estrés.
 
### *__3.9.2. Componentes del Sistema__*
 
Asegúrate de contar con los siguientes elementos: 
* Unidad Shimmer3 GSR+: Sensor principal para medir la actividad electrodérmica. 
* Base del dispositivo: Para cargar y conectar el equipo. 
* Cables biofísicos: Se conectan a los electrodos en los dedos. 
* Velcro: Sujeta los electrodos en las manos. 
* Sensor de pulso óptico: Para medir PPG desde el lóbulo de la oreja.
* Cable USB: Para conexión con la computadora. 

### *__3.9.3. Medidas de Bioseguridad__* 

1. Usa equipo de protección personal (guantes, batas). 
2. Limpia la piel con agua destilada antes de colocar los electrodos. 
3. Nunca conectes los electrodos al cuerpo si el Shimmer está conectado a la base o al USB. 
4. Mantén el dispositivo lejos de fuentes de calor o llamas. 
5. Desinfecta los electrodos después de cada uso. 

### *__3.9.4 Instalación del Software__*

__4.1 Instalación de Drivers__
1. Descarga los drivers desde FTDI Drivers. 
2. Ejecuta el archivo de instalación y sigue las instrucciones. 
3. Verifica la instalación en el Administrador de dispositivos bajo "Controladores de USB serie universal". 

__4.2 Instalación del Software ConsensysPRO__
1. Descarga el software desde Shimmer Downloads. 
2. Extrae y ejecuta el instalador. 
3. Sigue las instrucciones hasta completar la instalación. 

__4.3 Configuración de Bluetooth (si es necesario)__
1. Descarga e instala los controladores de Bluetooth desde Intel Bluetooth.
2. Empareja el dispositivo con el Shimmer introduciendo la contraseña "1234". 

### *__3.9.5. Configuración del Dispositivo__*
1. Conexión física: 
* Conecta la base al cable USB y al Shimmer3 GSR+. 

2. Configuración de parámetros: 
* Abre el software ConsensysPRO. 
* En "Manage Devices", selecciona el dispositivo y ajusta la frecuencia de muestreo, los sensores activos y algoritmos. 
* Usa la opción "Write Config" para guardar la configuración. 

### *3.9.6 Colocación de Sensores*
1. Electrodos GSR: 
* Coloca un electrodo en la falange medial y otro en la falange distal de los dedos índice y medio. 
* Ajusta con el velcro.

<div align="center">
  <img src="https://github.com/neuropucp/lab-book/blob/main/book/res/manualEDA_Posicionamiento_de_electrodos.png" alt="Localización de electrodos ECG" width="auto" height="auto">
  <p><em><strong> Figura 1 </strong>Ejemplo de posicionamiento 	de los electrodos del GSR+</em></p>
</div>
 
2. Sensor de pulso óptico: 
* Colócalo en la parte inferior del lóbulo de la oreja para minimizar interferencias. 

### *3.9.7 Registro de Datos*
1. Presiona el botón naranja en el Shimmer para comenzar a grabar.
2. Verifica que la luz verde esté intermitente. 
3. Para detener el registro, presiona nuevamente el botón naranja. 

<div align="center">
  <img src="https://github.com/neuropucp/lab-book/blob/main/book/res/manualEDA_Venta_de_intruscciones.png" alt="Localización de electrodos ECG" width="auto" height="auto">
  <p><em><strong> Figura 2 </strong>Ventana con instrucciones para el registro de datos.</em></p>
</div>

8. Visualización de Datos 
	1. Accede a la pestaña "Live Data" en ConsensysPRO. 
	2. Haz clic en "Stream" para visualizar las señales en tiempo real. 
	3. Personaliza los gráficos: 
	* Selecciona los datos a visualizar. 
	* Configura los ejes y colores según tus preferencias. 
	
<div align="center">
  <img src="https://github.com/neuropucp/lab-book/blob/main/book/res/manualEDA_Visualiación_de_data.png" alt="Localización de electrodos ECG" width="auto" height="auto">
  <p><em><strong> Figura 3 </strong>Visualización de la data en vivo.</em></p>
</div>

### *__3.9.8. Resolución de Problemas__*
* El dispositivo no se conecta: 
	* Revisa que los drivers estén correctamente instalados. 
	* Asegúrate de que el Bluetooth está activado. 
* Datos inconsistentes: 
	* Verifica que los electrodos estén bien ajustados. 
	* Aplica un filtro pasa-bajos para eliminar ruido. 

### *__3.9.9. Mantenimiento del Equipo__*
* Limpia los electrodos con un paño húmedo y desinfecta después de cada uso. 
* Almacena el dispositivo en un lugar seco y protegido de la luz solar. 
* Carga la batería antes de guardarlo por períodos prolongados.

### __3.10. Referencias Bibliográficas__

Shimmer Sensing. (n.d.). Shimmer3 GSR+ User Manual. Recuperado de: https://shimmersensing.com 

Lüken, M., Misgeld, B. J. E., & Rüschen, D. (2015). Multi-sensor calibration of low-cost magnetic, angular rate and gravity systems. Sensors, 15(10), 25919-25936. https://doi.org/10.3390/s151025919 

Varshney, N. (2021). Combining electrocardiogram signal with accelerometer signals for human activity recognition using convolution neural network. Journal of Physics Conference Series, 1947(1), 012037. https://doi.org/10.1088/1742-6596/1947/1/012037 
