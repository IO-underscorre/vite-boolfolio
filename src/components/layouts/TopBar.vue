<script>
export default {
    name: 'TopBar',

    data() {
        return {
            links: [
                {
                    text: 'Home',
                    url: '/',
                },
            ]
        }
    }
}
</script>

<template>
    <div class="top-bar">
        <nav>
            <router-link class="logo" to="/">
                <img src="../../assets/logo.webp" alt="Arasaka Corporation">
            </router-link>

            <menu class="links">
                <li v-for="link in links" class="">
                    <router-link :to="link.url" class="link">
                        {{ link.text }}
                    </router-link>
                </li>
            </menu>
        </nav>
    </div>
</template>

<style lang="scss" scoped>
.top-bar {
    position: fixed;
    top: 0;
    width: 100%;
    height: $hgt-topbar;

    &>nav {
        height: 100%;
        @include align-container;
        @include display-flex('between', 'center');

        color: $clr-brand-primary;
        font-size: $fnt-size-l;
        font-weight: $fnt-weight-bd;
        text-shadow: 0 0 4px rgba($clr-brand-primary, .25);

        .logo {
            display: block;
            height: 50%;
            filter: drop-shadow(0px 0px 4px rgba($clr-brand-primary, .25));

            &:hover {
                animation: blink 3s infinite;
            }

            &:active {
                filter: brightness(50%);
                animation: none;
            }

            img {
                height: 100%;
            }
        }

        .links {
            @include display-flex('between', 'center');
            gap: $fnt-size-m;

            .link {
                &:hover {
                    animation: blink 3s infinite;
                }

                &:active {
                    filter: brightness(50%);
                    animation: none;
                }

                &.router-link-active {
                    text-shadow: 0 0 4px rgba($clr-brand-secondary, .25);
                    color: $clr-brand-secondary;
                }
            }
        }
    }
}

@keyframes blink {
    0% {
        -webkit-filter: brightness(100%);
        filter: brightness(100%);
    }

    50% {
        -webkit-filter: brightness(50%);
        filter: brightness(50%);
    }

    100% {
        -webkit-filter: brightness(100%);
        filter: brightness(100%);
    }
}
</style>