<template>
  <div class="home">
    <video poster="../assets/home/concert.jpg" id="bgvid" playsinline autoplay muted loop>
      <!-- WCAG general accessibility recommendation is that media such as background video play through only once. Loop turned on for the purposes of illustration; if removed, the end of the video will fade in the same way created by pressing the "Pause" button  -->
      <source src="../assets/home/concert.webm" type="video/webm">
      <source src="../assets/home/concert.mp4" type="video/mp4">
    </video>
    <div class="full-screen-overlay"></div>
    <Row class="content">
      <Col span="24">
        <img class="logo" src="../assets/_global/logo.png" alt="">
        <div class="info">
          <p>Get Rewarded for Loving Music</p>
          <p>Sonotize is coming to Denver and Boulder</p>
          <p class="icant">I can't even rn.</p>
          <p>Yeah, I want rewards for going to shows!</p>
        </div>
        <Button type="ghost" shape="circle" class="sign-me-up">SIGN ME UP NOW</Button>

        <div class="sns">
          <span class="button-box">
            <Button type="ghost" class="facebook" icon="social-facebook" @click="openLink('facebook')"></Button>
          </span>
          <span class="button-box">
            <Button type="ghost" class="twitter" icon="social-twitter" @click="openLink('twitter')"></Button>
          </span>
          <span class="button-box">
            <Button type="ghost" class="instagram" icon="social-instagram" @click="openLink('instagram')"></Button>
          </span>
        </div>
      </Col>
    </Row>
  </div>
</template>

<script>
  export default {
    name: 'Home',
    data () {
      return {
        msg: 'This is Home'
      }
    },
    methods: {
      openLink: function (destination) {
        let url
        switch (destination) {
          case 'facebook':
            url = 'https://www.facebook.com/sonotize'
            break
          case 'twitter':
            url = 'https://twitter.com/sonotize'
            break
          case 'instagram':
            url = 'https://www.instagram.com/sonotize/'
            break
          default:
            url = ''
        }
        window.open(url, '_blank')
      }
    }
  }
</script>

<style lang="scss" scoped>
  .home{
    video {
      position: fixed;
      top: 50%;
      left: 50%;
      min-width: 100%;
      min-height: 100%;
      width: auto;
      height: auto;
      z-index: -100;
      transform: translateX(-50%) translateY(-50%);
      background: url('../assets/home/concert.jpg') no-repeat;
      background-size: cover;
      transition: 1s opacity;
    }

    .full-screen-overlay{
      position: fixed;
      top: 50%;
      left: 50%;
      min-width: 100%;
      min-height: 100%;
      width: auto;
      height: auto;
      z-index: -99;
      transform: translateX(-50%) translateY(-50%);
      background: rgba(0,0,0,0.7);
      background-size: cover;
      transition: 1s opacity;
    }

    $base-color: #00f7e0;

    .content{
      .logo{
        width: 5%;
        margin-bottom: 30px;
      }
      .info{
        color: #FFFFFF;
        font-size: 40px;
        p{
          margin-top: 15px;
          &.icant{
            margin-top: 40px;
            margin-bottom: 40px;
          }
        }
      }
      .sign-me-up{
        margin-top: 80px;
        font-size: 30px;
        color: $base-color;
        border-color: $base-color;
        border-width: 3px;
        padding: 10px;
        padding-left: 20px;
        padding-right: 20px;
        &:hover{
          color: #FFFFFF;
          background-color: $base-color;
        }
      }
      .sns{
        margin-top: 30px;
        color: $base-color;
        display: flex;
        justify-content: center;
        .button-box{
          width: 50px;
          display: flex;
          justify-content: center;
          button{
            width: 40px;
            font-size: 30px;
            background-color: transparent;
            color: $base-color;
            border-style: none;
            cursor: pointer;
            padding: 0;
            &:active{
              border-style: none;
            }
          }
        }
      }
    }

  }

</style>
