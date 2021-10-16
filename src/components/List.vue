<template>
    <div>
        <v-card
            class="pa-3"
            outlined
            style="margin:15px 0 0 20px; width:90%;"
            v-for="(list, index) in todoList"
            :key="index"
            :class="{ 'done': list.status === 'done' }"
        >
            <p>{{ list.memo }}</p>
            <v-row>
                <v-col class="text-right">

                    <!-- 삭제 -->
                    <v-btn 
                        @click="$emit('listDelete', index)"
                        fab text small color="red"
                    >
                        <v-icon>mdi-delete</v-icon>
                    </v-btn>

                    <!-- 수정 -->
                    <v-btn  v-if="list.status === 'created'"
                        fab text small color="orange"
                    >
                        <v-icon>mdi-pencil</v-icon>
                    </v-btn>
                    
                    <!-- 완료 -->
                    <v-btn v-if="list.status === 'created'"
                        @click="$emit('statusControl', index, 'done')"
                        fab text small color="primary"
                    >
                        <v-icon>mdi-check</v-icon>
                    </v-btn>

                    <!-- 부활 -->
                    <v-btn v-else
                        @click="$emit('statusControl', index, 'created')"
                        fab text small color="green"
                    >
                        <v-icon>mdi-rotate-left</v-icon>
                    </v-btn>
                </v-col>
            </v-row>
        </v-card>
    </div>
</template>

<script>
    export default {
        name: 'todoList',
        props:["todoList"],
        methods: {

        }
    }
</script>

<style scoped>
    .done {
        background-color:rgba(0, 0, 0, 0.1) !important;
    }

    .done p {
        text-decoration:line-through;
        color:rgba(0, 0, 0, 0.5);
    }
</style>
