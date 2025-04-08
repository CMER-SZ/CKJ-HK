<script lang="ts" setup>

const props = defineProps({
  // 当前显示的牙科类型
  nowType: {
    type: String,
    default: '105',
  },
})

// 牙科类型列表
const typeList = ref([
  {
    id: '101',
    name: '種植科',
    status: false,
    doctor: [
      {
        name: '李川',
        appellation: '醫生',
        img: 'https://static.ckjhk.com/ckj-image/2025040315151501.png',
        title: '集團常務院長',
      },
      {
        name: '盧勇輝',
        appellation: '醫生',
        img: 'https://static.ckjhk.com/ckj-image/2025040315151502.png',
        title: '種植學總監',
      }
    ]
  },
  {
    id: '102',
    name: '修復科',
    status: false,
    doctor: [
      {
        name: '李川',
        appellation: '醫生',
        img: 'https://static.ckjhk.com/ckj-image/2025040315151501.png',
        title: '集團常務院長',
      },
      {
        name: '盧勇輝',
        appellation: '醫生',
        img: 'https://static.ckjhk.com/ckj-image/2025040315151502.png',
        title: '種植學總監',
      }
    ]
  },
  {
    id: '103',
    name: '矯正科',
    status: false,
    doctor: [
      {
        name: '李川',
        appellation: '醫生',
        img: 'https://static.ckjhk.com/ckj-image/2025040315151501.png',
        title: '集團常務院長',
      },
      {
        name: '盧勇輝',
        appellation: '醫生',
        img: 'https://static.ckjhk.com/ckj-image/2025040315151502.png',
        title: '種植學總監',
      }
    ]
  },
  {
    id: '104',
    name: '牙髓病科',
    status: false,
    doctor: [
      {
        name: '方宇',
        appellation: '醫生',
        img: 'https://static.ckjhk.com/ckj-image/2025040315380203.png',
        title: '副主任醫師',
      },
      {
        name: '鞏賢平',
        appellation: '醫生',
        img: 'https://static.ckjhk.com/ckj-image/2025040315380202.png',
        title: '口腔醫院院長',
      },
      {
        name: '楊福強',
        appellation: '醫生',
        img: 'https://static.ckjhk.com/ckj-image/2025040315380201.png',
        title: '口腔醫院<br />綜合科總監',
      }
    ]
  },
  {
    id: '105',
    name: '牙周病科',
    status: false,
    doctor: [
      {
        name: '李川',
        appellation: '醫生',
        img: 'https://static.ckjhk.com/ckj-image/2025040315151501.png',
        title: '集團常務院長',
      },
      {
        name: '盧勇輝',
        appellation: '醫生',
        img: 'https://static.ckjhk.com/ckj-image/2025040315151502.png',
        title: '種植學總監',
      }
    ]
  },
  {
    id: '106',
    name: '兒童牙科',
    status: false,
    doctor: [
      {
        name: '李川',
        appellation: '醫生',
        img: 'https://static.ckjhk.com/ckj-image/2025040315151501.png',
        title: '集團常務院長',
      },
      {
        name: '盧勇輝',
        appellation: '醫生',
        img: 'https://static.ckjhk.com/ckj-image/2025040315151502.png',
        title: '種植學總監',
      }
    ]
  },
  {
    id: '107',
    name: '口腔頜面外科',
    status: false,
    doctor: [
      {
        name: '李川',
        appellation: '醫生',
        img: 'https://static.ckjhk.com/ckj-image/2025040315151501.png',
        title: '集團常務院長',
      },
      {
        name: '盧勇輝',
        appellation: '醫生',
        img: 'https://static.ckjhk.com/ckj-image/2025040315151502.png',
        title: '種植學總監',
      }
    ]
  },
])
const id = ref('')
const num = ref(0)
const handletab2 = (id: string, i: number) => {
  console.log(id);
  num.value = i
  typeList.value.forEach((item) => {
    if (item.id === id) {
      item.status = true
    } else {
      item.status = false
    }

  })
}
const getNowIndex = (id: string) => {
  return typeList.value.findIndex((item) => item.id === id)
}
onMounted(() => {
  id.value = props.nowType
  handletab2(id.value, getNowIndex(id.value))
})
</script>

