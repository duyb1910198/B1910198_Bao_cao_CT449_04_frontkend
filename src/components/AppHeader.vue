<template>
    <nav class="navbar navbar-expand navbar-dark bg-dark" style="background: #005c6b;">
        <a href="/" class="navbar-brand text-success">Ứng Dụng Quản Lý Truyện</a>
        <div class="ml-auto navbar-nav">
            <li class="nav-item">
                <router-link :to="{ name: 'postbook' }" class="nav-link text-success">
                    Truyện
                    <i class="fa-regular fa-bookmark"></i>
                </router-link>
            </li>
            <li class="nav-item">
                <router-link :to="{ name: 'userbook' }" class="nav-link text-success">
                    Người dùng
                    <i class="fas fa-user"></i>
                </router-link>
            </li>
        </div>
    </nav>
</template>