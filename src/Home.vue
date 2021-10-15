<template>
  <v-app>
      <div>
          <v-app-bar
            app
            color="primary"
            dark
            >
                <v-btn text href="/ " class="d-flex align-center">
                    <v-img
                    alt="Vuetify Logo"
                    class="shrink mr-2"
                    contain
                    src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
                    transition="scale-transition"
                    width="40"/>
                    <h1 style="font-weight:500;">VuetifyStudy</h1>
                </v-btn>

                <v-spacer></v-spacer>

                <v-btn
                    href="https://github.com/kibum0405/vue-vuetify"
                    target="_blank"
                    text>
                    <span class="mr-2">Github</span>
                    <v-icon>mdi-git</v-icon>
                </v-btn>
            </v-app-bar>
      </div>
      <!-- header  -->
    
<!-- 투두리스트 영역 -->
<div>
    <v-main>
        <v-row>
            <v-col cols="6">
                <List
                />
            </v-col>

            <v-col cols="6">
                <ListAdd
                    @listAdd="listAdd"
                />
            </v-col>
        </v-row>
    </v-main>
</div>
    
<!-- 투두리스트 영역 끝 -->
  </v-app>
</template>

<script>
import List from '@/components/List'
import ListAdd from '@/components/ListAdd'

export default {
    name: 'Home',
    components: {
        List,
        ListAdd
    },
    data() {
        return {
            todoList: [],
        }
    },
    methods: {
        listAdd(memo){
            this.todoList.push(memo)
            console.log(memo)
        }
    }
    
};
</script>
