<template>
  <section class="tooth_tray_flow_custom_made_bg">
    <section class="ckj-container  tooth_tray_flow_custom_made">
      <div class="flow_custom_made_tab">
        <div class="flow_custom_made_tab_text" :class="[!cutTab ? 'flow_custom_made_tab_active' : '']"
          @click="cutTabCustomMade">固定式假牙</div>
        <div class="flow_custom_made_tab_text" :class="[cutTab ? 'flow_custom_made_tab_active' : '']"
          @click="cutTabCustomMade">活動式假牙</div>
      </div>
      <div class="flow-tabs" v-if="!cutTab">
        <div v-for="(tab, index) in flowCustomMadeTabLists" :key="tab.id" class="tab-item"
          :class="{ 'is-open': isOpen(index) }">
          <!-- 装饰条 -->
          <div class="decor-bar" :class="{ 'expanded': isOpen(index) }"></div>

          <!-- 内容框体 -->
          <div class="tab-box">
            <!-- Header -->
            <div class="tab-header" @click="toggle(index)">
              <div>
                <div class="tab-id">{{ tab.id }}</div>
                <h2 class="tab-title">{{ tab.title }}</h2>
              </div>
              <div class="toggle-icon">{{ isOpen(index) ? '−' : '+' }}</div>
            </div>

            <!-- Body -->
            <transition name="accordion">
              <div v-show="isOpen(index)" class="tab-content">
                <div v-for="(item, idx) in tab.content" :key="idx" class="content-item">
                  <p class="content-title">{{ item.sonTitle }}</p>
                  <p class="content-text">{{ item.sonText }}</p>
                </div>
              </div>
            </transition>
          </div>
        </div>
      </div>
      <div class="flow-tabs" v-if="cutTab">
        <div v-for="(tab, index) in flowCustomMadeTabListsTwo" :key="tab.id" class="tab-item"
          :class="{ 'is-open': isOpen(index) }">
          <!-- 装饰条 -->
          <div class="decor-bar" :class="{ 'expanded': isOpen(index) }"></div>

          <!-- 内容框体 -->
          <div class="tab-box">
            <!-- Header -->
            <div class="tab-header" @click="toggle(index)">
              <div>
                <div class="tab-id">{{ tab.id }}</div>
                <h2 class="tab-title">{{ tab.title }}</h2>
              </div>
              <div class="toggle-icon">{{ isOpen(index) ? '−' : '+' }}</div>
            </div>

            <!-- Body -->
            <transition name="accordion">
              <div v-show="isOpen(index)" class="tab-content">
                <div v-for="(item, idx) in tab.content" :key="idx" class="content-item">
                  <p class="content-title">{{ item.sonTitle }}</p>
                  <p class="content-text">{{ item.sonText }}</p>
                </div>
              </div>
            </transition>
          </div>
        </div>
      </div>
    </section>
  </section>

</template>

<script setup>
import { ref } from 'vue'
const cutTab = ref(false)
const cutTabCustomMade = () => {
  cutTab.value = !cutTab.value
}

const flowCustomMadeTabLists = ref(
  [
    {
      id: 1, title: '初診與評估',
      content: [
        { sonTitle: '諮詢與診斷：', sonText: '醫生將詳細評估患者的口腔健康狀況，了解具體需求、預算和期望效果。' },
        { sonTitle: '牙齒準備：', sonText: '醫生會對牙齒進行磨削，以便為牙橋及牙套提供足夠空間。' }
      ]
    },
    {
      id: 2, title: '牙齒印模',
      content: [
        { sonTitle: '製作印模：', sonText: '使用專業材料對磨削後的牙齒及相鄰牙齒進行精確印模，以用於牙套的製作。' },
        { sonTitle: '咬合記錄：', sonText: '記錄您的咬合方式，以確保牙托在您咬合時能提供適當的支持和保護。' },
        { sonTitle: '製作臨時牙套：', sonText: '在牙套製作期間，牙醫會安裝臨時牙套以保護磨削過的牙齒。' }
      ]
    },
    {
      id: 3, title: '牙橋及牙套製作',
      content: [
        { sonTitle: '製作牙橋：', sonText: '根據患者選擇的材料精準製作牙橋，以提供更舒適的咬合。' }
      ]
    },
    {
      id: 4, title: '牙橋及牙套安裝及指導',
      content: [
        { sonTitle: '試戴及安裝：', sonText: '製作完成後，患者需要進行試戴及安裝，確保其貼合性、美觀效果和舒適度。' }
      ]
    },
    {
      id: 5, title: '使用指導與後續跟進',
      content: [
        { sonTitle: '使用指導：', sonText: '提供如何正確佩戴和保養牙托的指導，確保患者獲得最佳使用效果。' },
        { sonTitle: '後續跟進：', sonText: '定期安排回診，檢查牙橋及牙套的狀態和口腔健康，及時調整或保養。' }
      ]
    }
  ])

