<script>
export default {
    props: {
        users: { type: Array, default: [] },
        activeIndex: { type: Number, default: -1 },
    },
    emits: ["update:activeIndex"],
    methods: {
        updateActiveIndex(index) {
            this.$emit("update:activeIndex", index);
        }
    }
};
</script>
<template>
    <table class="table">
        <thead class="text-warning bg-dark">
            <tr>
            <th scope="col"><strong>Tên</strong></th>
            <th scope="col"><strong>Email</strong></th>
            <th scope="col"><strong>Địa chỉ</strong></th>
            <th scope="col"><strong>SĐT</strong></th>
            <th scope="col"><strong>Truy cập Post</strong></th>
            </tr>
        </thead>

        <tbody class="text-info">
            <tr
                v-for="(user, index) in users"
                :key="user._id"
                :class="{ active: index === activeIndex }"
                @click="updateActiveIndex(index)"

            >
                <td>
                    {{ user.name }}
                </td>
                <td>
                    {{ user.email }}
                </td>
                <td>
                    {{ user.address }}
                </td>
                <td>
                    {{ user.phone }}
                </td>
                <td class="text-center">
                    <router-link v-if="user.access" :to="{ name: 'postbook' }" data-toggle="tooltip" data-placement="right" title="Chuyển đến trang post">
                        <i class="fa-regular fa-circle-check"></i>
                    </router-link>
                    <i v-else class="fa-regular fa-circle-xmark text-danger"></i>
                </td>
            </tr>
        </tbody>
    </table> <hr>

</template>