<template>
  <v-container>
      <h1 align="center">뷰 기초 익히기</h1>
      <div>이름 : {{ person.name }} / 나이 : {{ person.age }} 123</div>
      <v-btn @click="add()"></v-btn>

  </v-container>
</template>

<script>
export default {
    name:'vueStudy',
    data() {
        return {
            person: {
                name: 'park',
                age: 10,
            }
        }
    },
    methods: {
        add() {
            if(this.person.name == "park") {
                this.person.age = 18
            }
        }
    }
}
</script>

<style>

</style>