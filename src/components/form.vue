<template>
  <div class="login-wrap">
    <input type="radio" class="signIn" name="reg" id="entrance" checked><label for="entrance" class="tab" @click="showForm(1)">Вход</label>
    <input type="radio" class="signUp" name="reg" id="registr" checked><label for="registr" class="tab" @click="showForm(2)">Регистрация</label>

    <transition name="component-fade">
    <form action="#" class="signInForm" v-show="showSignInForm">
      <div class="input-group">
        <label for="email" class="label">Почта</label>
        <input type="email" id="email" class="input">
      </div>

      <div class="input-group">
        <label for="pass" class="label">Пароль</label>
        <input type="password" id="pass" class="input">
      </div>

       <button type="submit">ВОЙТИ</button>
          <div class="hr"></div>
          <div class="footer-link">
            <a href="#forgot">Забыли пароль?</a>
          </div>
    </form>  
    </transition>

    <transition name="component-fade">
       <form action="#" class="signUnForm" v-show="showSignUpForm">
      <div class="input-group">
        <label for="email" class="label">Почта</label>
        <input type="email" id="email" class="input">
      </div>

      <div class="input-group">
        <label for="pass" class="label">Пароль</label>
        <input type="password" id="pass" class="input">
      </div> 

      <div class="input-group">
        <label for="pass2" class="label">Повторите пароль</label>
        <input type="password" id="pass2" class="input">
      </div>

      <button type="submit">РЕГИСТРАЦИЯ</button>
          <div class="hr"></div>
          <div class="footer-link">
            <label for="tabInput">Уже зарегестрированы?</label>
          </div>
    </form>  
    </transition>
  </div>
</template>

<script>
  export default {
  data() {
    return {
      showSignInForm: true,
      showSignUpForm: false,
    }
  },
  methods: {
    showForm(num) {
      switch (num) {
        case 1:
          this.showSignInForm = true
          this.showSignUpForm = false
          break;
        case 2:
          this.showSignInForm = false
          this.showSignUpForm = true
          break;
      
        default:
          break;
      }
    }
  }
};
</script>

<style scoped>
  .login-wrap{ 
  width: 100%;
  margin:0 auto;
  max-width: 400px;
  min-height: 400px;
  position: relative;   
  box-shadow: 0 12px 15px 0 rgba(0,0,0,.24),0 17px 50px 0 rgba(0,0,0,.19);
  padding: 50px 50px 50px 50px;
  background: #eaeaea;
  border-radius: 10px;
}

.component-fade-enter-active, .component-fade-leave-active {
    transition: opacity .3s ease;
  }
  .component-fade-enter, .component-fade-leave-to{
    opacity: 0;     
  }

  .signIn,.signUp{
    display: none;
  }

  .tab{
    font-size: 18px;
    margin-right: 15px;
    padding-bottom: 5px;
    margin: 10px 10px 20px 0px;
    display: inline-block;
    border-bottom: 2px solid transparent ; 
    text-transform: uppercase;
    cursor: pointer;
  }

  .signInForm,.signUpForm{
    top: 120px;
    left: 50px;
    right: 50px;
    position: absolute;
  }

  .input-group{
    margin-bottom: 15px;
  }

  .label{
        text-transform: uppercase;
        width: 100%;
        color: #6D6D6D;
        display: block;
        font-size: 12px;
        cursor: pointer;
      }

      .input{
        width: 100%;
        color: silver;
        display: block;
        border: 1px solid #CECECE;
        padding: 15px 0;
        background: #EAEAEA;
      }

    .input[data-type="password"]{
        text-security: circle;    
      }

    .input:focus{
        outline: none;
        border: 1px solid black;
        }

    button{
      text-transform: uppercase;
      border: none;
      padding: 15px 20px;      
      width: 100%;
      color: #fff;
      display: block;
      background: primary_color;
      outline: none;
      cursor: pointer;
      }

    button:active{
      opacity: 0.7;      
    }

    .hr{
      height: 2px;
      margin: 10px 0 10px 0;
      background: silver;
    }

    .footer-link{
      text-align: center;   
    }

    a{ 
        color: inherit; 
        text-decoration: none;
      }
      a:hover{
        color: silver;
      }
      
               
      label:hover{
        color: silver;
      }
</style>