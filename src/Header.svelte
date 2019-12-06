<script>
    import { createEventDispatcher } from 'svelte';
    const dispatch = createEventDispatcher();

    function loginOpen(e) {
        e.srcElement.blur();
        dispatch('loginOpen', {
            // toggle: false
        });
    }
</script>

<header class="header">
    <div class="header__logo logo-container">
    <a href="http://www.kstu.ru/"><img src="img/logo.png" class="logo-container__logo logo"></a>
    <h1 class="logo-container__title title"><a href="#" class="title__link">Вестник технологического университета</a></h1>
    </div>

    <div class="header__user">
            <div class="find header__find">
                <input type="text" class="find__input" placeholder="Введите поисковый запрос">
            </div>
    <button on:click={loginOpen} class="account-button account-button--login button header__button">войти</button>
    <button onclick="logPopup('registration')" class="account-button account-button--registration button header__button">регистрация</button>
            <a href="#" class="user-login header__user">
                <span class="user-login__name">admin</span>
                <img src="img/user-icon.png" class="user-login__img">
            </a>
    </div>
</header>

<style>
    .header {
        display: flex;
        justify-content: space-between;
        padding: 17px 20px;
        border-bottom: 1px solid #e8e8e8;
        border-top: none;
        background-color: white;
        box-shadow: 0 5px 5px -8px #34495e;
        }

    .header__user {
        display: flex;
        align-items: center;
    }

    .header__button {
        margin-left: 20px; 
    }

    .logo {
        width: 60px;
        display: block;
    }
</style>