<template>
  <div id="app" class="container">
    <div class="sidenav">
      <h2>Menú</h2>
      <ul>
        <li><a class="active" href="#">Inicio</a></li>
        <li><a href="#">Servicios</a></li>
        <li><a href="#">Nosotros</a></li>
        <li><a href="#">Contacto</a></li>
      </ul>
    </div>
    <div class="grid-container">
      <div v-for="(item, index) in divisiones" :key="index"  class="grid-item">
        <img :src="getImage(index)" :alt="`Imagen de ${item}`" />
        </div>
      </div>
    </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      divisiones: ['Migración a AWS', 'División 2', 'División 3', 'División 4']
    };
  },
  methods: {
    getImage(index) {
      // Aquí puedes personalizar las URLs de las imágenes
      const images = [
        '/img/cloud.jpg',
        '/img/connect.jpg',
        '/img/div1.jpg',
        'https://via.placeholder.com/150?text=División+4'
      ];
      return images[index] || 'https://via.placeholder.com/150';
    }
  }
};
</script>

<style scoped>
.container {
  display: flex;
  height: 100vh;
  margin: 0;
  font-family: Arial, sans-serif;
}


div {
    display: block;
    unicode-bidi: isolate ;
}
ul {
            list-style-type: none;
            margin: 0;
            padding: 0;
            width: 200px;
            background-color: #f1f1f1;
        }
        
        li a {
            display: block;
            color: #000;
            padding: 8px 16px;
            text-decoration: none;
        }
        
        li a.active {
            background-color: #4CAF50;
            color: white;
        }
        
        li a:hover:not(.active) {
            background-color: #555;
            color: white;
        }
        div.content {
            margin-left: 25%;
            padding: 1px 16px;
            height: 1000px;
        }
        
        @media screen and (max-width: 900px) {
            ul.sidenav {
                width: 100%;
                height: auto;
                position: relative;
            }
            ul.sidenav li a {
                float: left;
                padding: 15px;
            }
            div.content {
                margin-left: 0;
            }
        }
        .image-name {
          position: absolute;
          top: 0;
          left: 0;
          width: 100%;
          background-color: rgba(0,0,0,0.5);
          color: white;
          text-align: center;
          padding: 10px;
        }
      @media screen and (max-width: 400px) {
            ul.sidenav li a {
                text-align: center;
                float: none;
            }
        
        }
      .o-teaser-collection .teaser-image {
        overflow: hidden;
    }
    body {
      margin: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background-color: #f0f0f0;
      font-family: Arial, sans-serif;
    }

    .grid-container {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 10px;
      width: 80%;
      height: 80%;
    }

    .grid-item {
      display: flex;
      justify-content: center;
      align-items: center;
      background-color: #ffffff;
      border: 1px solid #ddd;
      border-radius: 8px;
      overflow: hidden;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    }

    .grid-item img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }

/* Para dispositivos pequeños */
@media (max-width: 768px) {
  .container {
    flex-direction: column;
  }

  .menu, .contenido {
    width: 100%;
    box-shadow: none;
  }

  .menu {
    border-bottom: 1px solid #ddd;
  }
}
</style>
