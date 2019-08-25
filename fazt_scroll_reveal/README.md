## [Youtube - Bootstrap 4 Sitio Web Desde Cero, con Scroll Reveal y Smooth scrolling](https://www.youtube.com/watch?v=X8OysJsdYxA)

> He probado codeanywhere pero no me convece. Pide acceso a tu cuenta de github y solo te da 1 contenedor para un solo proyecto gratuito <br/>

#### Indice
- [Scroll Reveal](https://youtu.be/X8OysJsdYxA?t=492)
  - crea animación
- [Instalación fonts.google.com](https://youtu.be/X8OysJsdYxA?t=552)
- [Configurando js de scrollreveal](https://youtu.be/X8OysJsdYxA?t=2490)
  - Antes de esto se diseña el layout en boostrap definiendo las secciones con un id
  ```js
  window.sr = ScrollReveal()
  //selecciona el elemento o elementos con clase .navbar
  sr.reveal(".navbar",{
    duration: 2000, //2 segundos
    origin: "bottom",//vendrá desde abajo
  })

  //animación imagen cayendo dentro de su caja
  sr.reveal(".header-content-left",{
    duration: 2000, //2 segundos
    origin: "top",	//vendrá desde arriba, como si cayera en su sitio
    distance: 300px,
  })

  //animación de texto viniendo desde la derecha a su posición final al lado de la imagen
  sr.reveal(".header-content-right",{
    duration: 2000, //2 segundos
    origin: "top",	//vendrá desde arriba, como si cayera en su sitio
    distance: 300px,
  })

  //animación del botón, aparecerá con retraso despues de pintarse la imagen y el texto
  sr.reveal(".header-btn",{
    duration: 2000, //2 segundos
    origin: "bottom",
    delay: 1000, //retraso en aparecer
    distance: 300px,
  })

  //smoth scrolling:
  //https://stackoverflow.com/questions/7717527/smooth-scrolling-when-clicking-an-anchor-link
  //la página es un layout con mucha altura dividida en secciones
  //el menú principal navega entre estas secciones de manera directa
  //con el siguiente código se hace ese scroll hacia las secciones mas suave y animado
  document.querySelectorAll('a[href^="#"]').forEach(anchor => {
    //se selecciona todos los elementos anchor que tengan # 
      anchor.addEventListener('click', function (e) {
      //se cancela el comportamiento original, tratar el evento y desplazar la página hasta la sección
          e.preventDefault();
      //this hace referencia al <a></a> que tiene configurado el href que es el id de la seccion.
      //en resumen se obtiene el elemento sección y se le configura un scroll smooth
          document.querySelector(this.getAttribute('href')).scrollIntoView({
              behavior: 'smooth'
          });
      });
  });
  ```
