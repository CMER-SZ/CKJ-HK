<script lang="ts" setup>
import { Pagination } from 'swiper'
import { useAppState } from '~/stores/appState'
import { toWhatsApp } from '~/assets/js/common'
import { useElementBounding, useWindowSize } from '@vueuse/core'

const modules = [Pagination]
const appState = useAppState()
appState.setDentistryService('rootCanal-test')
useHead({
  title: '根管治療(杜牙根) | 牙科服務',
  meta: [
    {
      hid: 'description',
      name: 'description',
      content:
        '愛康健提供根管治療（杜牙根）服務，用於治療嚴重蛀牙或牙根受細菌感染的情況。當蛀牙菌感染深入牙髓並引發神經發炎時，需要進行根管治療手術，以徹底清除感染部分。',
    },
    {
      hid: 'Keywords',
      name: 'Keywords',
      content:
        '牙齦炎治療 根管治療 杜牙根 杜牙根價錢 愛康健 深圳愛康健 深圳專業牙科中心 愛康健醫院 愛康健口腔醫院 深圳愛康健口腔醫院愛康健 CKJ愛康健齒科集團 深圳口腔專科醫院 愛康健齒科集團 深圳牙科醫院牙科服務內地牙科 深圳口腔專科',
    },
  ],
})

const headerConfig = {
  img: 'https://static.ckjhk.com/ckj-image/48ea553e8947.webp',
  mbImg: 'https://static.ckjhk.com/ckj-image/cb4c12ce4e80.webp',
  bg: '',
  pageName: 'rootCanal-test',
  pcText: [
    '根管治療助您解決牙痛，恢復健康的口腔狀態',
    '立即接受專業治療手術，徹底解放美食自由',
  ],
  mbText: ['根管治療助您解決牙痛', '恢復健康的口腔狀態'],
}

const introduceData = {
  title: '什麼是杜牙根(根管治療)?',
  content:
    '杜牙根(根管治療)是治療嚴重蛀牙或牙根受細菌感染的療程，當蛀牙菌的感染深入牙髓，以致牙齒內的神經發炎，便需要以杜牙根療程徹底清除感染的部分。',
  mbImg: 'https://static.cmereye.com/imgs/2023/05/4981f5bda13e2428.jpg',
  pcImg: 'https://static.cmereye.com/imgs/2023/05/3030e00ebf385a45.jpg',
  tabNavName: 'pages.dental-service.rootCanal.introduce.tabNavName',
  pageName: 'rootCanal-test',
}

const reasonData = {
  title: '蛀牙階段',
  reasonLists: [
    {
      img: 'https://static.cmereye.com/imgs/2023/10/fafa2f37cf68b4fb.jpg',
      title: '蛀牙初期',
      context: '最外層琺瑯質受損',
    },
    {
      img: 'https://static.cmereye.com/imgs/2023/10/91c57e27b6a68095.jpg',
      title: '蛀牙中期',
      context: '受損至象牙質',
    },
    {
      img: 'https://static.cmereye.com/imgs/2024/02/110eb2fe9f155701.jpg',
      title: '蛀牙後期',
      context: '細菌深入牙髓\n內部組織發炎',
    },
  ],
}

const careData = {
  title: ['什麼情況下', '會考慮做根管治療？'],
  lists: [
    {
      img: 'https://static.cmereye.com/imgs/2023/10/a508f80b579ed63e.png',
      text: '牙髓壞死',
    },
    {
      img: 'https://static.cmereye.com/imgs/2023/10/3d61ee4cd60a9d28.png',
      text: '深齦蛀牙',
    },
    {
      img: 'https://static.cmereye.com/imgs/2023/10/c4471a0fdbd2eef9.png',
      text: '牙髓發炎',
    },
    {
      img: 'https://static.cmereye.com/imgs/2023/10/bfe0997793014633.png',
      text: '根尖發炎',
    },
    {
      img: 'https://static.cmereye.com/imgs/2023/10/78e7d8ea517b188e.png',
      text: '牙外傷',
    },
    {
      img: 'https://static.cmereye.com/imgs/2023/10/88e72fd91eb8aca5.png',
      text: '殘冠殘根',
    },
  ],
}

const infoCardData = {
  lists: [
    {
      text: '顯微根管治療，即在顯微鏡下輔助放大局部來進行根管治療的操作。',
      img: 'https://static.cmereye.com/imgs/2024/08/d6bd484a95024be1.png',
    },
    {
      text: '牙科顯微鏡可以在手術中提供放大畫面，這樣擁有良好照明環境， 保證視野穩定的前提下，將根管治療推進到可視化階段。',
      img: 'https://static.cmereye.com/imgs/2024/08/5cb1e585e20a031c.png',
    },
    {
      text: '愛康健引進德國蔡司顯微鏡根管治療儀，結合顯微鏡技術和醫學技術。能清楚觀察牙齒的解剖結構和根管形態。',
      img: 'https://static.cmereye.com/imgs/2024/08/54a2a0c8b7fca6d7.png',
    },
  ],
}

const stepData = {
  title: '治療7大步驟',
  lists: [
    {
      title: '第1步',
      titleNum: '1',
      img: 'https://static.cmereye.com/imgs/2023/11/8c25f9c3f1d8c834.jpg',
      name: '診斷',
      context: '進行X光檢查，以確定牙齒損壞程度，制定治療方案',
    },
    {
      title: '第2步',
      titleNum: '2',
      img: 'https://static.cmereye.com/imgs/2023/10/0b7ef1a0f39e9ca9.jpg',
      name: '麻醉',
      context: '治療前會先為客人口腔局部麻醉',
    },
    {
      title: '第3步',
      titleNum: '3',
      img: 'https://static.cmereye.com/imgs/2023/11/b7337bbff6017483.jpg',
      name: '牙齒分隔',
      context: '使用橡皮障將需治療的牙齒分隔出來，減低細菌感染其他牙齒的機會',
    },
    {
      title: '第4步',
      titleNum: '4',
      img: 'https://static.cmereye.com/imgs/2023/11/bfd54a465dbc28b8.jpg',
      name: '計算根管長度',
      context: '以牙根探針放入根管，以X光或電子儀器量度牙根深度',
    },
    {
      title: '第5步',
      titleNum: '5',
      img: 'https://static.cmereye.com/imgs/2023/11/8e3ca8afdfa82d6c.jpg',
      name: '清理牙根管',
      context: '使用藥水清理，消毒牙根管',
    },
    {
      title: '第6步',
      titleNum: '6',
      img: 'https://static.cmereye.com/imgs/2023/11/8f9ed7b27c9c0fdc.jpg',
      name: '根管充填',
      context: '將牙膠等物質充填牙根',
    },
    {
      title: '第7步',
      titleNum: '7',
      img: 'https://static.cmereye.com/imgs/2023/11/d542e53ca685f034.jpg',
      name: '修復',
      context: '用牙套保護已杜牙根的牙齒，減低其損壞機會',
    },
  ],
}

const noteData = {
  title: '療程後注意事項',
  lists: [
    {
      name: '避免咀嚼食物或咬硬物，以免損壞治療後的牙齒。',
    },
    {
      name: '避免用治療後的牙齒咬開堅硬的食物，例如堅果、糖果等。',
    },
    {
      name: '在治療後的前幾天內，嘗試避免刷牙或使用牙線，以免影響治療區域的恢復。',
    },
    {
      name: '如果需要刷牙，可以使用軟毛刷，輕柔地刷牙，避免刷太用力或刷到治療區域。',
    },
    {
      name: '如果感覺到疼痛或不適，可以使用過濾口的冰水或冰袋敷在治療區域附近，以減輕疼痛和腫脹。',
    },
    {
      name: '如醫生處方止痛藥，應按照指示使用。',
    },
    {
      name: '定期到口腔醫院進行檢查和清潔，以確保治療後的牙齒保持健康。',
    },
  ],
  listsMobile: [
    {
      name: '避免咀嚼食物或咬硬物，以免損壞治療後的牙齒。',
    },
    {
      name: '如果需要刷牙，可以使用軟毛刷，輕柔地刷牙，避免刷太用力或刷到治療區域。',
    },
    {
      name: '避免用治療後的牙齒咬開堅硬的食物，例如堅果、糖果等。',
    },
    {
      name: '如果感覺到疼痛或不適，可以使用過濾口的冰水或冰袋敷在治療區域附近，以減輕疼痛和腫脹。',
    },
    {
      name: '在治療後的前幾天內，嘗試避免刷牙或使用牙線，以免影響治療區域的恢復。',
    },
    {
      name: '定期到牙醫診所進行檢查和清潔，以確保治療後的牙齒保持健康。',
    },
  ],
}


let services_include_cur = ref(0)
let swiperRef: any = {
  slidePrev: () => { },
  slideNext: () => { },
  slideTo: () => { },
}

const setSwiperRef = (swiper: any) => {
  swiperRef = swiper
  services_include_cur.value = swiperRef.activeIndex
}

const addNum = () => {
  swiperRef.slideNext()
  handleProcessBtnClick()
}
const subNum = () => {
  swiperRef.slidePrev()
  handleProcessBtnClick()
}

const handleProcessBtnClick = () => {
  services_include_cur.value = swiperRef.activeIndex
  const swiperPoints = document.querySelectorAll('.swiper-point')
  swiperPoints.forEach((item: any, index: number) => {
    if (index == services_include_cur.value) {
      item.classList.add('swiper-point-active')
    } else {
      item.classList.remove('swiper-point-active')
    }
  })
}

