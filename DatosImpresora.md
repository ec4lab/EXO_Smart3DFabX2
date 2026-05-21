# Información del sistema actual

Existen diferentes maneras de obtener la info del sistema actual

## Manual de la impresora

|**CARACTERÍSTICAS**||
|---|---|
|Tecnología de Funcionamiento|Fused Deposition Modeling (FDM)|
|Resolución de Capas|hasta 50 micrones (0.05mm)|
|Velocidad|10 mm/s – 100mm/s|
|Extrusores|2 metálico y modular, de sencillo montaje|
|Dimensiones externas|460 / 520 / 510 mm|
|Volumen de impresión (X, Y, Z)|210 x 210 x 220 mm|
|Precisión posicionamiento X / Y / Z|10 / 10 / 5 micrones|
|Fines de carrera|5 más 1 sensor inductivo|
|Diámetro Boquillas|0.4 mm (Intercambiables)|
|Tipos de Filamento|1.75 mm estándar|
|Cama de impresión|Aluminio|
|Nivelación de cama|Automático|
|Temperatura de operación Boquilla|150° C – 300° C|
|Conectividad|WiFi 802.11n, Lan Fast Ethernet, USB-B|
|Cámara interna|Imágenes: HD 5MP a 2592×1944p|
|Video|Full HD 1080p30, 720p60, 640x480p|
|Pantalla de visualización|Color 7” (800*600) táctil multi touch|
|Plataforma|Arduino Mega 2560|
|Computador interno|Raspberry Pi 3 Modelo “B” versión 1.2|
|Procesador|BCM 2837 ARMv8 Cortex A53 Quad-Core 64-Bit 1.2GHz|
|Videocore|IV 3D Dual Core GPU / 1GB de RAM|
|Puertos|1 x USB 2.0 / 1 x Ethernet 10/100 Mbps RJ45|

Más  información en el [manual](EXO3DFAB_Manual.pdf)

## Sistema OctoPrint actual

La interfaz web nos da info de la versión  
`Version 1.3.4.post0.dev0+gfe481e1 (master branch)`

## Plugins Instalados

Es posible que muchos de estos plugins sean obsoletos, sin embargo los guardamos por si aparecen problemas:

* Action Comands
* Cost Plugin
* CuraEngine(<=15.04)
* Custom Background
* Custom Control Editor
* Firmware Updates
* Navbar Temperatura Plugin
* Network connection
* Octoprint Anywhere
* Print History Plugin
* Printer Stats
* TouchUI

## Información de Marlin

Desde la pestaña terminal podemos enviar ciertos comandos que nos devolverán información util del sistema, los que podremos utilizar luego de la instalación:

```bash
M105 # Comprobar conexión y ver sensores 
```

Recv: ok T:23.24 /0 B:24.10 /0 T0:23.24 /0 T1:23.83 /0 @:0 B@:0 @0:0 @1:0

```bash
M119 #Verificar EndStops
```

Recv: Reporting endstop status  
Recv: x_min: open  
Recv: x_max: open  
Recv: y_min: open  
Recv: y_max: open  
Recv: z_min: open  
Recv: z_max: open  
Recv: ok

```bash
G28 #Homing
```

Recv: echo:Active Extruder: 0  
Recv: echo:busy: processing  
Recv: echo:busy: processing  
Recv: echo:Active Extruder: 0  
Recv: X:130.00 Y:65.00 Z:10.00 E:0.00 Count A:15600 B:5200 Z:4000  
Recv: ok  
Recv: echo:endstops hit:  Z:26.00  

> [!TIP]  
> Para los próximos comandos tal vez sea buena idea evitar los mensajes de temperatura `[x] Suppress temperature messages` para evitar "ruido" en las salidas.

```bash
M115 # versión de Marlin, Compilación, Características.
```

Recv: FIRMWARE_NAME:Marlin 1.1.3 (EXO By TheraSoft) SOURCE_CODE_URL:<http://www.exo.com.ar> PROTOCOL_VERSION:1.0 MACHINE_TYPE:EXO SMART 3D FAB V0.8.1.12 20170824 PID BED 2 Hotend EXTRUDER_COUNT:2 UUID:cede2a2f-41a2-4748-9b12-c55c62f367ff
Recv: ok

```bash
M503 # Configuración actual de Marlin
```

