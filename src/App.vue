<template>
  <div id="#app">
    <div class="app__container">
      <div class="container__progressbar"></div>
      <div class="container__form">
        <div class="form">
          <ul>
            <li v-for="form in forms">
               <div v-if="form.type === 'text'">
                <div class="form__title">
                  <div class="title__name">{{form.title}}</div>
                  <div class="title__icon">
                    <div :class="{iconError: form.error}"></div>
                    <div :class="{iconSuccess : form.success}"></div>
                  </div>
                </div> 
                 <input @blur="onBlur()" @focus="onFocus()"  v-model="form.validate" :type="form.type">
               </div>
               <div v-if="form.type === 'textarea'">
                 <div class="form__title">
                  <div class="title__name">{{form.title}}</div>
                </div>
                 <textarea></textarea>
               </div>
            </li>
          </ul>
          <button>Send</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      forms: [
        {
          id: 0,
          title: 'Name',
          type: 'text',
          validate: '',
          error: false,
          success: false,
        },
        {
          id: 1,
          title: 'Email',
          type: 'text',
          validate: ''
        },
        {
          id: 2,
          title: 'Phone',
          type: 'text',
          validate: ''
        },
        {
          id: 3,
          title: 'Message',
          type: 'textarea'
        },
      ]
    }
  },
  methods: {
      onBlur(){
        if(this.forms[0].validate === ''){
          this.forms[0].error = true
        }
      },
      onFocus(){
        if(this.forms[0].validate){
          this.forms[0].error = false
        }
      },
    },
}
</script>

<style lang="less" scoped>
@import url('./assets/stylus/main.less');
@import url('./assets/stylus/animation.less');

.app__container{
  max-width: 550px;
  margin: 100px auto;
  .container__progressbar{
    
  }
  .container__form{
    ul{
      li{
        list-style-type: none;
        margin-bottom: 20px;
      }
    }
  }
}

.form__title{
  display: flex;
  justify-content: space-between;
  padding-bottom: 10px;
  align-items: center;
  .title__name{
    font-family: "Roboto-bold";
    font-size: 22px;
    color: #000;
  }
  .title__icon{
    height: 15px;
    width: 15px;
  }
}

.iconError{
  height: 15px;
  background: url('./assets/images/error.png');
  background-size: cover;
}

.iconSuccess{
  height: 15px;
  background: url('./assets/images/valid.png');
  background-size: cover;
}

input{
  width: 100%;
  height: 40px;
  border-radius: 3px;
  border: 1px solid #ddd;
  box-sizing: border-box;
  padding: 0px 15px;
  font-family: "Roboto-regular";
  font-size: 16px;
  color: #000;
  outline: none;
}

textarea{
  width: 100%;
  height: 300px;
  border-radius: 3px;
  border: 1px solid #ddd;
  box-sizing: border-box;
  padding: 15px 15px;
  font-family: "Roboto-regular";
  font-size: 16px;
  color: #000;
  outline: none;
  resize: none;
}

button{
  font-family: "Roboto-regular";
  color: green;
  font-size: 18px;
  border: 1px solid green;
  height: 40px;
  width: 150px;
  background: #fff;
  cursor: pointer;
  outline: none;
  border-radius: 2px;
  -webkit-transition: all 0.3s ease;
  -moz-transition: all 0.3s ease;
  transition: all 0.3s ease;
  &:hover{
    background: green;
    color: #fff;
  }
}


</style>