const handleProcessBtn = (_type: number) => {
  const swiperPoints = document.querySelectorAll('.swiper-point')
  swiperPoints.forEach((item: any, index: number) => {
    if (index == _type) {
      item.classList.add('swiper-point-active')
    } else {
      item.classList.remove('swiper-point-active')
    }
  })
  swiperRef.slideTo(_type, 0, 'slide')
}

const doctorData = {
  title: '根管治療醫療團隊',
  lists: [
    {
      id: '101',
      name: '楊福強',
      job: '總監醫生',
      addressType: '101',
      addressname: '羅湖區',
      text: '口腔美觀設計、瓷牙修復、牙體牙髓病的診治、牙體缺損的修復以及瓷冠、義齒的修復等方面的診治，在水激光無痛治牙方面有著豐富的臨床經驗。 操作手法靈巧精確， 解決疑難病例無數。',
      img: 'https://static.cmereye.com/imgs/2024/02/e7f0a15e92483e5f.png',
    },
    {
      id: '102',
      name: '鞏賢平',
      job: '院長',
      addressType: '101',
      addressname: '羅湖區',
      text: '牙齒美容修復、烤瓷及全瓷修復、 各類復雜義齒修復、種植修復 等。',
      img: 'https://static.cmereye.com/imgs/2024/02/48ce5ddebca789de.png',
    },
    {
      id: '103',
      name: '韋柱山',
      job: '主任醫生',
      addressType: '101',
      addressname: '羅湖區',
      text: '前牙美學修復、根管治療、口腔修復、美容修復等。',
      img: 'https://static.cmereye.com/imgs/2024/02/03f45d5c4bf3922d.png',
    },
    {
      id: '104',
      name: '劉鑫',
      job: '院長',
      addressType: '102',
      addressname: '福田區',
      text: '各種疑難植牙、穿顴穿翼、全口無牙顎、上顎竇增高、複雜的軟硬組織移植、即時植牙即刻修復、前牙美觀、數位化和植牙導航等諸多領域。',
      img: 'https://static.cmereye.com/imgs/2024/02/0762d56bee690392.png',
    },
    {
      id: '105',
      name: '劉章智',
      job: '院長',
      addressType: '102',
      addressname: '福田區',
      text: '將無痛治療技術與美學設計理念相結合，運用於根管治療、固定及活動義齒的診療當中。對各類疑難牙體牙髓病積累了大量成功治療案例和豐富的經驗。',
      img: 'https://static.cmereye.com/imgs/2024/02/6683a60841dc732e.png',
    },
    {
      id: '106',
      name: '馮曉瑛',
      job: '院長',
      addressType: '103',
      addressname: '南山區',
      text: '複雜病例整體診療方案的設計、根管治療、數字化種植修復技術。',
      img: 'https://static.cmereye.com/imgs/2024/02/211667de3a4ffa59.png',
    },
  ],
}

const doctorTeam = ref(null)
const { top, bottom } = useElementBounding(doctorTeam)
const { height } = useWindowSize()

let windowWidth = ref(390)
const getWindowWidth = () => {
  windowWidth.value = window.innerWidth
}
onMounted(() => {
  getWindowWidth()
  window.addEventListener('resize', getWindowWidth)
  handleMessageLineCur(1)
  onMessageNewSlideChange(newsMessageSwiperRef)
})
const triangleColor = ref(false)
const triangleDefault = ref(true)
let messageCurrtNew = ref(1)
const handleMessageLineCur = (_value: number) => {
  newsMessageSwiperRef.slideToLoop(_value - 1)
}
const setMessageNewsSwiperRef = (swiper: any) => {
  newsMessageSwiperRef = swiper
}
const onMessageNewSlideChange = (swiper: any) => {
  messageCurrtNew.value = (swiper.realIndex ? Number(swiper.realIndex) : 0) + 1
  if (swiper.activeIndex == 0) {
    triangleColor.value = true
    triangleDefault.value = true
  } else {
    triangleDefault.value = false
    triangleColor.value = false
  }
}
let newsMessageSwiperRef = {
  slideToLoop: (a) => { },
}


const stepDataList = ref([
  {
    id: 1,
    img: 'https://static.cmereye.com/imgs/2023/11/8c25f9c3f1d8c834.jpg',
    name: 'X光檢查及診斷',
    notText: false,
  },
  {
    id: 2,
    img: 'https://static.cmereye.com/imgs/2023/10/0b7ef1a0f39e9ca9.jpg',
    name: '麻醉',
    notText: false,
  },
  {
    id: 3,
    img: 'https://static.cmereye.com/imgs/2023/11/b7337bbff6017483.jpg',
    name: '牙齒分隔',
    notText: false,
  },
  {
    id: 4,
    img: 'https://static.cmereye.com/imgs/2023/11/bfd54a465dbc28b8.jpg',
    name: '計算根管長度',
    notText: false,
  },
  {
    id: 5,
    img: 'https://static.cmereye.com/imgs/2023/11/8e3ca8afdfa82d6c.jpg',
    name: '清理牙根管',
    notText: false,
  },
  {
    id: 6,
    img: 'https://static.cmereye.com/imgs/2023/11/8f9ed7b27c9c0fdc.jpg',
    name: '根管充填',
    notText: false,
  },
  {
    id: 7,
    img: 'https://static.cmereye.com/imgs/2023/11/d542e53ca685f034.jpg',
    name: '(可選) 牙冠修復',
    notText: false,
  },
  {
    id: 8,
    img: 'https://static.ckjhk.com/ckj-image/5c1ac98cb00a.png',
    notText: true,
  }
])

const problemData = {
  title: '<span>杜牙根</span><span>常見問題</span>',
  lists: [
    {
      Q:'什麼情況下需要做杜牙根？',
      A:'嚴重蛀牙，已經侵犯到牙髓（牙神經）。牙髓炎，牙齒出現持續性疼痛，對冷熱刺激敏感。根尖周炎，牙根尖周圍的組織發炎，引起牙齒鬆動、腫脹。牙齒外傷，導致牙髓受損。其他原因，例如牙齒隱裂、牙周病等，導致牙髓壞死。'
    },
    {
      Q:'杜牙根需要做幾次？',
      A:'杜牙根的次數取決於牙齒的具體情況。有些簡單的病例可能一次完成，但大多數情況下需要2-3次。' 
    },
    {
      Q:'杜牙根後可以維持多久？',
      A:'如果杜牙根治療成功，並且做好日常的口腔護理，牙齒可以維持很長時間，甚至終身。'
    },
    {
      Q:'杜牙根後注意事項?',
      A:'避免咀嚼食物或咬硬物，以免損壞治療後的牙齒。<br /><br />·避免用治療後的牙齒咬開堅硬的食物，例如堅果、糖果等。<br />·在治療後的前幾天內，嘗試避免刷牙或使用牙線，以免影響治療區域的恢復。<br />·如果需要刷牙，可以使用軟毛刷，輕柔地刷牙，避免刷太用力或刷到治療區域。<br />·如果感覺到疼痛或不適，可以使用過濾口的冰水或冰袋敷在治療區域附近，以減輕疼痛和腫脹。<br />·如醫生處方止痛藥，應按照指示使用。<br />·定期到口腔醫院進行檢查和清潔，以確保治療後的牙齒保持健康。<br />其他牙科服務' 
    }
  ],
}

</script>

