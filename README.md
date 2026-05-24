# programa-python-exmen-final
# =====================================================================
# REQUISITO 2: Módulo (Función) para calcular el precio final
# =====================================================================
def calcular_precio_final(precio_base, categoria_actual, categoria_objetivo, umbral):
    """
    Calcula el precio final aplicando un 15% de descuento si se cumplen
    las condiciones de la lógica de negocio.
    """
    # REQUISITO 3: Lógica de negocio (Condicional doble)
    if categoria_actual == categoria_objetivo and precio_base > umbral:
        # Se aplica el 15% de descuento
        precio_final = precio_base * 0.85
    else:
        # Se mantiene el precio base original
        precio_final = precio_base
        
    return precio_final

# =====================================================================
# REQUISITO 1: Crear la matriz con al menos 6 productos
# =====================================================================
# Estructura de cada fila: [Nombre, Categoría, Precio Base]
menu_restaurante = [
    ["Hamburguesa Gourmet", "Platos Fuertes", 25000],
    ["Papas Supremas", "Entradas", 12000],
    ["Limonada Cerezada", "Bebidas", 8000],
    ["Baby Beef", "Platos Fuertes", 35000],
    ["Volcán de Chocolate", "Postres", 14000],
    ["Club Colombia", "Bebidas", 7500],
    ["Crema de Tomate", "Entradas", 10000]
]

# Definición de variables para la promoción actual
# Ejemplo: Queremos dar descuento a los "Platos Fuertes" que cuesten más de 20,000
CATEGORIA_PROMO = "Platos Fuertes"
UMBRAL_PRECIO = 20000

# =====================================================================
# REQUISITO 4: Procesar la matriz y mostrar la salida
# =====================================================================
print("-" * 75)
print(f"   PROMOCIÓN: 15% de desc. en '{CATEGORIA_PROMO}' con precio mayor a ${UMBRAL_PRECIO}")
print("-" * 75)
# Cabecera de la tabla de resultados
print(f"{'Producto':<25} | {'Categoría':<15} | {'Precio Base':<12} | {'Precio Final':<12}")
print("-" * 75)

# Recorremos la matriz fila por fila
for producto in menu_restaurante:
    nombre = producto[0]
    categoria = producto[1]
    precio_base = producto[2]
    
    # Invocamos la función para obtener el precio final
    precio_final = calcular_precio_final(precio_base, categoria, CATEGORIA_PROMO, UMBRAL_PRECIO)
    
    # Imprimimos los resultados formateados
    print(f"{nombre:<25} | {categoria:<15} | ${precio_base:<11,.0f} | ${precio_final:<11,.0f}")

print("-" * 75)
