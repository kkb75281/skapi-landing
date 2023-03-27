<template lang="pug">
main
  section.sectionBox
    .overflow
      .helloSkapi
        .helloCont
          .tit
            .withImg 
              img.icon1(src="@/assets/img/Asset5.svg")
              em Empower
              img.icon2(src="@/assets/img/Asset4.svg")
              img.icon3(src="@/assets/img/Asset3.svg")
              img.icon4(src="@/assets/img/Asset2.svg")
            .withImg 
              img.icon5(src="@/assets/img/Asset8.svg")
              em Your Website with 
              img.icon6(src="@/assets/img/Asset7.svg")
            .withBtn
              span Robust Backend API
              button GET STARTED
                img(src="@/assets/img/Asset9.svg")
          p "Welcome to skapi, a robust and easy-to-use API service designed to help developers build faster, more efficient, and scalable applications. Our platform offers a suite of advanced tools and features, allowing you to streamline your development process and focus on what matters most: creating incredible user experiences."
          button.readBtn Read Document
  section.sectionBox.showVideo
    .videoCont 
      img(src="@/assets/img/video.svg")
  section.sectionBox.features
    .feaCont 
      h3 Key Features
    .cardWrap 
      .cardInner
        .card
          .cardIcon 
            img(src="@/assets/img/Asset21.svg" style="width: 103px;")
          .cardCont
            h4 Serverless Architecture
            p Embrace the simplicity of skapi's 100% serverless architecture. Say goodbye to dealing with terminals, installing frameworks on your machine, or worrying about scalability. With skapi, you can focus on building incredible web services without the hassle.
        .card
          .cardIcon 
            img(src="@/assets/img/Asset14.png" style="width: 72px;")
          .cardCont
            h4 Database
            p Experience the power of an auto-indexed, scalable database that combines the best of relational and NoSQL architectures. skapi's innovative database solution ensures optimal performance and flexibility for your web services.
        .card
          .cardIcon 
            img(src="@/assets/img/Asset21.svg")
          .cardCont
            h4 Serverless Architecture
            p
        .card
          .cardIcon 
            img(src="@/assets/img/Asset21.svg")
          .cardCont
            h4 Serverless Architecture
            p
  section.sectionBox.getStart
  section.sectionBox.trySkapi
</template>

<script setup>

</script>

<style lang="less">
main {
  height: 100%;
  background-color: #f5f5f5;

  .sectionBox {
    .overflow {
      width: 100vw;
      overflow: hidden;
      position: relative;
  
      &::before {
        position: absolute;
        content: '';
        bottom: 200px;
        left: 50%;
        transform: translateX(-50%);
        width: 2024px;
        height: 440px;
        background: url(../assets/img/Asset10.svg) no-repeat;
      }
      .helloSkapi {
        width: 1024px;
        height: 100vh;
        margin: 0 auto;
        display: flex;
        align-items: center;
        justify-content: center;

        .helloCont {
          position: relative;
          text-align: center;
          
          .tit {
            font-size: 60px;
            font-weight: 700;
            margin-bottom: 128px;
            color: #262626;
            &:nth-child(2) {
              padding-top: 24px;
            }
            .withImg {
              display: flex;
              font-style: normal;
              align-items: center;
              justify-content: center;
              color: #293FE6;
  
              em {
                padding: 0 25px;
              }
              img {
                &.icon1 {
                  width: 100px;
                }
                &.icon2 {
                  width: 68px;
                  padding-right: 35px;
                }
                &.icon3 {
                  width: 92px;
                  padding-right: 25px;
                }
                &.icon4 {
                  width: 161px;
                }
                &.icon5 {
                  width: 127px;
                }
                &.icon6 {
                  width: 137px;
                }
              }
            }
            .withBtn {
              display: flex;
              align-items: center;
              justify-content: center;
              margin-top: 23px;
  
              span {
                position: relative;
    
                &::before {
                  position: absolute;
                  content: '';
                  width: 100%;
                  height: 100%;
                  background: linear-gradient(183.26deg, #FAFF00 2.7%, rgba(255, 230, 0, 0) 94.99%);
                  z-index: -1;
                }
              }
              button {
                width: 402px;
                height: 70px;
                border: 0;
                outline: 0;
                font-size: 24px;
                margin-left: 21px;
                padding-left: 34px;
                background: url(../assets/img/Asset6.svg) no-repeat;
                color: #fff;
                display: flex;
                align-items: center;
                cursor: pointer;
                img {
                  width: 42px;
                  padding-left: 20px;
                }
              }
            }
          }
          p {
            position: relative;
            font-size: 24px;
            font-weight: 500;
            color: #262626;
          }
          .readBtn {
            position: relative;
            width: 180px;
            height: 40px;
            font-weight: 700;
            font-size: 16px;
            margin-top: 62px;
            color: #fff;
            background: #293FE6;
            border: 0.5px solid #8C8C8C;
            box-shadow: inset -1px -1px 2px rgba(0, 0, 0, 0.25), inset 1px 1px 2px rgba(255, 255, 255, 0.65);
            border-radius: 4px;
            cursor: pointer;
          }
        }
      }
    }
    &.showVideo {
      width: 1024px;
      height: 100vh;
      margin: 0 auto;
      display: flex;
      align-items: center;
      justify-content: center;
      
      .videoCont {
        img {
          width: 621px;
          height: 363px;
        }
      }
    }
    &.features {
      position: relative;
      height: 100vh;
      display: flex;
      align-items: center;

      .feaCont {
        width: 1024px;
        margin: 0 auto;
        padding-bottom: 400px;

        h3 {
          font-size: 32px;
          font-weight: 700;
        }
      }
      .cardWrap {
        position: absolute;

        .cardInner {
          width: 100%;
          display: flex;
          flex-wrap: nowrap;
          box-sizing: border-box;

          .card {
            width: 460px;
            height: 280px;
            background: #fafafa;
            box-shadow: 4px 4px 4px rgba(0, 0, 0, 0.25);
            border-radius: 8px;
            margin-right: 40px;
            padding: 0 30px;
            display: flex;
            flex-wrap: nowrap;

            .cardIcon {
              width: 30%;
              padding-right: 30px;
              display: flex;
              align-items: center;
              justify-content: center;

              img {
                width: 100%;
              }
            }
            .cardCont {
              width: 70%;

              h4 {
                font-size: 20px;
                font-weight: 700;
                margin: 0;
                padding: 40px 0 18px 0;
              }
              p {
                font-size: 14px;
                font-weight: 400;
                line-height: 24px;
                margin: 0;
              }
            }
          }
        }
      }
    }
  }
}
</style>