<script>
    import { createEventDispatcher } from 'svelte';
    const dispatch = createEventDispatcher();

    function loginClose(event) {
        if ((event.type == "click") || (event.keyCode == 27) ) {
            dispatch('loginClose', {

            });
        }
    }


</script>
<svelte:window on:keydown={loginClose}/>
<div class="login-container">
    <div on:click={loginClose} class="login-container__background"></div>
    <form class="login-container__window" onsubmit="log()">
        <p class="login-container__title">Войти</p>
        <div class="login-container__form">
            <input type="name" id="login" class="login-container__input" maxlength="20" required>
            <label for="login" class="login-container__label">Логин</label>
            <input type="password" id="password" class="login-container__input" maxlength="20" required>
            <label for="password" class="login-container__label">пароль</label>
        <p class="login-container__incorrect">Неверный логин или пароль</p>
            <a href="#" class="login-container__remember-password">Не помню пароль</a>
        </div>
        <div class="login-container__buttons">
            <button type="submit" class="login-container__button button login-container__button--login">Войти</button>
            <a href="#" class="login-container__button button login-container__button--registration">Зарегистрироваться</a>
        </div>
    </form>
</div>

<style>
    .login-container {
        position: absolute;
        width: 100%;
        height: 100%;
        position: fixed;
        top: 0;
        left: 0;
        z-index: 99;
    }

    .login-container__incorrect {
        color: #DF4B41;
        margin: 0;
        display: none
    }

    .visible {
        display: block;
    }

    .login-container__background {
        position: absolute;
        width: 100%;
        height: 100%;
        background-color: rgba(0, 0, 0, 0.2);
        z-index: 2;
    }

    .login-container__window {
        background-color: white;
        z-index: 3;
        position: absolute;
        top: 0;
        right: 0;
        left: 0;
        bottom: 0;
        margin: auto;
        width: 400px;
        height: 500px;
        border-radius: 5px;
        box-shadow: 0 0px 5px -1.5px #34495e;
        box-sizing: border-box;
        padding: 30px 30px;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
    }

    .login-container__title {
        font-size: 30px;
        margin-top: 0;
    }

    .login-container__form {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: flex-start;
    }

    .login-container__button {
        width: 100%;
        margin-top: 25px;
    }

    .login-container__button--login {
        background-color: #7f2620;
        color: white;
    }

    .login-container__button--login:hover, .login-container__button--login:focus {
        background-color: #8c2f2a;
    }

    .login-container__input {
        width: 100%;
        border: none;
        border-bottom: 1px solid #cccccc;
        font-size: 18px;
        margin-top: 25px;
    }

    .login-container__input:first-child {
        margin-top: 0;
    }

    .login-container__input:focus {
        outline: none;
        border-bottom: 1px solid #7f2620;
    }

    .login-container__label {
        color: #9d9d9d;
        text-transform: capitalize;
        position: relative;
        top: -27px;
        font-size: 18px;
        transition: 0.25s ease all;
        transform-origin: left;
    }

    #login:focus ~ .login-container__label[for="login"],
    #password:focus ~ .login-container__label[for="password"],
    #login:valid ~ .login-container__label[for="login"],
    #password:valid ~ .login-container__label[for="password"]{
        transform: scale(0.83);
        top: -47px;
    }

    .login-container__remember-password {
        color: #4981d7;
        text-decoration: none;
        margin-top: 10px;
        transition: 0.5s ease all;
    }

    .login-container__remember-password:hover {
    color: #0044bb;
    }

    .login-container__input--false {
        border-bottom: 1px solid #DF4B41;
    }

</style>