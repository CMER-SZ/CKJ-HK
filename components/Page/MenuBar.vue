<script lang="ts" setup>
// import { defineProps } from "vue";
import { useElementBounding } from '@vueuse/core'
import { smallPhoneNum, phoneNum } from '~/assets/js/common'
const menuBar = ref(null)
// const { x, y, top, right, bottom, left, width, height } = useElementBounding(menuBar)
// defineProps({
//   str:{
//     type: String,
//     default: ''
//   }
// })
</script>

<template>
  <div></div>
  <!-- <div class="menuBar" ref="menuBar"></div> -->
</template>


<style lang="scss" scoped>
.menuBar {
  width: 100%;
  height: auto;
  display: flex;
  // position: relative;
  &-in {
    width: 100%;
    height: 67px;
    background: var(--indexColor1);
    position: fixed;
    z-index: 0;
    left: 0;
    padding: 0 60px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    .menuBar-box {
      display: flex;
      align-items: center;
      & > img {
        display: inline-block;
        vertical-align: middle;
        margin-top: -5px;
        margin-right: 5px;
      }
      p {
        font-size: 22px;
        color: #fff;
        display: inline-block;
      }
    }
    &-l {
      display: flex;
      align-items: center;
      .menuBar-box {
        margin-right: 40px;
      }
    }
    &-r {
      display: flex;
      align-items: center;
      .menuBar-box {
        margin-left: 30px;
        & > img {
          max-height: 24px;
          margin-top: -3px;
        }
      }
      .menuBar-icon {
        display: flex;
        align-items: center;
        cursor: pointer;
        &-in {
          margin-left: 15px;
          position: relative;
          & > img {
            max-height: 27px;
          }
          .weChatCode {
            position: absolute;
            top: 100%;
            right: 0;
            display: none;
            opacity: 0;
            transform: translateX(10px);
            z-index: 42;
            &-in {
              transition: all 0.5s;
              background: var(--indexColor1);
              height: 100%;
              padding: 20px;
              justify-content: center;
              align-items: center;
              border-radius: 10px;
              color: #fff;
              .weChat {
                width: 200px;
                background: var(--indexColor3);
                img {
                  width: 100%;
                }
              }
            }
          }
          &.weChatBox:hover .weChatCode {
            display: flex;
            animation: animRightIn 1s forwards;
          }
        }
      }
    }
  }
}
@keyframes animRightIn {
  from {
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}
@media (min-width: 768px) and (max-width: 1920px) {
  .menuBar {
    &-in {
      padding: 0 3.125vw;
      .menuBar-box {
        & > img {
          margin-top: -0.2604vw;
          margin-right: 0.2604vw;
        }
        p {
          font-size: 1.1458vw;
        }
      }
      &-l {
        .menuBar-box {
          margin-right: 2.0833vw;
        }
      }
      &-r {
        .menuBar-box {
          margin-left: 1.5625vw;
          & > img {
            max-height: 1.25vw;
            margin-top: -0.1563vw;
          }
        }
        .menuBar-icon {
          &-in {
            margin-left: 0.7813vw;
            & > img {
              max-height: 1.4063vw;
            }
            .weChatCode {
              &-in {
                padding: 1.0417vw;
                border-radius: 0.5208vw;
                .weChat {
                  width: 10.4167vw;
                }
              }
            }
          }
        }
      }
    }
  }
}
@media screen and (max-width: 768px) {
  .menuBar {
    display: none;
  }
}
</style>