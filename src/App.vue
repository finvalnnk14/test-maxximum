<template>
  <nav class="bg-blue-600 p-4 shadow-md fixed top-0 right-0 w-full sm:w-auto">
    <div class="container mx-auto flex justify-between items-center">
      <!-- Gambar di sebelah kiri -->
      <div class="logo">
        <img src="/src/assets/logo.jpeg" alt="Logo" class="h-8">
      </div>
      
      <!-- Menu di sebelah kanan -->
      <ul class="flex space-x-6">
        <li v-for="(item, index) in menuItems" :key="index">
          <a :href="item.link" class="text-black hover:text-gray-300 transition">{{ item.name }}</a>
        </li>
      </ul>
    </div>
  </nav>
  <h1>Navigating the <br /> digital landscape <br /> for success </h1>
  <img src="/src/assets/illustration.jpg" alt="Digital Success" className="illustration" width="500">
  <div class="consultation-box">Book a consultation</div>
   
</template>

<script>
export default {
  data() {
    return {
      menuItems: [
        { name: "About Us", link: "#about" },
        { name: "Services", link: "#services" },
        { name: "Use Cases", link: "#use-cases" },
        { name: "Pricing", link: "#pricing" },
        { name: "Blog", link: "#blog" }
      ]
    };
  },
  
};
</script>

<style scoped>
nav {
  position: fixed;
  top: 0;
  right: 0;
  width: 100%;
  z-index: 999;
}

ul {
  display: flex;
  list-style-type: none;
  padding-left: 0;
}

li {
  margin-right: 20px;
}

a {
  text-decoration: none;
}

.container {
  display: flex;
  justify-content: space-between; /* Membuat konten di kiri dan kanan */
  align-items: center;
  width: 100%;
}

.logo img {
  height: 20px; /* Sesuaikan ukuran gambar */
}
  h1 {
    
            text-align: left; /* Menjadikan teks berada di sebelah kiri */
            font-size: 60px; /* Ukuran teks 40 cm */
             margin-left: -5cm;
             margin-top: -4cm;
             font-family: 'Space Grotesk', sans-serif;
        }
.illustration {
  margin-top: -5cm; /* Sesuaikan sesuai kebutuhan */
}
.consultation-box {
            background-color: black;
            color: white;
            padding: 10px 20px;
            border-radius: 5px;
            display: inline-block;
            font-size: 18px;
            width: 10cm;
            font-weight: bold;
            text-align: center;
            cursor: pointer;
            margin-left: -5cm;
        }
        
</style>
