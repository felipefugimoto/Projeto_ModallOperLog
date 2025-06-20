
<template>
    
    <img :src="vetorImg" alt="Imagem vetor" class="vetor" />
    <img :src="logoModalle" alt="Imagem log modall" class="logoModall" />
    <img :src="logoLoginn" alt="Imagem log login" class="logoModallWeb" />

 
</template>
<style>
    .vetor {
        position: absolute;
        bottom: 0;
        width: 100%;
    }
    .logoModall {
        position: absolute;
        right: 40px;
        bottom: 50px;
        width: 50%;
        max-width: 280px;
    }
    .logoModallWeb {
        width: 40%;
        max-width: 411px;
        position: absolute;
        bottom: 50%;
        right: 50%;
        transform: translateX(50%);
    }
    </style>

    
    <script setup lang="ts">
    import vetorImg from '@/assets/img/vetor.png';
    import logoModalle from '@/assets/img/logomodall.png'
    import logoLoginn from '@/assets/img/logologin.png'
    </script>