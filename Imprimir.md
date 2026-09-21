# Parámetros Básicos de impresión

## ORCA Slicer

> [!IMPORTANT]  
> Los parámetros indicados aquí son los de una configuración básica después de algunas pruebas, son un buen punto de partida, pero es muy probable que no sean los óptimos, si descubres un error o mejora, no dudes en contactarnos.

### Parámetros de la Impresora

* A partir de una `Custom FFF Printer`
* Switch de avanzado: Posición 2
* Los parámetros que no se indican, dejarlos con el valor por defecto.  

|Parámetro|Valor Recomendado|Notas|
|---|---|---|
|**Basic Information**|||
|Printable area|200x200||
|Origin|x=0,y=o||
|Support multi bed types|No||
|Z offset|0 mm||
|G-code flavor|Marlin(legacy)||
|**Multimaterial**|||
|Extruders|2||
|**Extruder 1**|||
|Nozzle diameter|0.4 mm||
|Layer height limits|0.08-0.32 mm||
|Extruder offset|X=0,Y=0|Corrige la impresora|
|Retraction length|4.0 mm|con 6 funciona mejor, pero trae problemas en el extrusor|
|**Extruder 2**|||
|Nozzle diameter|0.4 mm||
|Layer height limits|0.08-0.32 mm||
|Extruder offset|X=0,Y=0|Corrige la impresora|
|Retraction length|4.0 mm|con 6 funciona mejor, pero trae problemas en el extrusor|
|**Motion ability**|||
|Emit limits to G-code|Yes||
|Maximum speed X|120 mm/s||
|Maximum speed Y|120 mm/s||
|Maximum speed Z|10 mm/s||
|Maximum speed E|60 mm/s||
|Maximum acceleration X|10000 mm/s2||
|Maximum acceleration Y|10000 mm/s2||
|Maximum acceleration Z|500 mm/s2||
|Maximum acceleration E|5000 mm/s2||
|Maximum acceleration for extruding|10000 mm/s2||
|Maximum acceleration for retracting|1000 mm/s2||
|Maximum Jerk X|9 mm/s2||
|Maximum Jerk Y|9 mm/s2||
|Maximum Jerk Z|5 mm/s2||
|Maximum Jerk E|5 mm/s2||

### Parámetros del Proceso

* Switch de avanzado: Posición 2
* Los parámetros que no se indican, dejarlos con el valor por defecto.  

|Parámetro|Valor Recomendado|Notas|
|---|---|---|
|**Quality**|||
|Layer height|0.15 mm|0.20,0.22 para mayor velocidad|
|First layer height|0.28 mm||
|Line width default|0.4||
|Line width first layer|0.5||
|Top surface flow ratio|0.98||
|First Layer flow Ratio|1.1||
|**Strength**|||
|Wall loops|2||
|Top shell layers|4||
|Top surface pattern|Monotonic|`Hilbert Curve` para textura rugosa|
|Bottom surface pattern|Monotonic line|`Concentric` si la base es grande|
|Sparse infill density|15 %|Probado hasta 25% sin problemas|
|**Speed**|||
|First layer|40 mm/s||
|Number of slow layers|2||
|Outer wall|60 mm/s||
|Inner wall|90 mm/s||
|Small perimeters|50%||
|Sparse infill|100 mm/s||
|Internal solid infill|100 mm/s||
|Top surface|60 mm/s||
|Gap infill|100 mm/s||
|Support|120 mm/s||
|Support interface|80 mm/s||
|Travel speed|120 mm/s||
|Acceleration|||
|Normal printing|1500 mm/s2||
|Outer wall|800 mm/s2||
|Inner wall|1500 mm/s2||
|Top surface|800 mm/s2||
|Travel|200 mm/s2||
|Jerk (XY)|||
|Default|8 mm/s||
|Outer wall|7 mm/s||
|Inner wall|8 mm/s||
|Infill|8 mm/s||
|Top surface|7 mm/s||
|First Layer|8 mm/s||
|Travel|9 mm/s||
|**Support**|||
|Activar y configurar cuando corresponda|||
|**Multimaterial**|||
|Valores por defecto|||
|**Others**|||
|Skirt|||
|Skirt loops|2|3-4 si la pieza es pequeña|
|Skirt type|Combined||
|Skirt distance|20 mm||
|Skirt speed|50 mm/s||
|Brim|||
|Brim type|Outer only|En piezas con base pequeña, sino `No-Brim`|
|Brim width|5 mm|Ajustar a criterio|

### Parámetros del Filamento

* Switch de avanzado: Posición 2
* Los parámetros que no se indican, dejarlos con el valor por defecto.  

|Parámetro|Valor Recomendado|Notas|
|---|---|---|
|**Filament**|||
|Type|PLA||
|Vendor|Generic||
|Diameter|1.75 mm||
|Flow ratio|1||
|Pressure advance|Off|La impresora no corrige pressure advance|
|Print temperature|||
|Nozzle First Layer|210 ºC||
|Nozzle First Other Layers|205 ºC||
|Bed First Layer|65 ºC||
|Bed First Other Layers|50 ºC||
|Max Volumetric speed|12 mm3/s||
|**Cooling**|||
|No cooling for the first|2 layer||
|Full fan speed at layer|4||
|Min fan speed|70% Layer time 100s||
|Max fan speed|70% Layer time 4s|VER, fan al 100% puede traer problemas de caída de temperatura en el extrusor|
|**Setting Overrides**|||
|Retraction Length|4 mm|hasta 6 mm|
|Resto por defecto|||

## Ultimaker Cura

Valores similares a los de ORCA

### Thumbnails en los gcodes

* Extensions
  * Post-processing
    * Modify G-code  
Agregar el script "Create thumbnails"  
Resolution por lo menos a 300x300px  
A parti de ahora, con cada slice, se creará en la parte superior del G-Code el thumbnail de la pieza a imprimir.
