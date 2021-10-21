<template>
    <v-app>
        <div>
            <v-app-bar
                app
                color="primary"
                dark
            >
                <v-btn text href="/" class="d-flex align-center">
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
            <v-tabs
                v-model="tab"
                background-color="transparent"
                color="basil"
                grow
                >
                <v-tab
                    v-for="item in items"
                    :key="item"
                >
                    {{ item }}
                </v-tab>
            </v-tabs>
            <v-tabs-items v-model="tab">
                <v-tab-item v-for="item in items"
                            :key="item"
                >
                    <div v-if="tab === 0">
                        <div style = "text-align:center;">
                            <h1>할일 목록</h1>
                            <p>전체 할일: {{ todoList.length }}/ 완료돤 할일:{{ countDone }} / 남은 할일:{{ todoList.length - countDone }} </p>
                        </div>
                        <v-row>
                            <v-col cols="6">
                                <List
                                    :todoList="todoList"
                                    @statusControl="statusControl"
                                    @listDelete="listDelete"
                                />
                            </v-col>

                            <v-col cols="6">
                                <ListAdd 
                                    @listAdd="listAdd"
                                    @listEdit="listEdit"
                                />
                            </v-col>
                        </v-row>
                    </div>

                    <div v-if="tab === 1">
                        <div style = "width:100px; height:100px; background-color:red;"></div>
                    </div>
                </v-tab-item>
            </v-tabs-items>
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
            tab: null,
            items: [
                'TodoList', 'Routes', 'Deserts', 'Cocktails',
            ],
        }
    },
    computed: {
        countDone() {
            let count = 0
            this.todoList.forEach(list => {
                if (list.status === 'done') count++
            })
            return count
        }
    },
    methods: {
        listAdd(memo){
            this.todoList.push({ memo: memo, status: "created" })
            console.log(memo)
        },
        statusControl(index, status){
            this.todoList[index].status = status
        },

        listDelete(index){
            this.todoList.splice(index, 1)
        },

        listEdit(memo, index){
            this.todoList[index].memo = memo
        }
    }
    
};
</script>
