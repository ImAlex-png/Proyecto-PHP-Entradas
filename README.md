# 🎫 Proyecto PHP – Gestión de Entradas con QR

Este proyecto es una aplicación completa en **PHP** que permite gestionar entradas de cine mediante:

- Selección de asiento  
- Generación de códigos QR  
- Generación de PDF  
- Envío de entradas por correo electrónico  
- Validación de entradas mediante URL (simulando lector de QR)  

Perfecto como proyecto educativo para aprender sesiones, cookies, FPDF, PHPMailer y manejo de formularios.

---

## 📌 Características principales

### ✔ 1. **Generación de QR**
En `codigo.php` se genera un código QR que contiene la URL con los datos de la entrada:


Ese QR puede ser escaneado por un lector externo.

---

### ✔ 2. **Generación de PDF**
El archivo `codigoPdf.php` genera un PDF con:

- Datos de la entrada  
- Imagen del QR  
- Usuario, asiento y cine  
- Diseño básico con FPDF  

---

### ✔ 3. **Envío por correo**
`codigoCorreo.php` usa **PHPMailer** para enviar:

- El QR como archivo adjunto  
- Los datos de la entrada  
- Posible PDF adjunto (opcional)  

Se conecta mediante SMTP (en este proyecto, Gmail).

---

### ✔ 4. **Validación de entradas**
`entrada.php` recibe los datos desde el QR y valida usando una matriz de arrays:

```php
$entradas = [
    ["usuario" => "Antonio", "asiento" => 1, "cine" => "los_arcos"],
    ["usuario" => "Noelia",  "asiento" => 2, "cine" => "cine_alcores"],
    ["usuario" => "Pepe",    "asiento" => 3, "cine" => "los_arcos"],
    ["usuario" => "Sofia",   "asiento" => 4, "cine" => "cine_nervion"]
];

📂 Proyecto-PHP-Entradas
 ├── 📂 lib/               # Librería FPDF
 ├── 📂 vendor/            # PHPMailer instalado con Composer
 ├── asientos.php          # Selección de asientos
 ├── codigo.php            # Generación de QR
 ├── codigo.png            # QR generado
 ├── codigoCorreo.php      # Envío por correo con PHPMailer
 ├── codigoPdf.php         # Generación de PDF
 ├── entrada.php           # Validación mediante URL del QR
 ├── inicio.php            # Página de inicio
 ├── validacion.php        # Comprobación de formulario
 ├── composer.json         # Dependencias (PHPMailer)
 └── README.md             # Este archivo

