<template lang="pug">
main
  section.sectionBox
    .overflow
      .helloSkapi
        .helloCont
          img.logo(src="@/assets/img/Skapi_logo.svg")
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
              span A Robust Backend API
              button GET STARTED
                img(src="@/assets/img/Asset9.svg")
            .arrowImg 
              img(src="@/assets/img/Asset1.svg")
          h3 Welcome to Skapi
          p "Welcome to skapi, a robust and easy-to-use API service designed to help developers build faster, more efficient, and scalable applications. Our platform offers a suite of advanced tools and features, allowing you to streamline your development process and focus on what matters most: creating incredible user experiences."
          button.readBtn Read Document
  section.sectionBox.showVideo
    .videoCont 
      img(src="@/assets/img/video.svg")
  section.sectionBox.features
    .feaCont 
      .cardTit
        h3 Key Features
      .cardWrap()
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
              img(src="@/assets/img/Asset15.png" style="width: 86px;")
            .cardCont
              h4 Authentication
              p Take advantage of unlimited, pay-as-you-go cloud storage with skapi. Whether it's web hosting or serving large files with security restrictions, our platform provides the flexibility and reliability you need to manage your digital assets.
          .card
            .cardIcon 
              img(src="@/assets/img/Asset16.png" style="width: 122px;")
            .cardCont
              h4 Cloud Storage
              p Take advantage of unlimited, pay-as-you-go cloud storage with skapi. Whether it's web hosting or serving large files with security restrictions, our platform provides the flexibility and reliability you need to manage your digital assets.
  section.sectionBox.getStart
    .startCont 
      h3 Getting Started
      .levelWrap 
        .levelBar 
          .lb.lb1 
            .num 01
            .dot
          .lb.lb2
            .num 02
            .dot
          .lb.lb3 
            .num 03
            .dot
        .levelInner
          .level.lv1
            .lvCont
              .lvTit Create Service
              .lvDesc Log and Create new Service from your dashboard 
            .lvImg 
              img(src="@/assets/img/lvImg1.png" style="width: 512px;")
          .level.lv2
            .lvCont
              .lvTit Retrieve ID
              .lvDesc Retrieve the service ID and the owner’s ID from the dashboard
            .lvImg 
              img(src="@/assets/img/lvImg2.png" style="width: 512px;")
          .level.lv3
            .lvCont
              .lvTit Initialize Skapi
              .lvDesc
                | Import and Initialize Skapi from index.html. Replace
                br
                em ‘SERVICE_ID’ 
                | and 
                br
                em ‘OWNERS_ID’ 
                | with appropriate value.
            .lvImg.preCode
              pre
                code 
                  |&lt;!DOCTYPE html&gt;
                  |  &lt;head&gt;
                  |    &lt;script src="https://broadwayinc.dev/lib/js/skapi/latest/skapi.js"&gt;&lt;/script&gt;
                  |  &lt;/head&gt;
                  |  &lt;script&gt;
                  |    let skapi = new Skapi('
                  span SERVICE_ID
                  | ', '
                  span OWNERS_ID
                  | ');
                  |  &lt;/script&gt;
  section.sectionBox.trySkapi
      .tryCont 
        h3 DON’T JUST TAKE OUR WORD FOR IT
        h2 Ready to try Skapi?
        button.startBtn Get Started
</template>

<script setup>
import { onMounted, ref } from 'vue';

let currentScroll = ref(0);

onMounted(() => {
  let features = document.querySelector('.features');
  let featuresTop = features.offsetTop + 200;
  let cardTit = document.querySelector('.cardTit');
  let feaContPoition = cardTit.getBoundingClientRect();
  let cardWrap = document.querySelector('.cardWrap');
  let cardInner = document.querySelector('.cardInner');
  
  cardWrap.style.left = feaContPoition.left + "px";
  
  window.addEventListener('scroll', () => {
    let moveSpeed = (currentScroll - featuresTop) * 2;
    let cardInnerRight = cardInner.getBoundingClientRect().right - 1024;
    currentScroll = window.scrollY + (window.innerHeight/2);

    if(currentScroll >= featuresTop) {
      cardWrap.style.left = (feaContPoition.left - moveSpeed) + "px";
    }

    document.querySelectorAll('.lb').forEach((lb) => {
      let num = lb.querySelector(".num");
      let dot = lb.querySelector(".dot");

      if(currentScroll >= lb.offsetTop) {
        num.classList.add('active');
        dot.classList.add('active');
      } else {
        num.classList.remove('active');
        dot.classList.remove('active');
      }
    })

  })

})
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
        top: 545px;
        left: 50%;
        transform: translateX(-48%);
        width: 2024px;
        height: 440px;
        background: url(../assets/img/Asset10.svg) no-repeat;
      }
      .helloSkapi {
        width: 1024px;
        // height: 100vh;
        margin: 0 auto;

        .helloCont {
          position: relative;
          text-align: center;
          
          .logo {
            width: 320px;
            margin-top: 110px;
          }
          .tit {
            position: relative;
            font-size: 52px;
            font-weight: 700;
            margin: 35px 0 100px 0;
            color: #262626;

            .withImg {
              display: flex;
              font-style: normal;
              align-items: center;
              justify-content: center;
              color: #293FE6;
              margin-bottom: 10px;
  
              em {
                padding: 0 25px;
              }
              img {
                &.icon1 {
                  width: 74px;
                }
                &.icon2 {
                  width: 59px;
                  padding-right: 30px;
                }
                &.icon3 {
                  width: 80px;
                  padding-right: 20px;
                }
                &.icon4 {
                  width: 139px;
                  margin-top: 8px;
                }
                &.icon5 {
                  width: 99px;
                }
                &.icon6 {
                  width: 131px;
                }
              }
            }
            .withBtn {
              display: flex;
              align-items: center;
              justify-content: center;
  
              span {
                height: 70px;
                line-height: 70px;
                background: linear-gradient(183.26deg, #FAFF00 2.7%, rgba(255, 230, 0, 0) 94.99%);
              }
              button {
                width: 355px;
                height: 70px;
                border: 0;
                outline: 0;
                font-size: 20px;
                font-weight: 700;
                margin-left: 21px;
                padding-left: 32px;
                background: url(../assets/img/Asset6.svg) no-repeat;
                background-size: cover;
                color: #fff;
                display: flex;
                align-items: center;
                cursor: pointer;

                img {
                  width: 40px;
                  padding-left: 20px;
                }
              }
            }
            .arrowImg {
              position: absolute;
              right: 25px;
              bottom: 10px;
              width: 94px;
              transform: rotate(-15deg);
            }
          }
          h3 {
            font-size: 32px;
            font-weight: 700;
            margin: 0;
            margin-bottom: 28px;
          }
          p {
            position: relative;
            font-size: 20px;
            font-weight: 500;
            margin: 0;
            color: #262626;
          }
          .readBtn {
            position: relative;
            width: 180px;
            height: 40px;
            font-weight: 700;
            font-size: 16px;
            margin: 70px 0 90px 0;
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
      position: relative;
      width: 1024px;
      height: 363px;
      margin: 0 auto;
      padding: 90px 0;
      display: flex;
      align-items: center;
      justify-content: center;
      
      .videoCont {
        position: absolute;

        img {
          width: 621px;
          height: 363px;
        }
      }
    }
    &.features {
      .feaCont {  
        height: 500px;
        padding: 110px 0 200px 0;

        .cardTit {
          width: 1024px;
          margin: 0 auto;
          font-size: 32px;
          font-weight: 700;
        }
        .cardWrap {
          position: absolute;
          height: 290px;
  
          .cardInner {
            width: 100%;
            display: flex;
            flex-wrap: nowrap;
  
            &:last-child {
              margin-right: 0;
            }
            .card {
              width: 460px;
              height: 280px;
              background: #fafafa;
              box-shadow: 4px 4px 4px rgba(0, 0, 0, 0.25);
              border-radius: 8px;
              margin-right: 40px;
              padding-right: 24px;
              display: flex;
              flex-wrap: nowrap;
  
              .cardIcon {
                width: 30%;
                padding: 0 30px;
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
    &.getStart {
      width: 1024px;
      height: 100vh;
      margin: 0 auto;

      .startCont {
        h3 {
          font-size: 32px;
          font-weight: 700;
          margin: 0;
        }
        .levelWrap {
          display: flex;
          flex-wrap: nowrap;

          .levelBar {
            width: 20%;
            margin-top: 40px;

            .lb {
              display: flex;
              flex-wrap: nowrap;
              justify-content: space-between;
              margin-bottom: 255px;

              .num {
                width: 90px;
                height: 90px;
                border: 10px solid transparent;
                border-radius: 50%;
                background-image: linear-gradient(#fff, #fff);
                background-origin: border-box;
                background-clip: content-box, border-box;
                display: flex;
                align-items: center;
                justify-content: center;
                font-size: 40px;
                font-weight: 700;

                &.active {
                  background-image: linear-gradient(#fff, #fff), 
                  linear-gradient(to right, #001CE9 0%, #fff 100%);
                }
              }
              .dot {
                position: relative;
                width: 30px;
                height: 30px;
                margin-top: 40px;
                margin-right: 20px;

                &::before {
                  position: absolute;
                  content: '';
                  left: 50%;
                  top: 15px;
                  transform: translateX(-50%);
                  width: 10px;
                  height: 370px;
                  background-color: #ddd;
                }
                &.active::before {
                  background-image: linear-gradient(to bottom, #001CE9 0%, #5B8BFB 100%);
                  animation: fadeInText 1s ease-out forwards;
                }
                @keyframes fadeInText {
                  0% {
                    opacity: 0;
                  }
                  100% {
                      opacity: 1;
                  }
                }
                &::after {
                  position: absolute;
                  content: '';
                  left: 50%;
                  transform: translateX(-50%);
                  width: 30px;
                  height: 30px;
                  border-radius: 50%;
                  background-color: #fff;
                }
                &.active::after {
                  width: 30px;
                  height: 30px;
                  border: 10px solid transparent;
                  border-radius: 50%;
                  background-image: linear-gradient(to right, #001CE9 0%, #fff 100%),
                  linear-gradient(#fff, #fff);
                  background-origin: border-box;
                  background-clip: content-box, border-box;
                  animation: fadeInText 0.1s ease-out forwards;
                }
              }
              &.lb2 {
                .dot {
                  margin-top: 35px;

                  &.active::before {
                    background-image: linear-gradient(to bottom, #5B8BFB 0%, #fff 100%);
                    animation: fadeInText 1s ease-out forwards;
                  }
                }
              }
              &.lb3 {
                .dot::before {
                  display: none;
                } 
              }
            }
          }
          .levelInner {
            width: 80%;
            margin-top: 70px;
            
            &:last-child {
              padding-bottom: 0;
            }
            .level {
              display: flex;
              flex-wrap: nowrap;
              justify-content: space-between;
              height: 300px;
              padding-bottom: 58px;

              &.lv2 {
                padding-bottom: 72px;
              }
              .lvCont {
                width: 260px;
                margin-left: 20px;
                box-sizing: border-box;

                .lvTit {
                  font-size: 24px;
                  font-weight: 700;
                  margin: 10px 0 20px 0;
                }
                .lvDesc {
                  font-size: 16px;
                  font-weight: 400;
                  line-height: 24px;

                  em {
                    color: #293FE6;
                  }
                }
              }
              .lvImg {
                width: 512px;
                // width: 65%;
                box-sizing: border-box;

                &.preCode {
                  height: 234px;
                  background-color: #434343;
                  border-radius: 8px;
                  color: #fff;
                  overflow: scroll;
                  font-size: 16px;
                  font-weight: 400;
                  line-height: 24px;
                  display: flex;
                  align-items: center;
                  padding: 24px 28px;

                  span {
                    color: #7C8CFF;
                  }
                }
                img {
                  width: 512px;
                  height: 300px;
                  object-fit: cover;
                  object-position: top;
                  border-radius: 8px;
                }
              }
            }
          }
        }
      }
    }
    &.trySkapi {
      width: 1024px;
      margin: 0 auto;
      text-align: center;
      font-weight: 700;

      h3 {
        font-size: 32px;
        margin: 0;
        margin-bottom: 20px;
      }
      h2 {
        font-size: 60px;
        color: #293FE6;
        margin: 0;
        margin-bottom: 40px;
      }
      .startBtn {
        position: relative;
        width: 180px;
        height: 40px;
        font-weight: 700;
        font-size: 16px;
        margin-bottom: 350px;
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
</style>