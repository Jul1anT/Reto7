# Sistema de Gestión de Menú y Pedidos

## Descripción
Este sistema permite la gestión de un menú de restaurante y el manejo de pedidos. Ofrece funcionalidades para agregar, actualizar y eliminar elementos del menú, así como procesar pedidos en cola y aplicar descuentos automáticos.

## Características Principales

### 1. Gestión del Menú
- **Agregar elementos al menú**: Se pueden añadir bebidas, aperitivos y platos principales con nombre, precio y tamaño.
- **Actualizar elementos existentes**: Modificar detalles de un ítem del menú.
- **Eliminar elementos**: Remover ítems del menú.
- **Persistencia de datos**: Guardar y cargar el menú en un archivo JSON.

### 2. Gestión de Pedidos
- **Crear pedidos**: Permite seleccionar ítems del menú y definir cantidades.
- **Aplicar descuentos**: Se ofrece un descuento automático si la cantidad de productos en el pedido supera un umbral.
- **Procesar pedidos**: Los pedidos se gestionan en una cola FIFO (First In, First Out).
- **Visualizar pedidos pendientes**.

## Estructura del Código

### Clases Principales

#### `MenuItem`
Representa un ítem del menú con atributos:
- `name`: Nombre del producto.
- `price`: Precio del producto.
- `size`: Tamaño del producto.

#### `MenuManager`
Maneja la gestión del menú:
- `add_item(category, item)`: Agrega un ítem a la categoría especificada.
- `update_item(category, item_name, new_item)`: Modifica un ítem existente.
- `delete_item(category, item_name)`: Elimina un ítem del menú.
- `save_menu(filename)`: Guarda el menú en un archivo JSON.
- `load_menu(filename)`: Carga el menú desde un archivo JSON.

#### `Order`
Representa un pedido con métodos para:
- Añadir ítems.
- Calcular el total con descuento si aplica.

#### `OrderManager`
Maneja la cola de pedidos:
- `add_order(order)`: Agrega un pedido a la cola.
- `process_order()`: Procesa el primer pedido en la cola.
- `show_orders()`: Muestra los pedidos pendientes.

