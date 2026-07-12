# Ejemplos de comandos G-Code

El G-Code es básicamente una lista de instrucciones "paso a paso" para un robot.

Las instrucciones se dividen principalmente en dos:

* G (Geometría): Movimientos y coordenadas.
* M (Misceláneos): Funciones de la máquina (ventiladores, motores, temperaturas).
* F (Velocidad): mm/minuto.

## Home

```gcode
G28 ; Home en los tres ejes
```

```gcode
G28 X Y ; Home en X e Y (Esquina delantera izquierda)
```

```gcode
G28 Z ;Home en Z
```

## Movimientos

```gcode
G91     ;Modo relativo
```

```gcode
G1 X50 F3000 ;Se mueve 50mm a la derecha
```

```gcode
G90 ;Modo Absoluto
```

```gcode
G1 X50 F3000 ; Se mueve al punto X=50
```

```gcode
G1 X50 Y50 F3000 ; ir a (X=50, Y=50)
```

```gcode
G1 X150 Y150 F3000 ; ir a (X=150, Y=150)
```

```gcode
M122 ; Estado de motores y sensores
```

```gcode
M106 P0 S150 ; Encender fan 1 a 150/255
```

```gcode
M106 P1 S250 ; Encender fan 2 a 255/255 
```

## Control de temperaturas

```gcode
M104 S200 ; Encender Pico seleccionado a 200
```

```gcode
M104 P1 S200 ; Encender segundo HotEnd a 200
```

```gcode
M104 S0 ; Apaga el Hotend (Extrusor)
```

```gcode
M140 S0 ; Apaga la Cama caliente (Bandeja)
```

```gcode
M107    ; Apaga el ventilador de capa
```

```gcode
M84     ; Apaga los motores (los deja "sueltos")
```

## Filamento

```gcode
G92 E0          ; Resetea el contador del extrusor a 0
```

```gcode
G1 E10 F200     ; Empuja 10mm de filamento a una velocidad de 200 mm/min
```

```gcode
G1 X100 Y100 E5 F1200 ; Se mueve al punto (100,100) soltando 5mm de filamento
```
