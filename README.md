# Calculadora de horas extras

Aplicación web que calcula cuánto recibirá un trabajador por sus horas extras, a partir de su sueldo base, su jornada semanal y la cantidad de horas extras trabajadas.

🔗 **Demo:** [nerdale.github.io/calculadora_horas_extras](https://nerdale.github.io/calculadora_horas_extras/)

## Por qué este proyecto

Calcular las horas extras suele requerir fórmulas que no todos tienen a mano. Esta herramienta lo resuelve en tres pasos simples, sin registro ni instalación, y muestra el resultado al instante.

## Cómo se usa

1. **Ingresa tu sueldo:** escribe tu sueldo base. El valor de tu hora extra se calcula automáticamente.
2. **Selecciona tus horas semanales:** elige entre 40 y 44 horas, según tu contrato. Si no eliges ninguna opción, se usan 44 horas por defecto.
3. **Ingresa las horas extras:** indica el total de horas extras trabajadas, en números.

El resultado se actualiza mientras escribes, sin necesidad de presionar ningún botón, y muestra el monto que recibirás por trabajar horas extras.

> Recuerda que las horas extras son imponibles.

## Características

- **Cálculo en tiempo real:** el valor de la hora extra y el total se recalculan con cada cambio en el formulario.
- **Formato chileno:** los montos se muestran en pesos, con separador de miles (por ejemplo, `$1.250.000`).
- **Entrada validada:** los campos numéricos aceptan solo dígitos; cualquier otro carácter se descarta.
- **Mensaje adaptable:** el texto del resultado cambia según la cantidad de horas ("1 hora extra" o "3 horas extras").
- **Sin dependencias:** funciona con HTML, CSS y JavaScript puro, sin librerías externas.

## Cómo se calcula

El valor de la hora extra se obtiene a partir de la hora ordinaria, con el recargo del 50% que establece la normativa laboral chilena:

```js
valorHoraExtra = Math.floor(((sueldo * 28) / (30 * horasSemanales * 4)) * 1.5);
montoTotal     = valorHoraExtra * horasExtras;
```

- `sueldo * 28 / 30` corresponde a lo que se paga por 28 días, es decir, cuatro semanas.
- Al dividirlo por `horasSemanales * 4` se obtiene el valor de una hora ordinaria de trabajo.
- Al multiplicarlo por `1.5` se aplica el recargo del 50% de la hora extra.
- `Math.floor` redondea el valor de la hora extra hacia abajo, a pesos enteros, y el total se calcula a partir de ese valor.

Es un cálculo referencial. No reemplaza la liquidación de sueldo ni la asesoría de un profesional.

## Tecnologías

- **HTML** para la estructura de la página.
- **CSS** para los estilos y el diseño responsivo.
- **JavaScript** para la lógica de cálculo y la interacción con el formulario.
- **Git y GitHub Pages** para el control de versiones y la publicación.

## Estructura del proyecto

```
calculadora_horas_extras/
├── css/          # estilos
├── img/          # imágenes
├── js/           # lógica de la calculadora
└── index.html    # página principal
```

## Ejecutar en local

No requiere instalación ni dependencias.

```bash
git clone https://github.com/nerdale/calculadora_horas_extras.git
cd calculadora_horas_extras
```

Luego abre `index.html` en tu navegador.

