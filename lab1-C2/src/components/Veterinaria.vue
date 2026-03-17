<script>
export default {
  data() {
    return {
      nombreMascota: "",
      cliente: "",
      servicio: "",
      error: false,
      mensajeError: "",
      mascotas: [],
    };
  },

  methods: {
    agregarMascota() {
      if (
        this.nombreMascota.trim() === "" ||
        this.cliente.trim() === "" ||
        this.servicio.trim() === ""
      ) {
        this.error = true;
        this.mensajeError = "Todos los campos son obligatorios";
        return;
      }

      this.mascotas.push({
        nombre: this.nombreMascota,
        cliente: this.cliente,
        servicio: this.servicio,
        estado: "Pendiente",
      });

      this.nombreMascota = "";
      this.cliente = "";
      this.servicio = "";
      this.error = false;
    },

    cambiarEstado(index) {
      if (this.mascotas[index].estado === "Pendiente") {
        this.mascotas[index].estado = "Atendido";
      } else {
        this.mascotas[index].estado = "Pendiente";
      }
    },

    eliminarMascota(index) {
      this.mascotas.splice(index, 1);
    },
  },
};
</script>


<template>
    <div class="container">
    <h1>Sistema Veterinario MagicPet</h1>

    <form @submit.prevent="agregarMascota">
      <input
        type="text"
        placeholder="Nombre de la mascota"
        v-model="nombreMascota"
      />

      <input
        type="text"
        placeholder="Nombre del cliente"
        v-model="cliente"
      />

      <select v-model="servicio">
        <option disabled value="">Seleccione el servicio</option>
        <option>Consulta</option>
        <option>Vacuna</option>
        <option>Cirugía</option>
      </select>

      <button type="submit">Agregar</button>
    </form>

    <p v-if="error" style="color:red;">
      {{ mensajeError }}
    </p>

    <table border="1">
      <thead>
        <tr>
          <th>Mascota</th>
          <th>Cliente</th>
          <th>Servicio</th>
          <th>Estado</th>
          <th>Acciones</th>
        </tr>
      </thead>

      <tbody>
        <tr v-for="(m, index) in mascotas" :key="index">
          <td>{{ m.nombre }}</td>
          <td>{{ m.cliente }}</td>
          <td>{{ m.servicio }}</td>

          <td :class="m.estado === 'Atendido' ? 'verde' : 'rojo'">
            {{ m.estado }}
          </td>

          <td>
            <button @click="cambiarEstado(index)">
              Cambiar Estado
            </button>

            <button @click="eliminarMascota(index)">
              Eliminar
            </button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<style>
body {
  background: linear-gradient(135deg, #fdcbff, #ffc2ec);
  font-family: Arial, sans-serif;
}

.container {
  max-width: 700px;
  margin: 40px auto;
  background: white;
  padding: 25px;
  border-radius: 15px;
  box-shadow: 0px 10px 25px rgba(0,0,0,0.2);
}

h1 {
  text-align: center;
  color: #333;
}

input, select {
  width: 90%;
  display: block;
  margin: 10px auto;
  padding: 10px;
  border-radius: 8px;
  border: 1px solid #ccc;
}

button {
  margin: 5px;
  padding: 10px;
  border: none;
  display: block;
  margin: 10px auto;
  border-radius: 8px;
  background-color: #9358b8;
  color: white;
  cursor: pointer;
  transition: 0.3s;
}

button:hover {
  background-color: #9358b8;
}

table {
  width: 100%;
  margin-top: 20px;
  border-collapse: collapse;
}

th {
  background-color: #c2377f;
  color: white;
  padding: 10px;
}

td {
  padding: 10px;
  border-bottom: 1px solid #ccc;
  text-align: center;
}

.verde {
  color: green;
  font-weight: bold;
}

.rojo {
  color: red;
  font-weight: bold;
}

p {
  text-align: center;
  font-weight: bold;
}
</style>