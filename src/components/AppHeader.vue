<template>
    <link rel="stylesheet" type="text/css" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.1.1/css/all.min.css">
    <nav class="navbar navbar-expand navbar-dark bg-success">
    <a href="/" class="navbar-brand">Ứng dụng Quản lý Cầm xe</a>
    <div class="mr-auto navbar-nav">
    <li class="nav-item">

    <router-link :to="{ name: 'contactbook' }" class="nav-link">
    Danh bạ
    <i class='fa fa-car'></i>
    
    </router-link>
    
    </li>
    </div>
    </nav>
</template>