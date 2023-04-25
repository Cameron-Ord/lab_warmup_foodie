<template>
    <div>

    </div>
</template>

<script>
import axios from 'axios';

    export default {
        


        mounted(){


            axios({

                method: `GET`,

                url:`https://foodie.bymoen.codes/api/validate`,


                headers:{

                    'x-api-key': `qK2iR1gTkkAjPH0kfGDY`


                }

            }).then((response) =>{


                console.log(response);

            }).catch((error) =>{

                console.log(error);


            })


        }
    }
</script>

<style scoped>

</style>