Recv: echo:  G21    ; Units in mm  
Recv:  
Recv: echo:Filament settings: Disabled  
Recv: echo:  M200 D1.75  
Recv: echo:  M200 T1 D1.75  
Recv: echo:  M200 D0  
Recv: echo:Steps per unit:  
Recv: echo:  M92 X80.00 Y80.00 Z400.00 E100.00  
Recv: echo:Maximum feedrates (units/s):  
Recv: echo:  M203 X300.00 Y300.00 Z5.00 E25.00  
Recv: echo:Maximum Acceleration (units/s2):  
Recv: echo:  M201 X3000 Y3000 Z100 E10000  
Recv: echo:Acceleration (units/s2): P<print_accel> R<retract_accel> T<travel_accel>  
Recv: echo:  M204 P3000.00 R3000.00 T3000.00  
Recv: echo:Advanced: S<min_feedrate> T<min_travel_feedrate> B<min_segment_time_ms> X<max_xy_jerk> Z<max_z_jerk> E<max_e_jerk>  
Recv: echo:  M205 S0.00 T0.00 B20000 X20.00 Y20.00 Z0.40 E5.00  
Recv: echo:Home offset:  
Recv: echo:  M206 X0.00 Y0.00 Z0.00  
Recv: echo:Hotend offsets:  
Recv: echo:  M218 T1 X14.50 Y-1.50  
Recv: echo:Auto Bed Leveling:  
Recv: echo:  M420 S0 Z0.00  
Recv: echo:PID settings:  
Recv: echo:  M301 P22.20 I1.08 D114.00  
Recv: echo:Z-Probe Offset (mm):  
Recv: echo:  M851 Z0.00  
Recv: ok  

```bash
M500 # Información de la EEPROM
```

Recv: Error:EEPROM disabled
Changing monitoring state from 'Operational' to 'Error: EEPROM disabled\x0a'
Recv: ok

>[!NOTE]
> la EEPROM está desactivada en compilación, no se puede modificar desde OctoPrint, lo tendremos en cuenta si alguna vez actualizamos marlin en el Arduino Mega

```bash
M501 # Configuración de Marlin
```
```text
Recv: echo:Hardcoded Default Settings Loaded  
Recv: echo:  G21    ; Units in mm  
Recv:  
Recv: echo:Filament settings: Disabled  
Recv: echo:  M200 D1.75  
Recv: echo:  M200 T1 D1.75  
Recv: echo:  M200 D0  
Recv: echo:Steps per unit:  
Recv: echo:  M92 X80.00 Y80.00 Z400.00 E100.00  
Recv: echo:Maximum feedrates (units/s):  
Recv: echo:  M203 X300.00 Y300.00 Z5.00 E25.00  
Recv: echo:Maximum Acceleration (units/s2):  
Recv: echo:  M201 X3000 Y3000 Z100 E10000  
Recv: echo:Acceleration (units/s2): P<print_accel> R<retract_accel> T<travel_accel>  
Recv: echo:  M204 P3000.00 R3000.00 T3000.00  
Recv: echo:Advanced: S<min_feedrate> T<min_travel_feedrate> B<min_segment_time_ms> X<max_xy_jerk> Z<max_z_jerk> E<max_e_jerk>  
Recv: echo:  M205 S0.00 T0.00 B20000 X20.00 Y20.00 Z0.40 E5.00  
Recv: echo:Home offset:  
Recv: echo:  M206 X0.00 Y0.00 Z0.00  
Recv: echo:Hotend offsets:  
Recv: echo:  M218 T1 X14.50 Y-1.50  
Recv: echo:Auto Bed Leveling:  
Recv: echo:  M420 S0 Z0.00  
Recv: echo:PID settings:  
Recv: echo:  M301 P22.20 I1.08 D114.00  
Recv: echo:Z-Probe Offset (mm):  
Recv: echo:  M851 Z0.00  
Recv: ok  
```

## información desde APIS

Fuente: <https://docs.octoprint.org/en/main/events/index.html>

En la interfaz web ir a: ################## y obtener la API KEY

Luego:

```http
http://10.1.6.2/api/version?apikey=COLOCAR_ACA_EL_APIKEY
```

{  
  "api": "0.1",  
  "server": "1.3.4.post0.dev0+gfe481e1"  
}  

```web
http://10.1.6.2/api/connection?apikey=COLOCAR_ACA_EL_APIKEY
```

