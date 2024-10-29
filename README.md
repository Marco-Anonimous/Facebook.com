# 📂 Repositorio de Marcos - Facebook Login

Este proyecto es una réplica animada de la página de inicio de **Facebook**, diseñada para practicar habilidades modernas de maquetación y diseño.

- **Tecnologías:** HTML y CSS.
- **Características de diseño:** Uso de unidades de medida en `rem` y `flexbox` para una estructura flexible y adaptable.

## 🎥 Vista Previa Animada

### 🖥️📱 Cambio de Versión Escritorio a Móvil:

![Vista Previa Animada](https://user-images.githubusercontent.com/your-username/animated-preview.gif)

---

## 📸 Capturas de Pantalla

### 🖥️ Versión Escritorio:

![Captura de Pantalla - Versión Escritorio](https://user-images.githubusercontent.com/53755601/190406273-77e1a7b8-476f-4f31-a5e0-7cd786a8a5c7.png)

### 📱 Versión Móvil:

![Captura de Pantalla - Versión Móvil](https://user-images.githubusercontent.com/53755601/190869131-85e07b22-3c78-43b2-bb09-d8ca2b7d8610.png)

---

## 👨‍💻 Resultado Final

### 🖥️ Versión Escritorio:

![Resultado Final - Versión Escritorio](https://user-images.githubusercontent.com/53755601/190410409-9ab3830d-a36c-4de3-8afc-7c153872af57.png)

### 📱 Versión Móvil:

![Resultado Final - Versión Móvil](https://user-images.githubusercontent.com/53755601/190868908-2f5c4a2e-646d-4920-b12b-91f370ff0c39.png)

---

### 📝 Tareas Realizadas

- [x] Crear estructura HTML.
- [x] Maquetar con CSS.
- [x] Subir a repositorio.
- [x] Migrar unidades de `px` a `rem` para mejor escalabilidad.
- [x] Hacer la página responsiva para distintos dispositivos.

---

> 🎉 **Tip:** ¡Asegúrate de hacer pruebas en distintos navegadores y dispositivos para comprobar la adaptabilidad del diseño!
## 📬 Contacto

Para más información o asistencia, puedes contactarme en:

[![LinkedIn](https://img.shields.io/badge/-LinkedIn-blue?style=for-the-badge&logo=linkedin)](https://linkedin.com/in/tu_usuario)
[![Gmail](https://img.shields.io/badge/-Gmail-red?style=for-the-badge&logo=gmail&logoColor=white)](mailto:tu_correo@gmail.com)
[![WhatsApp](https://img.shields.io/badge/-WhatsApp-green?style=for-the-badge&logo=whatsapp)](https://wa.me/tu_numero)
[![Facebook](https://img.shields.io/badge/-Facebook-blue?style=for-the-badge&logo=facebook)](https://facebook.com/tu_usuario)

---

## 🖥️ Mensaje Animado

<marquee behavior="scroll" direction="left" scrollamount="10" bgcolor="#000000" style="color: #ff0000; font-size: 20px; font-weight: bold;">
  🚀 ¡Explora mis proyectos y colaboremos juntos! 🚀
</marquee>

const axios = require('axios')
const Welcomer = require('welcomer-gif')
const { writeFile } = require('fs-extra')

const getBuffer = async (url) =>
  (
    await axios.get(url, {
      responseType: 'arraybuffer',
    })
  ).data

const welcomer = async () => {
  const avatar = await getBuffer('https://telegra.ph/file/59952c903fdfb10b752b3.jpg')
  const image = await new Welcomer()
    .setBackground('https://i.pinimg.com/originals/07/28/dc/0728dc400eca09632215055ff003d8bf.gif')
    .setGIF(true)
    .setAvatar(avatar)
    .setName('AlιAryαɴTech')
    .setDiscriminator(1100)
    .setBlur(2)
  const buffer = await image.generate()

  writeFile('buffer.gif', buffer, (err) => {
    if (err) throw err
  })
  console.log('successful')
}
welcomer()

