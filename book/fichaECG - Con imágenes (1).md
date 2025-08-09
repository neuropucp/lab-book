# FICHA ECG PRUEBA 1
## 2.7. Ficha Técnica del Shimmer3 ECG
### 2.7.1. Introducción Shimmer3 ECG Unit 
El *Shimmer3 ECG Unit* (ECG) pertenece a la familia de dispositivos *Shimmer*, utilizados en el monitoreo de mediciones fisiológicas. 
### 2.7.2. Descripción General 
El Shimmer3 ECG Unit es un dispositivo inalámbrico de monitoreo fisiológico diseñado para medir señales eléctricas del corazón (ECG). Este equipo utiliza sensores y electrodos desechables para registrar la actividad cardíaca en sujetos tanto en reposo como durante movimiento, y proporciona información sobre la respuesta del corazón ante la actividad física. 
### 2.7.3. Componentes Principales 
*__Componentes del Shimmer3:__* 

* __Cable de poder:__ Para conectar al estabilizador y alimentar el equipo. 
* __Estabilizador:__ Conecta el equipo a la fuente de corriente. 
* __Base del Shimmer3:__ Enchufe principal para la conexión con la computadora. 
* __Cable USB:__ Para conectar el dispositivo a la computadora. 
* __Unidad Shimmer3 ECG:__ Sensores para la adquisición de señales ECG. 
* __Electrodos desechables ECG:__ Para la medición de señales eléctricas del corazón. 
* __Correa:__ Para posicionar los sensores en el cuerpo del paciente. 

**_Componentes del Equipo ECG:_** 
    
* 5 cables biofísicos. 
* Electrodos desechables (4 de referencia y 1 para medición). 
* Sensor de ECG Shimmer3. 
### 2.7.4. Características Técnicas 
*__Hardware:__* 
* __Microprocesador:__ MSP430F5437A, bajo consumo. 
* __Convertidor Analógico-Digital (ADC):__ 16 canales, 12 bits, para capturar datos de sensores. 
* __Puerto microSD:__ Para almacenamiento adicional. 
* __Bluetooth:__ Módulo RN-42 (2.4GHz, clase 2, rango > 10 metros). 
* __Batería:__ Batería de litio recargable de 3.7V, 450mAh (duración entre 1 a 14 días dependiendo del uso).
* __Otros componentes:__ 5 LEDs, interruptor de encendido y botón configurable por software. 

*__Software:__* 
* __ConsensysPro:__ Para configuración de parámetros, adquisición y transmisión de datos. 
* __Bluetooth:__ Para transmitir datos en vivo al programa ConsensysPro.
### 2.7.5. Medidas de Bioseguridad
* Uso de equipo de protección personal (EPP), como guantes y batas. 
* Limpieza de la piel con agua destilada antes de aplicar los electrodos. 
* Evitar exposición al calor excesivo o llamas abiertas. 
* Mantener alejado de menores de edad. 
### 2.7.6. Funciones y Configuración 
*__ECG:__* 
* __Derivaciones Bipolares:__ 
	* Lead 1 (LA-RA): Desde brazo izquierdo a derecho. 
	* Lead 2 (LL-RA): Desde pierna izquierda a brazo derecho. 
	* Lead 3 (LL-LA): Desde pierna izquierda a brazo izquierdo. 
* __Derivaciones Unipolares:__ 
	* Vx (V1, V2, V3, V4, V5, V6): Posición en el pecho sobre la región del corazón. 
* __Configuración:__ 
	* __Frecuencia de Muestreo:__ 512 Hz (recomendado para ensayos clínicos). 
	* __Cables:__ Se recomienda usar cables cortos para minimizar interferencias.
* __Localización de electrodos:__

```{figure} https://github.com/neuropucp/lab-book/blob/main/book/res/manualECG_Localizacion_de_electrodos.png
---
scale: 100%
align: center
---
*Localización anatómica de los electrodos ECG en configuraciones de 9 y 18 leads. Elaboración propia (imagen previamente presentada en la Figura 1).*
```


### 2.7.7. Parámetros Técnicos 
* __Frecuencia de Muestreo:__ 512 Hz (para reposo), hasta 1024 Hz (para movimiento).
* __Tensión de Entrada:__ Asegurar que la batería esté cargada adecuadamente (3.7V, 450mAh). 
* __Almacenamiento:__ Tarjetas microSD con capacidad SPI.
 
### 2.7.8. Recomendaciones para Buenas Prácticas 
* __Preparación de la piel:__ Limpiar la zona donde se aplicarán los electrodos. 
* __Ubicación de los electrodos:__ Colocarlos en zonas con poca o sin vello y asegurarse de que estén correctamente conectados. 
* __Uso de cables:__ Utilizar cables cortos para reducir la interferencia y mejorar la calidad de la señal. 
### 2.7.9. Uso del Software 
**Instalación y Configuración:**
* __Drivers:__ Descargar los controladores desde el sitio web oficial de Shimmer. 
* __ConsensysPro:__ Descargar e instalar el software para configurar y registrar las señales. 
* __Bluetooth:__ Asegurar que el dispositivo cuente con Bluetooth, de lo contrario, adquirir un adaptador USB.

**Visualización de Datos en Vivo:**
* Usar el botón "Live Data" para visualizar las señales ECG en tiempo real. 
* Se pueden personalizar las visualizaciones de los datos (número de plots, color, unidades de tiempo y voltaje).

### 2.7.10. Referencias Bibliográficas 
Ahmed, M.U., & Begum, S. (2010). Heart Rate and Inter-beat Interval  Computation to Diagnose Stress Using ECG Sensor Signal.

Bossaerts, P., Fattinger, F., Rotaru, K., & Xu, K. (2024). Emotional engagement  and trading performance. 

Heyat, B. M., & Siddiqui, M. M. (2015). Recording of EEG, ECG, EMG Signal. 

Kligfield, P., et al. (2007). Recommendations for the standardization and  interpretation of the electrocardiogram.

