<template>
  <div class="flex flex-col ">
    <div class="text-black bg-[#D4ADFC] p-2 md:p-0">
    <p class="bg-zinc-800 text-center text-white p-2 ">Periodo {{ info.periodo }}</p>
<div class="flex flex-row gap-20 items-center justify-center mb-5 mt-5 text-center">
  <p v-if="isLoading">Cargando...</p>
  <p v-else>Inicio: {{ formatDate(info.inicio) }}</p>
  <p v-if="isLoading">Cargando...</p>
  <p v-else>Fin: {{formatDate(info.fin)}}</p>
</div>
<div v-if="isLoading2">
        Cargando...
      </div>
      <div v-else>
      <div class="flex flex-row items-center justify-center mb-5">
        <div class="p-5 md:px-20">
          <img src="../assets/Completa.png" alt="logotipo del sitmotul" class="mx-auto w-10 md:w-20">
        <div class="flex flex-col text-center">
          <h1>Total</h1>
          <p > {{ info.alTotal }}</p>
        </div>
        </div>
        
<div class="p-5 md:px-20">
  <img src="../assets/Lista.png" alt="logotipo del sitmotul" class="mx-auto w-10 md:w-20">
      <div class="flex flex-col text-center">
        <h1>Evaluados</h1>
      <p> {{ info.alEvaluados }}</p>
        </div>
</div>
     
<div class="p-5 md:px-20">
  <img src="../assets/Fallido.png" alt="logotipo del sitmotul" class="mx-auto w-10 md:w-20">
      <div class="flex flex-col text-center">
      <h1>Faltantes</h1>
        <p> {{ info.alTotal - info.alEvaluados }}</p>
      </div>
      </div>  
      </div>
      
    </div>
    <div v-if="isLoading2">
        Cargando...
      </div>
      <div v-else>
   <div class="bg-[#D4ADFC] p-4">
    <h1 class="text-center text-2xl text-black font-bold">Estado de evaluación por Ingenierias</h1><br>
    <div class="flex flex-row gap-5 mb-5 items-center justify-center ">
      <div class=" flex flex-col text-white text-center bg-[#713ABE] p-2 rounded-lg w-11/12 h-4/5">
        <img src="../assets/IEM.png" alt="logotipo del sitmotul" class="w-10 mx-auto ">
      <h1>Ingeniería Electromecánica</h1>
      <p v-if="info2.IE">listas {{ info2.IE.listas }}, faltantes {{ info2.IE.faltantes }}</p>
      <div class="md:flex flex-row mb-5 mt-5">
        <label class="md:px-2">0%</label>
        <div class="h-5 bg-[#FFBDF7] w-full rounded-lg mt-1 ">
        <div class="h-full bg-[#9336B4] rounded-lg " :style="{ width: `${((info2.IE.listas - info2.IE.faltantes)/info2.IE.listas)*100}%` }"></div></div>
        <label class="md:px-2">100%</label>
      </div>
        <label v-if="info2.IE"> Porcentaje completado: {{ (((info2.IE.listas - info2.IE.faltantes)/info2.IE.listas)*100).toFixed(0) }}%</label>
    </div>
    <div class=" flex flex-col text-white text-center bg-[#713ABE] p-2 rounded-lg w-11/12 h-4/5">
      <img src="../assets/IE.png" alt="logotipo del sitmotul" class="w-10 mx-auto ">
      <h1>Ingeniería Electrónica</h1>
      <p v-if="info2.IEM">listas {{ info2.IEM.listas }}, faltantes {{ info2.IEM.faltantes }}</p>
      <div class="md:flex flex-row mb-5 mt-5">
        <label class="md:px-2">0%</label>
        <div class="h-5 bg-[#FFBDF7] w-full rounded-lg mt-1 ">
        <div class="h-full bg-[#9336B4] rounded-lg " :style="{ width: `${((info2.IEM.listas - info2.IEM.faltantes)/info2.IEM.listas)*100}%` }"></div></div>
        <label class="md:px-2">100%</label>
      </div>
        <label v-if="info2.IEM"> Porcentaje completado: {{ (((info2.IEM.listas - info2.IEM.faltantes)/info2.IEM.listas)*100).toFixed(0) }}%</label>
    </div>
    </div>
    <div class="flex flex-row gap-5 mb-5 items-center justify-center">
    <div class=" flex flex-col text-white text-center bg-[#713ABE] p-2 rounded-lg w-11/12 h-4/5">
      <img src="../assets/IER.png" alt="logotipo del sitmotul" class="w-10 mx-auto ">
      <h1>Ingeniería en Energias Renovables</h1>
      <p v-if="info2.IER">listas: {{ info2.IER.listas }}, faltantes {{ info2.IER.faltantes }}</p>
      <div class="md:flex flex-row mb-5 mt-5">
        <label class="md:px-2">0%</label>
        <div class="h-5 bg-[#FFBDF7] w-full rounded-lg mt-1 ">
        <div class="h-full bg-[#9336B4] rounded-lg " :style="{ width: `${((info2.IER.listas - info2.IER.faltantes)/info2.IER.listas)*100}%` }"></div></div>
        <label class="md:px-2">100%</label>
      </div>
        <label v-if="info2.IER"> Porcentaje completado: {{ (((info2.IER.listas - info2.IER.faltantes)/info2.IER.listas)*100).toFixed(0) }}%</label>
    </div>
    <div class=" flex flex-col text-white text-center bg-[#713ABE] p-2 rounded-lg w-11/12 h-4/5">
      <img src="../assets/II.png" alt="logotipo del sitmotul" class="w-10 mx-auto ">
      <h1>Ingeniería Industrial</h1>
      <p v-if="info2.II">listas {{ info2.II.listas }}, faltantes {{ info2.II.faltantes }}</p>
      <div class="md:flex flex-row mb-5 mt-5">
        <label class="md:px-2">0%</label>
        <div class="h-5 bg-[#FFBDF7] w-full rounded-lg mt-1 ">
        <div class="h-full bg-[#9336B4] rounded-lg " :style="{ width: `${((info2.II.listas - info2.II.faltantes)/info2.II.listas)*100}%` }"></div></div>
        <label class="md:px-2">100%</label>
      </div>
        <label v-if="info2.II"> Porcentaje completado: {{ (((info2.II.listas - info2.II.faltantes)/info2.II.listas)*100).toFixed(0) }}%</label>
    </div>
    </div>
    <div class="flex items-center justify-center">
      <div class=" flex flex-col text-white text-center bg-[#713ABE] p-2 rounded-lg w-11/12 h-4/5">
        <img src="../assets/ISC.png" alt="logotipo del sitmotul" class="w-10 mx-auto ">
      <h1>Ingeniería en Sistemas Computacionales</h1>
      <p v-if="info2.ISC">listas {{ info2.ISC.listas }}, faltantes {{ info2.ISC.faltantes }}</p>
      <div class="md:flex flex-row mb-5 mt-5">
        <label class="md:px-2">0%</label>
        <div class="h-5 bg-[#FFBDF7] w-full rounded-lg mt-1 ">
        <div class="h-full bg-[#9336B4] rounded-lg " :style="{ width: `${((info2.ISC.listas - info2.ISC.faltantes)/info2.ISC.listas)*100}%` }"></div></div>
        <label class="md:px-2">100%</label>
      </div>
        <label v-if="info2.ISC"> Porcentaje completado: {{ (((info2.ISC.listas - info2.ISC.faltantes)/info2.ISC.listas)*100).toFixed(0) }}%</label>
    </div>
  </div>
  </div>
