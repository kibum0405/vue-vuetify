<template>
  <v-container>
        <h1 align="center">뷰 기초 익히기</h1>
        <div>이름 : {{ person.name }} / 나이 : {{ person.age }}</div>
        <v-btn @click="plus()" color="primary">plus</v-btn>
        <v-btn @click="subtract()" color="red">subtract</v-btn>

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
        plus() {
            if(this.person.age < 20 && this.person.name == "park") {
                this.person.age = this.person.age +1
            } else {
                this.person.age = this.person.age -1
            }
        },
        subtract() {
            if(this.person.name == "park") {
                this.person.age = this.person.age -1
            }
        }
    }
}
</script>

<style>

</style>