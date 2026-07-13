<script setup>
import { reactive } from 'vue'

const genderList = ['Male', 'Female', 'UnIdentify']
const interestList = ['Sport', 'Reading', 'Politics', 'Game']

const submitForm =  ()=>{
  console.log('Submit')
  console.log(formData)
}

const formData = reactive({
  firstName: '',
  lastName: '',
  gender: '',
  interests: [],
  description: ''
})
</script>
<template>
  <div>
    <div>
      <div>First Name</div>
      <input type="text" name="firstName" v-model="formData.firstName">
    </div>
    <div>
      <div>Last Name</div>
      <input type="text" name="lastName" v-model="formData.lastName">
    </div>
    <div>
      <div>
        <div>Gender</div>
        <div v-for="gender in genderList">
          <!-- v-bind:something = attribute binding  short = :something-->
          <input type="radio" name="gender" :value="gender" v-model="formData.gender">
          {{ gender }}
        </div>
        <div>
          <div>interestList</div>
          <div v-for="interest in interestList">
            <input type="checkbox" name="interest" v-bind:value="interest" v-model="formData.interests">
            {{ interest }}
          </div>
        </div>
      </div>
      <div>Description</div>
      <textarea v-model="formData.description"></textarea>
    </div>
    <button @click="submitForm()">Submit</button>
  </div>
</template>