<template>
  <div>
    <PageHeaderV2 v-if="windowWidth > 768" :headerConfig="headerConfig" />
    <MobileHeaderV2 v-if="windowWidth < 768" :headerConfig="headerConfig">
      <template #xxxxxxxxxxx-home>
        <div class="banner-in-box">
          <div class="banner-content" style="display: flex">
            <div class="content-title">與你一齊守護健康牙齒</div>
            <div class="content-price">
              <div>杜牙根</div>
            </div>
          </div>
        </div>
      </template>
    </MobileHeaderV2>
    <PagePcBannerNoHome v-if="windowWidth > 768" :headerConfig="headerConfig">
      <template #xxxxxxxxxxx-home>
        <div class="banner-in-box">
          <div class="banner-image">
            <img src="https://static.ckjhk.com/ckj-image/a1ed0bfa1d61.webp" alt="" loading="lazy" />
          </div>
          <div class="banner-content" style="display: flex">
            <div class="content-title">與你一齊守護健康牙齒</div>
            <div class="content-price">
              <div>杜牙根</div>
            </div>
          </div>
        </div>
      </template>
    </PagePcBannerNoHome>

    <div class="root-canal">
      <section class="ckj-container root-canal-therapy">
        <div>
          <div class="root-canal-therapy-title  subheading flex-row align-items-end">
            <span>什麼是</span><span>杜牙根(根管治療)</span>
          </div>
          <div class="d-md-none"><img src="https://static.ckjhk.com/ckj-image/2025040809513201.jpg" alt=""></div>
          <div>杜牙根(根管治療)是治療嚴重蛀牙或牙根受細菌感染的療程，當蛀牙菌的感染深入牙髓，以致牙齒內的神經發炎，便需要以杜牙根療程徹底清除感染的部分。</div>
        </div>
        <div class="d-none d-md-block"><img src="https://static.ckjhk.com/ckj-image/c2bd71c74791.png" alt="杜牙根(根管治療)">
        </div>
      </section>
      <section class="ckj-container charge-item">
        <div class="d-flex flex-row align-items-end subheading">
          <span>愛康健杜牙根</span><span>收費項目</span>
        </div>
        <div class="charge-item-content">
          <div><img src="https://static.ckjhk.com/ckj-image/ba66d4b13ce0.png" alt=""></div>
          <div>
            <div>
              <div>項目</div>
              <div>價錢</div>
            </div>
            <div>
              <div>前牙杜牙根</div>
              <div>￥2,000/顆</div>
            </div>
            <div>
              <div>後牙杜牙根</div>
              <div>￥3,000/顆</div>
            </div>
          </div>
          <div>
            <div>愛康健杜牙根價格<span>已包含麻醉及3張X光片。</span></div>
            <div>*有可能因牙齒的實際複雜程度而添加額外治療項目。</div>
          </div>
        </div>
      </section>
      <section class="ckj-container seven-steps">
        <div class="seven-steps-title">
          <div>\ <span>杜牙根治療步驟</span> /</div>
        </div>
        <div class="seven-steps-content">
          <div v-for="item in stepDataList" :key="item.id">
            <div v-if="!item.notText" class="seven-steps-content-item">
              <div>
                <div>{{ item.id }}</div>
                <div><img :src="item.img" :alt="item.name"></div>
              </div>
              <div>{{ item.name }}</div>
            </div>
            <div v-if="item.notText" class="seven-steps-content-item">
              <div><img :src="item.img" :alt="item.name"></div>
            </div>
          </div>
        </div>
      </section>
      <section class="ckj-container microroot-canal">
        <div class="d-flex flex-row align-items-end subheading">
          <span>什麼是</span><span>顯微根管治療</span>
        </div>
        <div class="microroot-canal-content d-none d-md-flex">
          <div><img src="https://static.ckjhk.com/ckj-image/14db8a4e2307.png" alt=""></div>
          <div>
            <ul>
              <li>顯微根管治療，即在顯微鏡輔助下放大局部來治療根管。 </li>
              <li>牙科顯微鏡可以在手術中放大畫面，在良好照明環境及視野穩定的前提下，將根管治療推進到可視化階段。 </li>
              <li>愛康健引進德國蔡司顯微鏡根管治療儀，結合顯微鏡技術和醫學技術，能清楚觀察牙齒的解剖結構和根管形態。</li>
            </ul>
          </div>
        </div>
        <div class="microroot-canal-content d-md-none">
          <div>
            <div><img src="https://static.ckjhk.com/ckj-image/2025040814372901.png" alt=""></div>
            <div>顯微根管治療，即在顯微鏡輔助下放大局部來治療根管。 </div>
          </div>
          <div>
            <div><img src="https://static.ckjhk.com/ckj-image/2025040814372902.png" alt=""></div>
            <div>牙科顯微鏡可以在手術中放大畫面，在良好照明環境及視野穩定的前提下，將根管治療推進到可視化階段。 </div>
          </div>
          <div>
            <div><img src="https://static.ckjhk.com/ckj-image/2025040814372903.png" alt=""></div>
            <div>愛康健引進德國蔡司顯微鏡根管治療儀，結合顯微鏡技術和醫學技術，能清楚觀察牙齒的解剖結構和根管形態。</div>
          </div>
        </div>
      </section>
      <section class="ckj-container microroot-canal-equipment">
        <div class="d-flex flex-row align-items-end subheading">
          <span>顯微</span><span>根管治療設備</span>
        </div>
        <div class="microroot-canal-equipment-content  d-none d-md-flex">
          <div><img src="https://static.ckjhk.com/ckj-image/63c3347f61dd.jpg" alt=""></div>
          <div>
            <div><img src="https://static.ckjhk.com/ckj-image/8286033922e5.jpg" alt=""></div>
            <div>我們使用德國蔡司顯微鏡根管治療儀，一款結合顯微鏡與醫學技術的設備，大幅提升牙醫治療根管的精準度。醫生能夠清楚觀察牙齒結構和根管形態，無論進行常規治療或顯微外科手術，都能更好地保留客人健康牙齒組織。
            </div>
          </div>
        </div>
        <div class="microroot-canal-equipment-content  d-md-none">
          <swiper :slidesPerView="'auto'" :loop="true" :spaceBetween="30" :modules="modules" class="mySwiper"
            @swiper="setSwiperRef">
            <swiper-slide class="swiper-slide-item">
              <div><img src="https://static.ckjhk.com/ckj-image/63c3347f61dd.jpg" alt=""></div>
              <div>我們使用德國蔡司顯微鏡根管治療儀，一款結合顯微鏡與醫學技術的設備，大幅提升牙醫治療根管的精準度。</div>
            </swiper-slide>
            <swiper-slide class="swiper-slide-item">
              <div><img src="https://static.ckjhk.com/ckj-image/8286033922e5.jpg" alt=""></div>
              <div>醫生能夠清楚觀察牙齒結構和根管形態，無論進行常規治療或顯微外科手術，都能更好地保留客人健康牙齒組織。</div>
            </swiper-slide>
          </swiper>
        </div>
        <div class="crown-case-content-btn">
          <div @click="subNum"></div>
          <div>
            <div class="swiper-point swiper-point-active" @click="handleProcessBtn(0)"></div>
            <div class="swiper-point" @click="handleProcessBtn(1)"></div>
          </div>
          <div @click="addNum"></div>
        </div>
      </section>
      <section class="ckj-container doctor-team">
        <div class="d-flex flex-row align-items-end subheading">
          <span>牙體牙髓專科</span><span>醫生團隊</span>
        </div>
        <div class="doctor-team-content-text">牙髓病科專科醫生專門診斷和治療牙髓 (牙神經)
          及根尖周圍組織疾病，精通各種根管治療技術，包括複雜病處理、顯微根管治療、根尖手術等，能應對各種複雜情況。
        </div>
        <div class="doctor-team-content">
          <DoctorV2 :nowType="'104'" />
        </div>
        <div class="doctor-team-content-btn">
          <PageAnimBtnTypeTwo :str="'即時配對醫生'" />
        </div>
      </section>
      <section class="ckj-container root-canal-problem">
        <div>
          <V2ServiceProblem :problem-data="problemData" :v2-versions="true" />
        </div>
      </section>
    </div>

    <serviceCard />
    <BranchAddress />
    <AppointmentFormV2 />
    <FooterV2 />
    <AsideV2 />
  </div>
</template>

<style lang="scss" scoped>
:deep(.header-content) {
  .explain_box_mobile {
    background: transparent !important;
    position: absolute;
    bottom: 70px;
    z-index: 38;
    right: 0;
    left: 0;
    top: auto;
    display: flex;
    align-items: flex-end;
    justify-content: flex-end;
    margin: 0 auto !important;
  }
}

.reason {
  margin-top: 188px;

  &-lists {
    width: 100%;
    max-width: 1656px;
    display: flex;
    margin: 116px auto 0;

    &-item {
      padding: 0 55px;
      width: calc(100% / 3);

      .image {
        position: relative;

        img {
          width: 100%;
        }
      }

      .text {
        font-style: normal;
        text-align: center;
        margin-top: -45px;
        display: flex;
        flex-direction: column;
        align-items: center;
        position: relative;
        z-index: 1;

        span {
          font-size: 35px;
          font-weight: 900;

          &:nth-of-type(1) {
            color: #fff;
            border-radius: 30px;
            background: var(--indexColor1);
            text-align: center;
            width: max-content;
            padding: 0 40px;
            filter: drop-shadow(0px 3.7044363021850586px 7.408872604370117px rgba(252, 22, 130, 0.38));
          }

          &:nth-of-type(2) {
            color: var(--indexColor1);
            white-space: pre-wrap;
            margin-top: 44px;
          }
        }
      }
    }
  }
}

.care {
  margin-top: 206px;

  &-lists {
    display: flex;
    flex-wrap: wrap;
    width: 100%;
    max-width: 819px;
    margin: 127px auto 0;

    &-item {
      width: calc(100% / 3);

      &>div {
        .image {
          width: 100%;
          position: relative;
          padding: 0 calc((89px / 273px) * 100% / 2);

          &-in {
            width: 100%;
            height: 0;
            padding-bottom: 100%;
            background: #fff1f0;
            margin-bottom: 13px;
            border-radius: 10px;
            position: relative;

            img {
              position: absolute;
              top: 50%;
              left: 50%;
              transform: translate(-50%, -50%);
              max-width: 90%;
              max-height: 90%;
            }
          }
        }

        .text {
          text-align: center;
          font-size: 24px;
          font-weight: 600;
          white-space: nowrap;
        }
      }

      &:nth-of-type(n + 4) {
        margin-top: 90px;
      }

      &:nth-of-type(2n + 2) {
        &>div {
          .image {
            &-in {
              background: #fee6f1;
            }
          }
        }
      }
    }
  }

  &-btn {
    margin-top: 106px;
    display: flex;
    justify-content: center;
  }
}

.infoCard {
  margin-top: 230px;

  &-title {
    &-in {
      font-size: 50px;

      span {
        color: var(--indexColor1);
      }
    }
  }

  &-content {
    display: flex;
    align-items: center;
    width: 100%;
    max-width: 1242px;
    margin: 60px auto 0;

    &-l {
      width: calc((509 / 1242) * 100%);

      img {
        width: 100%;
      }
    }

    &-r {
      margin-left: calc((56 / 1242) * 100%);
      flex: 1;

      &>div {
        display: flex;

        span {
          color: #4d4d4d;
          font-size: 28px;
          line-height: 160%;
          font-weight: 600;

          &:nth-of-type(1) {
            min-width: 30px;
          }
        }
      }
    }
  }
}

