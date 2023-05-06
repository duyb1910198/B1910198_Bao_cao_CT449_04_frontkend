<script>
export default {
    props: {
        user: { type: Object, required: true },
    },
};
</script>
<template>
    <div>
        <div class="p-1">
            <strong class="text-info">Cho phép truy cập:&nbsp;</strong>
            <router-link v-if="user.access" :to="{ name: 'postbook' }" data-toggle="tooltip" data-placement="right" title="Chuyển đến trang post">
                <i class="fa-solid fa-circle-check"></i>
            </router-link>
            <i v-else class="fa-regular fa-circle-xmark text-danger"></i>

        </div>
    </div>
</template>

