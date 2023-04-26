<template>
    <div>

        <input placeholder="your email" class="email" type="value">
        <input placeholder="your name" class="name" type="value">
        <input placeholder="your last name" class="last_name" type="value">
        <input placeholder="your avatar" class="user_avatar" type="value">
        <input placeholder="username" class="username" type="value">
        <input placeholder="password" class="password" type="value">

        <button @click="sign_up">signup</button>

    </div>
</template>

<script>
import axios from 'axios';
import Cookies from 'vue-cookies';
    export default {
    
        
        data() {
            return {
       
            }
        },

        methods:{


            sign_up(){

                let email_input = document.querySelector(`.email`);

                let email_input_value = email_input[`value`];

                let name_input = document.querySelector(`.name`);

                let first_name_value = name_input[`value`];

                let last_name = document.querySelector(`.last_name`);

                let last_name_value = last_name[`value`];

                let avatar_input = document.querySelector(`.user_avatar`);

                let image_url_value = avatar_input[`value`];

                let username_input = document.querySelector(`.username`);

                let username_value = username_input[`value`];

                let password_input = document.querySelector(`.password`);

                let password_value = password_input[`value`];

                axios({

                   method: `POST`,

                   url: `https://foodie.bymoen.codes/api/client`,

                   headers:{

                    'x-api-key': `qK2iR1gTkkAjPH0kfGDY`

                   },

                   data:{


                    email: email_input_value,

                    first_name: first_name_value,

                    last_name: last_name_value,

                    image_url: image_url_value,

                    username: username_value,

                    password: password_value


                   }


                    
                }).then((response) => {

                    console.log(response);

                    Cookies.set(`token`, `${response[`data`][`token`]}`);

                    Cookies.set(`id`, `${response[`data`][`client_id`]}`)


                }).catch((error) =>{

                    console.log(error);

                })

            }

        }


    }
    
</script>

<style scoped>

</style>