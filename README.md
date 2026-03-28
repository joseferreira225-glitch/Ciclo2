# 💻 Reto 2 — Registro de Donaciones de Computadores
### Ciclo 2 · Programación Básica · MisiónTIC 2022

---

## 📋 Descripción del proyecto

Sistema desarrollado en Java para el colegio **"Nuestro Señor Jesús"**, que permite registrar el valor de los computadores recibidos en donación. El programa calcula el precio individual de cada equipo y muestra los totales separados por tipo de computador.

---

## 🧠 Conceptos aplicados

- **Herencia** — `ComputadoresMesa` y `ComputadoresPortatiles` heredan de `Computadores`
- **Polimorfismo** — cada clase sobreescribe `calcularPrecio()` con su propia lógica
- **Encapsulamiento** — atributos protegidos y accedidos mediante getters
- **instanceof** — para clasificar objetos en tiempo de ejecución

---

## 📁 Estructura del proyecto

```
src/
├── Computadores.java           ← Clase padre (base)
├── ComputadoresMesa.java       ← Hereda de Computadores, agrega almacenamiento
├── ComputadoresPortatiles.java ← Hereda de Computadores, agrega pulgadas y cámara
├── PrecioTotal.java            ← Calcula y muestra los totales
└── Main.java                   ← Clase principal, punto de entrada
```

---

## 💰 Lógica de precios

### Fórmula general
```
precioTotal = precioBase + adición
```

### Adición por consumo energético (consumoW)
| Letra | Adición |
|-------|---------|
| A     | $100    |
| B     | $80     |
| C     | $60     |
| D     | $50     |
| E     | $30     |
| F     | $10     |

### Adición por peso
| Peso (kg)  | Adición |
|------------|---------|
| 0 — 18     | $10     |
| 20 — 48    | $50     |
| 50 — 79    | $80     |
| 80 o más   | $100    |

### Extras por tipo
| Tipo                  | Condición                        | Adición         |
|-----------------------|----------------------------------|-----------------|
| ComputadoresMesa      | Almacenamiento > 100 GB          | +$50            |
| ComputadoresPortatiles| Pantalla > 40 pulgadas           | +30% precioBase |
| ComputadoresPortatiles| Tiene cámara integrada           | +$50            |

### Valores por defecto
| Clase                  | Atributo            | Valor por defecto |
|------------------------|---------------------|-------------------|
| Computadores           | consumoW            | 'F'               |
| Computadores           | precioBase          | 100.0             |
| Computadores           | peso                | 5                 |
| ComputadoresMesa       | almacenamiento      | 50 GB             |
| ComputadoresPortatiles | pulgadas            | 20                |
| ComputadoresPortatiles | camaraITG           | false             |

---

## ▶️ Cómo compilar y ejecutar

### Requisitos
- Java JDK 8 o superior
- NetBeans IDE (o cualquier IDE de Java) o terminal

### Desde NetBeans
1. Abrir NetBeans
2. `File` → `Open Project` → seleccionar la carpeta del proyecto
3. Clic derecho sobre el proyecto → `Run`

### Desde la terminal
```bash
# 1. Ir a la carpeta src del proyecto
cd ruta/del/proyecto/src

# 2. Compilar todos los archivos
javac *.java

# 3. Ejecutar
java Main
```

---

## 📊 Resultados esperados

### Prueba 1
```
La suma del precio de los computadores es de 3000.0
La suma del precio de los computadores de mesa es de 130.0
La suma del precio de los computadores portátiles es de 910.0
```

### Prueba 2
```
La suma del precio de los computadores es de 715.0
La suma del precio de los computadores de mesa es de 350.0
La suma del precio de los computadores portátiles es de 175.0
```

---

## 👤 Autor

**[Tu nombre completo]**
[Tu carrera / curso]
[Tu institución]
[Año]