const flowCustomMadeTabListsTwo = ref(
  [
    {
      id: 1,
      title: '初診與評估',
      content: [
        {
          sonTitle: '需求評估：',
          sonText: '在您的首次來訪時，我們的牙醫將與您進行深入的交談，了解具體需求及預算。',
        },
        {
          sonTitle: '口腔檢查：',
          sonText: '進行全面的口腔檢查，評估您的牙齦、牙齒狀態及任何可能影響牙托設計的問題。',
        }
      ]
    },
    {
      id: 2,
      title: '牙齒印模',
      content: [
        {
          sonTitle: '牙齒印模：',
          sonText: '在使用先進的牙齒印模材料，為您的牙齒製作精確的模型，確保牙托能夠完美契合您的牙齒。',
        },
        {
          sonTitle: '咬合記錄：',
          sonText: '記錄您的咬合方式，以確保牙托在您咬合時能提供適當的支持和保護。',
        },
      ]
    },
    {
      id: 3,
      title: '牙橋及牙套製作',
      content: [
        {
          sonTitle: '製作牙橋：',
          sonText: '使用高品質的材料製作牙托，以確保牙托的耐用性、安全性和舒適性。',
        },
        {
          sonTitle: '個性化調整：',
          sonText: '根據需要，牙托可以進行個性化的調整，如顏色選擇、厚度調整等，以適應不同的需求或個人偏好。',
        }
      ]
    },
    {
      id: 4,
      title: '牙橋及牙套安裝及指導',
      content: [
        {
          sonTitle: '試戴：',
          sonText: '製作完成後，患者需要進行試戴及安裝，確保其貼合性、美觀效果和舒適度。',
        },
        {
          sonTitle: '細節調整：',
          sonText: '醫生會對牙齒進行磨削，以便為牙橋及牙套提供足夠空間。',
        }
      ]
    },
    {
      id: 5,
      title: '使用指導與後續跟進',
      content: [
        {
          sonTitle: '使用指導：',
          sonText: '提供如何正確佩戴和保養牙托的指導，確保患者獲得最佳使用效果。',
        },
        {
          sonTitle: '後續跟進：',
          sonText: '定期安排回診，檢查牙托的狀態和口腔健康，及時調整或保養牙托。',
        }
      ]
    }
  ])


const openIndex = ref(null)

function toggle(index) {
  openIndex.value = openIndex.value === index ? null : index
}

function isOpen(index) {
  return openIndex.value === index
}
</script>

<style scoped lang="scss">
@keyframes identifier {
  0% {
    opacity: 0;
  }

  100% {
    opacity: 1;
  }
}

