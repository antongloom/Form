<template>
  <div id="#app">
    <div class="app__container">
      <div class="container__progressbar"></div>
      <div class="container__form">
        <div class="form">
          <ul>
            <li>
              <div class="form__title">
                <div class="title__name">Name</div>
                <div class="title__icon">
                  <img src="./assets/images/error.png" alt="Img">
                </div>
              </div>
              <input type="text">
            </li>
            <li>
              <div class="form__title">
                <div class="title__name">Email</div>
                <div class="title__icon">
                  <img src="./assets/images/error.png" alt="Img">
                </div>
              </div>
              <input type="text">
            </li>
            <li>
              <div class="form__title">
                <div class="title__name">Phone</div>
                <div class="title__icon">
                  <img src="./assets/images/error.png" alt="Img">
                </div>
              </div>
              <input type="text">
            </li>
            <li>
              <div class="form__title">
                <div class="title__name">Message</div>
              </div>
              <textarea></textarea>
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
  name: 'App'
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
    img{
      height: 15px;
    }
  }
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
