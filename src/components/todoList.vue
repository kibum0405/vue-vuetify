<template>
  <v-container style="width:100%;
    margin-top:20px;">
        <v-row>
            <div style = "width:49%; background-color:red;">123</div>

            <!-- 오른쪽 -->
            <div style = "width:49%; margin-left:2%;">
                <v-card  
                    style="width:100%;
                    height:300px;"
                >
                <v-card-title>todoList</v-card-title>
                    <v-textarea
                        height="150"
                        solo
                        label="todoList - text"
                        style="padding:3%;
                        margin-top:-20px;"
                    ></v-textarea>
                


                </v-card>
            </div>
        </v-row>
      
  </v-container>
</template>

<script>
  export default {
    name: 'todoList',
  }
</script>
