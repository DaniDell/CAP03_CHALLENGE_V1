```mermaid
sequenceDiagram
    actor Cliente
    participant Sistema
    participant Inventario
    participant Pagos
    participant BaseDeDatos

    Cliente->>Sistema: Solicitar disponibilidad de habitaciones
    Sistema->>Inventario: Verificar disponibilidad
    Inventario-->>Sistema: Disponibilidad confirmada
    Sistema->>Cliente: Mostrar habitaciones disponibles

    Cliente->>Sistema: Seleccionar habitación
    Sistema->>BaseDeDatos: Registrar selección de habitación
    BaseDeDatos-->>Sistema: Confirmación de selección

    Cliente->>Sistema: Confirmar reserva
    Sistema->>BaseDeDatos: Guardar reserva
    BaseDeDatos-->>Sistema: Confirmación de reserva guardada
    Sistema->>Cliente: Confirmar reserva

    Cliente->>Pagos: Realizar pago
    Pagos->>Sistema: Verificar pago
    Pagos-->>Sistema: Pago confirmado
    Sistema->>BaseDeDatos: Actualizar estado de pago
    BaseDeDatos-->>Sistema: Confirmación de pago
    Sistema->>Cliente: Confirmar pago y reserva finalizada
```