{  
  "current": {  
    "baudrate": 115200,  
    "port": "/dev/ttyUSB0",  
    "printerProfile": "_default",  
    "state": "Operational"  
  },  
  "options": {  
    "baudratePreference": 115200,  
    "baudrates": [  
      115200,  
      250000,  
      230400,  
      57600,  
      38400,  
      19200,  
      9600  
    ],  
    "portPreference": "/dev/ttyUSB0",  
    "ports": [  
      "/dev/ttyUSB0"  
    ],  
    "printerProfilePreference": "_default",  
    "printerProfiles": [  
      {  
        "id": "_default",  
        "name": "Default"  
      },  
      {  
        "id": "_default2",  
        "name": "EXO"  
      }  
    ]  
  }  
}  

```web
http://10.1.6.2/api/printer?apikey=COLOCAR_ACA_EL_APIKEY
```

{  
  "sd": {  
    "ready": false  
  },  
  "state": {  
    "flags": {  
      "closedOrError": false,  
      "error": false,  
      "operational": true,  
      "paused": false,  
      "printing": false,  
      "ready": true,  
      "sdReady": false  
    },  
    "text": "Operational"  
  },  
  "temperature": {  
    "bed": {  
      "actual": 24.37,  
      "offset": 0,  
      "target": 0.0  
    },  
    "tool0": {  
      "actual": 23.48,  
      "offset": 0,  
      "target": 0.0  
    },  
    "tool1": {  
      "actual": 24.06,  
      "offset": 0,  
      "target": 0.0  
    }  
  }  
}  

```web
http://10.1.6.2/api/settings?apikey=COLOCAR_ACA_EL_APIKEY
```

