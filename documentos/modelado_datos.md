# DISEÑO DE LA BASE DE DATOS - SUPERGOL

USUARIOS
-
id_usuarios int PK
nombre_usuarios varchar (50)
apellido_usuarios varchar (50)
fecha_nacimiento date
correo_usuario varchar (50)
rol_usuario varchar (50)
agregar_usuario varchar (30)

PRODUCTOS
-
id_producto int PK
nombre_producto varchar(100)
cantidad_producto int
precio_producto float
descripcion_producto string
costo_producto float
stock_minimo int
stock_maximo int

RESERVAS
-
id_reserva int PK
id_servicio int FK > SERVICIOS.id_servicio
id_usuarios int FK > USUARIOS.id_usuarios
id_espacio int
fecha_reservas date
hora_inicio date
hora_fin date
estado varchar (30)

VENTAS_REPORTE
-
id_venta int PK
id_producto int FK > PRODUCTOS.id_producto
cantidad_vendida int
precio_unitario_venta float
fecha_venta date

SERVICIOS
-
id_servicio int PK
nombre_servicio varchar
tipo_servicio varchar
descripcion_servicio varchar
precio_servicio float

REGISTRO_HORAS_USOS
-
id_registro int PK
id_zona int
fecha_hora_uso date

CONFIGURACION_SISTEMA
-
id_config int PK
nombre_establecimiento varchar(100)
direccion varchar(100)
telefono varchar(20)
correo_contacto varchar(50)
logo_url varchar(255)