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
                            <a :class="{'header__burger-list-link': true, 'header__burger-list-link--active': isActive}" 
                                href="#Home" role="link">Home</a>
                        </li>
                        <li class="header__burger-list-item">
                            <a :class="{'header__burger-list-link': true, 'header__burger-list-link--active': isActive}" 
                                href="#About" role="link">About</a>
                        </li>
                        <li class="header__burger-list-item">
                            <a :class="{'header__burger-list-link': true, 'header__burger-list-link--active': isActive}" 
                                href="#Activities" role="link">Activities</a>
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
/* Header normal settings: >1024 */
.header {
    padding: 2.2rem 2.5rem;
    -webkit-transition: all .3s ease;
    transition: all .3s ease;
    z-index: 6;
}

/* Header normal settings: 1024+ */
@media screen and (min-width: 1024px) {
    .header {
        padding: 4.2rem 3.5rem;
        -webkit-transition: all .3s ease;
        transition: all .3s ease;
        z-index: 6;
    }

    /* Header scrolled settings */
    .header--fixed {
        background: white;
        padding: 1.2rem 3.5rem;
    }
}

/* Header inner div settings: Universal */
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

/* Header nav settings: Universal */
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

/* Header logo container div settings: Universal */
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

/* Header logo container div settings: >1024 */
.header__logo-icon {
    width: 4rem;
    height: 4rem;
}

/* Header logo container div settings: 1024+ */
@media screen and (min-width: 1024px) {
   .header__logo-icon {
        width: 5rem;
        height: 5rem;
    } 
}

/* Header large device nav links settings: >1024 */
/* ul CSS */
.header__ulist {
    display: none;
}

/* Header large device nav links settings: 1024+ */
@media screen and (min-width: 1024px) {
    /* ul CSS */
    .header__ulist {
        -webkit-box-sizing: inherit;
                box-sizing: inherit;
        list-style: none;
        padding: 0;
        margin: 0;
        display: inline-block;
    }

    /* li CSS */
    .header__list-item {
        -webkit-box-sizing: inherit;
                box-sizing: inherit;
        margin-right: 4.8rem;
        display: -webkit-inline-box;
        display: -ms-inline-flexbox;
        display: inline-flex;   
    }

    /* a CSS */
    .header__nav-link {
        font-size: 1.2rem;
        letter-spacing: .25px;
    }

    /* Hover anim CSS: set width to 100% from 0% */
    .header__nav-link:hover::after {
        width: 100%;
    }

    /* Hover anim CSS using ::after content */
    .header__nav-link::after {
        background-color: #000;
        content: "";
        display: block;
        height: 3px;
        -webkit-transition: width .3s;
        transition: width .3s;
        width: 0;
    }
}

/* Header burger menu settings: >1024 */
.header__burger {
    display: inline-block;
    cursor: pointer;
    z-index: 13;
}

/* Header burger menu settings: 1024+ */
@media screen and (min-width: 1024px) {
   .header__burger {
        display: none;
    }
}

/* Header burger lines settings: >1024 */
.header__burger-bar1,
.header__burger-bar3 {
    border-radius: 3px;
    width: 35px;
    height: 5px;
    background-color: #333;
    margin: 6px 0;
    -webkit-transition: all 0.3s ease;
    transition: all 0.3s ease;        
}
.header__burger-bar2 {
    border-radius: 3px;
    width: 30px;
    height: 5px;
    background-color: #333;
    margin: 6px 0;
    -webkit-transition: all 0.3s ease;
    transition: all 0.3s ease;     
}

/* Header burger lines animation settings: >1024 */
/* Rotate first bar */
.header__burger-transform .header__burger-bar1 {
    background: white;
    -webkit-transform: rotate(-45deg) translate(-8.5px, 7px) ;
    transform: rotate(-45deg) translate(-8.5px, 7px) ;
}
/* Shorten second bar */
.header__burger-transform .header__burger-bar2 {
    background: white;
    width: 0;
}
/* Rotate last bar */
.header__burger-transform .header__burger-bar3 {
    background: white;
    -webkit-transform: rotate(45deg) translate(-8.5px, 7px) ;
    transform: rotate(45deg) translate(-8.5px, -7px) ;
}

/* Header burger menu settings: >1024 */
.header__burger-menu {
    position: fixed;
    padding: 0;
    text-align: right;
    top: 0;
    right: 0;
    border-radius: 0 0 0 100rem;
    width: 0;
    height: 0;
    background: rgb(98, 37, 177);
    z-index: 12;
    -webkit-transition: all 0.3s ease;
    transition: all 0.3s ease;
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-pack: center;
        -ms-flex-pack: center;
            justify-content: center;
    -webkit-box-align: center;
        -ms-flex-align: center;
            align-items: center;
    visibility: hidden;
}

/* Header burger active settings: >1024 */
.header__burger-on {
    visibility: visible;
    padding: 2.2rem 2.5rem;
    width: 50vw;
    height: 80vh;
}

/* Header burger active settings: >1024 */
.header__burger-items {
    list-style: none;
    display: inline-block;
}

/* Header burger innate settings: >1024 */
.header__burger-list-link {
    font-size: 0rem;
    color: white;
    font-weight: 600;
    -webkit-transition: all .05s ease;
    transition: all .05s ease;
}

/* Header burger active settings: >1024 */
.header__burger-list-link--active {
    -webkit-transition: all .5s ease;
    transition: all .5s ease;
    letter-spacing: .25px;
    font-size: 1.7rem;
}
</style>