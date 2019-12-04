<template>
    <div role="banner"> 
        <header class="header">
            <div class="header__inner">
                <div class="header__logo-container">
                    <img class="header__logo-icon" src="~/assets/img/stickBW.svg" alt="Kim Alexis Torres">
                </div>
                <nav class="header__nav" role="navigation">
                    <ul class="header__ulist">
                        <li class="header__list-item">
                            <a class="header__nav-link" href="#Home" role="link">Home</a>
                        </li>
                        <li class="header__list-item">
                            <a class="header__nav-link" href="#About" role="link">About</a>
                        </li>
                        <li class="header__list-item">
                            <a class="header__nav-link" href="#Activities" role="link">Activities</a>
                        </li>
                    </ul>

                    <div :class="{header__burger: true, 'header__burger-transform': isActive}" @click="toAnimateMenu">
                        <div class="header__burger-bar1"></div>
                        <div class="header__burger-bar2"></div>
                        <div class="header__burger-bar3"></div>   
                    </div>
                </nav>

                 <div :class="{'header__burger-menu': true, 'header__burger-on': isActive}">
                    <ul class="header__burger-items">
                        <li class="header__burger-list-item">
                            <a class="header__burger-list-link" href="#Home" role="link">Home</a>
                        </li>
                        <li class="header__burger-list-item">
                            <a class="header__burger-list-link" href="#About" role="link">About</a>
                        </li>
                        <li class="header__burger-list-item">
                            <a class="header__burger-list-link" href="#Activities" role="link">Activities</a>
                        </li>
                    </ul>
                </div>
            </div>
        </header>
    </div>
</template>

<script>
    export default {
        name: 'Header',
        data() {
            return {
                isActive: false
            }
        },
        methods: {
            toAnimateMenu() {
                this.isActive ? 
                this.isActive = false :
                this.isActive = true;
            }
        }        
    }
</script>

<style lang="css" scoped>
        .container-fluid {
            width: 100%;
            margin-right: auto;
            margin-left: auto;
        }

        .header {
            padding: 4.2rem 3.5rem 4.2rem 3.5rem;
            -webkit-transition: padding .3s ease;
            transition: padding .3s ease;
            -webkit-transition: background-color .3s ease;
            transition: background-color .3s ease;
            z-index: 6;
        }

        .header--fixed {
            background: white;
            padding: 1.2rem 3.5rem 1.2rem 3.5rem;
        }

        .header__inner {
            display: -webkit-box;
            display: -ms-flexbox;
            display: flex;
            -webkit-box-sizing: inherit;
                    box-sizing: inherit;
            -webkit-box-pack: justify;
                -ms-flex-pack: justify;
                    justify-content: space-between;
            -webkit-box-align: center;
                -ms-flex-align: center;
                    align-items: center;
        }

        .header__nav {
            -webkit-box-sizing: inherit;
                    box-sizing: inherit;
            display: -webkit-box;
            display: -ms-flexbox;
            display: flex;
            -webkit-box-align: center;
                -ms-flex-align: center;
                    align-items: center;
        }

        .header__ulist {
            -webkit-box-sizing: inherit;
                    box-sizing: inherit;
            list-style: none;
            padding: 0;
            margin: 0;
            display: inline-block;
        }

        .header__list-item {
            -webkit-box-sizing: inherit;
                    box-sizing: inherit;
            margin-right: 4.8rem;
            display: -webkit-inline-box;
            display: -ms-inline-flexbox;
            display: inline-flex;   
        }

        .header__nav-link {
            font-size: 1.2rem;
            letter-spacing: .25px;
        }

        .header__nav-link:hover::after {
            width: 100%;
        }

        .header__nav-link::after {
            background-color: #000;
            content: "";
            display: block;
            height: 3px;
            -webkit-transition: width .3s;
            -o-transition: width .3s;
            transition: width .3s;
            width: 0;
        }

        .header__logo-container {
            display: -webkit-box;
            display: -ms-flexbox;
            display: flex;
            -webkit-box-pack: center;
                -ms-flex-pack: center;
                    justify-content: center;
            -ms-flex-line-pack: center;
                align-content: center;
        }

        .header__logo-icon {
            width: 77px;
            height: 77px;
        }

    @media screen and (max-width: 1023px) {
        .header__ulist {
            display: none;
        }

        .header__burger {
            display: inline-block;
            cursor: pointer;
            z-index: 13;
        }
    
        .header__burger-bar1,
        .header__burger-bar3 {
            border-radius: 3px;
            width: 35px;
            height: 5px;
            background-color: #333;
            margin: 6px 0;
            -webkit-transition: transform 0.2s;
            transition: transform 0.2s;    
        }
    
        .header__burger-bar2 {
            border-radius: 3px;
            width: 30px;
            height: 5px;
            background-color: #333;
            margin: 6px 0;
            -webkit-transition: width 0.2s;
            transition: width 0.2s;     
        }
    
        /* Rotate first bar */
        .header__burger-transform .header__burger-bar1 {
            -webkit-transform: rotate(-45deg) translate(-8.5px, 7px) ;
            transform: rotate(-45deg) translate(-8.5px, 7px) ;
        }
    
        /* Fade out the second bar */
        .header__burger-transform .header__burger-bar2 {
            width: 0;
        }
    
        /* Rotate last bar */
        .header__burger-transform .header__burger-bar3 {
            -webkit-transform: rotate(45deg) translate(-8.5px, 7px) ;
            transform: rotate(45deg) translate(-8.5px, -7px) ;
        }

        .header__burger-menu {
            position: fixed;
            top: 0;
            right: 0;
            border-radius: 0 0 0 100rem;
            width: 0;
            height: 0;
            background: orange;
            z-index: 12;
            transition: all 0.3s ease;
        }

        .header__burger-on {
            display: block;
            width: 50vw;
            height: 80vh;
        }

        .header__burger-items {
            -webkit-box-sizing: inherit;
                box-sizing: inherit;
            list-style: none;
            display: inline-block;
        }

        .header__burger-list-link {

        }
    }

</style>