# Subasta de Cuartos · Casa Ski 2027

Sistema de **subasta dinámica** para repartir el costo de la casa entre 10 personas,
siempre cuadrando en el total exacto de **$12,611.30**.

## Cómo funciona

- **10 personas** en **6 espacios**: 4 cuartos de pareja + 2 camas del camarote (individuales).
- **Base por persona:** $1,261.13 (12,611.30 ÷ 10).
- Cada quien **puja por persona** en el espacio que quiere. Es una subasta **que solo sube**:
  para quedarte con un cuarto debes **superar la puja actual** (si ya tiene dueño).
- El cuarto con puja queda **bloqueado** en ese precio; los espacios **sin dueño** se
  reparten el resto y **bajan de precio**.
- El total **siempre** suma $12,611.30.
- **En tiempo real:** funciona sobre Firebase; todos ven las pujas al instante. Las pujas
  usan transacciones atómicas (a prueba de dos personas pujando a la vez).

### Ejemplo
Si la pareja del King Principal de Arriba fija **$1,550/persona** ($3,100 el cuarto),
los otros 8 lugares flotantes se reparten los $9,511.30 restantes → **$1,188.91/persona**.

### Espacios

| Espacio | Personas | Detalle |
|---|---|---|
| King Principal — Arriba | 2 | La grande. Baño privado y closet |
| King Principal — Abajo | 2 | Baño privado y closet |
| King Esquina — Abajo | 2 | Baño privado, sin closet |
| King Derecha — Abajo | 2 | Closet. Baño compartido con el camarote |
| Camarote — Cama de abajo | 1 | Baño compartido, sin closet |
| Camarote — Cama de arriba | 1 | Baño compartido, sin closet |

## Uso

Abre `index.html` en cualquier navegador (funciona sin internet). Las pujas, los
ocupantes y el registro se guardan automáticamente en el dispositivo. Botón
**Reiniciar todo** para empezar de cero.
