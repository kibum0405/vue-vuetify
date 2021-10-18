<template>
    <div>
        <v-col
            cols="12"
        >
            <v-textarea
                v-model="memo"
                outlined
                label="Add To-Do"
            ></v-textarea>

            <div style="position:absolute; right:10px; margin-top:-20px;">

                <v-btn v-if = "mode === 'add'"
                    @click="listAdd"
                    color="primary"
                >
                    AddList
                </v-btn>
                <v-btn v-else
                    @click="listEdit"
                    color="orange"
                    style="color:white;"
                >
                    listEdit
                </v-btn>
            </div>

        </v-col>
    </div>
</template>

<script>
import { eventBus } from "../main"
export default {
    data() {
        return{
            memo: null,
            index: null,
            mode: "add"
        }
    },
    created() {
        eventBus.$on("listEdit", (memo, index) => {
            this.memo = memo
            this.index = index
            this.mode = "edit"
        });
    },
    methods: {
        listAdd(){
            if(this.memo === null) {
                console.log('할일을 입력 해주세요')
            } else {
                this.$emit("listAdd", this.memo)
                this.memo = null
            }
        },
        listEdit(){
            if(this.memo === null) {
                console.log('할일을 입력 해주세요')
            } else {
                this.$emit("listEdit", this.memo, this.index)
                this.memo = null
                this.mode = "add"
            }
        }
    },
}
</script>
