# Challenge-stores
Desafío de análisis de datos para identificar rentabilidad en tiendas.
Con el fin de ayudar al Sr Juan a decidir cuál de sus tiendas representa la mejor opción para comercializar sus productos, se realizó un estudio basado en datos sobre las ventas, ingresos, calificaciones de clientes, productos más populares y costos de envios. A través del análisis y visualización de estos factores, se determinará cuál tienda ofrece el entorno más favorable para maximizar ventas y satisfacción del cliente.

# ANALISIS DE FACTURACIÓN
# Se calcular el total de ingresos por cada tienda usando la funcion sum()
tienda1: Es el DataFrame que contiene la información de la tienda (por ejemplo, ventas, inventario, etc.).
groupby(["Producto", "Categoría del Producto"]): Agrupa los datos según las columnas "Producto" y "Categoría del Producto". Por ejemplo, podría agrupar todas las ventas del producto "Coca-Cola" dentro de la categoría "Bebidas".
.size(): Cuenta cuántas veces aparece cada grupo (es decir, cuántas veces se repite una combinación producto + categoría). Esto es útil si cada fila del DataFrame representa una venta o una entrada individual.
.sort_values(ascending=False): Ordena los resultados de mayor a menor, de forma que los productos más frecuentes aparezcan primero.

# Se imprimen los resultados
f"Tienda 1: ${ingresos_tienda1:,.0f}":
Es un f-string (una cadena con formato en Python).
ingresos_tienda1 es una variable que representa los ingresos (probablemente una suma en dinero).
:,.0f es un formato numérico:
, → incluye separadores de miles (por defecto en formato anglosajón, usa comas: 1,000,000).
 .0f → redondea a cero decimales (número entero).
Por ejemplo, si ingresos_tienda1 = 1234567.89, se vería así:
"Tienda 1: $1,234,568"
.replace(",", "."):
Cambia las comas por puntos, para adaptarse al formato de números europeo/latinoamericano, donde los miles se separan con puntos en lugar de comas.
Entonces "Tienda 1: $1,234,568" se convierte en → "Tienda 1: $1.234.568"

# VENTAS POR CATEGORIAS
# Agrupar por categoría y producto, luego contar cuántas veces aparece cada producto
Agrupa por "Producto" y "Categoría del Producto".
Cuenta cuántas veces aparece cada combinación.
Ordena de mayor a menor.
# Mostrar los resultados
Accedemos a la columna de llamada categoria del producto del DataFrame y cuenta cuantas veces aparece cada valor unico en esa columna
tienda1['Categoría del Producto']
Selecciona la columna "Categoría del Producto" del DataFrame tienda1.
.value_counts()
Cuenta cuántas veces aparece cada valor único en esa columna.
Es decir, cuántos productos (o filas) hay en cada categoría.
categorias_t1 = ...
Guarda ese conteo en una nueva variable llamada categorias_t1.

# CALIFICACIONES PROMEDIO DE LA TIENDA
# Calcular el promedio de calificaciones
promedio_t1 = tienda1['Calificación'].mean() 
accede a la columna 'Calificación' del DataFrame tienda1, calcula el promediode los valores numericos en esa columna usando  .mean(), guarda el resultado en la variable promedio_t1 

# PRODUCTOS MAS VENIDOS Y MENOS VENDIDOS
# Estilo del gráfico
plt.style.use("ggplot") Lo usamos para aplicar el estilo visual llamado "ggplot" a los gráficos creados con Matplotlib (plt).
Este estilo está inspirado en el paquete ggplot2 de R, y cambia automáticamente colores, fondos, cuadrículas y otros detalles estéticos del gráfico para que se vean más limpios y profesionales.

# Para poder procesar cada tienda
for nombre, url in urls.items():
    df = pd.read_csv(url)
se usa para recorrer un diccionario llamado urls, donde cada clave (nombre) está asociada a un valor (url).

# Crear gráficos
    fig, axes = plt.subplots(1, 2, figsize=(16, 6))
Crea una figura (fig) con 2 subgráficos en una sola fila (1, 2). por otro lado axes es una lista (o array) de los ejes de esos subgráficos y figsize=(16, 6) define el tamaño total de la figura (ancho 16, alto 6).
 fig.suptitle(f'{nombre} - Productos más y menos vendidos', fontsize=16)
Le pone un título general a la figura completa, no solo a un subplot y usa una f-string para personalizar el título con la variable nombre.

plt.tight_layout() Ajusta automáticamente el espaciado entre subplots para que no se sobrepongan los títulos, ejes, etiquetas, entre otras. Es muy útil cuando hay muchos elementos en los gráficos y se ven amontonados.

plt.subplots_adjust(top=0.85) Ajusta manualmente el espacio superior de la figura para que el título general (fig.suptitle) no se corte o se encime con los subgráficos. Aquí lo sube un poco más alto (top=0.85 significa que el límite superior del área usable es el 85% del alto total).

plt.show() Muestra la figura con todos los subplots en pantalla. Si no lo ponés, en algunos entornos (como scripts de Python normales) no aparece nada.

# ENVIO RPOMEDIO POR TIENDA

# Calcular el promedio del costo de envío por tienda

envio_prom_t1 = tienda1["Costo de envío"].mean()
tienda1 es un DataFrame (probablemente de pandas) que contiene información sobre productos o ventas de una tienda.

"Costo de envío" es una columna dentro del DataFrame tienda1 que contiene los valores del costo de envío de los productos.

.mean() es una función de pandas que calcula el promedio de todos los valores numéricos en esa columna.
