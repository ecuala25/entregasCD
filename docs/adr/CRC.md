
# 1. Tarjetas CRC — Sistema de gestión de una biblioteca

## Clase: Libro

| Responsabilidades | Colaboradores |
|---|---|
| Conocer autor, título e ISBN | — |
| Conocer número de ejemplares disponible | — |
| Prestar un ejemplar (comprobar disponibilidad) | Préstamo |
| Recibir devoluciones | Préstamo |

---

## Clase: Socio

| Responsabilidades | Colaboradores |
|---|---|
| Conocer su nombre, nº de socio y fecha de alta | — |
| Solicitar un libro | Libro, Préstamo |
| Devolver un libro | Préstamo |

---

## Clase: Préstamo

| Responsabilidades | Colaboradores |
|---|---|
| Conocer qué libro y socio están implicados | Libro, Socio |
| Conocer la fecha del préstamo | — |
| Registrar la devolución del libro | Libro |



## 2. Comportamiento de la clase `Libro` al prestar un ejemplar

Cuando se intenta prestar un ejemplar, la clase `Libro` debe comprobar primero si hay ejemplares disponibles.

- **Si hay ejemplares disponibles:** el préstamo tiene éxito y el número de ejemplares disponibles disminuye en uno.
- **Si no hay ejemplares disponibles:** el préstamo no se realiza y el número de ejemplares disponibles permanece igual.


## 3. Descripción del flujo

### 1. Se da de alta un libro con 3 ejemplares

- **Clase que actúa:** `Libro`.
- **Colaboradores:** Ninguno.
- Se crea un libro con sus datos: autor, ISBN y título; y se establece que tiene 3 ejemplares disponibles.

### 2. Se dan de alta dos socios

- **Clase que actúa:** `Socio`.
- **Colaboradores:** Ninguno.
- Se registran dos socios con sus respectivos datos personales, número de socio y fecha de alta.

### 3. El primer socio toma prestado el libro

- **Clases que actúan:** `Socio`, `Libro` y `Préstamo`.
- **Colaboradores:** `Libro` y `Préstamo`.
- El primer socio solicita el libro. Como hay 3 ejemplares disponibles, el préstamo tiene éxito. Se registra el préstamo y quedan 2 ejemplares disponibles.

### 4. El segundo socio intenta tomar el mismo libro

- **Clases que actúan:** `Socio`, `Libro` y `Préstamo`.
- **Colaboradores:** `Libro` y `Préstamo`.
- El segundo socio solicita el mismo libro. Como quedan 2 ejemplares disponibles, el préstamo también tiene éxito. Se registra el préstamo y queda 1 ejemplar disponible.

### 5. El primer socio devuelve el libro

- **Clases que actúan:** `Socio`, `Préstamo` y `Libro`.
- **Colaboradores:** `Préstamo` y `Libro`.
- Se registra la devolución del ejemplar prestado por el primer socio y el número de ejemplares disponibles aumenta de 1 a 2.

### 6. El segundo socio vuelve a intentar tomar el libro

- **Clases que actúan:** `Socio`, `Libro` y `Préstamo`.
- **Colaboradores:** `Libro` y `Préstamo`.
- Como quedan 2 ejemplares disponibles, el préstamo tiene éxito. Se registra el nuevo préstamo y quedan 1 ejemplar disponible.
