⚽ DOCUMENTACIÓN TÉCNICA DEL PROYECTO: SUPERGOL

---

## 📋 1. REQUISITOS DEL SISTEMA

### Requisitos Funcionales (Lo que hace la aplicación)
* **RF 01 - Gestión y Registro de Usuarios:** El sistema debe permitir el registro de nuevos usuarios (clientes) capturando sus datos básicos y asignándoles un rol por defecto.
* **RF 02 - Control de Acceso (Inicio de Sesión):** El sistema debe contar con un módulo de autenticación que valide las credenciales de los usuarios y diferencie los permisos según el rol: Administrador (Samaca) o Usuario Normal.
* **RF 03 - Gestión de Reservas de Espacios Deportivos (Super Gol):** El sistema debe permitir a los usuarios visualizar la disponibilidad en tiempo real de las canchas de fútbol y las pistas de motocross de Super Gol, así como realizar sus respectivas reservas. Asimismo, el administrador del complejo podrá gestionar, aprobar, modificar o cancelar dichas reservas desde el panel de control.
* **RF 04 - Control y Contabilización de Usos:** El sistema debe permitir al encargado registrar y acumular manualmente cada uso de las mesas de billar y zonas recreativas para llevar un conteo histórico.
* **RF 05 - Módulo de Inventario y Alertas de Stock:** El sistema debe permitir al administrador ingresar el inventario inicial de productos. Debe incluir botones para restar unidades con cada venta y generar una notificación automática en pantalla cuando el producto llegue a su stock mínimo.
* **RF 06 - Reporte de Productos Más Vendidos:** El sistema debe procesar los datos de las ventas realizadas y generar un reporte visual para el administrador que resalte los productos con mayor demanda.

### Requisitos No Funcionales (Características del sistema)
* **RNF 01 - Interfaz Visual (Temática Oscura):** El diseño de la interfaz gráfica de usuario debe aplicar una temática exclusivamente en color negro (Dark Mode), garantizando un contraste adecuado, legibilidad y una estética moderna alineada al motocross y entretenimiento.
* **RNF 02 - Seguridad del Sistema:** La aplicación debe implementar un nivel alto de seguridad que incluya la protección de rutas (para que los usuarios comunes no accedan al panel de Samacá) una vez autenticados, y la encriptación de contraseñas en la base de datos.

---

## 👥 2. HISTORIAS DE USUARIO (HU)

### HU 01 - Registro de Clientes
* **Como:** Usuario visitante
* **Quiero:** Registrarme en la plataforma ingresando mis datos básicos
* **Para:** Tener una cuenta y poder acceder a los servicios de Supergol.
* **Criterios de Aceptación:**
  * **CA 1:** El formulario debe solicitar obligatoriamente: Nombre, Correo y Contraseña.
  * **CA 2:** Al registrarse, el sistema debe asignar por defecto el rol de Usuario Normal.
  * **CA 3:** La contraseña debe guardarse de forma encriptada en la base de datos (RNF 02).
  * **CA 4:** La interfaz de registro debe cumplir con la temática oscura (fondo negro, texto legible y estética moderna) (RNF 01).

### HU 02 - Inicio de Sesión y Control de Accesos
* **Como:** Usuario registrado (Cliente o Administrador)
* **Quiero:** Iniciar sesión con mis credenciales
* **Para:** Acceder a las funciones correspondientes a mi rol dentro de la aplicación.
* **Criterios de Aceptación:**
  * **CA 1:** El sistema debe validar que el correo y la contraseña coincidan con los registrados.
  * **CA 2:** Si el rol es Administrador (Samacá), el sistema debe redirigir al panel de control total.
  * **CA 3:** Si el rol es Usuario Normal, debe redirigir a la vista de cliente (reservas).
  * **CA 4:** Protección de rutas: Si un Usuario Normal intenta ingresar manualmente a la URL del panel de Samacá, el sistema debe denegar el acceso y redirigirlo al inicio.

### HU 03 - Visualización y Reserva de Espacios (Clientes)
* **Como:** Usuario Normal
* **Quiero:** Ver la disponibilidad en tiempo real de las canchas de fútbol y pistas de motocross y realizar una reserva
* **Para:** Asegurar mi espacio deportivo en el horario que deseo.
* **Criterios de Aceptación:**
  * **CA 1:** El sistema debe mostrar un calendario o agenda visual con los horarios disponibles y ocupados en tiempo real.
  * **CA 2:** El usuario debe poder seleccionar el tipo de espacio (Cancha de fútbol o Pista de motocross), la fecha y la hora.
  * **CA 3:** Al confirmar, la reserva queda en estado "Pendiente" hasta que el administrador la revise.
  * **CA 4:** Toda la interfaz de reserva debe mantener el diseño en modo oscuro.

### HU 05 - Control Manual de Usos
* **Como:** Encargado / Administrador
* **Quiero:** Registrar y acumular manualmente cada uso de las mesas de billar y zonas recreativas
* **Para:** Llevar un conteo histórico y estadístico del uso del establecimiento.
* **Criterios de Aceptación:**
  * **CA 1:** El sistema debe mostrar un botón o formulario rápido para "Registrar Uso" por cada mesa de billar o zona recreativa.
  * **CA 2:** Cada vez que se registre un uso, el sistema debe sumar (+1) al contador histórico de ese espacio.
  * **CA 3:** Se debe almacenar la fecha y hora en la que se realizó el registro manual.

### HU 06 - Inventario Inicial y Alertas de Stock
* **Como:** Administrador (Samaca)
* **Quiero:** Ingresar el inventario de los productos y recibir alertas cuando queden pocas unidades
* **Para:** Evitar quedarme sin mercancía para vender en el centro de entretenimiento.
* **Criterios de Aceptación:**
  * **CA 1:** El sistema debe permitir registrar un producto con su nombre, cantidad inicial y stock mínimo permitido.
  * **CA 2:** Debe existir un botón rápido para restar unidades de forma manual o automática con cada venta realizada.
  * **CA 3:** Notificación en pantalla: En el momento exacto en que la cantidad de un producto sea igual o menor al stock mínimo establecido, debe aparecer una alerta visual automática en la interfaz del administrador.

### HU 07 - Reporte de Productos Más Vendidos
* **Como:** Administrador (Samaca)
* **Quiero:** Ver un reporte visual de los productos con mayor demanda
* **Para:** Saber qué mercancía es la que genera más ingresos y planificar mejor las compras.
* **Criterios de Aceptación:**
  * **CA 1:** El sistema debe procesar el histórico de las unidades restadas (ventas).
  * **CA 2:** Debe mostrar un gráfico o lista visual que resalte los productos ordenados de mayor a menor demanda.
  * **CA 3:** El reporte debe ser fácil de interpretar y mantener la estética oscura y moderna del sistema (RNF 01).