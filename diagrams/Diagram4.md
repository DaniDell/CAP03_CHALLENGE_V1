# Diagrama de Transición de Estados: Sistema de Reservas

```mermaid
stateDiagram-v2
    [*] --> Pendiente: Crear reserva
    
    Pendiente --> Confirmada: Confirmar reserva
    Pendiente --> Cancelada: Cancelar reserva
    
    Confirmada --> Pagada: Completar pago
    Confirmada --> Modificada: Modificar reserva
    Confirmada --> Cancelada: Cancelar reserva
    
    Modificada --> Pagada: Completar pago
    Modificada --> Modificada: Modificar nuevamente
    Modificada --> Cancelada: Cancelar reserva
    
    Pagada --> Modificada: Modificar reserva
    Pagada --> Cancelada: Cancelar reserva
    Pagada --> [*]: Finalizar reserva
    
    Cancelada --> [*]: Proceso finalizado
```

## Leyenda
- **Pendiente**: La reserva ha sido creada pero no confirmada
- **Confirmada**: La reserva ha sido confirmada por el sistema
- **Pagada**: El cliente ha completado el pago de la reserva
- **Modificada**: La reserva ha sido actualizada por el cliente o el sistema
- **Cancelada**: La reserva ha sido cancelada por el cliente o el sistema