</div>
</div>
  </div>

</template>

<script setup>
import { onMounted, ref } from 'vue';

const info = ref({});
const isLoading = ref(true);

const info2 = ref({});
const isLoading2 = ref(true);

async function fetchData() {
  try {
    const response = await fetch('https://sitmotul.com.mx/api/statusEval');
    const data = await response.json();
    info.value = data;
    isLoading.value = false;
    console.log(data);
  } catch (error) {
    console.error('Error al obtener datos:', error);
  }
}

async function fetchDataApi() {
  try {
    const response = await fetch('https://sitmotul.com.mx/api/statusEvalIng');
    const data = await response.json();
    info2.value = data;
    isLoading2.value = false;
    console.log(data);
  } catch (error) {
    console.error('Error al obtener datos de API:', error);
  }
}

onMounted(() => {
  fetchData();
  fetchDataApi();

});
function formatDate(fecha) {
  const meses = ["Enero", "Febrero", "Marzo", "Abril", "Mayo", "Junio", "Julio", "Agosto", "Septiembre", "Octubre", "Noviembre", "Diciembre"];

  const fechaActual = new Date(fecha);
  const dia = fechaActual.getDate();
  const mes = meses[fechaActual.getMonth()];
  const año = fechaActual.getFullYear();

  return `${dia} de ${mes} de ${año}`;
}

const fechaFormateada = formatDate(info.fin);
console.log(fechaFormateada);

</script>



