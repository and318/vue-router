<template>
<div id="app">
    <div id="nav">
        <router-link to="/">Portada</router-link> |
        <router-link to="/sobremi">Sobre Mí</router-link> |
        <router-link to="/contacto">Contacto</router-link> |
        <router-link to="/post/1">Último post</router-link>|
        <router-link to="/*">No Existe</router-link> |
    </div>
    <transition name="router-anim" mode="out-in">
        <router-view />
    </transition>
</div>
</template>

<style lang="scss">
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
}

#nav {
    padding: 30px;

    a {
        font-weight: bold;
        color: #2c3e50;

        &.router-link-exact-active {
            color: #42b983;
        }
    }
}

.router-anim-enter-active {
    animation: coming .3s;
    animation-delay: .2s;
    opacity: 0;
}

.router-anim-leave-active {
    animation: going .3s;
}

@keyframes going {
    0% {
        transform: translateX(0)
    }

    100% {
        transform: translateX(0px);
        opacity: 0;
    }
}

@keyframes coming {
    from {
        transform: translateX(0px);
        opacity: 0;
    }

    to {
        transform: translateX(0px);
        opacity: 1;
    }
}
</style>
