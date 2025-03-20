<script lang="ts" setup>
defineProps({
  problemData: {
    type: Object,
    default() {
      return {
        title: '',
        lists: [],
      }
    },
  },
  v2Versions: {
    type: Boolean,
    default: false,
  },
})
const activeNames = ref(0)
</script>

<template>
  <div class="problem">
    <div
      class="d-flex flex-row mb-3 align-items-end subheading"
      v-if="v2Versions"
    >
      <span>植牙常見</span><span>問題</span>
    </div>
    <div class="dentistryServices-title problem-title" v-else>
      <div class="dentistryServices-title-in bb problem-title-in">
        {{ $t(problemData.title) }}
      </div>
    </div>
    <div class="problem-in pageCon ckj-contrain">
      <el-collapse v-model="activeNames" accordion>
        <el-collapse-item
          v-for="(problemItem, problemIndex) in problemData.lists"
          :key="problemIndex"
          :name="problemIndex"
        >
          <template #title>
            <div class="problem-in-title">
              <div>Q</div>
              <div>{{ $t(problemItem.Q) }}</div>
              <div>
                <img src="@/assets/images/icon_91.png" alt="" />
              </div>
            </div>
          </template>
          <div
            class="problem-in-context"
            style="
              box-shadow: 0 2px 4px 2px #4d4d4d33;
              border-radius: 10px;
              overflow: hidden;
            "
          >
            <span
              :style="{
                display:
                  $t(problemItem.Q) == '誰是牙周病高危一族？'
                    ? 'none'
                    : 'block',
              }"
              >A</span
            >
            <div
              class="risk_group"
              v-if="$t(problemItem.Q) == '誰是牙周病高危一族？'"
            >
              <div>
                <div>
                  <img
                    src="https://static.cmereye.com/imgs/2024/08/cc6965e73ac20a7c.png"
                    alt=""
                  />
                </div>
                <div>吸煙人士</div>
              </div>
              <div>
                <div>
                  <img
                    src="https://static.cmereye.com/imgs/2024/08/82bc7bc8d1b7f798.png"
                    alt=""
                  />
                </div>
                <div>糖尿病患者</div>
              </div>
              <div>
                <div>
                  <img
                    src="https://static.cmereye.com/imgs/2024/08/3094a7678ce6bb14.png"
                    alt=""
                  />
                </div>
                <div>長期服用藥物</div>
              </div>
              <div>
                <div>
                  <img
                    src="https://static.cmereye.com/imgs/2024/08/52774259a391577f.png"
                    alt=""
                  />
                </div>
                <div>孕婦</div>
              </div>
              <div>
                <div>
                  <img
                    src="https://static.cmereye.com/imgs/2024/08/d9852c16d65a15ce.png"
                    alt=""
                  />
                </div>
                <div>衛生意識薄弱</div>
              </div>
              <div>
                <div>
                  <img
                    src="https://static.cmereye.com/imgs/2024/08/6e5bbfe0fc991979.png"
                    alt=""
                  />
                </div>
                <div>飲食不均衡</div>
              </div>
              <div>
                <div>
                  <img
                    src="https://static.cmereye.com/imgs/2024/08/b96537aa679013ac.png"
                    alt=""
                  />
                </div>
                <div>壓力大</div>
              </div>
              <div>
                <div>
                  <img
                    src="https://static.cmereye.com/imgs/2024/08/bd40104a82d20991.png"
                    alt=""
                  />
                </div>
                <div>家族遺傳</div>
              </div>
            </div>
            <span v-else v-html="$t(problemItem.A)"></span>
          </div>
        </el-collapse-item>
      </el-collapse>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@font-face {
  font-family: 'Helvetica Neue';
  src: url(https://statichk.cmermedical.com/ckj/font/helveticaneue-thin.woff2)
    format('woff2');
}
.risk_group {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px 10px;
  width: 80%;
  margin: 24px auto;
  & > div {
    display: flex;
    flex-direction: column;
    align-items: center;
    & > div:nth-child(2) {
      margin-top: 7px;
      color: var(--Grey-Deep, #4d4d4d);
      text-align: center;
      font-family: 'FakePearl-Regular';
      font-size: 22px;
      font-style: normal;
      font-weight: 600;
      line-height: 130%; /* 20.8px */
    }
  }
}
.problem {
  margin-top: 98px;
  &-in {
    margin-top: 35px;
    width: 100%;
    max-width: 960px;
    &-title {
      display: flex;
      justify-content: space-between;
      align-items: center;
      width: 100%;
      & > div:nth-of-type(1) {
        color: var(--Brand-Color, #f8298a);
        text-align: center;
        font-family: 'Helvetica Neue';
        font-size: 30px;
        font-style: normal;
        font-weight: 500;
        line-height: 130%; /* 39px */
      }
      & > div:nth-of-type(2) {
        font-style: normal;
        font-weight: 700;
        font-size: 24px;
        color: #505050;
        max-width: calc(100% - 70px);
        line-height: 1.2;
        flex: 1;
        text-align: center;
      }
      & > div:nth-of-type(3) {
        margin-right: 0;
      }
    }
    &-context {
      display: flex;
      & > span:first-child {
        font-style: normal;
        font-weight: 700;
        font-size: 40px;
        line-height: 160%;
        color: var(--indexColor1);
        margin-left: 0;
        margin-top: 0;
      }
      & > span:last-child {
        flex: 1;
        font-style: normal;
        font-weight: 600;
        font-size: 20px;
        line-height: 160%;
        color: #666666;
        white-space: pre-wrap;
        padding: 0;
      }
    }
  }
}
:deep(.el-collapse) {
  border: none;
}
:deep(.el-collapse-item) {
  margin-bottom: 15px;
  border: none;
}
:deep(.el-collapse-item__wrap) {
  border: none;
  .problem-in-context {
    box-sizing: border-box;
    padding: 10px 28px;
    display: flex;
    gap: 0 19px;
    & > span:nth-child(2) {
      color: var(--Grey-Dark, #333);
      font-family: 'Noto Sans HK';
      font-size: 20px;
      font-style: normal;
      font-weight: 400;
      line-height: 160%; /* 32px */
      letter-spacing: 4px;
    }
  }
}
:deep(.el-collapse-item__header) {
  padding: 0;
  background: var(--indexColor2);
  border: none;
  box-sizing: initial;
  line-height: 160%;
  height: auto;
  border-top-left-radius: 10px;
  border-top-right-radius: 10px;
  box-shadow: 0 2px 4px 2px #4d4d4d33;
  .problem-in-title {
    display: flex;
    align-items: center;
    gap: 0 20px;
    box-sizing: border-box;
    padding: 0 28px;
    height: 50px;
    & > div:nth-of-type(2) {
      color: var(--Grey-Dark, #333);
      font-family: 'Noto Sans HK';
      font-size: 24px;
      font-style: normal;
      font-weight: 700;
      line-height: normal;
      letter-spacing: 2.4px;
    }
  }
}
:deep(.el-collapse-item__header.is-active) {
  background: var(--indexColor1);
  .problem-in-title > div:nth-of-type(1) {
    color: var(--indexColor2);
  }
  .problem-in-title > div:nth-of-type(2) {
    color: #ffffff;
  }
}
:deep(.el-collapse-item__content) {
  overflow: none;
  padding-bottom: 5px;
}
:deep(.problem-in-context) {
  border-radius: 10px;
  box-shadow: 0px 2px 4px 2px rgba(77, 77, 77, 0.2);
}
:deep(.el-icon) {
  display: none;
}
@media (min-width: 768px) and (max-width: 1920px) {
  .problem {
    margin-top: 5.1042vw;
    &-in {
      margin-top: 1.8229vw;
      max-width: 960px;
      &-title {
        & > div:nth-of-type(1) {
          font-size: 2.0833vw;
        }
        & > div:nth-of-type(2) {
          font-size: 1.25vw;
          max-width: calc(100% - 3.6458vw);
          text-align: left;
        }
        & > div:nth-of-type(3) {
          margin-right: 1.6667vw;
        }
      }
      &-context {
        & > span:first-child {
          font-size: 2.0833vw;
        }
        & > span:last-child {
          font-size: 1.0417vw;
        }
      }
    }
  }
  :deep(.el-collapse-item__header) {
    border-radius: 10px;
  }
}

.problem-in-context {
  border-radius: 10px;
  box-shadow: 0 2px 4px 2px #4d4d4d33;
}
@media screen and (max-width: 768px) {
  .risk_group {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 2.665vw 2.665vw;
    box-sizing: border-box;
    padding: 2.665vw 0;
    width: 100%;
    margin: 3.5vw auto 0;
    & > div {
      & > div:nth-child(2) {
        margin-top: 3px;
        font-size: 3.2vw;
        text-align: center;
        letter-spacing: 0;
      }
    }
  }
  .problem {
    margin-top: 30px;
    &-title {
      &-in {
        font-size: 26px;
      }
    }
    &-in {
      margin-top: 30px;
      width: calc(100% - 60px);
      &-title {
        & > div:nth-of-type(1) {
          font-size: 26px;
          // margin-left: 3px;
        }
        & > div:nth-of-type(2) {
          font-size: 16px;
          // margin-left: 0px;
          text-align: left;
        }
        & > div:nth-of-type(3) {
          width: 13px;
          margin-right: 8px;
        }
      }
      &-context {
        & > span:first-child {
          // margin-left: 16px;
          font-size: 26px;
          line-height: normal;
        }
        & > span:last-child {
          // padding: 20px 17px 20px 14px;
          font-size: 16px;
        }
      }
    }
  }
  :deep(.el-collapse-item__header) {
    // height: 43px;
    border-radius: 2.65vw;
    min-height: 11.465vw;
    box-sizing: border-box;
    .problem-in-title {
      height: auto;
      & > div:nth-child(1) {
        color: var(--Brand-Color, #f8298a);
        text-align: center;
        font-family: 'Helvetica Neue';
        font-size: 5.33vw;
        font-style: normal;
        font-weight: 400;
        line-height: 160%; /* 32px */
      }
      & > div:nth-child(2) {
        color: var(--Grey-Dark, #333);
        font-family: 'Noto Sans HK';
        font-size: 3.2vw;
        font-style: normal;
        font-weight: 400;
        line-height: 150%; /* 18px */
        letter-spacing: 0.16vw;
      }
      box-sizing: border-box;
      padding: 1.3vw 2.13vw;
      display: flex;
      gap: 0 4vw;
    }
  }
  :deep(.el-collapse-item__wrap) {
    .problem-in-context {
      padding: 2.13vw 2.65vw;
      box-sizing: border-box;
      gap: 0 4vw;
      & > span:nth-child(1) {
        color: var(--Brand-Color, #f8298a);
        text-align: center;
        font-family: 'Helvetica Neue';
        font-size: 4.8vw;
        font-style: normal;
        font-weight: 500;
        line-height: 160%; /* 25.6px */
      }
      & > span:nth-child(2) {
        color: var(--Grey-Dark, #333);
        text-align: justify;
        font-family: 'Noto Sans HK';
        font-size: 3.2vw;
        font-style: normal;
        font-weight: 350;
        line-height: 150%; /* 18px */
        letter-spacing: 0.163vw;
      }
    }
  }
  :deep(.el-collapse-item) {
    margin-bottom: 1.3vw;
    border: none;
  }
}

:deep(.is-active) {
  border-bottom-right-radius: 0 !important;
  border-bottom-left-radius: 0 !important;
}
</style>
