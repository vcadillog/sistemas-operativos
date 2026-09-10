# Proceso
- Programa fuente: Colección de instrucciones para ejecutar una tarea que se guarda en una carpeta.
- Programa ejecutable: Es el resultado de compilar el programa fuente, se guarda con el nombre que suele ser el mismo del programa. Ej ls
- Proceso: Es una abstracción que hace referencia a la ejecución de un programa ejecutable.

# Tipos de procesos
## Según su diseño:
- Reutilizables: Se cargan en memoria cada vez que se usan.
- Reentrantes: Se carga una sola copia de código en memoria.

## Según su acceso a CPU y recursos:
- Apropiativo
- No apropiativo

## Según su permanencia en memoria:
- Residentes: Permanecen en la memoria.
- Intercambiables (swappables): El SO decide llevarlo a disco.

## Según su nivel de privilego:
- Privilegiado: Se ejecuta modo supervisor
- No privilegiado

## Según su propietario:
- Procesos de usuario: Diseñado por el usuario. No usan permisos.
- Procesos del sistema: 

# Estructura de datos:

- Carga el codigo en memoria
- Un mismo programa puede originar varios procesos
- Si no se ejecuta necesita guardar información de ejecución (BCP), usando:
BCP: Bloque de control de procesos (PCB)
- Stack, queue, heap, list, registros (información de una instrucción para ejecutarse en CPU).

# SCB: Bloque de control del sistema
Es un conjunto de datos que usa el SO para la ejecución de todos los procesos.
Incluye:
- Lista de descriptores de procesos.
- Puntero al descriptor del procesos que usa CPU.

Las Interrupciones permiten al SO tomar el control del CPU.
Ejm: 
- Sucede un error
- Evento externo, finalizacion I/O
- Reloj
El SO usa la información del SCB para seleccionar la secuencia de procesos a ejecutar.

## PCB incluye:
- Identificación:
- Planificación:

## Mapa de memoria de un proceso:
Se divide en bloques, una posible forma:
- Código
- Datos con valor inicial
- Datos sin valor inicial
- Archivos proyectados
- Pila (datos de funciones)
- Heap

# Vida de un proceso

## Creación de un proceso
- El código ejecutable se ubica en la RAM, el SO:
1. Asigna un identificador.
2. Crea e inicializa su PCB
3. Actualiza el SCB.
4. 

Procesos de primer plano: Interactua con el usuario.
Procesos en segundo plano: Están a la espera a ser ejecutados , daemons.

Creación de un proceso en UNIX
Se crea una jerarquía (árbol) de dos  formas:
- Fork: El hijo es un clon del proceso padre, copia todo: contador de programa, valor de variables, estado de pila, etc.
- Exec: Elimina al programa que lo llama y para el SCB apenas hay cambios.

# Destrucción de un proceso.
- Formas de terminación
1. Normal
2. Error
3. Error fatal: Involuntaria u operación no posible
4. Por señal de terminación (kill)
