<template>
    <div class="page t-edit my-3">
        <LoginForm
        @submit:login="login"
        />
    </div>
</template>

<script>
import LoginForm from "@/components/LoginForm.vue";

export default {
    components: {
        LoginForm,
    },



}

</script>
