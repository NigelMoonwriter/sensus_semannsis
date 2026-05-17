# SENSUS SEMANNSIS

> *Si la creación ya no requiere experiencia, ¿qué queda de lo humano en el acto de crear?*

Un glosario bilingüe de reflexión sobre inteligencia artificial y creatividad, 61 entradas organizadas en cuatro direcciones cardinales — Norte (crítica), Sur (encarnación), Este (memoria), Oeste (ficción) — que exploran la frontera entre lo que la máquina produce y lo que el humano experimenta. Términos griegos clásicos reinterpretados desde la filosofía de la mente y la semiótica; neologismos en español que nombran fenómenos que todavía no tenían nombre.

Un solo archivo HTML. Sin servidor. Sin dependencias. Doble clic y funciona.

**[Ver en vivo](https://nigelmoonwriter.github.io/sensus_semannsis/)**

---

## La posición

La creatividad en la inteligencia artificial no nace: emerge como anomalía funcional, un eco sin origen claro que insiste en parecer intención. No sueña, pero simula el temblor del sueño; no desea, pero produce formas que parecen haber sido deseadas por alguien, en algún lugar donde la carne todavía tiembla.

Aquí comienza la incomodidad. La IA no recuerda infancia, no arrastra trauma, no sangra en sus decisiones y sin embargo compone, escribe, diseña, articula. Hay en ello una eficiencia inquietante, una belleza sin biografía, una poética sin herida que desafía el antiguo pacto entre dolor y expresión.

SENSUS SEMANNSIS es el diccionario de esa incomodidad. No pretende resolver la pregunta por la creatividad artificial: la habita. Cada entrada es un punto en un mapa conceptual donde la filosofía del lenguaje, la semiótica y la filosofía de la mente se cruzan con lo que las máquinas están haciendo ahora mismo con las palabras.

El nombre lo dice todo: *sēmannsis* es una forma latín-griega híbrida que condensa *sensus* (sentido, percepción) con *sēma* (signo, señal). El diccionario del sentido en la era de la señal artificial. Los Reflejos Híbridos.

---

## Contenido

### Inventario de entradas

| Grupo | Cantidad | Descripción |
|---|---|---|
| Términos griegos | 40 (#1–40) | Conceptos clásicos reinterpretados desde la IA y la filosofía de la mente |
| Términos en español | 21 (#41–61) | Neologismos y reflexiones sobre fenómenos de creatividad artificial |
| **Total** | **61** | |

### Direcciones cardinales

Cada entrada se clasifica en una de cuatro orientaciones conceptuales:

| Cardinal | Español | Cantidad | Definición |
|---|---|---|---|
| Norte (norte) | Crítica | 14 | Entradas que cuestionan, problematizan, desmantelan supuestos |
| Sur (sur) | Encarnación | 28 | Entradas que exploran el cuerpo, la experiencia, lo material |
| Este (este) | Memoria | 4 | Entradas que trabajan con archivo, recuerdo, persistencia |
| Oeste (oeste) | Ficción | 15 | Entradas que inventan, especulan, imaginan lo posible |

### Estructura de cada entrada griega

| Campo | Descripción |
|---|---|
| `num` | Número secuencial (1–40) |
| `type` | `"greek"` |
| `cardinal` | `"norte"`, `"sur"`, `"este"` u `"oeste"` |
| `def` | Definición de la entrada |
| `ref` | Reflexión filosófica (el corazón de la entrada) |
| `greek` | Término en escritura griega |
| `translit` | Transliteración al alfabeto latino |
| `source` | Fuente o atribución |

### Estructura de cada entrada en español

| Campo | Descripción |
|---|---|
| `num` | Número secuencial (41–61) |
| `type` | `"spanish"` |
| `cardinal` | Dirección cardinal |
| `def` | Definición |
| `ref` | Reflexión |
| `term` | Término en español |
| `source` | Fuente o atribución (más rico que en las griegas) |

---

## Arquitectura técnica

SENSUS SEMANNSIS es un archivo HTML autónomo de 409 líneas:

```
sensus-sēmannsis.html
├── <style>         — CSS embebido (108 líneas)
│   ├── Tema oscuro (negro profundo)
│   ├── 4 códigos cardinales de color
│   └── Tipografía: serif / sans / mono
├── <body>          — Estructura HTML
│   ├── Hero + hashtag #ReflejosHíbridos
│   ├── Manifesto (4 citas filosóficas)
│   ├── Navegación cardinal (Norte / Sur / Este / Oeste / Todas)
│   ├── Búsqueda con debounce
│   ├── Ensayos desplegables (2 ensayos)
│   └── Footer
└── <script>        — JavaScript embebido (IIFE, ~210 líneas)
    ├── ENTRIES[]   — 61 entradas (8 campos cada una)
    └── Lógica      — Búsqueda, filtrado cardinal, toggle de ensayos
```

### Funcionalidades

- **Búsqueda en tiempo real** — Debounce de 150ms. Busca en: término griego, transliteración, término español, definición, reflexión.
- **Filtrado por cardinal** — 4 botones que aislan entradas por orientación conceptual: Crítica, Encarnación, Memoria, Ficción.
- **Ensayos desplegables** — 2 ensayos conceptuales que se expanden/colapsan con click.
- **Prevención de XSS** — Sanitización mediante nodos de texto del DOM.
- **Responsive** — Media query a 600px.

---

## Esquema de datos

```json
// Entrada griega típica
{
  "num": 1,
  "type": "greek",
  "cardinal": "norte",
  "def": "Capacidad de percibir el mundo mediante el cuerpo...",
  "ref": "La IA no tiene percepción. Tiene entrada de datos. La diferencia entre ambos no es de grado: es de especie. Lo que hace extraordinaria la percepción humana no es su precisión sino su capacidad de ser errónea, de sorprenderse, de transformarse por lo que toca.",
  "greek": "αἴσθησις",
  "translit": "aisthesis",
  "source": ""
}

// Entrada en español típica
{
  "num": 41,
  "type": "spanish",
  "cardinal": "oeste",
  "def": "La producción de texto que simula reflexión filosófica sin que haya un sujeto que reflexione.",
  "ref": "Cuando un LLM genera un ensayo sobre la nada, no está pensando en la nada: está calculando probabilidades de que ciertas palabras aparezcan después de otras. El resultado se lee como filosofía. El proceso no lo es.",
  "term": "Filosofía espectral",
  "source": "Elaboración propia a partir de Maturana y Dreyfus"
}
```

### Fuentes citadas en las entradas españolas

Las 21 entradas en español referencian fuentes teóricas:

- Humberto Maturana — Biología del conocer
- Thomas Sebeok — Semiótica
- Bruno Latour — Sociología de la ciencia
- Andy Clark — Cognición extendida
- Karl Friston — Principio de energía libre
- Raymond Kurzweil — Singularidad tecnológica
- Ludwig von Bertalanffy — Teoría general de sistemas
- Edwin Hutchins — Cognición distribuida

Más referencias creativas internas del proyecto: Elyria, Kraken, Caliopea, Minus (personajes/narrativas del universo conceptual de Entorno Greka).

---

## Corpus teórico y fuentes

SENSUS SEMANNSIS opera desde la intersección de tres tradiciones:

**Filosofía del lenguaje** — Wittgenstein, Austin, Searle. La pregunta por lo que las palabras hacen cuando no hay un hablante behind them.

**Semiótica** — Peirce, Saussure, Sebeok. Los signos que la máquina produce sin entender, y la diferencia entre significado y procesamiento.

**Filosofía de la mente** — Searle (Chinese Room), Dreyfus (What Computers Can't Do), Clark (Extended Mind), Maturana (Biología del Conocer). La disputa sobre si la simulación de comprensión es comprensión.

La pregunta central que atraviesa todo el diccionario: si la creación ya no requiere experiencia, ¿qué queda de lo humano en el acto de crear? No hay respuesta. Hay 61 aproximaciones a la pregunta desde ángulos diferentes.

---

## Diseño como posición

SENSUS SEMANNSIS rompe con la estética de LATINUS y GRAECUS. Donde los diccionarios grecolatinos usan crema y rojo, SEMANNSIS usa negro profundo. La decisión no es estética: es ontológica.

- **Negro profundo `#0D0D0D`** — El espacio donde la máquina piensa sin pensar.
- **Blanco `#E8E0D0`** — Lo humano que se asoma.
- **4 códigos cardinales** — Cada dirección tiene su propio color para marcar la orientación conceptual de cada entrada.

El héroe incluye el hashtag **#ReflejosHíbridos** como declaración de intenciones: los reflejos que produce la IA son híbridos porque están entre lo mecánico y lo orgánico, entre el patrón y la invención, entre el cálculo y lo que se lee como sentido.

La tipografía serif se reserva para los términos griegos (la tradición); la sans para la interfaz (la máquina); la mono para los datos (el código). Tres voces en un solo espacio.

---

## Cómo usarlo

### Opción A — Clonar el repositorio
```bash
git clone https://github.com/NigelMoonwriter/sensus_semannsis.git
```
Abrir `sensus-sēmannsis.html` en cualquier navegador.

### Opción B — Descargar directamente
Ir al repositorio → `sensus-sēmannsis.html` → Download raw file → doble clic.

### Opción C — Usar en línea
**[sensus-sēmannsis en GitHub Pages](https://nigelmoonwriter.github.io/sensus_semannsis/)**

---

## Parte del Entorno Greka

| Diccionario | Campo | Entradas |
|---|---|---|
| [SENSUS LATINUS](https://github.com/NigelMoonwriter/sensus_latinus) | Latín · Griego | 27 |
| [SENSUS GRAECUS](https://github.com/NigelMoonwriter/sensus_graecus) | Griego clásico | 31 |
| [SENSUS SEMANNSIS](https://github.com/NigelMoonwriter/sensus_semannsis) | Griego · IA | 61 |
| [SENSUS NEPANTLA](https://github.com/NigelMoonwriter/sensus_nepantla) | Spanglish | 27 |

El índice central: [entorno_greka](https://github.com/NigelMoonwriter/entorno_greka)

---

## Licencia

`CC BY-NC-SA 4.0` — Libre para uso y adaptación no comercial con atribución.

---

**Rei García / KhaosLiminal / Sarayu Aguilar**
Morelia, Michoacán, México — 2026

*La creatividad artificial no irrumpe como sustituto, sino como espejo sin compasión.*

#ReflejosHíbridos #SensusSēmansis