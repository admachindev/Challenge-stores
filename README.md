# Challenge-stores
Desafío de análisis de datos para identificar rentabilidad en tiendas.
Con el fin de ayudar al Sr Juan a decidir cuál de sus tiendas representa la mejor opción para comercializar sus productos, se realizó un estudio basado en datos sobre las ventas, ingresos, calificaciones de clientes, productos más populares y costos de envios. A través del análisis y visualización de estos factores, se determinará cuál tienda ofrece el entorno más favorable para maximizar ventas y satisfacción del cliente.

# ANALISIS DE FACTURACIÓN
# Se calcular el total de ingresos por cada tienda usando la funcion sum()
tienda1: Es el DataFrame que contiene la información de la tienda (por ejemplo, ventas, inventario, etc.).
# .groupby(["Producto", "Categoría del Producto"]): Agrupa los datos según las columnas "Producto" y "Categoría del Producto". Por ejemplo, podría agrupar todas las ventas del producto "Coca-Cola" dentro de la categoría "Bebidas".
# .size(): Cuenta cuántas veces aparece cada grupo (es decir, cuántas veces se repite una combinación producto + categoría). Esto es útil si cada fila del DataFrame representa una venta o una entrada individual.
# .sort_values(ascending=False): Ordena los resultados de mayor a menor, de forma que los productos más frecuentes aparezcan primero.
# Se imprimen los resultados
# f"Tienda 1: ${ingresos_tienda1:,.0f}":
Es un f-string (una cadena con formato en Python).
ingresos_tienda1 es una variable que representa los ingresos (probablemente una suma en dinero).
# :,.0f es un formato numérico:
# , → incluye separadores de miles (por defecto en formato anglosajón, usa comas: 1,000,000).
# .0f → redondea a cero decimales (número entero).
Por ejemplo, si ingresos_tienda1 = 1234567.89, se vería así:
"Tienda 1: $1,234,568"
# .replace(",", "."):
Cambia las comas por puntos, para adaptarse al formato de números europeo/latinoamericano, donde los miles se separan con puntos en lugar de comas.
Entonces "Tienda 1: $1,234,568" se convierte en → "Tienda 1: $1.234.568"

# VENTAS POR CATEGORIAS
# Agrupar por categoría y producto, luego contar cuántas veces aparece cada producto
Agrupa por "Producto" y "Categoría del Producto".
Cuenta cuántas veces aparece cada combinación.
Ordena de mayor a menor.
# Mostrar los resultados
# Accedemos a la columna de llamada categoria del producto del DataFrame y cuenta cuantas veces aparece cada valor unico en esa columna
# tienda1['Categoría del Producto']
Selecciona la columna "Categoría del Producto" del DataFrame tienda1.
# .value_counts()
Cuenta cuántas veces aparece cada valor único en esa columna.
Es decir, cuántos productos (o filas) hay en cada categoría.
# categorias_t1 = ...
Guarda ese conteo en una nueva variable llamada categorias_t1.
# Mostrar resultados

# CALIFICACIONES PROMEDIO DE LA TIENDA
# Calcular el promedio de calificaciones
Selecciona la columna llamada "Calificación" dentro del DataFrame tienda2.
Esta columna debería contener números (por ejemplo, del 1 al 5, o del 0 al 10).
Selecciona la columna llamada "Calificación" dentro del DataFrame tienda2.
Esta columna debería contener números (por ejemplo, del 1 al 5, o del 0 al 10).