{  
  "api": {  
    "allowCrossOrigin": false,  
    "enabled": true,  
    "key": "###############################3"  
  },  
  "appearance": {  
    "color": "red",  
    "colorTransparent": false,  
    "defaultLanguage": "es",  
    "name": "EXO Smart 3D - 001",  
    "showFahrenheitAlso": false  
  },  
  "feature": {  
    "alwaysSendChecksum": false,  
    "blockWhileDwelling": false,  
    "externalHeatupDetection": true,  
    "firmwareDetection": true,  
    "g90InfluencesExtruder": false,  
    "gcodeViewer": true,  
    "ignoreIdenticalResends": false,  
    "keyboardControl": true,  
    "mobileSizeThreshold": 2097152,  
    "modelSizeDetection": true,  
    "neverSendChecksum": false,  
    "pollWatched": false,  
    "printCancelConfirmation": true,  
    "repetierTargetTemp": false,  
    "sdAlwaysAvailable": false,  
    "sdRelativePath": false,  
    "sdSupport": true,  
    "sizeThreshold": 20971520,  
    "swallowOkAfterResend": true,  
    "temperatureGraph": true,  
    "waitForStart": false  
  },  
  "folder": {  
    "logs": "/home/pi/.octoprint/logs",  
    "timelapse": "/home/pi/.octoprint/timelapse",  
    "timelapseTmp": "/home/pi/.octoprint/timelapse/tmp",  
    "uploads": "/home/pi/.octoprint/uploads",  
    "watched": "/home/pi/.octoprint/watched"  
  },  
  "plugins": {  
    "actioncommands": {  
      "command_definitions": []  
    },  
    "announcements": {  
      "channel_order": [  
        "_important",  
        "_releases",  
        "_blog",  
        "_plugins",  
        "_octopi"  
      ],  
      "channels": {  
        "_blog": {  
          "description": "Development news, community spotlights,  
          OctoPrint On Air episodes and more from the official  OctoBlog.",  
          "name": "On the OctoBlog",  
          "priority": 2,  
          "read_until": 1770891780,  
          "type": "rss",  
          "url": <http://octoprint.org/feeds/octoblog.xml>  
        },  
        "_important": {  
          "description": "Important announcements about OctoPrint.",  
          "name": "Important Announcements",  
          "priority": 1,  
          "read_until": 1698310200,  
          "type": "rss",  
          "url": <http://octoprint.org/feeds/important.xml>  
        },  
        "_octopi": {  
          "description": "News around OctoPi, the Raspberry Pi image  
          including OctoPrint.",  
          "name": "OctoPi News",  
          "priority": 2,  
          "read_until": 1746515700,  
          "type": "rss",  
          "url": <http://octoprint.org/feeds/octopi.xml>  
        },  
        "_plugins": {  
          "description": "Announcements of new plugins released on  
          the official Plugin Repository.",  
          "name": "New Plugins in the Repository",  
          "priority": 2,  
          "read_until": 1771545600,  
          "type": "rss",  
          "url": <http://plugins.octoprint.org/feed.xml>  
        },  
        "_releases": {  
          "description": "Announcements of new releases and release  
          andidates of OctoPrint.",  
          "name": "Release Announcements",  
          "priority": 2,  
          "read_until": 1771420200,  
          "type": <http://octoprint.org/feeds/releases.xml>  
        }  
      },  
      "display_limit": 3,  
      "enabled_channels": [  
        "_octopi",  
        "_plugins",  
        "_releases",  
        "_important",  
        "_blog"  
      ],  
      "forced_channels": [  
        "_important"  
      ],  
      "summary_limit": 300,  
      "ttl": 360  
    },  
    "cost": {  
      "cost_per_length": 0.08,  
      "cost_per_time": "10000",  
      "cost_per_weight": "18000",  
      "currency": "$",  
      "density_of_filament": 1.25,  
      "length": "m",  
      "time": "h",  
      "weight": "kg"  
    },  
    "cura": {  
      "cura_engine": "/usr/local/bin/cura_engine",  
      "debug_logging": false,  
      "default_profile": null  
    },  
    "customControl": {  
      "controls": []  
    },  
    "custombackground": {  
      "axes_text_color": "",  
      "background_url": "/plugin/custombackground/custom/uploaded.png",  
      "customFillSize": "50%",  
      "fillMethod": "contain",  
      "icon_url": "/static/img/tentacle-20x20.png",  
      "position": "center center",  
      "temp_line_colors": "",  
      "tick_color": "",  
      "uploaded_url": "/plugin/custombackground/custom/uploaded.png"  
    },  
    "discovery": {  
      "httpPassword": null,  
      "httpUsername": null,  
      "model": {  
        "description": null,  
        "name": null,  
        "number": null,  
        "serial": null,  
        "url": null,  
        "vendor": null,  
        "vendorUrl": null  
      },  
      "pathPrefix": null,  
      "publicHost": null,  
      "publicPort": 80,  
      "upnpUuid": "00e46e46-bb04-4d6f-9803-eb0d16c4e332",  
      "zeroConf": []  
    },  
    "firmwareupdater": {  
      "avrdude_path": "/usr/bin/avrdude",  
      "check_after_connect": true,  
      "update_service_url": <http://devices.bq.com/api/checkUpdate3D/>  
      {model}/{language}/{version}"  
    },  
    "navbartemp": {  
      "cmd": "",  
      "cmd_name": "",  
      "displayRaspiTemp": true,  
      "makeMoreRoom": false,  
      "piSocTypes": [  
        "BCM2708",  
        "BCM2709",  
        "BCM2835",  
        "BCM2711"  
      ],  
      "soc_name": "SoC",  
      "useShortNames": false  
    },  
    "netconnectd": {  
      "hostname": null,  
      "socket": "/var/run/netconnectd.sock",  
      "timeout": 10  
    },  
    "pluginmanager": {  
      "dependency_links": false,  
      "hidden": [],  
      "notices": <http://plugins.octoprint.org/notices.json>,  
      "notices_ttl": 360,  
      "pip_args": null,  
      "pip_force_user": false,  
      "repository": <http://plugins.octoprint.org/plugins.json>,  
      "repository_ttl": 1440  
    },  
    "printhistory": {  
      "spool_inventory": []  
    },  
    "softwareupdate": {  
      "cache_ttl": 1440,  
      "notify_users": true,  
      "octoprint_branch_mappings": [  
        {  
          "branch": "master",  
          "name": "Stable"  
        },  
        {  
          "branch": "rc/maintenance",  
          "name": "Maintenance RCs"  
        },  
        {  
          "branch": "rc/devel",  
          "name": "Devel RCs"  
        }  
      ],  
      "octoprint_checkout_folder": "/home/pi/OctoPrint",  
      "octoprint_method": "update_script",  
      "octoprint_release_channel": "master",  
      "octoprint_type": "github_release",  
      "pip_command": null  
    },  
    "stats": {  
      "eletronics": "11.3",  
      "hotend": "32.5",  
      "pcbheatbed": "98.5",  
      "steppermotors": "0.6"  
    },  
    "touchui": {  
      "automaticallyLoad": true,  
      "colors": {  
        "bgColor": "#111111",  
        "customPath": "",  
        "mainColor": "#AA0000",  
        "termColor": "#EEEEEE",  
        "textColor": "#FFFFFF",  
        "useLocalFile": false  
      },  
      "hasCustom": true,  
      "hasVisibleSettings": true,  
      "refreshCSS": false,  
      "requireNewCSS": false,  
      "useCustomization": true,  
      "whatsNew": false  
    }  
  },  
  "printer": {  
    "defaultExtrusionLength": 5  
  },  
  "scripts": {  
    "gcode": {  
      "afterPrintCancelled": "; disable motors\nM84\n\n;disable all heaters\n{% snippet 'disable_hotends' %}\n{% snippet 'disable_bed' %}\n;disable fan\nM106 S0",  
      "snippets/disable_bed": "{% if printer_profile.heatedBed %}M140 S0\n{% endif %}",  
      "snippets/disable_hotends": "{% for tool in range(printer_profile.extruder.count) %}M104 T{{ tool }} S0\n{% endfor %}"  
    }  
  },  
  "serial": {  
    "additionalBaudrates": [],  
    "additionalPorts": [],  
    "autoconnect": true,  
    "baudrate": 115200,  
    "baudrateOptions": [  
      115200,  
      250000,  
      230400,  
      57600,  
      38400,  
      19200,  
      9600  
    ],  
    "checksumRequiringCommands": [  
      "M110"  
    ],  
    "disconnectOnErrors": true,  
    "helloCommand": "M110 N0",  
    "ignoreErrorsFromFirmware": false,  
    "log": false,  
    "longRunningCommands": [  
      "G4",  
      "G28",  
      "G29",  
      "G30",  
      "G32",  
      "M400",  
      "M226",  
      "M600"  
    ],  
    "maxTimeoutsIdle": 2,  
    "maxTimeoutsLong": 5,  
    "maxTimeoutsPrinting": 5,  
    "port": "/dev/ttyUSB0",  
    "portOptions": [  
      "/dev/ttyUSB0"  
    ],  
    "supportResendsWithoutOk": false,  
    "timeoutCommunication": 30.0,  
    "timeoutConnection": 10.0,  
    "timeoutDetection": 0.5,  
    "timeoutSdStatus": 1.0,  
    "timeoutTemperature": 5.0,  
    "timeoutTemperatureTargetSet": 2.0,  
    "triggerOkForM29": true  
  },  
  "server": {  
    "commands": {  
      "serverRestartCommand": "sudo service octoprint restart",  
      "systemRestartCommand": "sudo shutdown -r now",  
      "systemShutdownCommand": "sudo shutdown -h now"  
    },  
    "diskspace": {  
      "critical": 209715200,  
      "warning": 524288000  
    }  
  },  
  "system": {  
    "actions": [],  
    "events": null  
  },  
  "temperature": {  
    "cutoff": 30,  
    "profiles": [  
      {  
        "bed": "90",  
        "extruder": "240",  
        "name": "ABS"  
      },  
      {  
        "bed": "40",  
        "extruder": "210",  
        "name": "PLA"  
      },  
      {  
        "bed": "50",  
        "extruder": "220",  
        "name": "HIPS"  
      },  
      {  
        "bed": "80",  
        "extruder": "250",  
        "name": "Nylon"  
      },  
      {  
        "bed": "60",  
        "extruder": "200",  
        "name": "Flex"  
      }  
    ]  
  },  
  "terminalFilters": [  
    {  
      "name": "Suppress temperature messages",  
      "regex": "(Send: (N\\d+\\s+)?M105)|(Recv: ok (B|T\\d*):)"  
    },  
    {  
      "name": "Suppress SD status messages",  
      "regex": "(Send: (N\\d+\\s+)?M27)|(Recv: SD printing byte)"  
    },  
    {  
      "name": "Suppress wait responses",  
      "regex": "Recv: wait"  
    }  
  ],  
  "webcam": {  
    "bitrate": "5000k",  
    "ffmpegPath": "/usr/bin/avconv",  
    "ffmpegThreads": 1,  
    "flipH": true,  
    "flipV": true,  
    "rotate90": false,  
    "snapshotUrl": <http://127.0.0.1:8080/?action=snapshot>,  
    "streamRatio": "4:3",  
    "streamUrl": "/webcam/?action=stream",  
    "watermark": false  
  }  
}  

