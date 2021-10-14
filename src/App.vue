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
                <todoList/>
                {{ todoList }}
            </v-col>

            <v-col cols="6">
                <addList
                    @listAdd="listAdd()"
                />
            </v-col>
        </v-row>
    </v-main>
</div>
    
<!-- 투두리스트 영역 끝 -->
  </v-app>
</template>

<script>
import todoList from './components/todoList';
import addList from './components/addList';

export default {
    name: 'App',
    data(){
        return{
            todoList: [],
        } 
    },

    components: {
        todoList,
        addList,
    },

    methods: {
        listAdd(memo) {
            this.todoList.push({
                memo : memo,
                status : "created"
            })
        },
    },

};
</script>
