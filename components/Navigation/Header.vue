<template>
    <div role="banner"> 
        <header class="header header--fixed container fluid">
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
                </nav>
            </div>
        </header>
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style lang="css" scoped>
    .container-fluid {
        width: 100%;
        margin-right: auto;
        margin-left: auto;
    }

    .header {
        padding: 4.2rem 5.7rem 4.2rem 3.5rem;
        -webkit-transition: padding .3s ease;
        transition: padding .3s ease;
        -webkit-transition: background-color .3s ease;
        transition: background-color .3s ease;
        z-index: 6;
    }

    .header--fixed {
        background: white;
        padding: 1.2rem 5.7rem 1.2rem 3.5rem;
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
        -webkit-transition: all .2s ease-in-out;
        transition: all .2s ease-in-out;
    }

    .header__nav-link:hover::after {
        width: 100%;
    }

    .header__nav-link::after {
        background-color: royalblue;
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
</style>