```web
http://10.1.6.2/api/files?apikey=COLOCAR_ACA_EL_APIKEY
```

Da un listado de todos los archivos cargados en la memoria, no es relevante en este momento.

```web
http://10.1.6.2/api/printerprofiles?apikey=COLOCAR_ACA_EL_APIKEY
```

{  
  "profiles": {  
    "_default": {  
      "axes": {  
        "e": {  
          "inverted": false,  
          "speed": 300  
        },  
        "x": {  
          "inverted": false,  
          "speed": 6000  
        },  
        "y": {  
          "inverted": false,  
          "speed": 6000  
        },  
        "z": {  
          "inverted": false,  
          "speed": 200  
        }  
      },  
      "color": "default",  
      "current": true,  
      "default": true,  
      "extruder": {  
        "count": 2,  
        "nozzleDiameter": 0.4,  
        "offsets": [  
          [  
            0.0,  
            0.0  
          ],  
          [  
            0.0,  
            0.0  
          ]  
        ],  
        "sharedNozzle": false  
      },  
      "heatedBed": true,  
      "id": "_default",  
      "model": "Generic RepRap Printer",  
      "name": "Default",  
      "resource": <http://10.1.6.2/api/printerprofiles/_default>,  
      "volume": {  
        "custom_box": false,  
        "depth": 220.0,  
        "formFactor": "rectangular",  
        "height": 200.0,  
        "origin": "lowerleft",  
        "width": 220.0  
      }  
    },  
    "_default2": {  
      "axes": {  
        "e": {  
          "inverted": false,  
          "speed": 300  
        },  
        "x": {  
          "inverted": false,  
          "speed": 6000  
        },  
        "y": {  
          "inverted": false,  
          "speed": 6000  
        },  
        "z": {  
          "inverted": true,  
          "speed": 200  
        }  
      },  
      "color": "default",  
      "current": false,  
      "default": false,  
      "extruder": {  
        "count": 2,  
        "nozzleDiameter": 0.4, 
        "offsets": [  
          [  
            0.0,  
            0.0  
          ],  
          [  
            0.0,  
            0.0  
          ]  
        ],  
        "sharedNozzle": false  
      },  
      "heatedBed": true,  
      "id": "_default2",  
      "model": "EXO Smart 3DFab X2",  
      "name": "EXO",  
      "resource": <http://10.1.6.2/api/printerprofiles/_default2>,  
      "volume": {  
        "custom_box": false,  
        "depth": 220.0,  
        "formFactor": "rectangular",  
        "height": 200.0,  
        "origin": "lowerleft",  
        "width": 278.0  
      }  
    }  
  }  
}  

