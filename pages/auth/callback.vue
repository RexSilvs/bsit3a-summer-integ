<template>
    <div class="p-4">Signing you in...</div>
</template>
<script>
export default {
    async mounted() {
        try {
            await this.$auth.fetchUser()
            this.$router.replace('/')
        } catch (error) {
            console.error('Login Failed:', error);
            this.$router.push('/auth/login')
        }
    }
}
</script>