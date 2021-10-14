<template>
    <div>
        <v-col
        cols="12"
        >
            <v-textarea
                v-model="memo"
                value=""
                outlined
                label="Add To-Do"
            ></v-textarea>

            <div style="position:absolute; right:10px; margin-top:-20px;">
                <v-btn
                    depressed
                    color="red"
                    style="margin-right:5px; color:white;"
                >
                Cancel
                </v-btn>

                <v-btn
                    @click="listAdd"
                    depressed
                    color="primary"
                >
                AddList
                </v-btn>
            </div>

        </v-col>
    </div>
</template>

<script>
    export default {
        name: 'listAdd',
        data() {
            return {
                memo: null
            }
        },
        methods: {
            listAdd(){
                console.log("리스트 추가")
                if(this.memo === null) {
                    alert("할일을 입력 해주세요")
                } else {
                    this.$emit("listAdd", this.memo)
                }
            },

            
        },
    }
</script>