## Clonado de la tarjeta SD original

Por seguridad se hizo un clonado de la tarjeta original con el S.O. y su configuración.

Con la tarjeta en la computadora, identificar donde está conectada:

```bash
lsblk
```

identificamos el disco

```text
mmcblk0     179:0    0   3,7G  0 disk 
├─mmcblk0p1 179:1    0  39,2M  0 part /media/exo/boot
└─mmcblk0p2 179:2    0   3,7G  0 part /media/exo/734d7a6d-e6b2-4d91-8978-192f695c8e5e
```

primero desmontar

```bash
sudo umount /dev/mmcblk0p1
sudo umount /dev/mmcblk0p2
```

y luego clonar s

```bash
sudo dd if=/dev/mmcblk0 of=~/backup_octopi.img bs=4M status=progress
```

* `if` → input (la SD)
* `of` → archivo de salida
* `bs=4M` → más rápido
* `status=progress` → muestra avance

chequear la imagen

```bash
fdisk -l ~/backup_octopi.img
```

Comprimir la imagen

```bash
gzip ~/backup_octopi.img
```

Restaurar (si es necesario)

```bash
gunzip backup_octopi.img.gz
```

```bash
sudo dd if=backup_octopi.img of=/dev/sdX bs=4M status=progress
# cambiar sdX por la dirección correcta (lsblk)
```

También es posible montar la `.img`sin necesidad de grabarla en una sd

```bash
udisksctl loop-setup -f ~/backup_octopi.img
```
