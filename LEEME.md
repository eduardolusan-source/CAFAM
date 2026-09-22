# CAFAM — captura de sesión

Tres archivos:

- `socio.html` — la página que abren los socios (enlace fijo en el grupo de WhatsApp).
- `secretario.html` — el formato que se llena solo; desde ahí se imprime y se cierra la sesión.
- `Code.gs` — el backend en Google Apps Script que guarda todo en una hoja de Google.

Puesta en marcha (una sola vez): seguir los pasos comentados al inicio de `Code.gs`, pegar la URL `/exec` en la constante `SCRIPT_URL` de los dos HTML y subir ambos a GitHub Pages (o cualquier hospedaje estático). Si se quiere una clave para el secretario, escribirla en `PIN` dentro de `secretario.html`.

Flujo por sesión: los socios envían sus movimientos durante el periodo; el secretario abre su página, pulsa "Actualizar envíos", revisa ENTRADAS, pasa a la pestaña SALIDAS para capturar préstamos, plazo e interés, imprime a PDF y pulsa "Cerrar sesión". Al cerrar, los envíos se archivan con un identificador de sesión, el formato se vacía y la caja de cierre pasa automáticamente como caja inicial de la siguiente.

Decisiones tomadas al construirlo: el abono a préstamo se captura en una sola cantidad (capital e interés juntos) y las multas las declara el socio; nada se calcula automáticamente; el ahorro se captura en pesos; una sesión es todo lo enviado desde el cierre anterior; el comprobante sigue yendo al WhatsApp; las celdas editadas a mano por el secretario prevalecen sobre los envíos (marcadas hasta el cierre); la fila "Firma" muestra "✔ enviado" para quien mandó su registro y queda en blanco en el PDF para firmar si se requiere.
