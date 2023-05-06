<script>
export default {
    props: {
        post: { type: Object, required: true },
    },

    data: () => ({
        date: '',
        time: ''
    }),

    methods: {
        printDate: function () {
            return new Date().toLocaleDateString();
        },
        printTime: function () {
            return new Date().toLocaleTimeString();
        }
    },
    mounted: function() {
        this.date = this.printDate();
        this.time = this.printTime();
    },
};
</script>
<template>
    <div>
        <div class="btn btn-outline-light">
            <div class="font-weight-bold t-det-title p-1 text-center text-info">
            <strong class="text-success">Tác giả: </strong>
            {{ post.title }}
        </div>
        <div class="text-mute t-det-title p-1 text-center text-info">
            <strong class="text-success">Cập nhật lần cuối: </strong>
            {{ date }}, {{ time }}
        </div>
        <div class="t-det-title p-1 text-center">
            <strong class="text-success">Trạng thái: </strong>
            <span v-if="post.completed" class="text-success"> hoàn thành</span>
            <span v-else class="text-danger"> chưa hoàn thành</span>
        </div>
        <div class="t-det-title p-1 text-center">
            <img :src="post.image" alt="aa">
        </div>
        </div>
        <div class="p-1 text text-left text-info">
            {{ post.des }}
        </div>
    </div>
</template>