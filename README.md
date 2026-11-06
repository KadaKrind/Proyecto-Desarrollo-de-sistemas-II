Actores, requisitos funcionales y no funcionales
Tipo	Nro.	Requisito / Actor
Actor	1	Recepcionista: Registra a los clientes, abre las órdenes de trabajo con los datos del equipo, asigna el técnico, registra la entrega y el pago, emite el recibo en PDF y cierra la orden.
Actor	2	Técnico: Ingresa al sistema para revisar las órdenes que tiene asignadas, cambia su estado, registra notas técnicas y lista los repuestos necesarios con sus costos.
Actor	3	Cliente: Persona que deja su equipo en el taller. Consulta desde la web (celular o PC) el estado de su reparación con su número de carnet o código de ticket, y acepta o rechaza el presupuesto en línea.
Actor	4	Administrador (Dueño): Gestiona los usuarios y roles del sistema y consulta el panel de control con reportes semanales y mensuales (equipos atendidos, técnicos más productivos, ingresos y repuestos más solicitados).
RF	1	RF-001: El sistema debe permitir a los usuarios internos (recepcionista, técnico y administrador) iniciar sesión con nombre de usuario y contraseña, mostrando únicamente las opciones correspondientes a su rol.
RF	2	RF-002: El sistema debe permitir al administrador crear, editar y desactivar cuentas de usuario, asignándoles el rol de recepcionista, técnico o administrador.
RF	3	RF-003: El sistema debe permitir a la recepcionista registrar a un cliente con su número de carnet de identidad, nombre completo, teléfono y correo electrónico, validando que el carnet no esté registrado previamente.
RF	4	RF-004: El sistema debe permitir a la recepcionista buscar clientes por número de carnet o nombre y actualizar sus datos.
RF	5	RF-005: El sistema debe permitir a la recepcionista abrir una orden de trabajo por cada equipo que deja el cliente, registrando el tipo de equipo (laptop, PC de escritorio, consola u otro), marca, modelo, número de serie, accesorios incluidos y la falla reportada por el cliente.
RF	6	RF-006: El sistema debe generar automáticamente un código de ticket único y la fecha/hora de ingreso al crear una orden de trabajo, y permitir imprimirlo o entregarlo al cliente como comprobante.
RF	7	RF-007: El sistema debe permitir a la recepcionista asignar un técnico responsable a cada orden de trabajo.
RF	8	RF-008: El sistema debe mostrar al técnico el listado de órdenes que tiene asignadas, con la posibilidad de filtrarlas por estado.
RF	9	RF-009: El sistema debe permitir al técnico cambiar el estado de la orden a “En diagnóstico”, “Esperando repuestos”, “Reparado” o “Entregado”, registrando la fecha, hora y usuario de cada cambio en un historial.
RF	10	RF-010: El sistema debe permitir al técnico registrar notas técnicas sobre lo que va descubriendo durante la revisión del equipo, guardando la fecha y hora de cada nota.
RF	11	RF-011: El sistema debe permitir al técnico listar los repuestos necesarios indicando descripción, cantidad y costo unitario, calculando automáticamente el subtotal de cada repuesto.
RF	12	RF-012: El sistema debe calcular automáticamente el presupuesto estimado de la orden sumando el costo de los repuestos y el costo de mano de obra.
RF	13	RF-013: El sistema debe permitir al cliente, sin iniciar sesión, consultar desde la página web el estado de su equipo y el presupuesto estimado ingresando su número de carnet o el código de ticket.
RF	14	RF-014: El sistema debe marcar la orden como “Pendiente de aprobación” y mostrar al cliente el nuevo presupuesto cuando el costo de la reparación supere el monto previsto inicialmente.
RF	15	RF-015: El sistema debe permitir al cliente aceptar o rechazar en línea el nuevo presupuesto, registrando su decisión con fecha y hora y notificándola al técnico asignado.
RF	16	RF-016: El sistema debe permitir a la recepcionista registrar la entrega del equipo y el pago, indicando el monto y el método de pago (efectivo, tarjeta o transferencia).
RF	17	RF-017: El sistema debe generar una nota de venta o recibo digital imprimible en formato PDF con los datos del cliente, del equipo, los repuestos, la mano de obra, el total pagado y el método de pago.
RF	18	RF-018: El sistema debe permitir a la recepcionista cerrar la orden una vez registrado el pago, cambiando su estado a “Entregado”.
RF	19	RF-019: El sistema debe registrar automáticamente la fecha de finalización al cerrar una orden y calcular la garantía de 90 días sobre el servicio, mostrando su fecha de vencimiento en la orden y en el recibo.
RF	20	RF-020: El sistema debe permitir buscar órdenes de trabajo por código de ticket, carnet del cliente, número de serie, estado, técnico o rango de fechas.
RF	21	RF-021: El sistema debe mostrar al administrador un panel de control con la cantidad de equipos atendidos por semana y por mes.
RF	22	RF-022: El sistema debe generar un reporte semanal y mensual de los técnicos más productivos según la cantidad de órdenes reparadas.
RF	23	RF-023: El sistema debe generar un reporte de ingresos totales por semana y por mes a partir de los pagos registrados.
RF	24	RF-024: El sistema debe generar un reporte de los repuestos más solicitados en un período seleccionado (semanal o mensual).
RF	25	RF-025: El sistema debe permitir a cualquier usuario interno cerrar su sesión de forma segura.
RNF	1	RNF-001 (Rendimiento): El sistema debe soportar al menos 30 usuarios consultando sus tickets de forma simultánea sin bloquearse ni presentar errores.
RNF	2	RNF-002 (Rendimiento): El sistema debe responder a cualquier búsqueda (clientes, órdenes o tickets) en menos de 2 segundos.
RNF	3	RNF-003 (Rendimiento): El sistema debe generar el recibo digital en formato PDF en menos de 5 segundos.
RNF	4	RNF-004 (Seguridad): El sistema debe almacenar las contraseñas de los usuarios cifradas mediante un algoritmo de hash seguro (por ejemplo, bcrypt o SHA-256 con salt), nunca en texto plano.
RNF	5	RNF-005 (Seguridad): El sistema debe implementar control de acceso basado en roles, de modo que la recepcionista, el técnico y el administrador accedan únicamente a las funciones que les corresponden.
RNF	6	RNF-006 (Seguridad): El sistema debe proteger la información de los clientes transmitiendo todos los datos mediante el protocolo HTTPS (cifrado TLS).
RNF	7	RNF-007 (Seguridad): El sistema debe mostrar en la consulta pública de tickets solo el estado del equipo, sus datos básicos y el presupuesto, sin exponer información personal completa del cliente.
RNF	8	RNF-008 (Seguridad): El sistema debe cerrar automáticamente la sesión de los usuarios internos después de 15 minutos de inactividad.
RNF	9	RNF-009 (Usabilidad): El sistema debe visualizarse correctamente tanto en pantallas de escritorio como en teléfonos móviles mediante un diseño web adaptable (responsive) desde 360 px de ancho.
RNF	10	RNF-010 (Usabilidad): El sistema debe permitir a la recepcionista registrar un cliente y abrir su orden de trabajo en un tiempo no mayor a 3 minutos.
RNF	11	RNF-011 (Usabilidad): El sistema debe presentar toda su interfaz en idioma español, con mensajes de error y confirmación claros para el usuario.
RNF	12	RNF-012 (Portabilidad): El sistema debe funcionar en las dos últimas versiones de los navegadores Google Chrome, Mozilla Firefox, Microsoft Edge y Safari, incluyendo sus versiones para Android e iOS.
RNF	13	RNF-013 (Confiabilidad): El sistema debe estar disponible el 99 % del tiempo durante el horario de atención del taller.
RNF	14	RNF-014 (Confiabilidad): El sistema debe realizar copias de seguridad automáticas de la base de datos al menos una vez al día, conservándolas por un mínimo de 30 días.
RNF	15	RNF-015 (Integridad): El sistema debe registrar en una bitácora de auditoría cada cambio de estado, pago y cierre de orden, indicando el usuario, la fecha y la hora.
RNF	16	RNF-016 (Mantenibilidad): El sistema debe desarrollarse con una arquitectura por capas (por ejemplo, MVC) y seguir estándares de codificación definidos por el equipo, facilitando su mantenimiento.
RNF	17	RNF-017 (Escalabilidad): El sistema debe permitir almacenar al menos 50 000 órdenes de trabajo sin que el tiempo de respuesta de las búsquedas supere los 2 segundos.
RNF	18	RNF-018 (Legal): El sistema debe resguardar los datos personales de los clientes conforme al derecho a la privacidad reconocido en la Constitución Política del Estado Plurinacional de Bolivia (art. 21 y art. 130).