.step {
  width: 100%;
  background: linear-gradient(90deg,
      rgba(255, 241, 240, 0) 0%,
      rgba(255, 241, 240, 0.7) 12.5%,
      rgba(255, 241, 240, 0.7) 81.99%,
      rgba(255, 241, 240, 0) 100%);
  padding: 61px 0 140px;
  margin-top: 140px;

  &-in {
    width: 100%;
    max-width: 1444px;
    margin: 0 auto;
  }

  &-lists {
    margin-top: 98px;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;

    &-in {
      display: flex;
      align-items: center;
      margin-bottom: 92px;

      &:nth-of-type(7),
      &:nth-of-type(8) {
        margin-bottom: 0;
      }

      &:nth-of-type(3),
      &:nth-of-type(6),
      &:nth-of-type(7) {
        .step-lists-in-r {
          display: none;
        }
      }

      &-l {
        width: 100%;
        max-width: 400px;
        height: 100%;
        display: flex;
        flex-direction: column;

        .title {
          display: flex;
          align-items: center;
          font-size: 35px;
          font-weight: 700;
          margin-bottom: 15px;
          color: #666666;

          img {
            height: auto;
            margin-right: 15px;
          }
        }

        .image {
          width: 100%;

          img {
            width: 100%;
            border-radius: 30px;
          }
        }

        .name {
          color: #fff;
          font-size: 20px;
          font-weight: 700;
          background: var(--indexColor1);
          margin-top: 24px;
          margin-bottom: 15px;
          padding: 8px 15px;
          clip-path: polygon(0 0, 80% 0, 85% 100%, 0 100%);
        }

        .context {
          font-size: 20px;
          font-weight: 700;
          color: #666666;
          padding: 0 15px;
        }
      }

      &-r {
        margin-left: 50px;

        img {
          width: 15px;
          height: auto;
        }
      }

      &:nth-of-type(8) {
        flex: 1;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;

        .lastBox-t {
          display: flex;
          align-items: flex-end;

          &>div {
            color: var(--indexColor1);
            font-size: 75px;
            font-weight: 700;

            // span {
            //   font-size: 85px;
            // }
            &:nth-of-type(1) {
              padding-bottom: 25px;
              margin-right: 30px;
            }

            &:nth-of-type(3) {
              padding-bottom: 25px;
              margin-left: 30px;
            }
          }
        }

        .lastBox-b {
          margin-top: 15px;
        }
      }
    }
  }
}

.note {
  margin-top: 140px;

  &-title {
    &-in {
      font-size: 50px;

      span {
        color: var(--indexColor1);
      }
    }
  }

  &-content {
    display: flex;
    align-items: center;
    width: 100%;
    max-width: 1286px;
    margin: 80px auto 0;

    &-l {
      width: calc((482 / 1242) * 100%);

      img {
        width: 100%;
      }
    }

    &-r {
      margin-left: calc((42 / 1242) * 100%);
      flex: 1;

      &>div {
        display: flex;

        span {
          color: #4d4d4d;
          font-size: 28px;
          line-height: 160%;
          font-weight: 600;

          &:nth-of-type(1) {
            min-width: 30px;
          }
        }
      }
    }
  }
}

.Root_canal_treatment_equipment {
  width: 100%;
  max-width: calc(1284px + 60px);
  margin: 140px auto 0;

  &-in {
    display: flex;
    margin-top: 53px;

    &-l {
      width: calc(595 / 1284 * 100%);
      margin-right: calc(53 / 1284 * 100%);

      img {
        width: 100%;
      }
    }

    &-r {
      flex: 1;

      img {
        width: 100%;
      }

      span {
        width: 100%;
        text-align: justify;
        font-size: 28px;
        line-height: 160%;
        color: var(--textColor);
        margin-top: 40px;
        display: block;
      }
    }
  }
}

.doctorTeam {
  margin-top: 140px;
}

@keyframes btnAnim {
  0% {
    clip-path: polygon(-10% 0, 0 0, -10% 100%, -20% 100%);
  }

  50% {
    clip-path: polygon(50% 0, 60% 0, 50% 100%, 40% 100%);
  }

  100% {
    clip-path: polygon(110% 0, 120% 0, 110% 100%, 100% 100%);
  }
}

@keyframes btnAnim2 {
  0% {
    width: 100%;
    height: 100%;
    opacity: 0;
  }

  50% {
    width: 100%;
    height: 100%;
    opacity: 1;
  }

  90% {
    width: 130%;
    height: 160%;
    opacity: 0;
  }

  100% {
    width: 130%;
    height: 160%;
    opacity: 0;
  }
}

@keyframes btnAnim3 {
  0% {
    width: 100%;
    height: 100%;
    opacity: 0;
  }

  60% {
    width: 100%;
    height: 100%;
    opacity: 1;
  }

  100% {
    width: 130%;
    height: 160%;
    opacity: 0;
  }
}

@media (min-width: 768px) and (max-width: 1920px) {
  .reason {
    margin-top: 9.7917vw;

    &-lists {
      max-width: 86.25vw;
      margin: 6.0417vw auto 0;

      &-item {
        padding: 0 2.8646vw;

        .text {
          margin-top: -2.3438vw;

          span {
            font-size: 1.8229vw;

            &:nth-of-type(1) {
              border-radius: 1.5625vw;
              padding: 0 2.0833vw;
              filter: drop-shadow(0px 0.1929vw 0.3859vw rgba(252, 22, 130, 0.38));
            }

            &:nth-of-type(2) {
              margin-top: 2.2917vw;
            }
          }
        }
      }
    }
  }

  .care {
    margin-top: 10.7292vw;

    &-lists {
      max-width: 42.6563vw;
      margin: 6.6146vw auto 0;

      &-item {
        &>div {
          .image {
            &-in {
              margin-bottom: 0.6771vw;
              border-radius: 0.5208vw;
            }
          }

          .text {
            font-size: 1.25vw;
          }
        }

        &:nth-of-type(n + 4) {
          margin-top: 4.6875vw;
        }
      }
    }

    &-btn {
      margin-top: 5.5208vw;
    }
  }

  .infoCard {
    margin-top: 11.9792vw;

    &-title {
      &-in {
        font-size: 2.6042vw;
      }
    }

    &-content {
      max-width: 64.6875vw;
      margin: 3.125vw auto 0;

      &-r {
        &>div {
          span {
            font-size: 1.4583vw;

            &:nth-of-type(1) {
              min-width: 1.5625vw;
            }
          }
        }
      }
    }
  }

  .Root_canal_treatment_equipment {
    max-width: calc(66.875vw + 3.125vw);
    margin: 7.2917vw auto 0;

    &-in {
      margin-top: 2.7604vw;

      &-r {
        span {
          font-size: 1.4583vw;
          margin-top: 2.0833vw;
        }
      }
    }
  }

  .step {
    padding: 3.1771vw 0 7.2917vw;
    margin-top: 7.2917vw;

    &-in {
      max-width: 75.2083vw;
    }

    &-lists {
      margin-top: 5.1042vw;

      &-in {
        margin-bottom: 4.7917vw;

        &-l {
          max-width: 20.8333vw;

          .title {
            font-size: 1.8229vw;
            margin-bottom: 0.7813vw;

            img {
              margin-right: 0.7813vw;
            }
          }

          .image {
            img {
              border-radius: 1.5625vw;
            }
          }

          .name {
            font-size: 1.0417vw;
            margin-top: 1.25vw;
            margin-bottom: 0.7813vw;
            padding: 0.4167vw 0.7813vw;
          }

          .context {
            font-size: 1.0417vw;
            padding: 0 0.7813vw;
          }
        }

        &-r {
          margin-left: 2.6042vw;

          img {
            width: 0.7813vw;
          }
        }

        &:nth-of-type(8) {
          .lastBox-t {
            &>div {
              font-size: 3.9063vw;

              &:nth-of-type(1) {
                padding-bottom: 1.3021vw;
                margin-right: 1.5625vw;
              }

              &:nth-of-type(3) {
                padding-bottom: 1.3021vw;
                margin-left: 1.5625vw;
              }
            }
          }

          .lastBox-b {
            margin-top: 0.7813vw;
          }
        }
      }
    }
  }

  .note {
    margin-top: 7.2917vw;

    &-title {
      &-in {
        font-size: 2.6042vw;
      }
    }

    &-content {
      max-width: 66.9792vw;
      margin: 4.1667vw auto 0;

      &-r {
        &>div {
          span {
            font-size: 1.4583vw;

            &:nth-of-type(1) {
              min-width: 1.5625vw;
            }
          }
        }
      }
    }
  }
}