@media screen and (min-width: 992px) {
  .tooth_tray_flow_custom_made_bg {
    background: linear-gradient(0deg, rgba(255, 241, 240, 0.00) 0%, rgba(255, 241, 240, 0.70) 12.5%, rgba(255, 241, 240, 0.70) 81.99%, rgba(255, 241, 240, 0.00) 100%);

    .tooth_tray_flow_custom_made {
      box-sizing: border-box;
      padding: 30px 0;
    }

    .flow_custom_made_tab {
      margin: 20px auto;
      display: flex;
      justify-content: center;
      align-items: center;

      .flow_custom_made_tab_text {
        color: var(--Grey-Mid, #666);
        text-align: center;

        /* 桌面版/PC-頂部目錄 */
        font-family: "Noto Sans TC";
        font-size: 20px;
        font-style: normal;
        font-weight: 700;
        line-height: 160%;
        letter-spacing: 2px;
        box-sizing: border-box;
        padding: 6px 40px;
        background: var(--White, #FFF);
      }

      .flow_custom_made_tab_active {
        transition: all 0.3s ease;
        color: var(--White, #FFF);
        text-align: center;
        font-family: "Noto Sans TC";
        font-size: 20px;
        font-style: normal;
        font-weight: 700;
        line-height: 160%;
        /* 32px */
        letter-spacing: 2px;
        background: var(--Brand-Color, #F8298A);
        position: relative;
      }

      .flow_custom_made_tab_active::after {
        content: '';
        position: absolute;
        bottom: -8px;
        left: 50%;
        transform: translateX(-50%);
        width: 0;
        height: 0;
        border-left: 8px solid transparent;
        border-right: 8px solid transparent;
        border-top: 8px solid var(--Brand-Color, #F8298A);
        z-index: 1;
      }

      .flow_custom_made_tab_text:nth-child(1) {
        border-radius: 10px 0 0 10px;
      }

      .flow_custom_made_tab_text:nth-child(2) {
        border-radius: 0 10px 10px 0;
      }
    }

    .flow-tabs {
      animation: identifier 0.5s ease forwards;

      .tab-item {
        position: relative;
        overflow: hidden;
        margin-bottom: 10px;

        .decor-bar {
          position: absolute;
          top: 0;
          left: 0;
          width: 43px;
          height: 56px;
          background-color: var(--Brand-Color, #F8298A);
          transition: height 0.3s ease;
          clip-path: polygon(50% 15%, 100% 0, 100% 85%, 50% 100%, 0 85%, 0 0);

          &.expanded {
            height: 100%;
            background-color: var(--Brand-Color, #F8298A);
            clip-path: polygon(50% 5%, 100% 0, 100% 95%, 50% 100%, 0 95%, 0 0);
          }
        }

        .tab-box {
          margin-left: 50px;
          overflow: hidden;
          box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
          border-radius: 0px 10px 10px 0px;
          background: var(--White, #FFF);

          .tab-header {
            height: 56px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 0 16px;
            cursor: pointer;
            background: #fff;

            &>div:nth-child(1) {
              display: flex;
              align-items: center;
            }

            .tab-id {
              color: var(--Theme-Color, #FC1682);

              /* 桌面版/PC-18Pt字（粗） */
              font-family: "Noto Sans HK";
              font-size: 18px;
              font-style: normal;
              font-weight: 700;
              line-height: 200%;
              /* 36px */
              letter-spacing: 1.8px;
              margin-right: 9px;
            }

            .tab-title {
              color: var(--Grey-Dark, #333);
              text-align: justify;
              font-family: "Noto Sans HK";
              font-size: 18px;
              font-style: normal;
              font-weight: 700;
              line-height: 200%;
              letter-spacing: 1.8px;
            }

            .toggle-icon {
              font-size: 30px;
              color: #F8298A;
              font-weight: 800;
              transition: all 0.3s ease;
            }
          }

          .tab-content {
            padding: 0 15px 15px 38px;
            background: #ffffff;

            .content-item {
              margin-bottom: 0;

              .content-title {
                color: var(--Brand-Color, #F8298A);
                text-align: justify;
                font-family: "Noto Sans HK";
                font-size: 18px;
                font-style: normal;
                font-weight: 500;
                line-height: 120%;
                letter-spacing: 1.2px;
                display: inline;
              }

              .content-text {
                color: var(--Grey-Dark, #333);
                text-align: justify;
                font-family: "Noto Sans HK";
                font-size: 18px;
                font-style: normal;
                font-weight: 500;
                line-height: 120%;
                letter-spacing: 1.2px;
                display: inline;
              }
            }
          }
        }
      }

      .tab-item:nth-child(1) {
        .decor-bar {
          opacity: 0.2;
          clip-path: polygon(50% 0%, 100% 0, 100% 85%, 50% 100%, 0 85%, 0 0);

          &.expanded {
            height: 100%;
            background-color: var(--Brand-Color, #F8298A);
            clip-path: polygon(50% 0%, 100% 0, 100% 95%, 50% 100%, 0 95%, 0 0);
          }
        }
      }

      // 循环样式
      .tab-item:nth-child(2) {
        .decor-bar {
          opacity: 0.4;
        }
      }

      .tab-item:nth-child(3) {
        .decor-bar {
          opacity: 0.6;
        }
      }

      .tab-item:nth-child(4) {
        .decor-bar {
          opacity: 0.8;
        }
      }

      .tab-item:nth-child(5) {
        .decor-bar {
          opacity: 1;
        }
      }
    }

    /* 动画 */
    .accordion-enter-active,
    .accordion-leave-active {
      transition: all 0.3s ease;
    }

    .accordion-enter-from,
    .accordion-leave-to {
      max-height: 0;
      opacity: 0;
      padding: 9px 15px;
    }

    .accordion-enter-to,
    .accordion-leave-from {
      max-height: 1000px;
      opacity: 1;
    }
  }
}

@media screen and (max-width: 991px) {
  .tooth_tray_flow_custom_made_bg {
    background: linear-gradient(0deg, rgba(255, 241, 240, 0.00) 0%, rgba(255, 241, 240, 0.70) 12.5%, rgba(255, 241, 240, 0.70) 81.99%, rgba(255, 241, 240, 0.00) 100%);

    .tooth_tray_flow_custom_made {
      margin: 8vw 0;
    }

    .flow_custom_made_tab {
      margin: 5.33vw auto;
      box-sizing: border-box;
      padding: 0 5.33vw;
      display: flex;
      justify-content: center;
      align-items: center;

      .flow_custom_made_tab_text {
        color: var(--Grey-Mid, #666);
        text-align: center;

        /* 桌面版/PC-頂部目錄 */
        font-family: "Noto Sans TC";
        font-size: 4.265vw;
        font-style: normal;
        font-weight: 700;
        line-height: 150%;
        letter-spacing: 1px;
        box-sizing: border-box;
        padding: 1.465vw 10.665vw;
        background: var(--White, #FFF);
      }

      .flow_custom_made_tab_text:nth-child(1) {
        border-radius: 1.33vw 0 0 1.33vw;
      }

      .flow_custom_made_tab_text:nth-child(2) {
        border-radius: 0 1.33vw 1.33vw 0;
      }

      .flow_custom_made_tab_active {
        transition: all 0.3s ease;
        color: var(--White, #FFF);
        text-align: center;
        font-family: "Noto Sans TC";
        font-size: 4.265vw;
        font-style: normal;
        font-weight: 700;
        line-height: 150%;
        letter-spacing: 1px;
        background: var(--Brand-Color, #F8298A);
        position: relative;
      }

    }

    .flow-tabs {
      padding: 0 5.33vw;
      animation: identifier 0.5s ease forwards;

      .tab-item {
        position: relative;
        overflow: hidden;
        margin-bottom: 3px;

        .decor-bar {
          position: absolute;
          top: 0;
          left: 0;
          width: 27px;
          height: 39px;
          background-color: var(--Brand-Color, #F8298A);
          transition: height 0.3s ease;
          clip-path: polygon(50% 15%, 100% 0, 100% 85%, 50% 100%, 0 85%, 0 0);

          &.expanded {
            height: 100%;
            background-color: var(--Brand-Color, #F8298A);
            clip-path: polygon(50% 2%, 100% 0, 100% 98%, 50% 100%, 0 98%, 0 0);
          }
        }

        .tab-box {
          margin-left: 36px;
          overflow: hidden;
          box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
          border-radius: 0px 10px 10px 0px;
          background: var(--White, #FFF);

          .tab-header {
            height: 39px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 0 16px;
            cursor: pointer;
            background: #fff;

            &>div:nth-child(1) {
              display: flex;
              align-items: center;
            }

            .tab-id {
              color: var(--Theme-Color, #FC1682);
              font-family: "Noto Sans HK";
              font-size: 14px;
              font-style: normal;
              font-weight: 600;
              line-height: 150%;
              letter-spacing: 0.7px;
              margin-right: 9px;
            }

            .tab-title {
              color: var(--Grey-Dark, #333);
              text-align: justify;
              font-family: "Noto Sans HK";
              font-size: 14px;
              font-style: normal;
              font-weight: 600;
              line-height: 150%;
              letter-spacing: 0.7px;
            }

            .toggle-icon {
              font-size: 25px;
              color: #F8298A;
              font-weight: 800;
              transition: all 0.3s ease;
            }
          }

          .tab-content {
            padding: 0 15px 15px 34px;
            background: #ffffff;

            .content-item {
              margin-bottom: 0;

              .content-title {
                color: var(--Brand-Color, #F8298A);
                text-align: justify;
                font-family: "Noto Sans HK";
                font-size: 12px;
                font-style: normal;
                font-weight: 400;
                line-height: 150%;
                letter-spacing: 0.6px;
                display: inline;
              }

              .content-text {
                color: var(--Grey-Dark, #333);
                text-align: justify;
                font-family: "Noto Sans HK";
                font-size: 12px;
                font-style: normal;
                font-weight: 400;
                line-height: 150%;
                letter-spacing: 0.6px;
                display: inline;
              }
            }
          }
        }
      }

      .tab-item:nth-child(1) {
        .decor-bar {
          clip-path: polygon(50% 0%, 100% 0, 100% 85%, 50% 100%, 0 85%, 0 0);
          opacity: 0.2;

          &.expanded {
            clip-path: polygon(50% 0%, 100% 0, 100% 95%, 50% 100%, 0 95%, 0 0);
          }
        }
      }

      // 循环样式
      .tab-item:nth-child(2) {
        .decor-bar {
          opacity: 0.4;
        }
      }

      .tab-item:nth-child(3) {
        .decor-bar {
          opacity: 0.6;
        }
      }

      .tab-item:nth-child(4) {
        .decor-bar {
          opacity: 0.8;
        }
      }

      .tab-item:nth-child(5) {
        .decor-bar {
          opacity: 1;
        }
      }
    }

    /* 动画 */
    .accordion-enter-active,
    .accordion-leave-active {
      transition: all 0.3s ease;
    }

    .accordion-enter-from,
    .accordion-leave-to {
      max-height: 0;
      opacity: 0;
      padding: 9px 15px;
    }

    .accordion-enter-to,
    .accordion-leave-from {
      max-height: 1000px;
      opacity: 1;
    }
  }
}
</style>
