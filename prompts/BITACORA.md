# Bitacora de prompts

Laboratorio 06: Fundamentos de Ingenieria de Prompts.

Herramienta de IA usada: ChatGPT

## Ejercicio 2: Tokens y ventana de contexto
| Texto | Caracteres | Tokens |
|-------|------------|--------|
| Los estudiantes programan en Java. | 34 | 7 |
| The students program in Java. | 29 | 6 |
| desafortunadamente | 18 | 4 |

En la primera parte el chat recordó que mi aplicación se llamaba TiendaTec y que usaba Java Swing porque ya le había dado esa información.

Al abrir un chat nuevo también recordó esos datos lo que indica que la función de memoria de la herramienta puede conservar información entre conversaciones.
## Ejercicio 3: Temperatura

| Temperatura | % de BiblioTec | Nombres en los 5 intentos |
|-------------|----------------|---------------------------|
| 0 | 100.0% | BiblioTec, BiblioTec, BiblioTec, BiblioTec, BiblioTec |
| 0.5 | 65.3% | BiblioTec, BiblioTec, BiblioTec, BiblioTec, BiblioTec |
| 1 | 44.5% | LibroYa, LibroYa, BiblioTec, LibroYa, BiblioTec |
| 1.8 | 32.2% | PrestaLibro, PaginaLibre, LibroYa, PrestaLibro, LectoGo |

Al subir la temperatura, los nombres comenzaron a variar más y BiblioTec dejó de aparecer siempre.
El simulador no inventa nombres nuevos porque solo puede elegir entre los nombres que ya están definidos en la lista.
## Ejercicio 4: Prompt vago vs estructurado
| Criterio | Prompt vago | Prompt estructurado |
|----------|-------------|---------------------|
| Menciona el objetivo del sistema | No | Sí |
| Menciona a los usuarios principales | Sí | Sí |
| Tiene exactamente 3 funcionalidades | No | Sí |
| Está en 3 párrafos | No | Sí |
| Lo usaría en un informe real | No | Sí |

## Ejercicio 5: Anatomia de un prompt

### Componentes del prompt final

| Componente | Texto de mi prompt |
|------------|--------------------|
| Rol | Actua como desarrollador Java. |
| Instruccion | Crea un programa en Java usando una clase Producto con los atributos codigo, nombre, precio y stock. |
| Contexto | El programa es para gestionar los productos de una tienda. |
| Ejemplo | Usa este estilo para los metodos: getPrecio(), setPrecio(double precio). |
| Formato | Explica primero la estructura de la clase y luego presenta el codigo Java. |

### Cambios observados

- Nivel 1: La IA no sabia que programar y me pidio mas informacion.
- Nivel 2: Aunque le indique que actue como desarrollador Java todavia me pidio mas informacion.
- Nivel 3: La respuesta mejoro porque ya sabia que el programa era para los productos de una tienda.
- Nivel 4: La IA ya creo el programa usando la clase Producto y los datos que le indique.
- Nivel 5: La respuesta salio mas ordenada, primero explico la clase y despues mostro el codigo.
- Con ejemplo: Los metodos salieron con el estilo que le indique, como getPrecio() y setPrecio(double precio).

## Ejercicio 6: Del prompt basico al profesional

| Que revisar | Cumple |
|-------------|--------|
| ¿Esta escrito en Java y usa Swing? | Si |
| ¿Pide correo y contraseña? | Si |
| ¿Explica el funcionamiento antes o despues del codigo? | Si |
| ¿El codigo esta organizado en clases? | Si |
| ¿Valida los datos que ingresa el usuario? | No |

### Prompt final

```text
Actua como desarrollador Java. Crea un ejemplo de login para una
aplicacion de escritorio utilizando Swing. El usuario debe ingresar
correo y contrasena. Explica brevemente el funcionamiento y presenta
el codigo organizado por clases.

Mejora el codigo anterior con estas restricciones: no uses librerias
externas, valida que el correo contenga @ y que la contrasena tenga
al menos 8 caracteres, y muestra los mensajes con JOptionPane.