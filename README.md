# GauchoRocket

## Descripción del Proyecto

GauchoRocket es una aplicación web diseñada para gestionar reservas, viajes y facturación en una empresa de transporte. La plataforma permite un control eficiente de las operaciones y la generación de reportes y estadísticas detalladas.

## Tecnologías Utilizadas

- **PHP**: Lenguaje de programación utilizado para la lógica del servidor.
- **Mustache**: Motor de plantillas utilizado para la generación de vistas dinámicas.
- **QRCode**: Librería utilizada para generar códigos QR.
- **FPDF**: Librería utilizada para generar documentos PDF.
- **MySQL**: Base de datos utilizada para almacenar información sobre reservas, viajes y facturación.
- **PHPMailer**: Librería utilizada para enviar correos electrónicos.

## Requisitos Previos

Asegúrate de tener instalados los siguientes componentes antes de comenzar:

- PHP
- MySQL Server
- Servidor web (como Apache o Nginx)
- Composer (para gestionar las dependencias de PHP)

## Instalación

1. **Clonar el repositorio**:
    ```bash
    git clone https://github.com/1cristianb/gauchorocket.git
    cd gauchorocket
    ```

2. **Instalar dependencias**:
    ```bash
    composer install
    ```

3. **Configurar la base de datos**:

   - Crear una base de datos en MySQL:
     ```sql
     CREATE DATABASE gauchorocket;
     ```

   - Utilizar el script de `databse/database_gauchorocketV9.sql`

4. **Configurar las credenciales de la base de datos**:

   Modifica el archivo `configuration/conexiondatabase.ini` con tus credenciales de MySQL:
    ```php
    <?php
    severname = 'localhost';
    username = 'tu_usuario';
    password = 'tu_contraseña';
    dbname = 'gauchorocket';
    ```

5. **Configurar PHPMailer**:

   Modifica el archivo `config/mail.php` con tus credenciales de correo:
    ```php
    <?php
    use PHPMailer\PHPMailer\PHPMailer;
    use PHPMailer\PHPMailer\Exception;

    require 'vendor/autoload.php';

    $mail = new PHPMailer(true);
    try {
        // Configuración del servidor
        $mail->isSMTP();
        $mail->Host = 'smtp.ejemplo.com';
        $mail->SMTPAuth = true;
        $mail->Username = 'tu_correo@ejemplo.com';
        $mail->Password = 'tu_contraseña';
        $mail->SMTPSecure = PHPMailer::ENCRYPTION_STARTTLS;
        $mail->Port = 465;

        // Configuración del remitente
        $mail->setFrom('tu_correo@ejemplo.com', 'GauchoRocket');
    } catch (Exception $e) {
        echo "No se pudo enviar el correo. Error: {$mail->ErrorInfo}";
    }
    ?>
    ```

6. **Desplegar la aplicación**:

   - Copia todos los archivos del proyecto al directorio raíz de tu servidor web.

   - Asegúrate de que tu servidor web esté configurado para servir archivos PHP y esté apuntando al directorio correcto.

7. **Acceder a la aplicación**:

   Abre tu navegador web y dirígete a la dirección donde está alojada tu aplicación. Por ejemplo: http://localhost/gauchorocket

   ## Autor
   Cristian Boschi, Fernando Sulka y Arnold Tomassini
