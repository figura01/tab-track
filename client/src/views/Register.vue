<template>
    <div>
        <h2>Register View</h2>

        <form @submit.prevent="register">
            <input type="email" name="email" placeholder="email@email.com" v-model="email">
            <input type="password" name="password" v-model="password">
            <button>Register</button>
        </form>
    </div>
</template>

<script>
    import AuthService from '@/services/AuthentificationService'
    export default {
        data () {
            return {
               email: null,
               password: null 
            }
        },
        watch: {
            email (value) {
                console.log('email has changed', value)
            }
        },
        methods: {
            async register () {
                await AuthService.register({
                    email: this.email,
                    password: this.password
                })
            }
        }     
    }
</script>

<style scoped>

</style>