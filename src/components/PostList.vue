<script>
export default {
    props: {
        posts: { type: Array, default: [] },
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
<div class="">
    <div class="row d-flex">
        <div class="card m-2 text-success" style="width: 16rem;"
            v-for="(post, index) in posts"
            :key="post._id"
            :class="{ active: index === activeIndex }"
            @click="updateActiveIndex(index)"
        >
            <img class="card-img-top img-fluid" :src="post.image" alt="Card image cap">
            <div class="card-body">
            <h5 class="card-title">
                {{ post.title }}</h5>
            <p class="card-text">
                <strong ><i class="fa-solid fa-user"></i> Tác giả:</strong>
                {{ post.author }}</p>
            <p class="card-text">
                <strong>
                    <i v-if="post.completed" class="fa-regular fa-circle-check"></i>
                    <i v-else class="fa-regular fa-circle-xmark"></i>
                     Hoàn thành&nbsp;</strong>

            </p>
            </div>
        </div>
    </div>
</div> <hr>


</template>