@media only screen and (max-width: 768px) {
  :deep(.explain_box_mobile) {
    top: 0 !important;
    margin-left: 0 !important;
    margin-right: auto !important;
  }

  :deep(.pageIn) {
    margin-top: 30px;
  }

  :deep(.header-content) {
    .explain_box_mobile {
      align-items: flex-end;
      background: transparent !important;
      display: flex;
      justify-content: flex-end;
      margin: 0 auto !important;
      left: auto;
      right: 0;
      bottom: -20px;
      position: absolute;
      top: auto;
      z-index: 35;
    }

    .waterBg-implant::after,
    .waterBg-implant::before {
      bottom: -28vw;
    }
  }

  .reason {
    margin-top: 54px;

    &-title {
      &-in {
        font-size: 26px;
      }
    }

    &-lists {
      flex-direction: column;
      gap: 0;
      margin: 50px auto 0;
      padding: 0 4vw;

      &-item {
        width: 42.6vw;
        padding: 0 0;

        .text {
          margin-top: -34px;

          span {
            font-size: 4.226vw;

            &:nth-of-type(1) {
              padding: 8px 40px;
            }

            &:nth-of-type(2) {
              margin-top: 20px;
              white-space: normal;
            }
          }
        }

        // &:not(:last-child) {
        //   margin-bottom: 35px;
        // }
      }

      &>div:nth-child(2) {
        margin: 0 0 0 auto;
      }

      &>div:nth-child(2),
      &>div:nth-child(3) {
        margin-top: -65px;
      }
    }
  }

  .care {
    margin-top: 80px;
    padding-bottom: 0px;

    &-title {
      &-in {
        font-size: 26px;
      }
    }

    &-lists {
      width: auto;
      margin: 34px 15px 0;

      &-item {
        width: calc(100% / 3);

        &>div {
          .image {
            padding: 0 5px;
          }

          .text {
            white-space: pre-wrap;
            font-size: 14px;
            font-size: 4.2665vw;
            color: #4d4d4d;
          }
        }

        &:nth-of-type(1) {
          &>div {
            .text {
              padding: 0 0;
            }
          }
        }

        &:nth-of-type(3) {
          &>div {
            .text {
              padding: 0 15px;
            }
          }
        }

        &:nth-of-type(n + 4) {
          margin-top: 30px;
        }
      }
    }

    &-btn {
      margin-top: 30px;
    }
  }

  .infoCard {
    margin-top: 80px;

    &-title {
      &-in {
        font-size: 26px;

        span {
          display: inline-block;
        }
      }
    }

    &-content {
      flex-direction: column;
      align-items: flex-start;
      margin: 0 auto 0;

      &-l {
        width: 100%;
        padding: 0 53px;
      }

      &-r {
        width: 100vw;
        margin-left: 0;
        padding: 9.065vw 6.665vw 0;

        &>div {
          display: flex;
          flex-direction: column;
          width: 41.825vw;

          &>div:nth-child(2) {
            margin-top: 1.6vw;

            span {
              color: var(--Grey-Deep, #4d4d4d);
              text-align: justify;
              font-family: 'FakePearl-Regular';
              font-size: 3.2vw;
              font-style: normal;
              font-weight: 500;
              line-height: 160%;
              /* 19.2px */
              letter-spacing: 1.2px;
            }
          }
        }

        &>div:nth-child(2) {
          margin: 0 0 0 auto;
        }

        &>div:nth-child(2),
        &>div:nth-child(3) {
          margin-top: -110px;
        }
      }
    }
  }

  .step::after {
    content: '';
    display: block;
    position: absolute;
    z-index: -1;
    width: 30%;
    height: 330vw;
    top: 0;
    left: 50%;
    transform: translateX(-50%);
    background: linear-gradient(0deg,
        rgba(255, 241, 240, 0) 0%,
        rgba(255, 241, 240, 0.7) 12.5%,
        rgba(255, 241, 240, 0.7) 81.99%,
        rgba(255, 241, 240, 0) 100%);
  }

  .step {
    // background: linear-gradient(
    //   0deg,
    //   rgba(255, 241, 240, 0) 0%,
    //   rgba(255, 241, 240, 0.7) 12.5%,
    //   rgba(255, 241, 240, 0.7) 81.99%,
    //   rgba(255, 241, 240, 0) 100%
    // );
    position: relative;
    background: transparent;
    margin-top: 40px;
    padding: 46px 0;

    &-title {
      &-in {
        font-size: 26px;
      }
    }

    &-lists {
      width: auto;
      margin: 57px 8vw 0;
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      justify-items: center;
      gap: 0 20px;

      &-in {
        width: calc(140 / 375 * 100vw);
        margin-bottom: 0;

        // &:nth-of-type(n + 4) {
        //   margin-bottom: 30px;
        // }
        // &:nth-of-type(3),
        // &:nth-of-type(6) {
        //   .step-lists-in-r {
        //     display: block;
        //   }
        // }
        &-l {
          position: relative;

          .title {
            position: absolute;
            padding: 0 6px;
            top: -45px;
            left: -15px;
            width: 70px;
            margin: 0 auto;
            color: var(--Theme-Color, #fc1682);
            text-align: center;
            font-family: 'Noto Serif HK';
            font-size: 60px;
            font-style: normal;
            font-weight: 400;
            line-height: 140%;
            /* 84px */
            letter-spacing: -3px;
            display: flex;
            justify-content: center;
            background: url('https://static.cmereye.com/imgs/2024/08/a53173454afef713.png') no-repeat;
            background-size: 100% 100%;
            display: inline-block;
            background-position-x: 5px;

            &>img {
              display: none;
            }
          }

          .image {
            padding: 0 6px;

            img {
              border-radius: 12px;
              border: 2px solid var(--Theme-Color, #fc1682);
            }
          }

          .name {
            margin: 0;
            margin-top: 6px;
            font-size: 16px;
            clip-path: none;
            background: transparent;
            padding: 0;
            padding-left: 5px;
            color: var(--Theme-Color, #fc1682);
            font-family: 'FakePearl-Regular';
            font-size: 16px;
            font-style: normal;
            font-weight: 600;
            line-height: 130%;
            /* 20.8px */
          }

          .context {
            // font-size: 16px;
            padding-left: 5px;
            color: var(--Grey-Deep, #4d4d4d);
            text-align: justify;
            font-family: 'FakePearl-Regular';
            font-size: 12px;
            font-style: normal;
            font-weight: 500;
            line-height: 160%;
            /* 19.2px */
            letter-spacing: 1.2px;
          }
        }

        &-r {
          display: none;
          margin-top: 30px;
          margin-left: 0;

          img {
            transform: rotate(90deg);
          }
        }

        &:nth-of-type(8) {
          margin-top: 15px;

          .lastBox-t {
            &>div {
              font-size: 28px;

              // span {
              //   font-size: 34px;
              // }
              img {
                width: 14px;
                height: 16px;
              }

              &:nth-of-type(1) {
                padding-bottom: 10px;
                margin-right: 7px;
              }

              &:nth-of-type(3) {
                padding-bottom: 10px;
                margin-left: 7px;
              }
            }
          }

          .lastBox-b {
            margin-top: 20px;
          }
        }
      }

      &>div:nth-child(odd) {
        margin-top: 60px;
      }

      &>div:nth-child(7) {
        margin-top: 20px;
      }

      &>div:nth-child(even) {
        margin-top: 120px;
      }
    }
  }

  .step-lists-outside {
    margin-top: 40px;
    width: 100%;

    &>div:nth-child(1) {
      display: none;
    }

    :deep(.lastBox-b) {
      margin: 0 auto;

      .animbtntypetwo {
        justify-content: center;
      }

      .animbtntypetwo-in {
        &>span {
          font-size: 5.33vw;
        }
      }
    }
  }

  .note {
    margin-top: 34px;

    &-title {
      &-in {
        font-size: 26px;

        span {
          display: inline-block;
        }
      }
    }

    &-content {
      flex-direction: column;
      align-items: flex-start;
      margin: 72px auto 0;

      &-l {
        width: 100%;
        padding: 0 53px;
      }

      &-r {
        margin-left: 0;
        padding: 35px 30px 0;

        &>div {
          span {
            font-size: 16px;
            font-weight: 500;

            &:nth-of-type(1) {
              min-width: 15px;
            }
          }
        }
      }
    }
  }

  .mobile-note-new {
    margin-top: 60px;
    margin-left: 30px;

    &>div:nth-child(1) {
      display: flex;
      align-items: flex-end;

      &>div:nth-child(1) {
        position: relative;
        z-index: 6;
      }

      &>div:nth-child(2) {
        position: relative;
        display: flex;
        flex-direction: column;
        padding-bottom: 20px;
        flex: 1;
        width: 100%;

        &>span:nth-child(1) {
          color: var(--Grey-Deep, #4d4d4d);
          font-family: 'FakePearl-Regular';
          font-size: 20px;
          font-style: normal;
          font-weight: 600;
          line-height: 126%;
          /* 25.2px */
        }

        &>span:nth-child(2) {
          color: var(--Theme-Color, #fc1682);
          font-family: 'FakePearl-Regular';
          font-size: 26px;
          font-style: normal;
          font-weight: 600;
          line-height: 126%;
          letter-spacing: 2.6px;
        }
      }

      &>div:nth-child(2)::after {
        display: inline-block;
        width: 120%;
        height: 1px;
        background: #fc1682;
        content: '';
        position: absolute;
        bottom: 15px;
        right: 0;
      }
    }
  }

  .mobile-note-content {
    margin-top: 25px;
    margin-right: 30px;
    display: grid;
    gap: 10px 36px;
    grid-template-columns: repeat(2, 1fr);

    &>div {
      padding-left: 12px;
      color: var(--Grey-Deep, #4d4d4d);
      text-align: justify;
      font-family: 'Noto Sans HK';
      font-size: 12px;
      font-style: normal;
      font-weight: 500;
      line-height: 200%;
      /* 24px */
      letter-spacing: 1.2px;

      &>span:nth-child(1) {
        display: none;
      }

      position: relative;
    }

    &>div::before {
      content: '';
      background: url('../../assets/images/triangle.svg') no-repeat;
      background-size: 100% 100%;
      display: inline-block;
      width: 9px;
      height: 11px;
      position: absolute;
      top: 7px;
      left: -2px;
    }
  }

  .Root_canal_treatment_equipment {
    margin-top: 60px;

    &-in {
      margin-top: 30px;
      padding: 0 5.33vw;
      flex-direction: column;
      position: relative;

      :deep(.swiper-slide) {
        width: 71.733vw;
        border-top: 1px solid #fc1682;
        border-left: 1px solid #fc1682;
        border-bottom: 1px solid #fc1682;
        box-sizing: border-box;
        padding: 5.33vw;

        &>div:nth-child(2) {
          margin-top: 16px;
          min-height: 33.0665vw;
          color: #4d4d4d;
          text-align: justify;
          font-family: 'FakePearl-Regular';
          font-size: 3.2vw;
          font-style: normal;
          font-weight: 400;
          line-height: 160%;
          /* 19.2px */
          letter-spacing: 1.2px;
        }
      }

      :deep(.swiper-slide:last-child) {
        border-right: 1px solid #fc1682;
      }

      &-l {
        width: 100%;
      }

      &-r {
        margin-top: 20px;

        span {
          font-size: 16px;
          line-height: 200%;
          margin-top: 20px;
          padding: 0 10px;
        }
      }
    }
  }

  :deep(.swiper) {
    margin: 0;
  }

  :deep(.point) {
    margin-top: 20px;
    width: 19.733vw;

    .boxLine {
      display: none;
    }

    .boxLine-current {
      display: none;
    }
  }

  .boxRound-rootCanal {
    position: absolute;
    bottom: -14vw;
    left: 14vw;
    display: flex;
    width: 19.733vw;
    height: 9.33vw;
    border: 1px solid #fc1682;

    &>div {
      flex: 1;
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 2.4vw;
      box-sizing: border-box;

      &>svg {
        fill: #f7c3c3;
      }
    }

    &>div:nth-child(1) {
      border-right: 1px solid #fc1682;
    }
  }

  .doctorTeam {
    margin-top: 30px;
  }

}
</style>

<style lang="scss" scoped>
@media screen and (min-width:991px) {
  .root-canal-therapy {
    margin-top: 42px;
    box-sizing: border-box;
    padding: 30px 0;
    display: flex;
    align-items: center;
    position: relative;
    justify-content: flex-end;

    &>div:nth-child(1) {
      position: absolute;
      z-index: 2;
      width: 467px;
      left: 0;
      display: flex;
      flex-direction: column;
      gap: 34px 0;

      &>div:nth-child(1) {
        &>span:nth-child(1) {
          color: var(--Grey-Dark, #333);
          font-family: "Noto Sans HK";
          font-size: 24px;
          font-style: normal;
          font-weight: 700;
          line-height: normal;
          letter-spacing: 2.4px;
        }

        &>span:nth-child(2) {
          color: var(--Brand-Color, #F8298A);
          font-family: "Noto Sans HK";
          font-size: 30px;
          font-style: normal;
          font-weight: 700;
          line-height: normal;
          letter-spacing: 3px;
        }
      }

      .subheading {
        margin-left: 0;
        padding-left: 0;
      }

      .subheading::after {
        content: none;
      }

      &>div:nth-child(2) {
        color: var(--Grey-Deep, #4D4D4D);
        text-align: justify;
        font-family: "Noto Sans HK";
        font-size: 20px;
        font-style: normal;
        font-weight: 400;
        line-height: 160%;
        /* 32px */
        letter-spacing: 4px;
      }
    }

    &>div:nth-child(2) {
      position: relative;
      z-index: 1;
      right: 0;
      width: 555px;
      height: 277px;

      &>img {
        width: 100%;
        height: 100%;
        object-fit: cover;
      }
    }
  }

  .charge-item {
    box-sizing: border-box;
    padding: 30px 0;

    &>div:nth-child(2) {
      &>div {
        margin-top: 20px;
      }

      &>div:nth-child(1) {
        width: 556px;
        height: 410px;
        margin: 20px auto 0;

        &>img {
          width: 100%;
          height: 100%;
          object-fit: cover;
        }
      }

      &>div:nth-child(2) {
        border-radius: 20px;
        box-shadow: 0px 6.761px 6.761px 0px rgba(77, 77, 77, 0.20);
        overflow: hidden;

        &>div {
          box-sizing: border-box;
          padding: 20px 35px;
          display: flex;
          align-items: center;
          justify-content: space-between;
          ;

          &>div {
            color: var(--White, #FFF);
            text-align: center;
            font-family: "Noto Sans HK";
            font-size: 24px;
            font-style: normal;
            font-weight: 700;
            line-height: normal;
            letter-spacing: 2.4px;
          }

        }

        &>div:nth-child(1) {
          background: var(--Brand-Color, #F8298A);
        }

        &>div:nth-child(2) {
          background: var(--White, #FFF);

          &>div {
            color: var(--Brand-Color, #F8298A);
          }
        }

        &>div:nth-child(3) {
          background: var(--Palest-Pink, #FFF7F8);

          &>div {
            color: var(--Blue-Deep, #00AEFF);
          }
        }
      }

      &>div:nth-child(3) {
        display: flex;
        flex-direction: column;
        align-items: center;

        &>div:nth-child(1) {
          color: var(--Grey-Dark, #333);
          text-align: center;
          font-family: "Noto Sans HK";
          font-size: 24px;
          font-style: normal;
          font-weight: 700;
          line-height: normal;
          letter-spacing: 2.4px;

          span {
            color: var(--Brand-Color, #F8298A);
          }
        }

        &>div:nth-child(2) {
          color: var(--Grey-Dark, #333);
          font-family: "Noto Sans HK";
          font-size: 20px;
          font-style: normal;
          font-weight: 400;
          line-height: 160%;
          letter-spacing: 4px;
        }
      }
    }
  }

  .seven-steps {
    padding: 30px 0;
    box-sizing: border-box;

    .seven-steps-title {
      &>div {
        color: var(--Grey-Deep, #4D4D4D);
        text-align: center;
        font-family: "Noto Sans HK";
        font-size: 30px;
        font-style: normal;
        font-weight: 700;
        line-height: normal;
        letter-spacing: 3px;

        &>span {
          color: var(--Brand-Color, #F8298A);
        }
      }
    }

    .seven-steps-content {
      margin-top: 20px;
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 32px 30px;

      &>div:last-child {
        grid-column: span 2;

        .seven-steps-content-item {
          width: 475.864px;
          height: 210.71px;
          margin-left: 53px;

          &>div {
            &>img {
              width: 100%;
              height: 100%;
              object-fit: cover;
            }
          }
        }
      }

      .seven-steps-content-item {
        display: flex;
        flex-direction: column;
        align-items: center;

        &>div:nth-child(1) {
          position: relative;

          &>div:nth-child(1) {
            position: absolute;
            z-index: 5;
            background: url('https://static.cmereye.com/imgs/2024/11/3b0a5e9326c68638.png') no-repeat;
            background-size: contain;

            top: -0.49vw;
            left: -0.49vw;
            width: 3.4375vw;
            height: 3.4375vw;

            color: var(--White, #FFF);
            font-family: "Noto Sans HK";
            font-size: 34px;
            font-style: normal;
            font-weight: 700;
            line-height: normal;
            letter-spacing: 3.4px;
            display: flex;
            align-items: center;
            justify-content: center;
          }

          &>div:nth-child(2) {
            position: relative;
          }

          &>div:nth-child(2)::after {
            content: "";
            position: absolute;
            width: 21px;
            height: 63px;
            background: url(~/assets/images/2025040208530601.png) no-repeat;
            background-size: cover;
            top: 50%;
            right: -15px;
            z-index: -1;
            transform: translateY(-50%);
          }

        }

        &>div:nth-child(2) {
          margin-top: 10px;
          color: var(--Grey-Dark, #333);
          text-align: center;
          font-family: "Noto Sans HK";
          font-size: 20px;
          font-style: normal;
          font-weight: 500;
          line-height: normal;
          letter-spacing: 2px;
        }
      }

      &>div:nth-child(7) {
        .seven-steps-content-item {
          &>div:nth-child(1) {
            background: salmon;

            &>div:nth-child(2)::after {
              content: none;
            }
          }
        }
      }
    }
  }

  .microroot-canal {
    padding: 30px 0;
    box-sizing: border-box;

    .microroot-canal-content {
      margin-top: 20px;
      display: flex;
      align-items: flex-start;
      gap: 0 15px;

      &>div:nth-child(1) {
        width: 300px;
        height: 206.324px;

        &>img {
          width: 100%;
          height: 100%;
          object-fit: cover;
        }
      }

      &>div:nth-child(2) {
        max-width: 645px;
        padding-left: 25px;

        ul>li {
          color: var(--Grey-Deep, #4D4D4D);
          text-align: justify;
          font-family: "Noto Sans HK";
          font-size: 18px;
          font-style: normal;
          font-weight: 400;
          line-height: 200%;
          letter-spacing: 1.8px;
          list-style: disc;
        }
      }
    }
  }

  .microroot-canal-equipment {
    padding: 30px 0;
    box-sizing: border-box;

    .microroot-canal-equipment-content {
      margin-top: 20px;
      gap: 0 35px;
      display: flex;

      &>div:nth-child(1) {
        width: 445.124px;
        height: auto;

        &>img {
          width: 100%;
          height: 100%;
          object-fit: cover;
        }
      }

      &>div:nth-child(2) {
        max-width: 478.164px;

        &>div:nth-child(1) {
          width: 478.164px;
          height: 368.948px;

          &>img {
            width: 100%;
            height: 100%;
            object-fit: cover;
          }
        }

        &>div:nth-child(2) {
          margin-top: 18px;
          color: var(--Grey-Deep, #4D4D4D);
          text-align: justify;
          font-family: "Noto Sans HK";
          font-size: 20px;
          font-style: normal;
          font-weight: 400;
          line-height: 160%;
          letter-spacing: 4px;
        }
      }
    }
  }

  .doctor-team {
    padding: 30px 0;
    box-sizing: border-box;

    .doctor-team-content-text {
      margin-top: 15px;
      color: var(--Grey-Deep, #4D4D4D);
      text-align: justify;
      font-family: "Noto Sans HK";
      font-size: 20px;
      font-style: normal;
      font-weight: 400;
      line-height: 160%;
      letter-spacing: 4px;
    }

    .doctor-team-content {
      margin-top: 15px;
    }

    .doctor-team-content-btn {
      margin: 15px auto;
      display: flex;
      justify-content: center;
      align-items: center;
    }
  }

  .root-canal-problem {
    padding: 30px 0;
    box-sizing: border-box;

    :deep(.problem) {
      margin-top: 0;
    }
  }

  :deep(.index-dentalServices) {
    box-sizing: border-box;
    padding: 30px 0;
  }




  .banner-in-box {
    position: absolute;
    top: 50%;
    left: 0;
    transform: translateY(-50%);
    height: 20.83vw;
    width: 100%;
    z-index: 10;
  }

  .banner-image {
    position: absolute;
    z-index: 3;
    top: 4vw;
    left: 50%;
    width: 9.0625vw;
    height: 9.0625vw;

    &>img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  }

  .banner-content {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    width: 23.9583vw;
    position: absolute;
    left: 40%;
    top: 50%;
    transform: translate(-50%, -50%);

    &>div {
      display: flex;
      align-items: flex-end;
      justify-content: center;
    }

    .content-title {
      color: var(--White, #fff);
      text-align: right;
      -webkit-text-stroke-width: 0.5;
      -webkit-text-stroke-color: var(--White, #fff);
      font-family: 'FakePearl-Regular';
      font-size: clamp(40px, 5.7vw, 110px);
      font-style: normal;
      font-weight: 600;
      line-height: 100%;
      /* 176px */
      letter-spacing: 6.6px;
      position: relative;
      z-index: 6;
      bottom: 0;

      border-radius: 0.6942vw 0.6942vw 0px 0px;
      background: var(--Liner-purple,
          linear-gradient(269deg,
            var(--Brand-Color, #fc1682) 10.21%,
            #710d54 122.73%));
      box-sizing: border-box;
      padding: 0.859375vw 0;
      color: var(--White, #fff);
      text-align: center;
      text-shadow: 0px 5.333px 5.333px rgba(0, 0, 0, 0.25);
      font-family: 'Noto Sans HK';
      font-size: 1.565vw;
      font-style: normal;
      font-weight: 700;
      letter-spacing: 0.165vw;
      width: 100%;
    }

    .price-style {
      width: 19.0625vw;
      height: 11.145vw;
      position: relative;
      right: -3.64583vw;

      &>img {
        width: 100%;
        height: 100%;
        object-fit: contain;
      }
    }

    .content-price {
      width: 100%;
      background: #fff;
      box-sizing: border-box;
      padding: 1.0465vw;
      display: flex;
      gap: 0 0.52vw;
      min-height: 4.78135vw;
      box-sizing: border-box;
      padding: 0.52vw;
      align-items: center;
      font-family: 'Noto Sans HK';
      font-size: 1.7442vw;
      font-style: normal;
      font-weight: 900;
      line-height: 2.2222vw;
      /* 114.286% */
      letter-spacing: 0.29165vw;
      justify-content: center;
      border-radius: 0px 0px 10px 10px;
      background: var(--White, #fff);
      box-shadow: 0px 4px 4px rgba(77, 77, 77, 0.2);

      &>div:nth-child(1) {
        position: relative;
        color: var(--Grey-Dark, #333);
        text-align: right;
        text-shadow: 1.3px 1.333px 1.333px #faeaf2,
          1.33px -1.333px 1.333px #faeaf2, -1.33px 1.333px 1.333px #faeaf2,
          -1.33px -1.333px 1.333px #faeaf2;
        font-family: 'Noto Sans HK';
        font-size: 1.744vw;
        font-style: normal;
        font-weight: 900;
        line-height: 2.2222vw;
        /* 114.286% */
        letter-spacing: 0.29165vw;
        top: auto;
      }
    }
  }
}

/* 992px */
@media screen and (max-width: 992px) {
  .root-canal-therapy {
    margin-bottom: 8vw;

    &>div:nth-child(1) {
      &>div:nth-child(3) {
        color: var(--Grey-Deep, #4D4D4D);
        text-align: justify;
        font-family: "Noto Sans HK";
        font-size: 3.733vw;
        font-style: normal;
        font-weight: 500;
        line-height: 150%;
        letter-spacing: 0.7px;
        box-sizing: border-box;
        padding: 0 8vw;
      }
    }
  }

  .charge-item {
    margin: 8vw 0;

    .charge-item-content {
      &>div:nth-child(1) {
        box-sizing: border-box;
        padding: 4vw 0;
        width: 83.465vw;
        height: auto;
        margin: 0 auto;

        &>img {
          width: 100%;
          height: 100%;
          object-fit: contain;
        }
      }

      &>div:nth-child(2) {
        border-radius: 5.33vw;
        margin: 4vw 5.33vw;
        box-shadow: 0px 6.761px 6.761px 0px rgba(77, 77, 77, 0.20);
        overflow: hidden;
        box-sizing: border-box;

        &>div {
          box-sizing: border-box;
          padding: 1.865vw 6.133vw;
          display: flex;
          align-items: center;
          justify-content: space-between;

          &>div {
            text-align: center;
            color: var(--White, #FFF);
            font-family: "Noto Sans HK";
            font-size: 4.265vw;
            font-style: normal;
            font-weight: 700;
            line-height: normal;
            letter-spacing: 0.4265vw;
          }

        }

        &>div:nth-child(1) {
          background: var(--Brand-Color, #F8298A);
        }

        &>div:nth-child(2) {
          background: var(--White, #FFF);

          &>div {
            color: var(--Brand-Color, #F8298A);
          }
        }

        &>div:nth-child(3) {
          background: var(--Palest-Pink, #FFF7F8);

          &>div {
            color: var(--Blue-Deep, #00AEFF);
          }
        }
      }

      &>div:nth-child(3) {
        display: flex;
        flex-direction: column;
        align-items: center;

        &>div:nth-child(1) {
          color: var(--Grey-Dark, #333);
          text-align: center;
          font-family: "Noto Sans HK";
          font-size: 4.265vw;
          font-style: normal;
          font-weight: 700;
          line-height: normal;
          letter-spacing: 0.4265vw;

          span {
            color: var(--Brand-Color, #F8298A);
          }
        }

        &>div:nth-child(2) {
          color: var(--Grey-Dark, #333);
          font-family: "Noto Sans HK";
          font-size: 3.733vw;
          font-style: normal;
          font-weight: 500;
          line-height: 150%;
          letter-spacing: 0.7px;
        }
      }

    }
  }

  .seven-steps {
    margin: 8vw 0;
    box-sizing: border-box;
    padding: 0 5.33vw;

    .seven-steps-title {
      color: var(--Grey-Mid, #666);
      text-align: center;
      font-family: "Noto Sans HK";
      font-size: 4.8vw;
      font-style: normal;
      font-weight: 700;
      line-height: normal;
      letter-spacing: 0.48vw;

      span {
        color: var(--Brand-Color, #F8298A);
      }
    }

    .seven-steps-content {
      margin-top: 5.33vw;
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 9.33vw 4.265vw;
      position: relative;
      z-index: 1;

      &>div:last-child {
        grid-column: span 2;

        .seven-steps-content-item {
          width: 58.893vw;
          height: 26.079vw;
          margin-left: 0;

          &>div {
            &>img {
              width: 100%;
              height: 100%;
              object-fit: cover;
            }
          }
        }
      }

      .seven-steps-content-item {
        display: flex;
        flex-direction: column;
        align-items: center;

        &>div:nth-child(1) {
          position: relative;

          &>div:nth-child(1) {
            position: absolute;
            z-index: 5;
            background: url('https://static.cmereye.com/imgs/2024/11/3b0a5e9326c68638.png') no-repeat;
            background-size: contain;

            top: -1.06vw;
            left: -1.06vw;
            width: 8vw;
            height: 8vw;

            color: var(--White, #FFF);
            font-family: "Noto Sans HK";
            font-size: 4.8vw;
            font-style: normal;
            font-weight: 700;
            line-height: normal;
            letter-spacing: 0.48vw;
            display: flex;
            align-items: center;
            justify-content: center;
          }

          &>div:nth-child(2) {
            position: relative;
          }

          &>div:nth-child(2)::after {
            content: "";
            position: absolute;
            width: 2.133vw;
            height: 6.4vw;
            background: url(/_nuxt/assets/images/2025040208530601.png) no-repeat;
            background-size: contain;
            top: 50%;
            right: -2.13vw;
            z-index: -1;
            transform: translateY(-50%);
          }

        }

        &>div:nth-child(2) {
          margin-top: 1.33vw;
          color: var(--Grey-Dark, #333);
          text-align: center;
          font-family: "Noto Sans HK";
          font-size: 3.733vw;
          font-style: normal;
          font-weight: 350;
          line-height: 150%;
          white-space: nowrap;
        }
      }

      &>div:nth-child(7) {
        .seven-steps-content-item {

          &>div:nth-child(1) {
            background: salmon;

            &>div:nth-child(2)::after {
              content: none;
            }
          }
        }
      }
    }
  }

  .microroot-canal {
    margin: 8vw 0;
    box-sizing: border-box;
    padding: 0 5.33vw;

    .microroot-canal-content {
      margin-top: 5.33vw;
      display: flex;
      flex-direction: column;
      gap: 5.33vw 0;
      position: relative;
      z-index: 1;

      &>div {
        display: flex;
        gap: 0 3.465vw;
        align-items: flex-start;
        justify-content: space-between;

        &>div:nth-child(1) {
          width: 40vw;
          padding-left: 1.865vw;
          padding-top: 1.865vw;
          height: 26.65vw;
          position: relative;
          z-index: 5;

          &>img {
            width: 100%;
            height: 100%;
            object-fit: cover;
          }
        }

        &>div:nth-child(1)::after {
          content: "";
          position: absolute;
          width: 22.936vw;
          height: 22.936vw;
          border-radius: 2.65vw;
          background: var(--Brand-Color, #F8298A);
          z-index: -1;
          top: 0;
          left: 0;
        }

        &>div:nth-child(2) {
          width: 43.733vw;
          color: var(--Grey-Deep, #4D4D4D);
          text-align: justify;
          font-family: "Noto Sans HK";
          font-size: 3.2vw;
          font-style: normal;
          font-weight: 400;
          line-height: 150%;
          /* 18px */
          letter-spacing: 0.6px;
        }
      }

      &>div:nth-child(2) {
        flex-direction: row-reverse;

        &>div:nth-child(1) {
          padding-left: 0;
          padding-right: 1.865vw;
        }

        &>div:nth-child(1)::after {
          content: "";
          position: absolute;
          width: 22.936vw;
          height: 22.936vw;
          border-radius: 2.65vw;
          background: var(--Brand-Color, #F8298A);
          z-index: -1;
          top: 0;
          left: auto;
          right: 0;
        }

      }
    }
  }

  .microroot-canal-equipment {
    margin: 8vw 0;
    box-sizing: border-box;
    padding: 0 5.33vw;

    .microroot-canal-equipment-content {
      margin-top: 5.33vw;

      .swiper-slide-item {
        max-width: 61.33vw;

        &>div:nth-child(1) {
          width: 61.33vw;
          height: 61.33vw;
          border-radius: 2.56vw;
          overflow: hidden;

          &>img {
            width: 100%;
            height: 100%;
            object-fit: cover;
          }
        }

        &>div:nth-child(2) {
          margin-top: 4vw;
          color: #4D4D4D;
          text-align: justify;
          font-family: "Noto Sans HK";
          font-size: 3.2vw;
          font-style: normal;
          font-weight: 500;
          line-height: 150%;
          letter-spacing: 0.6px;
        }
      }
    }

    .crown-case-content-btn {
      display: flex;
      align-items: center;
      justify-content: center;
      margin-top: 4vw;
      gap: 0 2.665vw;

      &>div:nth-child(2) {
        display: flex;
        align-items: center;
        justify-content: center;
        gap: 0 2.665vw;

        &>div {
          width: 3.21vw;
          height: 3.2vw;
          overflow: hidden;
          border-radius: 50%;
          background: var(white, #fff);
          box-shadow: 0px 5.333px 5.333px rgba(77, 77, 77, 0.2);
        }
      }

      &>div:nth-child(1),
      &>div:nth-child(3) {
        width: 5.33vw;
        height: 5.33vw;
        overflow: hidden;
        border-radius: 50%;
        background: url('~/assets/images/2025040215172701.svg') no-repeat;
        background-size: cover;
        box-shadow: 0px 5.333px 5.333px rgba(77, 77, 77, 0.2);
      }

      &>div:nth-child(3) {
        transform: rotate(180deg);
        box-shadow: -5.333px -5.333px 5.333px rgba(77, 77, 77, 0.2);
      }

      .swiper-point-active {
        background: var(--Pink-Mid, #f670ae);
        filter: drop-shadow(0px 4px 4px rgba(77, 77, 77, 0.2));
        transition: all 0.3s ease-in-out;
      }
    }
  }

  .doctor-team {
    margin: 8vw 0;

    .doctor-team-content-text {
      margin: 4vw 0;
      box-sizing: border-box;
      padding: 0 6.4vw;
      color: var(--Grey-Mid, #666);
      text-align: justify;
      font-family: "Noto Sans HK";
      font-size: 3.2vw;
      font-style: normal;
      font-weight: 400;
      line-height: 150%;
      letter-spacing: 0.6px;
    }

    .doctor-team-content-btn {
      margin: 4vw auto;
      display: flex;
      justify-content: center;
      align-items: center;
    }
  }

  :deep(.index-dentalServices) {
    padding-top: 0;
    margin: 8vw 0;
  }

  .banner-in-box {
    position: absolute;
    left: 0;
    height: 100vw;
    width: 100%;
    z-index: 22;
    box-sizing: border-box;
    padding-bottom: 9.33vw;
    top: 0;
    bottom: 0;
    transform: translateY(0px);
  }

  .banner-image {
    display: none !important;
  }

  .banner-content {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    width: 23.9583vw;
    position: absolute;
    left: 40%;
    top: 50%;
    transform: translate(-50%, -50%);

    &>div {
      display: flex;
      align-items: flex-end;
      justify-content: center;
    }

    .content-title {
      color: var(--White, #fff);
      text-align: right;
      -webkit-text-stroke-width: 0.5;
      -webkit-text-stroke-color: var(--White, #fff);
      font-family: 'FakePearl-Regular';
      font-size: clamp(40px, 5.7vw, 110px);
      font-style: normal;
      font-weight: 600;
      line-height: 100%;
      /* 176px */
      letter-spacing: 6.6px;
      position: relative;
      z-index: 6;
      bottom: 0;

      border-radius: 0.6942vw 0.6942vw 0px 0px;
      background: var(--Liner-purple,
          linear-gradient(269deg,
            var(--Brand-Color, #fc1682) 10.21%,
            #710d54 122.73%));
      box-sizing: border-box;
      padding: 0.859375vw 0;
      color: var(--White, #fff);
      text-align: center;
      text-shadow: 0px 5.333px 5.333px rgba(0, 0, 0, 0.25);
      font-family: 'Noto Sans HK';
      font-size: 1.565vw;
      font-style: normal;
      font-weight: 700;
      letter-spacing: 0.165vw;
      width: 100%;
    }

    .price-style {
      width: 19.0625vw;
      height: 11.145vw;
      position: relative;
      right: -3.64583vw;

      &>img {
        width: 100%;
        height: 100%;
        object-fit: contain;
      }
    }

    .content-price {
      width: 100%;
      background: #fff;
      box-sizing: border-box;
      padding: 1.0465vw;
      display: flex;
      gap: 0 0.52vw;
      min-height: 4.78135vw;
      box-sizing: border-box;
      padding: 0.52vw;
      align-items: center;
      font-family: 'Noto Sans HK';
      font-size: 1.7442vw;
      font-style: normal;
      font-weight: 900;
      line-height: 2.2222vw;
      /* 114.286% */
      letter-spacing: 0.29165vw;
      justify-content: center;
      border-radius: 0px 0px 10px 10px;
      background: var(--White, #fff);
      box-shadow: 0px 4px 4px rgba(77, 77, 77, 0.2);

      &>div:nth-child(1) {
        position: relative;
        color: var(--Grey-Dark, #333);
        text-align: right;
        text-shadow: 1.3px 1.333px 1.333px #faeaf2,
          1.33px -1.333px 1.333px #faeaf2, -1.33px 1.333px 1.333px #faeaf2,
          -1.33px -1.333px 1.333px #faeaf2;
        font-family: 'Noto Sans HK';
        font-size: 1.744vw;
        font-style: normal;
        font-weight: 900;
        line-height: 2.2222vw;
        /* 114.286% */
        letter-spacing: 0.29165vw;
        top: auto;
      }
    }
  }

  .banner-content {
    position: relative;
    align-items: flex-start;
    justify-content: flex-end;
    width: 86.665vw;
    left: 50%;
    top: auto;
    bottom: -75%;
    border-radius: 10px;
    transform: translate(-50%, 0%);

    .content-title {
      display: flex;
      justify-content: center;
      color: var(--White, #fff);
      text-align: center;
      font-size: 40px;
      font-style: normal;
      font-weight: 600;
      line-height: 100%;
      /* 72px */
      letter-spacing: 2.7px;
      position: relative;
      z-index: 6;
      bottom: 0;
      width: 100%;
      border-radius: 10px 10px 0px 0px;
      background: var(--Liner-purple,
          linear-gradient(269deg,
            var(--Brand-Color, #fc1682) 10.21%,
            #710d54 122.73%));
      padding: 16.5px 0;
      color: var(--White, #fff);
      text-align: center;
      text-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
      font-family: 'Noto Sans HK';
      font-size: 20px;
      font-style: normal;
      font-weight: 700;
      line-height: 20px;
      /* 83.333% */
      letter-spacing: 2px;
    }

    .content-price {
      min-height: 13.665vw;
      gap: 0 8px;
      padding: 2.65vw;
      border-radius: 0px 0px 10px 10px;
      background: var(--White, #fff);
      box-shadow: 0px 4px 4px rgba(77, 77, 77, 0.2);

      &>div:nth-child(1) {
        color: var(--Grey-Dark, #333);
        text-align: right;
        text-shadow: 1.3px 1.333px 1.333px #faeaf2,
          1.33px -1.333px 1.333px #faeaf2, -1.33px 1.333px 1.333px #faeaf2,
          -1.33px -1.333px 1.333px #faeaf2;
        font-family: 'Noto Sans HK';
        font-size: 5.865vw;
        font-style: normal;
        font-weight: 900;
        line-height: 6.23vw;
        letter-spacing: 0.82vw;
        position: relative;
      }
    }
  }
}
</style>