<template>
  <div class="doctor-v2">
    <div class="doctor-administrative-office">
      <div v-for="(item, index) in typeList" :key="index" @click="handletab2(item.id, index)"
        :class="item.status ? 'office-btn-active' : ''" :data-srt="item.id" class="office-btn">
        {{ item.name }}
      </div>
    </div>
    <div class="doctor-team">
      <div class="doctor-list" v-for="(doctor, index) in typeList[num].doctor" :key="index">
        <div class="img">
          <img :src="doctor.img" alt="">
        </div>
        <div class="name">
          <div class="name-t">{{ doctor.name }}</div>
          <div class="name-b">{{ doctor.appellation }}</div>
        </div>
        <div class="title" v-html="doctor.title"></div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@media screen and (min-width: 992px) {
  .doctor-v2 {
    max-width: 960px;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 15px 0;

    .doctor-administrative-office {
      display: flex;
      border-radius: 10px;
      border: 1px solid var(--Grey-Light, #E6E6E6);

      .office-btn {
        color: var(--Grey-Mid, #666);
        text-align: center;
        font-family: "Noto Sans TC";
        font-size: 20px;
        font-style: normal;
        font-weight: 700;
        line-height: 160%;
        letter-spacing: 2px;
        box-sizing: border-box;
        padding: 6.5px 20px;
        border-right: 1px solid var(--Grey-Light, #E6E6E6);
        transition: all 0.3s ease;
      }

      .office-btn:first-child {
        border-radius: 10px 0 0 10px;
      }

      .office-btn:last-child {
        border-radius: 0 10px 10px 0;
      }

      .office-btn-active {
        color: #fff;
        background: var(--Theme-Color, #fc1682);
        border-top: 1px solid var(--Theme-Color, #fc1682);
        border-bottom: 1px solid var(--Theme-Color, #fc1682);
        transition: all 0.3s ease;
        position: relative;
      }

      .office-btn-active::after {
        content: '';
        width: 20px;
        height: 10px;
        border-left: 10px solid transparent;
        border-right: 10px solid transparent;
        border-top: 10px solid var(--Theme-Color, #fc1682);
        position: absolute;
        bottom: -10px;
        left: 50%;
        transform: translateX(-50%);
      }

      .office-btn:last-child {
        border-right: none;
      }
    }

    .doctor-team {

      display: flex;
      gap: 0 50px;
      border-radius: 10px;
      align-items: flex-start;
      padding-bottom: 50px;

      .doctor-list {
        position: relative;
        display: flex;
        flex-direction: column;
        align-items: center;

        .img {
          width: 228.571px;
          height: 300px;

          &>img {
            border-radius: 10px;
            box-shadow: 0px 4px 4px 0px rgba(77, 77, 77, 0.20);
          }
        }

        .name {
          position: absolute;
          bottom: 0;
          display: flex;
          left: 10px;
          align-items: flex-end;
          gap: 0 5px;

          &>.name-t {
            color: #FFF;
            text-shadow: 0px 4px 4px #FC1682;
            font-family: "Noto Sans HK";
            font-size: 40px;
            font-style: normal;
            font-weight: 500;
            line-height: 160%;
          }

          &>.name-b {
            color: #FFF;
            font-family: "Noto Sans HK";
            font-size: 24px;
            font-style: normal;
            font-weight: 500;
            line-height: 160%;
            padding-bottom: 5px;
          }
        }

        .title {
          height: 70px;
          position: absolute;
          bottom: -75px;
          display: flex;
          flex-direction: column;
          justify-content: flex-start;
          align-items: center;
          color: var(--Grey-Dark, #333);
          text-align: center;
          font-family: "Noto Sans HK";
          font-size: 24px;
          font-style: normal;
          font-weight: 700;
          line-height: normal;
          letter-spacing: 2.4px;
        }
      }
    }
  }
}

@media screen and (max-width: 991px) {
  .doctor-v2 {
    margin: 15px 0;
    box-sizing: border-box;
    padding: 0 20px;

    .doctor-administrative-office {
      display: flex;
      flex-wrap: wrap;
      box-sizing: border-box;
      justify-content: center;
      padding: 0 10px;

      .office-btn {
        color: var(--Grey-Mid, #666);
        text-align: center;
        font-family: "Noto Sans HK";
        font-size: 16px;
        font-style: normal;
        font-weight: 700;
        line-height: normal;
        letter-spacing: 1.6px;
        box-sizing: border-box;
        padding: 8px 9px;
        border-top: 1px solid var(--Grey-Light, #E6E6E6);
        border-right: 1px solid var(--Grey-Light, #E6E6E6);
      }

      .office-btn:first-child {
        border-radius: 5px 0px 0px 0px;
        border-left: 1px solid var(--Grey-Light, #E6E6E6);
      }

      .office-btn:nth-child(4) {
        border-radius: 0px 5px 0px 0px;
      }

      .office-btn:nth-child(5),
      .office-btn:nth-child(6),
      .office-btn:nth-child(7) {
        border-bottom: 1px solid var(--Grey-Light, #E6E6E6);
      }

      .office-btn:nth-child(5) {
        border-radius: 0px 0px 0px 5px;
        border-left: 1px solid var(--Grey-Light, #E6E6E6);
      }

      .office-btn:nth-child(7) {
        border-radius: 0px 0px 5px 0px;
      }

      .office-btn-active {
        color: #fff;
        background: var(--Theme-Color, #fc1682);
        border-top: 1px solid var(--Theme-Color, #fc1682);
      }
    }



    .doctor-team {
      margin-top: 15px;
      display: flex;
      gap: 0 10px;
      border-radius: 10px;
      align-items: flex-start;
      padding-bottom: 50px;
      justify-content: center;

      .doctor-list {
        position: relative;
        display: flex;
        flex-direction: column;
        align-items: center;

        .img {
          width: 105px;
          height: 134px;
          transition: all 0.3s ease;
          &>img {
            border-radius: 5px;
            box-shadow: 0px 4px 4px 0px rgba(77, 77, 77, 0.20);
          }
        }

        .name {
          position: absolute;
          bottom: 0;
          display: flex;
          left: 5px;
          align-items: flex-end;
          gap: 0;

          &>.name-t {
            color: var(--White, #FFF);
            text-align: center;
            text-shadow: 0px 2px 2px #D2337D;
            font-family: "Noto Sans HK";
            font-size: 20px;
            font-style: normal;
            font-weight: 500;
            line-height: 130%;
          }

          &>.name-b {
            color: var(--White, #FFF);
            text-align: center;
            font-family: "Noto Sans HK";
            font-size: 14px;
            font-style: normal;
            font-weight: 400;
            line-height: 160%;
            padding-bottom: 0;
          }
        }

        .title {
          height: 40px;
          position: absolute;
          bottom: -45px;
          display: flex;
          flex-direction: column;
          justify-content: flex-start;
          align-items: center;
          color: var(--Grey-Dark, #333);
          text-align: center;
          font-family: "Noto Sans HK";
          font-size: 14px;
          font-style: normal;
          font-weight: 500;
          line-height: 150%;
          letter-spacing: 0.7px;
        }
      }
    }
  }
}
</style>