<!-- <script setup>
import { ref , computed} from 'vue';

const firstName = ref('')
const lastName = ref('')

// copmputed ใช้กับตัวแปร reactive
// computed เก็บ cache ไว้ในตัวแปร
const fullName = computed(() => {
  return `${firstName.value} ${lastName.value}`
})

const now = computed(() => Date.now())

// const newFullName = () => {
//   return `${firstName.value} ${lastName.value}`
// }
</script> -->


<!--<template>
  <div>
    {{ fullName }}
    {{ now }}
    {{ newFullName() }}
  </div>
  <div>
    Firstname<input type="text" v-model="firstName">
    Lastname<input type="text" v-model="lastName">
  </div>
  </template>-->


  <!-- Exchange Money -->
  <!-- <script setup>
  import { ref, computed } from 'vue';
  const priceUSD = ref(1)
  const exchangeRate = 35
  const priceTHB = computed({
    get: () => {
      return priceUSD.value * exchangeRate
    },
    set: (newValue) => {
      priceUSD.value = (newValue/ exchangeRate)
    }
  })

</script>

<template>
  <div>
  USD {{ priceUSD }} = THB {{ priceTHB }}
  </div>
  <div>
    THB <input type="text" v-model="priceTHB">
    USD <input type="text" v-model="priceUSD">
  </div>
</template> -->

<!-- Watcher -->
 <script setup>
import { ref, computed } from 'vue';

const upperFullname = computed(()=> {
  return fullname.value.toUpperCase()
})

const fullname = ref('')
</script>

<template>
<div>
  <div> Fullname: {{ upperFullname }}</div>
  <input type="text" v-model="fullname">
</div>
</template>