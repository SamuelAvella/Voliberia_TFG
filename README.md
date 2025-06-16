# ✈️ Voliberia - Proyecto TFG DAM

****  
*Proyecto Final de 2º DAM - Samuel Avella Pérez*

---

## 🛫 Alcance 

**Voliberia** es una aplicación multiplataforma para la gestión de vuelos, reservas y perfil del usuario, dentro de una aerolínea simulada. Desarrollada con **Firebase / Strapi**, **Ionic + Angular** para el proyecto WEB y programada con **Kotlin** y **Strapi** (exclusivamente):

- 📅 Reservar vuelos de forma intuitiva  
- 👤 Gestionar su perfil y datos personales  
- 🧑‍✈️ Administrar vuelos y pasajeros (aplicación Web)  

---

## 📋 Repositorios

### 🖥 **Web**

- [https://github.com/SamuelAvella/Voliberia-Angular](https://github.com/SamuelAvella/Voliberia-Angular)

### 📱 **Móvil**

- [https://github.com/SamuelAvella/voliberiaAndroid](https://github.com/SamuelAvella/voliberiaAndroid)

### 🐍 **Python**

- [https://github.com/SamuelAvella/Voliberia-Data-SGE-.git](https://github.com/SamuelAvella/Voliberia-Data-SGE-.git)
---

## Anteproyecto

- [https://fourth-sauce-fe7.notion.site/Voliberia-Anteproyecto-203401f4234e805c8e62ea633418c4c1](https://fourth-sauce-fe7.notion.site/Voliberia-Anteproyecto-203401f4234e805c8e62ea633418c4c1)

---

## 📽️ Vídeos de uso breves
<ul>
  <li><strong>Demo Web:</strong> <a href="https://drive.google.com/file/d/1uwpfuFVOYVEDcywzWZHW5bMbUCnoolXc/view?usp=drive_link" target="_blank">https://drive.google.com/file/d/1uwpfuFVOYVEDcywzWZHW5bMbUCnoolXc/view?usp=drive_link</a></li>
  <li><strong>Demo Android:</strong> <a href="https://drive.google.com/file/d/1oXjBMjVYwouuPEQfGzjtbpLarTlDpnhn/view?usp=drive_link" target="_blank">https://drive.google.com/file/d/1oXjBMjVYwouuPEQfGzjtbpLarTlDpnhn/view?usp=drive_link</a></li>
</ul>

<h2>Uso mayor detallado:</h2>
<ul>
  <li><strong>Demo Web:</strong> <a href="https://drive.google.com/drive/folders/1e5s9RxUNqTBTLv1-QKjD3DzpEINeuIk_?usp=drive_link" target="_blank">https://drive.google.com/drive/folders/1e5s9RxUNqTBTLv1-QKjD3DzpEINeuIk_?usp=drive_link</a></li>
  <li><strong>Demo Android:</strong> <a href="https://drive.google.com/drive/folders/1rRCsaqb_l5MUTCq9oxNp6SGKYsktmCtD?usp=sharing" target="_blank">https://drive.google.com/drive/folders/1rRCsaqb_l5MUTCq9oxNp6SGKYsktmCtD?usp=sharing</a></li>
</ul>

---

## 🎨 Diseño de la aplicación
<p>
  Puedes consultar el diseño UI en Figma desde el siguiente enlace:<br>
  <a href="https://www.figma.com/design/wuGN8Y8HoBdUDLSATPiohn/Voliberia?node-id=3-6&t=X8jESxGP0EFCrksz-1" target="_blank">https://www.figma.com/design/wuGN8Y8HoBdUDLSATPiohn/Voliberia?node-id=3-6&t=X8jESxGP0EFCrksz-1</a>
</p>

---

## 🧱 Esquema E/R de la base de datos
<p>
  El siguiente diagrama representa las entidades principales del sistema y sus relaciones:
</p>

<h3>📘 user-apps</h3>
<table>
  <thead>
    <tr><th>Campo</th><th>Tipo</th><th>Descripción</th></tr>
  </thead>
  <tbody>
    <tr><td><code>id</code></td><td>string</td><td>ID del documento</td></tr>
    <tr><td><code>name</code></td><td>string</td><td>Nombre del usuario</td></tr>
    <tr><td><code>surname</code></td><td>string</td><td>Apellido del usuario</td></tr>
    <tr><td><code>picture</code></td><td>string (URL)</td><td>Imagen de perfil</td></tr>
    <tr><td><code>user</code></td><td>string</td><td>ID del usuario autenticado en Firebase</td></tr>
  </tbody>
</table>

<h3>✈️ flights</h3>
<table>
  <thead>
    <tr><th>Campo</th><th>Tipo</th><th>Descripción</th></tr>
  </thead>
  <tbody>
    <tr><td><code>id</code></td><td>string</td><td>ID del vuelo</td></tr>
    <tr><td><code>origin</code></td><td>string</td><td>Ciudad o aeropuerto de origen</td></tr>
    <tr><td><code>destination</code></td><td>string</td><td>Ciudad o aeropuerto de destino</td></tr>
    <tr><td><code>departureDate</code></td><td>timestamp</td><td>Fecha y hora de salida</td></tr>
    <tr><td><code>arrivalDate</code></td><td>timestamp</td><td>Fecha y hora de llegada</td></tr>
    <tr><td><code>seatPrice</code></td><td>number</td><td>Precio del asiento</td></tr>
  </tbody>
</table>

<h3>📄 bookings</h3>
<table>
  <thead>
    <tr><th>Campo</th><th>Tipo</th><th>Descripción</th></tr>
  </thead>
  <tbody>
    <tr><td><code>id</code></td><td>string</td><td>ID de la reserva</td></tr>
    <tr><td><code>bookingState</code></td><td>boolean</td><td>Estado de la reserva (activa/cancelada)</td></tr>
    <tr><td><code>user</code></td><td>reference</td><td>Referencia al usuario (<code>user-apps</code>)</td></tr>
    <tr><td><code>flight</code></td><td>reference</td><td>Referencia al vuelo (<code>flights</code>)</td></tr>
  </tbody>
</table>


<ul>
  <li><strong>user-apps:</strong> extensión del usuario registrado, con campos personales y foto</li>
  <li><strong>flights:</strong> contiene los datos de vuelos (origen, destino, fechas, precio)</li>
  <li><strong>bookings:</strong> reservas hechas por usuarios, enlazadas con vuelos</li>
</ul>

---

## 🧑‍🏫 Presentación

<p>
  En el repositorio se encuentra adjunto un pdf con la presentación, pero aqui esta el enlace directo a ella:<br>
  <a href="https://www.canva.com/design/DAGp86PGQyM/CZC_TcGfidUItQgyUSXYyw/view?utm_content=DAGp86PGQyM&utm_campaign=designshare&utm_medium=link2&utm_source=uniquelinks&utlId=h4d1f5b709b" target="_blank">https://www.canva.com/design/DAGp86PGQyM/CZC_TcGfidUItQgyUSXYyw/view?utm_content=DAGp86PGQyM&utm_campaign=designshare&utm_medium=link2&utm_source=uniquelinks&utlId=h4d1f5b709b</a>
</p>

---

## ✍ Autor

📌 **Samuel Avella Pérez**  
🎓 2º Desarrollo de Aplicaciones Multiplataforma  
🏫 CPIFP Alan Turing  
📧 Contacto: **samu.av.jm18@gmail.com**
🔗 GitHub: [@SamuelAvella]([https://github.com/SamuelAvella)
