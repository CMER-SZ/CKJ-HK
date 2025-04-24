<script lang="ts" setup>
import { Swiper, SwiperSlide } from 'swiper/vue'
import { Autoplay, Navigation, Pagination } from 'swiper'
import gsap from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'
import { useAppState } from '~/stores/appState'
import doctorLists_cs from '~/assets/js/doctor'
import { toWhatsApp } from '~/assets/js/common'
import { useElementBounding, useWindowSize } from '@vueuse/core'
import { use } from 'chai'
const appState = useAppState()
const { t } = useLang()
useHead({
  title: 'CKJ愛康健齒科連鎖 | 香港官方網站 | 長者醫療券大灣區試點',
  titleTemplate: '',
  meta: [
    {
      hid: 'description',
      name: 'description',
      content:
        '愛康健集團是大灣區牙科連鎖機構，其口腔醫院為香港政府指定長者醫療券大灣區試點。（香港熱線: 6933 8128）14間門診有超過20種牙科治療項目，專注為港服務超過30年，可線上預約。',
    },
    {
      hid: 'Keywords',
      name: 'Keywords',
      content:
        '愛康健 爱康健 CKJ aikangjian 牙科服務 內地牙科 深圳愛康健口腔醫院 愛康健齒科集團 基楚牙科 美容牙科 深圳牙科 醫療券 長者醫療券大灣區試點 深圳睇牙 深圳整牙 種植牙 假牙 洗牙 補牙 拔牙 智慧齒 杜牙根 根管治療 兒童牙科 牙齒美白 牙齒檢查 矯齒 箍牙 牙醫 牙医 深圳 羅湖 朱咪咪 掛號收費 牙科價目表 線上預約 愛康健齒科,深圳爱康健口腔医院,深圳市口腔医院,深圳牙齿矫正多少钱,愛康健口腔醫院,希玛爱康健,深圳口腔医院,深圳牙科医院,深圳种植牙,深圳植牙價錢,愛康健,香港長者醫療券,愛康健牙科,愛康健牙科中心,愛康健牙科診所',
    },
  ],
})




let showTreatment = ref(false)
const scrollWatch = () => {
  let _dome: any = document.getElementsByClassName('treatment-data')
  let _offsetTop = 0
  if (_dome && _dome.length) {
    _offsetTop = _dome[0].offsetTop
  }
  if (
    _offsetTop >= window.pageYOffset &&
    _offsetTop + 200 <= window.pageYOffset + window.innerHeight
  ) {
    showTreatment.value = true
  }
}
onMounted(() => {
  scrollWatch()
  window.addEventListener('scroll', scrollWatch)
})



const headerConfigData = {
  img: 'https://static.cmereye.com/imgs/2024/02/5605cbd7689de37c.jpg',
  bg: '',
  mbImg: 'https://static.cmereye.com/imgs/2024/02/216458f63817b47e.jpg',
  pageName: 'course-new',
  pcText: ['重拾自信笑容', '愛牙愛己，由你做起'],
  mbText: ['重拾自信笑容', '愛牙愛己，由你做起'],
}

let dentalProfessionCur = ref('0')


let doctorCur = ref('')

let actDoctorListd: any = ref([])


let loading = ref(false)
const checkId = ref('101')
const handletab2 = async (id: string, dpc: Boolean = false) => {
  checkId.value = id
  if (!dpc && dentalProfessionCur.value === id) return
  actDoctorListd.value = []
  loading.value = true
  setTimeout(() => {
    dentalProfessionCur.value = id
    doctorCur.value =
      actDoctorListd.value.length > 0 ? actDoctorListd.value[0].id : ''
    nextTick(() => {
      doctorItemSwiper.slideToLoop('0')
    })
    loading.value = false
  }, 500)
}

let doctorItemSwiper: any = {
  slideToLoop: (a) => { },
}


let orgTabCur = ref(0)
const orgTabLists = ['監管單位', '戰略合作', '媒體合作', '服務客戶']
const orgLists = [
  [
    'https://static.cmereye.com/static/ckjnewsite/org/org-2001.png',
    'https://static.cmereye.com/static/ckjnewsite/org/org-2002.png',
    'https://static.cmereye.com/static/ckjnewsite/org/org-2003.png',
    'https://static.cmereye.com/static/ckjnewsite/org/org-2004.png',
    'https://static.cmereye.com/static/ckjnewsite/org/org-2005.png',
    'https://static.cmereye.com/static/ckjnewsite/org/org-2006.png',
    'https://static.cmereye.com/static/ckjnewsite/org/org-2007.png',
  ],
  [
    'https://static.cmereye.com/static/ckjnewsite/org/org-1001.png',
    'https://static.cmereye.com/static/ckjnewsite/org/org-1002.png',
    'https://static.cmereye.com/static/ckjnewsite/org/org-1003.png',
    'https://static.cmereye.com/static/ckjnewsite/org/org-1004.png',
    'https://static.cmereye.com/static/ckjnewsite/org/org-1005.png',
    'https://static.cmereye.com/static/ckjnewsite/org/org-1006.png',
    'https://static.cmereye.com/static/ckjnewsite/org/org-1007.png',
    'https://static.cmereye.com/static/ckjnewsite/org/org-1008.png',
    'https://statichk.cmermedical.com/ckj/image/org-1009.png',
  ],
  [
    'https://static.cmereye.com/imgs/2024/05/10fa105dea15be81.png',
    'https://static.cmereye.com/imgs/2024/04/0a0cc588677cf1ab.png',
    'https://static.cmereye.com/imgs/2024/04/746c9bc800d9bd68.png',
    'https://static.cmereye.com/imgs/2024/04/9dd67f204905f590.png',
    'https://static.cmereye.com/imgs/2024/04/438936f0a5412fd7.png',
    'https://static.ckjhk.com/ckj-image/2025042415011202.png',
    'https://static.ckjhk.com/ckj-image/2025042415011201.png',
    'https://static.cmereye.com/static/ckjnewsite/org/org-3002.png',
    'https://static.cmereye.com/static/ckjnewsite/org/org-3003.png',
    'https://static.cmereye.com/static/ckjnewsite/org/org-3004.png',
    'https://static.cmereye.com/static/ckjnewsite/org/org-3005.png',
    'https://static.cmereye.com/static/ckjnewsite/org/org-3006.png',
    'https://static.cmereye.com/static/ckjnewsite/org/org-3007.png',
    'https://static.cmereye.com/static/ckjnewsite/org/org-3008.png',
    'https://static.cmereye.com/static/ckjnewsite/org/org-3009.png',
    'https://static.cmereye.com/static/ckjnewsite/org/org-3010.png',
    'https://static.cmereye.com/static/ckjnewsite/org/org-3011.png',
    'https://static.cmereye.com/static/ckjnewsite/org/org-3012.png',
    'https://static.cmereye.com/static/ckjnewsite/org/org-3013.png',
  ],
  [
    'https://static.cmereye.com/static/ckjnewsite/org/org-4001.png',
    'https://static.cmereye.com/static/ckjnewsite/org/org-4002.png',
    'https://static.cmereye.com/static/ckjnewsite/org/org-4003.png',
    'https://static.cmereye.com/static/ckjnewsite/org/org-4004.png',
    'https://static.cmereye.com/static/ckjnewsite/org/org-4005.png',
    'https://static.cmereye.com/static/ckjnewsite/org/org-4006.png',
    'https://static.cmereye.com/static/ckjnewsite/org/org-4007.png',
    'https://static.cmereye.com/static/ckjnewsite/org/org-4008.png',
    'https://static.cmereye.com/static/ckjnewsite/org/org-4009.png',
    'https://static.cmereye.com/static/ckjnewsite/org/org-4010.png',
    'https://static.cmereye.com/static/ckjnewsite/org/org-4011.png',
    'https://static.cmereye.com/static/ckjnewsite/org/org-4012.png',
    'https://static.cmereye.com/static/ckjnewsite/org/org-4013.png',
    'https://static.cmereye.com/imgs/2024/08/649a4dcca06fa45a.png',
    'https://static.cmereye.com/imgs/2024/08/fb3b34ba5e3335e3.png',
    'https://static.ckjhk.com/ckj-image/2025041716205903.png',
    'https://static.ckjhk.com/ckj-image/2025041716205902.png',
    'https://static.ckjhk.com/ckj-image/2025041716205901.png',
    'https://static.ckjhk.com/ckj-image/2025041716114701.jpg'
  ],
]
const handleorgtabfun = (orgTabIndex) => {
  orgTabCur.value = orgTabIndex
  indexOrgSwiperRef.slideToLoop(orgTabIndex)
}
let indexOrgSwiperRef = {
  slideToLoop: (a) => { },
}
const setIndexOrgSwiperRef = (swiper: any) => {
  indexOrgSwiperRef = swiper
}
const onIndexOrgSlideChange = (swiper) => {
  orgTabCur.value = swiper.realIndex ? Number(swiper.realIndex) : 0
}

const problemData = {
  title: '<span>常見</span><span>問題</span>',
  lists: [
    {
      Q: '深圳哪裡有分店？',
      A: '我們在羅湖、福田、南山及蓮塘均有分店。',
    },
    {
      Q: '請問有什麼支付方式？',
      A: '我們接受人民幣、VISA、Master、銀聯、微信、內地支付寶及香港支付寶。',
    },
    {
      Q: '請問可以使用醫療券嗎？',
      A: '預計2024年第三季度（約9月份）將陸續展開相關安排，讓合資格的香港長者可使用醫療券支付費用。',
    },
    {
      Q: '一般洗牙需要多長時間？',
      A: '一次基本的洗牙程序通常需要30至60分鐘完成。具體時間會根據您的口腔情況和需要的清潔程度而有所不同。我們建議您預留1小時的時間。',
    },
    {
      Q: '植牙需要多少時間才能完成？',
      A: '植牙是一個多步驟的過程，通常需要2至3次就診才能完成。從植入牙根到完成冠修復，整個過程約需3至6個月。我們會為您詳細解釋每個步驟，檢查後再設計方案。',
    },
    // {
    //   Q: '牙周治療大約需要多長時間？',
    //   A: '這要視乎牙周的程度。一般來說，牙周基本治療大約需要2至3次就診，每次就診時間約1至2小時。具體時間需由牙醫根據您的情況評估。',
    // },
    {
      Q: '我可以同時進行牙齒美白和洗牙嗎？',
      A: '我們建議您先來諮詢牙醫，根據您的具體情況制定最佳的治療方案。',
    },
    {
      Q: '箍牙可以分期付款嗎？',
      A: '箍牙一般可以分期付款。面診時可以詳細了解我們的分期付款政策和細節，選擇最適合自己的方案。',
    },
    {
      Q: '為什麼你們的價錢比其他診所貴？',
      A: '我們建議您考慮牙科服務的整體價值。雖然價格是一個重要的考慮因素，但請記住，牙科治療的品質和效果對您的口腔健康和生活品質有著長遠的影響。',
    },
    // {
    //   Q: '預約需要提前多少天？',
    //   A: '平日最好提前3天預約，週末建議提前1至2星期預約。',
    // },
    {
      Q: '不預約可以直接到診所嗎？',
      A: '我們診所需要提前預約，這樣能提高就診效率，避免客人等待時間過長。',
    },
    // {
    //   Q: '請問診所有提供Wi-Fi嗎？',
    //   A: '有的，我們提供Wi-Fi服務。',
    // },
  ],
}

let windowWidth = ref(390)

const getWindowWidth = () => {
  windowWidth.value = window.innerWidth
}
let currtNew = ref(1)
const handleLineCur = (_value: number) => {
  newsSwiperRef.slideToLoop(_value - 1)
}

let newsSwiperRef = {
  slideToLoop: (a) => { },
}
const setNewsSwiperRef = (swiper: any) => {
  newsSwiperRef = swiper
}
const onSlideChange = (swiper: any) => {
  currtNew.value = (swiper.realIndex ? Number(swiper.realIndex) : 0) + 1
}

let messageCurrtNew = ref(1)
const handleMessageLineCur = (_value: number) => {
  newsMessageSwiperRef.slideToLoop(_value - 1)
}

let newsMessageSwiperRef = {
  slideToLoop: (a) => { },
}
const setMessageNewsSwiperRef = (swiper: any) => {
  newsMessageSwiperRef = swiper
}
const onMessageNewSlideChange = (swiper: any) => {
  messageCurrtNew.value = (swiper.realIndex ? Number(swiper.realIndex) : 0) + 1
}

onMounted(() => {
  getWindowWidth()
  window.addEventListener('resize', getWindowWidth)
})

// 临时隐藏  contentDom
const contentDom = ref(false)

const hideDom = ref(false)


const ddsasd = ref([
  "https://static.cmereye.com/static/ckj/imgs/environment/de/1001001.jpg",
  "https://static.cmereye.com/static/ckj/imgs/environment/de/1001002.jpg",
  "https://static.cmereye.com/static/ckj/imgs/environment/de/1001003.jpg",
  "https://static.cmereye.com/static/ckj/imgs/environment/de/1001004.jpg",
  "https://static.cmereye.com/static/ckj/imgs/environment/de/1001005.jpg",
  "https://static.cmereye.com/static/ckj/imgs/environment/de/1001006.jpg",
  "https://static.cmereye.com/static/ckj/imgs/environment/de/1001007.jpg",
  "https://static.cmereye.com/static/ckj/imgs/environment/de/1001008.jpg",
  "https://static.cmereye.com/static/ckj/imgs/environment/de/1001009.jpg",
  "https://static.cmereye.com/static/ckj/imgs/environment/de/1001010.jpg",
  "https://static.cmereye.com/static/ckj/imgs/environment/de/1001011.jpg",
  "https://static.cmereye.com/static/ckj/imgs/environment/de/1001012.jpg",
  "https://static.cmereye.com/static/ckj/imgs/environment/de/1001013.jpg"
])


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
  if (swiperRef.activeIndex >= ddsasd.value.length - 1) {
    swiperRef.slideTo(0)
  }
  swiperRef.slideNext()
  handleProcessBtnClick()
}
const subNum = () => {
  if (swiperRef.activeIndex <= 0) {
    swiperRef.slideTo(ddsasd.value.length - 1)
  }
  swiperRef.slidePrev()
  handleProcessBtnClick()
}


const handleLineCurStrength = (_value: number) => {
  swiperRef.slideTo(_value - 1)
  handleProcessBtnClick()
}

const handleProcessBtnClick = () => {
  services_include_cur.value = swiperRef.activeIndex
  const swiperPoints = document.querySelectorAll('.swiper-pagination-bullet')
  swiperPoints.forEach((item: any, index: number) => {
    if (index == services_include_cur.value) {
      item.classList.add('swiper-pagination-bullet-active')
    } else {
      item.classList.remove('swiper-pagination-bullet-active')
    }
  })
}
</script>

<template>
  <div>
    <HomeHeaderV2 :headerConfig="headerConfigData" />
    <div class="indexPage">

      <div class="service-item-pc">
        <div class="d-flex flex-row align-items-end subheading">
          <span>牙科</span><span>服務</span>
        </div>
        <div>
          <div class="service_item">
            <a href="#">
              <div><img src="https://static.ckjhk.com/ckj-image/1381e9540ac1.png" alt=""></div>
              <div><span>種植牙</span></div>
            </a>
          </div>
          <div class="service_item">
            <a href="#">
              <div><img src="https://static.ckjhk.com/ckj-image/b2eef97c5cb8.png" alt=""></div>
              <div><span>活動假牙</span><span>及牙橋</span></div>
            </a>
          </div>
          <div class="service_item">
            <a href="#">
              <div><img src="https://static.ckjhk.com/ckj-image/df725f68ae52.png" alt=""></div>
              <div><span>洗牙</span></div>
            </a>
          </div>
          <div class="service_item">
            <a href="#">
              <div><img src="https://static.ckjhk.com/ckj-image/3226530ad1ac.png" alt=""></div>
              <div><span>補牙</span></div>
            </a>
          </div>
          <div class="service_item">
            <a href="#">
              <div><img src="https://static.ckjhk.com/ckj-image/12306b9549f2.png" alt=""></div>
              <div><span>杜牙根</span><span class="service_item_sub">(根管治療)</span></div>
            </a>
          </div>
          <div class="service_item">
            <a href="#">
              <div><img src="https://static.ckjhk.com/ckj-image/23c019aefe2b.png" alt=""></div>
              <div><span>牙冠</span></div>
            </a>
          </div>
          <div class="service_item">
            <a href="#">
              <div><img src="https://static.ckjhk.com/ckj-image/0f03be1d7f26.png" alt=""></div>
              <div><span>拔牙及</span><span>智慧齒拔除</span></div>
            </a>
          </div>
          <div class="service_item">
            <a href="#">
              <div><img src="https://static.ckjhk.com/ckj-image/38875c2bba26.png" alt=""></div>
              <div><span>牙周治療</span></div>
            </a>
          </div>
          <div class="service_item">
            <a href="#">
              <div><img src="https://static.ckjhk.com/ckj-image/2025031009582001.png" alt=""></div>
              <div><span>牙齒美白</span></div>
            </a>
          </div>
          <div class="service_item">
            <a href="#">
              <div><img src="https://static.ckjhk.com/ckj-image/a30e76a0828c.png" alt=""></div>
              <div><span>瓷牙貼片</span></div>
            </a>
          </div>
          <div class="service_item">
            <a href="#">
              <div><img src="https://static.ckjhk.com/ckj-image/62682fc283e1.png" alt=""></div>
              <div><span>箍牙</span><span class="service_item_sub">(牙齒矯正)</span></div>
            </a>
          </div>
          <div class="service_item">
            <a href="#">
              <div><img src="https://static.ckjhk.com/ckj-image/9dfa76a2e948.png" alt=""></div>
              <div><span>隱形牙套</span></div>
            </a>
          </div>
          <div class="service_item">
            <a href="#">
              <div><img src="https://static.ckjhk.com/ckj-image/f2015ea8d422.png" alt=""></div>
              <div><span>兒童牙科</span></div>
            </a>
          </div>
          <div class="service_item">
            <a href="#">
              <div><img src="https://static.ckjhk.com/ckj-image/1622aad56701.png" alt=""></div>
              <div><span>口腔檢查</span></div>
            </a>
          </div>
          <div class="service_item">
            <a href="#">
              <div><img src="https://static.ckjhk.com/ckj-image/0d1c24437adc.png" alt=""></div>
              <div><span>長者牙科</span></div>
            </a>
          </div>
        </div>
      </div>

      <section class="ckj-container doctor-team">
        <div class="d-flex flex-row align-items-end subheading">
          <span>7大</span><span>專科醫生團隊</span>
        </div>
        <div class="doctor-team-content-text">全方位涵蓋口腔專科醫療服務，並由經驗豐富的專家醫生團隊執行，70%醫生執業超過10年。
        </div>
        <div class="doctor-team-content">
          <DoctorV2 :nowType="'101'" />
        </div>
        <div class="doctor-team-content-btn">
          <PageAnimBtnTypeTwo :str="'獲取免費諮詢'" />
        </div>
      </section>

      <!-- 实力 -->
      <section class="container strength">
        <div class="subheading">
          <span>30年</span>
          <span>實力牙科</span>
        </div>
        <div class="d-none d-lg-flex strength-intro">
          <p>愛康健集團由香港主板上市醫療集團管理，30年大灣區專業牙科連鎖機構，</p>
          <p>醫療品質受香港政府認可。</p>
          <p>12間深圳口岸店提供超過20種牙科治療項目，一站式服務港人超過100萬人次！</p>
        </div>
        <div class="strength-content">
          <Swiper class="mySwiper" @swiper="setSwiperRef" :modules="[Autoplay, Navigation, Pagination]"
            :slides-per-view="1" :loop="true" :speed="800" :autoplay="{
              delay: 6000,
              disableOnInteraction: false
            }">
            <SwiperSlide v-for="(img, index) in ddsasd" :key="index">
              <img class="d-block mx-auto wp-image-589" decoding="async" loading="lazy" :src="img"
                :srcset="`${img} 400w, ${img} 640w, ${img}`" sizes="(max-width: 992px) 100vw, 1216px"
                alt="Carousel image" />
            </SwiperSlide>
          </Swiper>
          <div class="position-absolute swiper-Title z-2">
            <div class="swiper-Title-Box d-flex align-items-end justify-content-end align-items-lg-center ">
              <div>
                <div class="swiper-button-prev" @click="subNum">
                  <svg width=" 13" height="18" viewBox="0 0 13 18" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path d="M10 15L2.5 8.99931L10 3" stroke="#D2337D" stroke-width="4" stroke-miterlimit="10"
                      stroke-linecap="square" stroke-linejoin="round" />
                  </svg>
                </div>
                <div class="swiper-pagination">
                  <div v-for="(item, index) in ddsasd" :key="index" @click="handleLineCurStrength(index + 1)"
                    :class="index == 0 ? 'swiper-pagination-bullet-active' : ''" class="swiper-pagination-bullet"></div>
                </div>

                <div class="swiper-button-next" @click="addNum">
                  <svg width="13" height="18" viewBox="0 0 13 18" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path d="M3 15L10.5 8.99931L3 3" stroke="#D2337D" stroke-width="4" stroke-miterlimit="10"
                      stroke-linecap="square" stroke-linejoin="round" />
                  </svg>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="strength-list">
          <div class="listText">
            <div><span>香港管理</span><span>30年專科</span></div>
            <div>
              愛康健是香港知名深圳牙科品牌，30年專科經驗，實力與信譽兼備。
            </div>
          </div>
          <div class="listText">
            <div><span>13間口岸店</span><span>一站式牙科</span></div>
            <div>
              集團有1家醫院、6間門診及6間診所，門店覆蓋羅湖、福田、深圳灣、蓮塘口岸。
            </div>
          </div>
          <div class="listText">
            <div><span>100萬+港人</span><span>信心之選</span></div>
            <div>
              提供一站式高品質牙科服務，設備符合國際標準，價格合理透明。
            </div>
          </div>
          <div class="listText">
            <div><span>港府認可</span><span>可用醫療券</span></div>
            <div>
              2024年獲香港政府認可，成為大灣區長者醫療券計劃唯一口腔專科醫院。
            </div>
          </div>
        </div>
      </section>

      <div class="index-org">
        <div class="subheading">
          <span>相關</span>
          <span>機構</span>
        </div>
        <div class="index-org-tag smallPageCon">
          <div class="index-org-tag-in" :class="{ active: orgTabCur === orgTabIndex }"
            v-for="(orgTabItem, orgTabIndex) in orgTabLists" :key="orgTabIndex" @click="handleorgtabfun(orgTabIndex)">
            {{ orgTabItem }}
          </div>
        </div>
        <div class="index-org-content smallPageCon">
          <Swiper class="index-org-content-swiper" :loop="true" :modules="[Autoplay]" :autoplay="{
            delay: 3000,
          }" @swiper="setIndexOrgSwiperRef" @slideChange="onIndexOrgSlideChange">
            <Swiper-slide class="index-org-content-swiper-slie" v-for="(orgListItem, orgListIndex) in orgLists"
              :key="orgListIndex">
              <div class="index-org-content-in" :class="`index-org-content-${orgTabCur}`"
                v-for="(orgItem, orgIndex) in orgListItem" :key="orgIndex">
                <img loading="lazy" :src="orgItem" alt="" />
              </div>
            </Swiper-slide>
          </Swiper>
        </div>
      </div>
      <!-- kol -->
      <section class="container kol-video">
        <div class="subheading">
          <span>咪咪姐</span>
          <span>23年用後感</span>
        </div>
        <div class="video-list">
          <iframe src="https://www.youtube.com/embed/Q7sHcjs6oCs?si=JmhIgriXU-qvuOkg" width="100%" height="100%"
            frameborder="0"></iframe>
        </div>
        <a class="d-none d-lg-flex video-user-id" target="_blank"
          href="https://www.youtube.com/channel/UC4AQD5eeOiHIGd3QYFGK4aA">
          <div>
            <svg xmlns="http://www.w3.org/2000/svg" width="44" height="36" viewBox="0 0 44 36" fill="none">
              <path fill-rule="evenodd" clip-rule="evenodd"
                d="M41.6583 3.27625C42.341 4.06058 42.8312 5.03586 43.08 6.10446C44 10.0486 44 18.2737 44 18.2737C44 18.2737 44 26.4987 43.08 30.4429C42.8312 31.5115 42.341 32.4868 41.6583 33.2711C40.9756 34.0555 40.1245 34.6213 39.19 34.9122C35.75 35.9681 22 35.9681 22 35.9681C22 35.9681 8.25 35.9681 4.81 34.9122C3.87554 34.6213 3.02438 34.0555 2.34169 33.2711C1.65901 32.4868 1.16876 31.5115 0.92 30.4429C0 26.4987 0 18.2737 0 18.2737C0 18.2737 0 10.0486 0.92 6.10446C1.16876 5.03586 1.65901 4.06058 2.34169 3.27625C3.02438 2.4919 3.87554 1.92599 4.81 1.63518C8.25 0.579224 22 0.579224 22 0.579224C22 0.579224 35.75 0.579224 39.19 1.63518C40.1245 1.92599 40.9756 2.4919 41.6583 3.27625ZM17.5039 10.8058V25.7433L29.0039 18.2746L17.5039 10.8058Z"
                fill="#D2337D" />
            </svg>
          </div>
          <div>@ckjhkofficial</div>
        </a>
      </section>
      <section class="ckj-container root-canal-problem">
        <div>
          <V2ServiceProblem :problem-data="problemData" :v2-versions="true" />
        </div>
      </section>
      <!-- 聯絡我們 -->
      <BranchAddress />
      <AppointmentFormV2 />
    </div>
    <FooterV2 />
    <AsideV2 />
  </div>
</template>

<style lang="scss" scoped>
@keyframes numAnim {
  100% {
    // transform: translateY(calc((100% - 96px) * -1));
    transform: none;
  }
}

svg:hover path {
  cursor: pointer;
  fill: rgba(255, 120, 117, 0.65);
}

.indexPage {
  width: 100%;
  background: #fff;
  position: relative;
  z-index: 1;
}

.treatment-data {
  margin-top: 80px;

  &-title {
    span {
      color: var(--indexColor1);
      text-align: center;
      font-size: 35px;
      font-style: normal;
      font-weight: 700;
      line-height: 160%;
      display: block;
    }
  }

  &-in {
    margin-top: 48px;
    display: flex;
    flex-wrap: wrap;

    .dataBox {
      flex: 1;

      .num {
        color: var(--indexColor1);
        text-align: center;
        font-size: 60px;
        font-style: normal;
        font-weight: 500;
        line-height: 160%;
        display: flex;
        justify-content: center;
        position: relative;

        img {
          position: absolute;
        }

        .numBold {
          font-family: initial;
          font-weight: bold;
          margin-top: 5px;
        }

        .numIn {
          height: 96px;
          overflow: hidden;
          position: relative;

          span {
            line-height: 96px;
            display: block;
          }

          .numInAnim {
            opacity: 0;
            transition: all 0.3s;
            display: flex;
            flex-direction: column-reverse;
            transform: translateY(-100%);

            &.showNumInAnim {
              opacity: 1;
              animation: numAnim 1s ease-in-out forwards;
            }
          }
        }
      }

      .name {
        color: var(--textColor);
        text-align: center;
        font-size: 28px;
        font-style: normal;
        font-weight: 700;
        line-height: 160%;
        margin-top: -10px;
      }
    }
  }

  &-bText {
    color: var(--textColor);
    text-align: center;
    font-size: 20px;
    font-style: normal;
    font-weight: 500;
    line-height: 160%;
    margin-top: 30px;
  }
}

//醫生團隊
.index-doctorTeam {
  margin: 60px auto 50px;

  &-t {
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
  }

  &-con {
    width: 70%;
    max-width: 1280px;
    margin: 25px auto 0;
  }

  &-tab1 {
    :deep(.areaTab) {
      div {
        flex: 1;
        text-align: center;
        font-size: 20px;
      }
    }
  }

  &-tab2 {
    margin-top: 30px;

    &-in {
      width: 100%;
      display: flex;

      &>div {
        flex: 1;
        color: #00aeff;
        transition: all 0.3s;
        border-top: 2px solid #00aeff;
        border-bottom: 2px solid #00aeff;
        border-left: 2px solid #00aeff;
        padding: 5px 0;
        font-size: 18px;
        text-align: center;
        letter-spacing: 3px;
        cursor: pointer;

        &:nth-of-type(4) {
          flex: 1.3;
        }

        &:nth-of-type(5) {
          flex: 1.3;
        }

        &:nth-of-type(6) {
          flex: 1.3;
        }

        &:nth-of-type(7) {
          flex: 1.7;
        }

        &:first-child {
          border-radius: 5px 0 0 5px;
        }

        &:last-child {
          border-radius: 0 5px 5px 0;
          border-right: 2px solid #00aeff;
        }

        &:hover,
        &.index-doctorTeam-tab2-in-active {
          color: #fff;
          background: #00aeff;
        }
      }
    }
  }

  &-lists {
    width: 100%;
    min-height: 152px;

    .pcLists {
      width: 100%;
      display: flex;
      justify-content: center;
      flex-wrap: wrap;

      &-in {
        cursor: pointer;
        margin-bottom: 30px;

        &:not(:last-child) {
          margin-right: 30px;
        }

        &-img {
          width: 150px;
          height: 150px;
          border-radius: 10px;
          overflow: hidden;
          background: rgba(254, 169, 209, 0.5);
          transition: all 0.3s;
        }

        &:hover,
        &.acitve {
          .pcLists-in-img {
            background: #ffa8c6;
          }
        }
      }

      &>section {
        max-width: 100%;
        width: 100%;
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
      }

      .swiperpcLists-in {
        width: 100%;
        overflow: visible;

        &-img {
          margin: 0 15px;
          height: auto;
          border-radius: 10px;
          overflow: hidden;
          background: rgba(254, 169, 209, 0.7);
          transition: all 0.3s;
          cursor: pointer;

          &:hover,
          &.acitve {
            background: #ffa8c6;
          }
        }
      }
    }

    .mbLists {
      width: calc(100% - 40px);
      margin: 0 auto;
      display: none;

      &-in {
        width: 100%;
        overflow: visible;

        &-img {
          // width: calc(100% - 20px);
          margin: 0 10px;
          height: auto;
          border-radius: 10px;
          overflow: hidden;
          background: rgba(254, 169, 209, 0.7);

          &.acitve {
            background: #ffa8c6;
          }
        }
      }
    }
  }

  &-detail {
    padding: 20px;
    display: flex;
    margin-top: 50px;

    &-l {
      width: calc(434 / 1365 * 100%);
      max-width: 434px;
      position: relative;
      height: max-content;

      &-in {
        width: 100%;

        &::after {
          content: '';
          position: absolute;
          top: -20px;
          left: -20px;
          width: 100%;
          height: 100%;
          border-radius: 30px;
          background: rgba(254, 169, 209, 0.7);
          z-index: 0;
        }
      }

      img {
        position: relative;
        border-radius: 30px;
        z-index: 1;

        &:nth-of-type(1) {
          border: 3px solid var(--indexColor1);
        }

        &:nth-of-type(2) {
          position: absolute;
          bottom: 3px;
          left: 50%;
          transform: translateX(-50%);
          max-height: calc(92% - 3px);
          display: block;
        }
      }

      &-btn {
        position: absolute;
        bottom: 0;
        left: 50%;
        transform: translate(-50%, 50%);
        z-index: 1;
        width: max-content;
      }
    }

    &-r {
      flex: 1;

      .detail-1 {
        color: var(--indexColor1);
        padding-left: 20px;

        span {
          font-size: 20px;

          &:nth-of-type(1) {
            font-size: 35px;
            margin-right: 5px;
          }
        }
      }

      .detail-2 {
        color: #fff;

        span {
          font-size: 28px;
          padding: 5px 70px 5px 20px;
          display: inline-block;
          background: var(--indexColor1);
          clip-path: polygon(0 0, 93% 0, 100% 100%, 0 100%);
        }
      }

      .detail-3 {
        color: var(--textColor);
        padding-left: 20px;
        font-size: 20px;
        margin-bottom: 30px;
        margin-top: 5px;

        span {
          display: block;
        }
      }

      .detail-4 {
        color: var(--textColor);
        padding-left: 20px;
        font-size: 20px;
        margin-bottom: 20px;

        span {
          display: block;
          display: -webkit-box;
          -webkit-line-clamp: 3;
          line-clamp: 3;
          -webkit-box-orient: vertical;
          overflow: hidden;
          text-overflow: ellipsis;
        }
      }

      .detail-5 {
        color: var(--textColor);
        padding-left: 20px;
        font-size: 20px;

        span {
          border-bottom: 1px solid var(--textColor);

          &:not(:last-child) {
            margin-right: 10px;
          }
        }
      }

      .detail-6 {
        margin-top: 30px;
        margin-left: 20px;
        margin-bottom: 20px;
        display: none;
      }
    }
  }

  &-detailBox {
    min-height: 550px;
  }

  .index-doctorTeam-detail-swiper {
    // overflow: visible;
    padding-bottom: 40px;
  }

  .group_photo {
    max-width: 860px;
    margin: 62px auto 50px;
  }

  .team_doctor_everybody {}
}

//個案分享
.index-caseSharing {
  padding: 35px 0;
  background: linear-gradient(180deg,
      rgba(255, 241, 240, 0) 0%,
      var(--indexColor2) 100%);
  margin-top: 80px;

  &-title {
    display: flex;
    justify-content: center;
  }

  &-in {
    width: 80%;
    max-width: 1046px;
    margin: 45px auto;

    .in-top {
      display: flex;
      height: 587px;
    }

    .in-cen {
      display: flex;
      justify-content: space-between;
      flex-wrap: wrap;
      margin-top: 120px;

      &-box {
        width: calc(50% - 8px);
      }
    }
  }
}



.index-videoBox {
  margin-top: 90px;
  margin-bottom: 90px;
  position: relative;

  &-tab {
    display: flex;
    justify-content: center;
    margin-top: 37px;

    .tab-in {
      border: 2px solid #fdd3e3;
      color: var(--Grey-Deep, #4d4d4d);
      text-align: center;
      font-size: 26px;
      font-style: normal;
      font-weight: 500;
      line-height: 160%;
      letter-spacing: 2.6px;
      cursor: pointer;
      padding: 3px 30px 0;
      position: relative;
      transition: all 0.3s;

      &:not(:last-child) {
        border-right: none;
      }

      &:first-child {
        border-radius: 5px 0 0 5px;
      }

      &:last-child {
        border-radius: 0 5px 5px 0;
      }

      &::after {
        content: '';
        position: absolute;
        top: 100%;
        left: 50%;
        transform: translateX(-50%);
        width: 24px;
        height: 12px;
        border-left: 12px solid transparent;
        border-right: 12px solid transparent;
        border-top: 12px solid #fdd3e3;
        opacity: 0;
        transition: all 0.3s;
      }

      &.active {
        color: #fff;
        background: var(--indexColor1);

        &::after {
          opacity: 1;
        }
      }
    }
  }

  &-in {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    justify-content: center;
    max-width: 1187px;
    margin: 50px auto;
    gap: 31px;

    .list-in {
      width: 100%;
      display: flex;
      flex-direction: column;

      .image {
        width: 100%;
        height: 0;
        padding-bottom: calc(383 / 680 * 100%);
        margin-bottom: 10px;
        position: relative;
        overflow: hidden;

        img {
          position: absolute;
          width: 100%;
          height: auto;
          left: 50%;
          top: 50%;
          transform: translate(-50%, -50%);
          transition: all 0.3s;
        }

        &:hover {
          img {
            transform: translate(-50%, -50%) scale(1.1);
          }
        }
      }

      h2 {
        color: var(--Theme-Color, #fc1682);
        font-size: 20px;
        font-style: normal;
        font-weight: 400;
        line-height: 160%;
        display: -webkit-box;
        -webkit-line-clamp: 2;
        line-clamp: 2;
        -webkit-box-orient: vertical;
        overflow: hidden;
        text-overflow: ellipsis;
        padding: 0 20px;
        font-family: 'Noto Sans HK', Serif;
      }

      p {
        color: var(--Grey-Mid, #666);
        text-overflow: ellipsis;
        font-size: 16px;
        font-style: normal;
        font-weight: 400;
        line-height: 200%;
        /* 32px */
        letter-spacing: 1.6px;
        margin-top: 10px;
        padding: 0 20px;
        display: -webkit-box;
        -webkit-line-clamp: 3;
        line-clamp: 3;
        -webkit-box-orient: vertical;
        overflow: hidden;
        text-overflow: ellipsis;
        padding: 0 20px;
        flex: 1;
      }

      .time {
        width: 100%;
        margin-top: 10px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 0 20px;

        &-l {
          color: var(--Grey-Mid, #666);
          font-size: 16px;
          font-style: normal;
          font-weight: 400;
          line-height: 200%;
          /* 32px */
          letter-spacing: 1.6px;
        }

        .shareIcon {
          position: relative;

          &-img {
            width: 30px;
            height: 30px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            border: 2px solid #aaa;
            z-index: 21;

            &>img {
              width: 16px;
              height: auto;
            }

            &.act {
              border: none;
            }
          }

          &-in {
            position: absolute;
            z-index: 20;
            top: 0;
            right: 0;
            width: 159px;
            height: 115px;
            background: url(https://static.cmereye.com/static/ckj/imgs/default/shareIcon.svg);
            background-size: 100% 100%;
            display: flex;
            flex-direction: column;
            justify-content: flex-end;
            filter: drop-shadow(0 2px 3px rgba(0, 0, 0, 0.3));
            padding: 12px 0;

            &-item {
              display: flex;
              align-items: center;
              padding: 5px 10px;
              margin: 0 2px;
              border-radius: 3px;

              &>img {
                width: 20px;
                margin-right: 5px;
              }

              &>span {
                font-size: 14px;
              }

              &:hover {
                background: #f6f6f6;
              }
            }
          }
        }
      }

      .logo {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 10px 20px;

        &-image {
          max-width: 100px;
          max-height: 59px;
        }

        &-text {
          display: flex;
          flex-direction: column;
          color: var(--Grey-Deep, #4d4d4d);
          text-align: right;
          font-size: 16px;
          font-style: normal;
          font-weight: 400;
          line-height: 200%;
          /* 32px */
          letter-spacing: 1.6px;
        }
      }

      .btn {
        display: flex;
        justify-content: center;
        margin-top: 20px;
        margin-bottom: 20px;
      }

      &.list-in-1 {
        .image {
          padding-bottom: 100%;
        }

        h2 {
          -webkit-line-clamp: 1;
          line-clamp: 1;
        }

        p {
          -webkit-line-clamp: 2;
          line-clamp: 2;
        }
      }

      &.list-in-2 {
        .image {
          padding-bottom: calc(562 / 1000 * 100%);
        }

        h2 {
          -webkit-line-clamp: 2;
          line-clamp: 2;
        }

        p {
          -webkit-line-clamp: 5;
          line-clamp: 5;
        }
      }
    }
  }

  &-btn {
    position: absolute;
    inset: 0;
    top: 65px;
    pointer-events: none;

    span {
      float: right;
      display: inline-block;
      color: var(--Theme-Color, #fc1682);
      font-size: 30px;
      font-style: normal;
      font-weight: 400;
      line-height: 160%;
      letter-spacing: 3px;
      position: relative;
      pointer-events: auto;
      cursor: pointer;

      &::before {
        content: '';
        height: 0;
        width: 90%;
        position: absolute;
        border-bottom: 2px solid var(--indexColor1);
        bottom: 0;
        left: 0;
      }

      &::after {
        content: '》';
        font-size: 28px;
      }
    }
  }
}

.Latest_Movies {
  margin-top: 60px;

  &_t {
    display: flex;
    justify-content: space-between;

    a {
      display: flex;
      align-items: center;

      svg {
        width: 44px;
        height: 35px;
        margin-right: 10px;
      }

      span {
        color: #4d4d4d;
        text-align: center;
        font-size: 22px;
        font-style: normal;
        font-weight: 400;
        line-height: 160%;
      }
    }
  }

  &_in {
    margin-top: 38px;
    display: flex;

    &_l {
      margin-right: 33px;
      width: 540px;
      display: flex;
      flex-direction: column;

      span {
        padding: 15px 20px 0;
        color: var(--Grey-Deep, #4d4d4d);
        text-align: justify;
        font-size: 20px;
        font-style: normal;
        font-weight: 400;
        line-height: 160%;
        display: block;
      }

      iframe {
        width: 540px;
        height: 303px;
      }
    }

    &_r {
      &_t {
        display: flex;

        .tab-in {
          border: 2px solid #fdd3e3;
          color: var(--Grey-Deep, #4d4d4d);
          text-align: center;
          font-size: 26px;
          font-style: normal;
          font-weight: 500;
          line-height: 160%;
          letter-spacing: 2.6px;
          cursor: pointer;
          padding: 3px 30px 0;
          position: relative;
          transition: all 0.3s;

          &:not(:last-child) {
            border-right: none;
          }

          &:first-child {
            border-radius: 5px 0 0 5px;
          }

          &:last-child {
            border-radius: 0 5px 5px 0;
          }

          &::after {
            content: '';
            position: absolute;
            top: 100%;
            left: 50%;
            transform: translateX(-50%);
            width: 24px;
            height: 12px;
            border-left: 12px solid transparent;
            border-right: 12px solid transparent;
            border-top: 12px solid #fdd3e3;
            opacity: 0;
            transition: all 0.3s;
          }

          &.active {
            color: #fff;
            background: var(--indexColor1);

            &::after {
              opacity: 1;
            }
          }
        }
      }

      &_b {
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        gap: 34px;
        margin-top: 43px;

        .list-in {
          iframe {
            width: 375px;
            height: 211px;
            max-width: 100%;
          }

          span {
            padding: 15px 20px 0;
            color: var(--Grey-Deep, #4d4d4d);
            text-align: justify;
            font-size: 20px;
            font-style: normal;
            font-weight: 400;
            line-height: 160%;
            display: block;
          }
        }
      }
    }
  }
}

@media (min-width: 768px) and (max-width: 1920px) {
  // .index-org {
  //   margin-top: 6.25vw;

  //   &-tag {
  //     max-width: 41.875vw;
  //     margin-top: 2.6042vw;

  //     &-in {
  //       padding: 0.2604vw;
  //       font-size: 1.25vw;

  //       &:first-child {
  //         border-radius: 0.2604vw 0 0 0.2604vw;
  //       }

  //       &:last-child {
  //         border-radius: 0 0.2604vw 0.2604vw 0;
  //       }
  //     }
  //   }

  //   &-content {
  //     max-width: 62.5vw;
  //     margin-top: 1.5625vw;

  //     &-in {
  //       // width: calc((100% - 15.625vw) / 5);
  //       // margin: 0 1.5625vw 2.0833vw;

  //       width: 9.583vw;
  //       height: 6vw;
  //       margin: 0;
  //     }
  //   }
  // }

  .index-videoBox {
    margin-top: 4.6875vw;
    margin-bottom: 4.6875vw;

    &-tab {
      margin-top: 1.9271vw;

      .tab-in {
        font-size: 1.3542vw;
        letter-spacing: 2.6px;
        padding: 0.1563vw 1.5625vw 0;

        &:first-child {
          border-radius: 0.2604vw 0 0 0.2604vw;
        }

        &:last-child {
          border-radius: 0 0.2604vw 0.2604vw 0;
        }

        &::after {
          width: 1.25vw;
          height: 0.625vw;
          border-left: 0.625vw solid transparent;
          border-right: 0.625vw solid transparent;
          border-top: 0.625vw solid #fdd3e3;
        }
      }
    }

    &-in {
      max-width: 61.8229vw;
      margin: 2.6042vw auto;
      gap: 1.6146vw;

      .list-in {
        .image {
          margin-bottom: 0.5208vw;
        }

        h2 {
          font-size: 1.0417vw;
          padding: 0 1.0417vw;
        }

        p {
          font-size: 0.8333vw;
          margin-top: 0.5208vw;
          padding: 0 1.0417vw;
        }

        .time {
          margin-top: 0.5208vw;
          padding: 0 1.0417vw;

          &-l {
            font-size: 0.8333vw;
          }
        }

        .logo {
          padding: 0.5208vw 1.0417vw;

          &-image {
            max-width: 5.2083vw;
            max-height: 3.0729vw;
          }

          &-text {
            font-size: 0.8333vw;
          }
        }

        .btn {
          margin-top: 1.0417vw;
        }
      }
    }

    &-btn {
      top: 4.1667vw;

      span {
        font-size: 1.5625vw;
        letter-spacing: 0.1563vw;

        &::after {
          font-size: 1.4583vw;
        }
      }
    }
  }

  .index-caseSharing {
    padding: 1.8229vw 0;
    margin-top: 4.1667vw;

    &-in {
      width: 70%;
      max-width: 54.4792vw;
      margin: 2.3438vw auto;

      .in-top {
        display: flex;
        height: 30.2vw;
      }

      .in-cen {
        margin-top: 6.25vw;

        &-box {
          width: calc(50% - 0.4167vw);
        }
      }
    }
  }

  .treatment-data {
    margin-top: 4.1667vw;

    &-title {
      span {
        font-size: 1.8229vw;
      }
    }

    &-in {
      margin-top: 2.5vw;

      .dataBox {
        .num {
          font-size: 3.125vw;

          .numBold {
            margin-top: 0.2604vw;
          }

          .numIn {
            height: 5vw;

            span {
              line-height: 5vw;
            }
          }
        }

        .name {
          font-size: 1.4583vw;
          margin-top: -0.5208vw;
        }
      }
    }

    &-bText {
      font-size: 1.0417vw;
      margin-top: 1.5625vw;
    }
  }

  .index-doctorTeam {
    margin: 3.125vw auto 2.6042vw;

    &-con {
      max-width: 66.6667vw;
      margin: 1.3021vw auto 0;
    }

    &-tab1 {
      :deep(.areaTab) {
        div {
          font-size: 1.0417vw;
        }
      }
    }

    &-tab2 {
      margin-top: 1.5208vw;

      &-in {
        &>div {
          padding: 0.2604vw 0;
          font-size: 0.9375vw;
          letter-spacing: 0.1563vw;

          &:first-child {
            border-radius: 0.2604vw 0 0 0.2604vw;
          }

          &:last-child {
            border-radius: 0 0.2604vw 0.2604vw 0;
          }
        }
      }
    }

    &-lists {
      min-height: 7.9167vw;

      .pcLists {
        &-in {
          margin-bottom: 1.5625vw;

          &:not(:last-child) {
            margin-right: 1.5625vw;
          }

          &-img {
            width: 7.8125vw;
            height: 7.8125vw;
            border-radius: 0.5208vw;
          }
        }

        .swiperpcLists-in {
          &-img {
            margin: 0 0.7813vw;
            border-radius: 0.5208vw;
          }
        }
      }

      .mbLists {
        width: calc(100% - 2.0833vw);

        &-in {
          &-img {
            margin: 0 0.5208vw;
            border-radius: 0.5208vw;
          }
        }
      }
    }

    &-detail {
      padding: 1.0417vw;
      margin-top: 2.6042vw;

      &-l {
        max-width: 22.6042vw;

        &-in {
          &::after {
            top: -1.0417vw;
            left: -1.0417vw;
            border-radius: 1.5625vw;
          }
        }

        img {
          border-radius: 1.5625vw;
        }
      }

      &-r {
        .detail-1 {
          padding-left: 1.0417vw;

          span {
            font-size: 1.0417vw;

            &:nth-of-type(1) {
              font-size: 1.8229vw;
              margin-right: 0.2604vw;
            }
          }
        }

        .detail-2 {
          span {
            font-size: 1.4583vw;
            padding: 0.2604vw 3.6458vw 0.2604vw 1.0417vw;
          }
        }

        .detail-3 {
          padding-left: 1.0417vw;
          font-size: 1.0417vw;
          margin-bottom: 1.5625vw;
          margin-top: 0.2604vw;
        }

        .detail-4 {
          padding-left: 1.0417vw;
          font-size: 1.0417vw;
          margin-bottom: 1.0417vw;
        }

        .detail-5 {
          padding-left: 1.0417vw;
          font-size: 1.0417vw;

          span {
            &:not(:last-child) {
              margin-right: 0.5208vw;
            }
          }
        }

        .detail-6 {
          margin-top: 1.5625vw;
          margin-left: 1.0417vw;
          margin-bottom: 1.0417vw;
        }
      }
    }

    &-detailBox {
      min-height: 28.6458vw;
    }

    .index-doctorTeam-detail-swiper {
      padding-bottom: 2.0833vw;
    }
  }

  .Latest_Movies {
    margin-top: 50px;

    &_t {
      a {
        svg {
          width: 2.2917vw;
          height: 1.8229vw;
          margin-right: 0.5208vw;
        }

        span {
          font-size: 1.1458vw;
        }
      }
    }

    &_in {
      margin-top: 1.9792vw;

      &_l {
        margin-right: 1.7188vw;
        width: 28.125vw;

        span {
          padding: 0.7813vw 1.0417vw 0;
          font-size: 1.0417vw;
        }

        iframe {
          width: 28.125vw;
          height: 15.7813vw;
        }
      }

      &_r {
        &_t {
          .tab-in {
            font-size: 1.3542vw;
            letter-spacing: 0.1354vw;
            padding: 0.1563vw 1.5625vw 0;

            &:first-child {
              border-radius: 0.2604vw 0 0 0.2604vw;
            }

            &:last-child {
              border-radius: 0 0.2604vw 0.2604vw 0;
            }

            &::after {
              width: 1.25vw;
              height: 0.625vw;
              border-left: 0.625vw solid transparent;
              border-right: 0.625vw solid transparent;
              border-top: 0.625vw solid #fdd3e3;
            }
          }
        }

        &_b {
          gap: 1.7708vw;
          margin-top: 2.2396vw;

          .list-in {
            iframe {
              width: 19.5313vw;
              height: 10.9896vw;
            }

            span {
              padding: 0.7813vw 1.0417vw 0;
              font-size: 1.0417vw;
            }
          }
        }
      }
    }
  }
}

@media screen and (max-width: 768px) {
  .treatment-data {
    margin-top: 70px;
    overflow: hidden;

    &-title {
      span {
        font-size: 20px;
      }
    }

    &-in {
      padding: 0 20px;
      margin-top: 60px;

      .dataBox {
        width: 50%;

        &:not(:last-child) {
          margin-bottom: 62px;
        }

        .num {
          font-size: 35px;

          img {
            width: 100px;
          }

          .numIn {
            height: 50px;

            span {
              line-height: 50px;
            }
          }
        }

        .name {
          font-size: 24px;
        }

        &:nth-of-type(1) {
          img {
            left: 15% !important;
            top: -60% !important;
          }
        }

        &:nth-of-type(2) {
          img {
            left: -5% !important;
            top: -30% !important;
            width: 50%;
          }
        }

        &:nth-of-type(3) {
          img {
            left: 5% !important;
            top: -50% !important;
          }
        }

        &:nth-of-type(4) {
          img {
            width: 70%;
            left: 45% !important;
            top: -10% !important;
          }
        }
      }
    }

    &-bText {
      font-size: 16px;
      margin-top: 0px;
    }
  }

  .indexPage {
    width: 100%;
    background: #fff;
    margin-top: 35px;
  }

  //醫生團隊
  .index-doctorTeam {
    margin: 50px 0 0;
    width: 100%;

    &-con {
      width: 100%;
    }

    &-t {
      flex-direction: column;
      align-items: flex-start;
      box-sizing: border-box;
    }

    &-tab1 {
      :deep(.areaTab) {
        div {
          font-size: 4.265vw;
        }
      }
    }

    &-tab2 {
      padding: 0 30px;
      margin-top: 20px;

      &-in {
        display: flex;
        flex-wrap: wrap;
        border: 1px solid #00aeff;
        border-radius: 5px;

        &>div {
          font-size: 4.065vw;
          padding: 1.33vw 0;
          letter-spacing: 0.8vw;
          border: none;

          &:not(:nth-of-type(n + 4)) {
            border-right: 1px solid #00aeff;
          }

          &:not(:nth-of-type(n + 5)) {
            border-bottom: 1px solid #00aeff;
          }

          &:nth-of-type(n + 6) {
            border-left: 1px solid #00aeff;
          }

          &.textlang-3,
          &.textlang-4 {
            min-width: calc(100% / 4);
          }

          &:first-child {
            border-radius: 0;
          }

          &:last-child {
            border-right: none;
            border-radius: 0;
          }

          &:hover {
            color: #00aeff;
            background: #fff;
          }

          &.index-doctorTeam-tab2-in-active {
            color: #fff;
            background: #00aeff;
          }
        }

        &.tablang-1,
        &.tablang-2,
        &.tablang-3,
        &.tablang-4 {
          &>div {
            border-bottom: none;

            &:last-child {
              border-right: none;
            }
          }
        }
      }
    }

    &-lists {
      margin-top: 20px;
      min-height: 96px;
      overflow: hidden;

      .pcLists {
        display: none;
      }

      .mbLists {
        display: block;
      }
    }

    &-detail {
      flex-direction: column;
      padding: 0;
      margin-top: 30px;

      &-l {
        width: 100%;

        &-in {
          &::after {
            display: none;
          }
        }

        img {
          border-radius: 0;

          &:nth-of-type(1) {
            border: none;
          }

          &:nth-of-type(2) {
            height: 100%;
            max-height: 90%;
            left: 50%;
            top: auto;
            bottom: 0;
            transform: translateX(-50%);
          }
        }

        &-btn {
          display: none;
        }
      }

      &-r {
        .detail-1 {
          margin: 5px 0;
          padding: 0 30px;

          span {
            font-size: 18px;
            display: inline-block;

            &:nth-of-type(1) {
              font-size: 30px;
              letter-spacing: 2px;
              margin-right: 5px;
            }
          }
        }

        .detail-2 {
          span {
            width: 100%;
            font-size: 20px;
            padding: 5px 75px 5px 30px;
            clip-path: polygon(0 0, 85% 0, 90% 100%, 0 100%);
          }
        }

        .detail-3 {
          margin-top: 10px;
          padding: 0 30px;
          font-size: 16px;
        }

        .detail-4 {
          font-size: 16px;
          padding: 0 30px;
          margin-bottom: 30px;

          span {
            text-align: justify;
          }
        }

        .detail-5 {
          font-size: 12px;
          padding: 0 30px;
          display: flex;
          justify-content: center;
        }

        .detail-6 {
          display: flex;
          justify-content: center;
          margin-left: 0;

          span {
            font-size: 28px;
          }
        }
      }
    }

    .group_photo {
      max-width: 100%;
      margin: 24px auto;
    }
  }

  //個案分享
  .index-caseSharing {
    background: none;
    background: linear-gradient(0, #fee6f1 0%, rgba(255, 241, 240, 0) 100%);
    padding: 0;
    margin-top: 40px;

    &-in {
      width: 100%;
      margin: 15px auto 0;
      // padding: 20px 30px;
      padding: 20px 0;

      .in-top {
        display: flex;
        width: 100%;
        height: 56vw;
      }

      .in-cen {
        margin-top: 34px;
        flex-direction: column;

        &-box {
          width: 100%;
        }
      }

      .in-bottom {
        width: 100%;
        background: linear-gradient(0deg,
            rgba(255, 241, 240, 0.7) 41.54%,
            rgba(255, 241, 240, 0) 137.31%);
        padding: 20px 0;
        margin-top: 0;

        span {
          width: 137px;
          height: 40px;
          font-weight: 500;
          font-size: 1rem;
          background: #ffffff;
          line-height: 40px;
          padding: 0;
          box-shadow: 1px 1px 4px rgba(255, 163, 158, 0.45);
          color: #666666;
          transition: all 0.3s;

          &:hover {
            background: var(--indexColor3);
            color: #ffffff;
            text-shadow: 0px 0px 8px rgba(255, 120, 117, 0.65);
          }
        }
      }
    }
  }



  .index-videoBox {
    &-tab {
      margin-top: 30px;

      .tab-in {
        border: 1px solid #fdd3e3;
        letter-spacing: 1.588px;
        font-size: 16px;
        padding: 3px 16px 0;
      }
    }

    &-in {
      grid-template-columns: repeat(1, 1fr);
      margin: 30px 30px 0 30px;
    }

    &-btn {
      position: relative;
      inset: auto;
      top: 0;
      display: flex;
      justify-content: center;
      margin: 10px auto 30px;

      span {
        float: initial;
        font-size: 20px;
        margin-left: 10px;

        &::before {
          border-bottom: 1px solid var(--indexColor1);
        }

        &::after {
          font-size: 18px;
        }
      }
    }

    .index-latestNews-line {
      width: 45%;
      margin: 0 auto;
    }
  }

  .Latest_Movies {
    margin-top: 70px;
    max-width: 100vw;
    overflow: hidden;
    opacity: 0.8;
    background: linear-gradient(270deg,
        rgba(255, 241, 240, 0) 0%,
        rgba(255, 241, 240, 1) 100%);
    padding: 20px 0;
    box-sizing: border-box;

    &_t {

      // width: 100vw;
      // margin-left: -30px;
      a {
        svg {
          width: 32px;
          height: 26px;
        }

        span {
          font-size: 18px;
          padding-right: 30px;
        }
      }
    }

    &_in {
      margin: 30px 30px 0;
      flex-direction: column;

      // margin-top: ;
      &_l {
        width: 84%;
        margin: 0;

        span {
          color: var(--indexColor1);
          padding-left: 0;
        }

        iframe {
          width: 100%;
          height: calc(153 / 315 * 100vw);
        }
      }

      &_r {
        &_t {
          justify-content: center;
          margin-top: 30px;
          margin-left: -50px;

          .tab-in {
            border: 1px solid #fdd3e3;
            letter-spacing: 1.588px;
            font-size: 16px;
            padding: 3px 16px 0;
          }
        }

        &_b {
          grid-template-columns: repeat(1, 1fr);
          gap: 25px;
          margin-top: 30px;
          width: 84%;

          .list-in {
            iframe {
              width: 100%;
              height: calc(153 / 315 * 100vw);
            }

            span {}
          }
        }
      }

      .index-latestNews-line {
        margin: 20px 0;
        margin-left: -60px;

        .point {
          width: calc(100% - 365px) !important;
          margin: 0px auto;
        }
      }
    }
  }

  .share-item {
    display: flex;
    flex-direction: column;
    gap: 15px 0;

    &>div:nth-child(1) {
      max-width: 74.35vw;
      margin-left: 0;
      padding: 10px 15px;
      box-sizing: border-box;
      display: flex;
      flex-direction: column;
      gap: 10px 0;
      background: var(--White, #fff);

      &>div:nth-child(1) {
        display: flex;
        justify-content: space-between;

        &>div:nth-child(1) {
          width: 29.48vw;

          &>img {
            width: 100%;
          }
        }

        &>div:nth-child(2) {
          &>div:nth-child(2) {
            display: flex;
            flex-direction: column;

            &>span:nth-child(1) {
              color: var(--Theme-Color, #fc1682);
              font-family: 'FakePearl-Regular';
              font-size: 5.12vw;
              font-style: normal;
              font-weight: 600;
              line-height: 160%;
              /* 32px */
            }

            &>span {
              color: var(--Grey-Mid, #666);
              font-family: 'Noto Sans HK';
              font-size: 3.07vw;
              font-style: normal;
              font-weight: 500;
              line-height: 160%;
              /* 19.2px */
              letter-spacing: 1.2px;
            }
          }
        }
      }
    }

    &>div:nth-child(2),
    &>div:nth-child(3) {
      background: var(--White, #fff);
      padding: 10px 15px;
      box-sizing: border-box;
      max-width: 74.35vw;
      display: flex;
      flex-direction: column;
      gap: 6px 0;

      &>div:nth-child(1) {
        display: flex;
        justify-content: space-between;

        &>div:nth-child(1) {
          display: flex;
          flex-direction: column;
        }
      }
    }

    &>div:nth-child(2) {
      margin-left: auto;
      margin-right: 0;

      .item-title {
        color: var(--Theme-Color, #fc1682);
      }
    }
  }

  .item-title {
    color: var(--Blue-Deep, #00aeff);
    font-family: 'FakePearl-Regular';
    font-size: 20px;
    font-style: normal;
    font-weight: 600;
    line-height: 160%;
    /* 32px */
  }

  .item-tag {
    color: var(--Grey-Pale, #aaa);
    font-family: 'Noto Sans HK';
    font-size: 12px;
    font-style: normal;
    font-weight: 500;
    line-height: 160%;
    /* 19.2px */
    letter-spacing: 1.2px;
  }

  .item-date {
    color: var(--Grey-Mid, #666);
    font-family: 'Noto Sans HK';
    font-size: 12px;
    font-style: normal;
    font-weight: 500;
    line-height: 160%;
    /* 19.2px */
    letter-spacing: 1.2px;
    text-align: right;
  }

  .item-content {
    color: var(--Grey-Deep, #4d4d4d);
    text-align: justify;
    font-family: 'Noto Sans HK';
    font-size: 3.07vw;
    font-style: normal;
    font-weight: 500;
    line-height: 160%;
    /* 19.2px */
    letter-spacing: 1.2px;
    display: flex;
    flex-direction: column;

    &>span {
      line-height: 160%;
      min-height: 19.19px;
    }
  }
}

@media screen and (min-width: 991px) {

  .service-item-pc {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 30px 0;
    margin: 0 auto;
    max-width: 1000px;

    &>div:nth-child(2) {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 15px 20px;
      margin-top: 15px;
    }

    .service_item {
      // margin-bottom: 45px;
      color: var(--White, #FFF);
      text-align: center;

      /* 桌面版/PC-頂部目錄 */
      font-family: "Noto Sans TC";
      font-size: 20px;
      font-style: normal;
      font-weight: 700;
      line-height: 160%;
      /* 32px */
      letter-spacing: 2px;
      box-sizing: border-box;
      padding: 15px 0;

      &>a {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 7px 0;
        width: 210px;
        color: var(--Grey-Dark, #333);


        &>div:nth-child(1) {
          border-radius: 50%;
          width: 100px;
          height: 100px;
          background: #FFE9EC;

          &>img {
            width: 100%;
            height: 100%;
            object-fit: cover;
          }
        }
      }
    }

    .service_item:hover {
      border-radius: 10px;
      background: var(--New-Theme-Color, #D2337D);
      box-sizing: border-box;

      &>a {
        width: 210px;

        &>div:nth-child(1) {
          border-radius: 50%;
          width: 100px;
          height: 100px;
          background: #fff;


          &>img {
            width: 100%;
            height: 100%;
            object-fit: cover;
          }
        }
      }

      div {
        color: #fff;
      }
    }
  }

  .doctor-team {
    padding: 30px 0;
    box-sizing: border-box;

    .doctor-team-content-text {
      margin-top: 15px;
      color: var(--Grey-Deep, #4D4D4D);
      text-align: center;
      font-family: "Noto Sans HK";
      font-size: 20px;
      font-style: normal;
      font-weight: 400;
      line-height: 160%;
      letter-spacing: 2px;
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

  .strength {
    max-width: 100%;
    background: var(--Pale-Pink-Grad, linear-gradient(180deg, rgba(255, 255, 255, 0.00) 0%, var(--Pink-Pale, #FFE9EC) 100%));
  }

  .swiper-Title {
    bottom: 12%;
    left: 50%;
    transform: translateX(-50%);
    width: fit-content;

    &-Box {
      .swiper-paginationEdit {
        max-width: 162px;
        height: 30px;

        .swiper-pagination {
          position: static;
          width: auto;
        }
      }
    }
  }

  .strength-intro {
    margin: 15px auto 20px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;

    &>p {
      color: var(--Grey-Dark, #333);
      text-align: center;
      font-family: "Noto Sans TC";
      font-size: 20px;
      font-style: normal;
      font-weight: 700;
      line-height: 160%;
      /* 32px */
      letter-spacing: 2px;
    }
  }

  .strength-content {
    max-width: 820px;
    height: 480px;
    margin: 0 auto;
    overflow: hidden;
    position: relative;

    .swiper-strength-Title {
      top: 50%;
      left: 50%;
      transform: translateX(-50%);
    }

    .swiper-Title-Box {
      &>div {
        display: flex;
        align-items: center;
      }

      .swiper-pagination-bullet {
        width: 18px;
        height: 18px;
        background: #fff;
        opacity: 1;
        margin: 0;
        cursor: pointer;
      }

      .swiper-pagination {
        position: initial;
        display: flex;
        align-items: center;
        gap: 0 10px;
        margin: 0 10px;
      }

      .swiper-pagination-bullet-active {
        background: #d2337d;
      }

      .swiper-button-next:after,
      .swiper-button-prev:after {
        content: none;
      }

      .swiper-button-prev,
      .swiper-button-next {
        background: #fff;
        border-radius: 50%;
        width: 30px;
        height: 30px;
        min-width: 30px;
        min-height: 30px;
        top: initial;
        margin-top: initial;
        position: initial;
        transition: background-color 0.3s ease;
      }

      .swiper-button-prev:hover,
      .swiper-button-next:hover {
        box-shadow: (0px 0px 10px rgba(0, 0, 0, 0.3));
        background: #d2337d;

        svg {
          path {
            stroke: white;
          }
        }
      }
    }
  }

  .strength-list {
    justify-content: center;
    display: flex;
    gap: 0 20px;
    position: relative;
    top: -45px;
    z-index: 70;
  }

  .listText {
    max-width: 230px;
    display: flex;
    flex-direction: column;
    align-items: center;
    border-radius: 15px;
    background: var(--White, #FFF);
    box-shadow: 0px 4px 4px 0px rgba(77, 77, 77, 0.20);
    box-sizing: border-box;
    padding: 20px;

    &>div:nth-child(1) {
      position: relative;
      display: flex;
      flex-direction: column;

      color: #8A5E1B;
      text-align: center;
      /* 桌面版/PC-H3 */
      font-family: "Noto Sans HK";
      font-size: 24px;
      font-style: normal;
      font-weight: 700;
      /* 28.8px */
      letter-spacing: 2.4px;

      &>span:nth-child(2) {
        color: #8A5E1B;
        font-family: "Noto Sans HK";
        font-size: 20px;
        font-style: normal;
        font-weight: 500;
        line-height: 100%;
        letter-spacing: 2px;
      }
    }

    &>div:nth-child(2) {
      color: var(--Grey-Dark, #333);
      text-align: justify;
      /* PC-16pt Text */
      font-family: "Noto Sans HK";
      font-size: 16px;
      font-style: normal;
      font-weight: 400;
      line-height: 150%;
      /* 24px */
      letter-spacing: 1.6px;
      margin-top: 17px;
    }
  }

  .listText {
    &>div:nth-child(1)::after {
      content: '';
      background: url(https://static.ckjhk.com/ckj-image/2025030715124001.png) no-repeat;
      background-size: cover;
      width: 187.203px;
      min-height: 78.934px;
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
    }
  }

  .listText:nth-child(1) {
    &>div:nth-child(1) {
      &>span {
        color: #8A5E1B;
        font-family: "Noto Sans HK";
        font-size: 16.116px;
        font-style: normal;
        font-weight: 500;
        line-height: normal;
        letter-spacing: 1.612px;
      }

      &>span:nth-child(2) {
        font-size: 24px;
        font-style: normal;
        font-weight: 700;
        line-height: 120%;
        letter-spacing: 2.4px;
      }
    }
  }

  .index-org {
    margin-top: 0;
    box-sizing: border-box;
    padding: 30px 0;

    &-tag {
      max-width: 504px;
      display: flex;
      margin-top: 0;
      box-sizing: border-box;
      padding: 10px 0;
      width: 100%;

      &-in {
        flex: 1;
        color: var(--indexColor1);
        padding: 5px;
        font-size: 24px;
        text-align: center;
        border-top: 2px solid var(--indexColor1);
        border-bottom: 2px solid var(--indexColor1);
        border-left: 2px solid var(--indexColor1);
        transition: all 0.3s;
        cursor: pointer;

        &:first-child {
          border-radius: 5px 0 0 5px;
        }

        &:last-child {
          border-radius: 0 5px 5px 0;
          border-right: 2px solid var(--indexColor1);
        }

        &:hover,
        &.active {
          color: #fff;
          background: var(--indexColor1);
        }

        &.active {
          position: relative;

          // 三角形
          &::after {
            content: '';
            position: absolute;
            bottom: -16px;
            left: 50%;
            transform: translateX(-50%);
            border: 8px solid transparent;
            border-top-color: var(--indexColor1);
            width: 0;
            height: 0;
            z-index: 1;
          }
        }
      }
    }

    &-content {
      max-width: 960px;
      margin-top: 0;
      width: 58vw;

      &-swiper {
        width: 100%;

        &-slie {
          width: 100%;
          display: flex;
          grid-template-columns: repeat(5, 1fr);
          gap: 22px 26px;
          flex-wrap: wrap;
          justify-content: center;
        }
      }

      &-in {
        display: flex;
        align-items: center;
        justify-content: center;
        max-width: 170px;
        width: 9.583vw;
        height: auto;
        margin: 0;
      }

      &-0 {
        align-items: flex-start !important;
      }
    }
  }


  .kol-video {
    position: relative;

    .video-list {
      width: 672px;
      height: 378px;
      margin: 30px auto 0;
    }

    .video-user-id {
      position: absolute;
      top: 10px;
      right: 10vw;
      display: flex !important;
      align-items: center;
      gap: 0 5px;
    }
  }
}

@media screen and (max-width: 992px) {
  .indexPage {
    margin: 0;
  }

  .service-item-pc {
    margin: 30px 0;

    &>div:nth-child(2) {
      margin-top: 2.665vw;
      display: grid;
      justify-content: center;
      grid-template-columns: repeat(4, 1fr);
      gap: 5.33vw 3.465vw;
      box-sizing: border-box;
      padding: 0 5.33vw;

      .service_item {
        &>a {
          display: flex;
          flex-direction: column;
          align-items: center;

          &>div:nth-child(1) {
            width: 18.2665vw;
            height: 18.265vw;

            img {
              width: 100%;
              height: 100%;
              object-fit: cover;
            }
          }

          &>div:nth-child(2) {
            min-height: 34px;

            span {
              display: flex;
              flex-direction: column;
              align-items: center;
              justify-content: center;
              color: var(--Grey-Dark, #333);
              text-align: center;
              font-family: "Noto Sans HK";
              font-size: 3.733vw;
              font-style: normal;
              font-weight: 700;
              line-height: 120%;
            }


            .service_item_sub {
              color: var(--Grey-Dark, #333);
              font-family: "Noto Sans HK";
              font-size: 3.733vw;
              font-style: normal;
              font-weight: 400;
              line-height: 150%;
            }
          }
        }
      }
    }
  }

  .doctor-team-content-text {
    margin-top: 14px;
    color: var(--Grey-Mid, #666);
    text-align: justify;

    /* 手機版/MB-14Pt字 */
    font-family: "Noto Sans HK";
    font-size: 14px;
    font-style: normal;
    font-weight: 400;
    line-height: 150%;
    /* 21px */
    letter-spacing: 0.7px;
    box-sizing: border-box;
    padding: 0 5.33vw;
  }

  .doctor-team {
    margin: 30px 0;
    background: linear-gradient(180deg, rgba(255, 255, 255, 0) 56.4%, var(--Pink-Pale, #FFE9EC) 82.58%);
    padding-bottom: 5.33vw;
  }

  .doctor-team-content-btn {
    margin: 15px auto;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .strength {
    padding: 0;
  }

  .strength-content {
    box-sizing: border-box;
    margin: 15px 20px 0;
    overflow: hidden;
    position: relative;
  }

  .strength-list {
    box-sizing: border-box;
    padding: 0 5.33vw;
    margin: 6.4vw 0 0;
    display: flex;
    flex-direction: column;
    gap: 6.5vw 0;

    .listText {
      display: flex;
      justify-content: space-between;
      gap: 0 5.33vw;
      align-items: center;

      &>div:nth-child(1) {
        background: url("https://static.ckjhk.com/ckj-image/2025030715124001.png") no-repeat center;
        background-size: cover;
        min-width: 130.334px;
        width: 130.334px;
        height: 59.112px;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;

        &>span {
          color: #8A5E1B;
          text-align: center;
          color: #8A5E1B;
          font-family: "Noto Sans HK";
          font-size: 18.104px;
          font-style: normal;
          font-weight: 700;
          line-height: normal;
        }

        &>span:last-child {
          color: #8A5E1B;
          font-family: "Noto Sans HK";
          font-size: 12.069px;
          font-style: normal;
          font-weight: 500;
          line-height: normal;
          letter-spacing: 1.207px;
        }
      }

      &>div:nth-child(2) {
        color: var(--Grey-Dark, #333);
        text-align: justify;
        font-family: "Noto Sans HK";
        font-size: 14px;
        font-style: normal;
        font-weight: 400;
        line-height: 150%;
        /* 21px */
        letter-spacing: 0.7px;
      }
    }

    .listText:first-child {
      &>div:nth-child(1) {
        &>span {
          color: #8A5E1B;
          font-family: "Noto Sans HK";
          font-size: 12.069px;
          font-style: normal;
          font-weight: 500;
          line-height: normal;
          letter-spacing: 1.207px;
        }

        &>span:last-child {
          color: #8A5E1B;
          text-align: center;
          font-family: "Noto Sans HK";
          font-size: 18.104px;
          font-style: normal;
          font-weight: 700;
          line-height: normal;
        }
      }
    }
  }

  .medium {
    margin-top: 50px;
  }

  .medium-tabs {
    width: fit-content;
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 12px auto 30px;
    overflow: hidden;
    border-radius: 5px;
    border: 1px solid var(--Grey-Light, #e6e6e6);
    background: var(--White, #fff);

    .medium-list {
      color: var(--Grey-Mid, #666);
      text-align: center;

      /* 手機版/MB-Body Text Bold */
      font-family: "Noto Sans HK";
      font-size: 16px;
      font-style: normal;
      font-weight: 700;
      line-height: normal;
      letter-spacing: 1.6px;
      box-sizing: border-box;
      padding: 8px;
      border: 1px solid var(--Grey-Light, #e6e6e6);
      border-right: 1px solid var(--Grey-Light, #e6e6e6);
      transition: all 0.3s ease-in;
    }

    .medium-list:last-child {
      border-right: none;
    }
  }

  .strength-content {

    .swiper-Title {
      left: 50%;
      transform: translateX(-50%);
      padding: 0;
      bottom: 3.933vw;

      &-Box {
        &>div {
          display: flex;
          align-items: center;
        }

        .swiper-paginationEdit {
          height: 0;

          .swiper-pagination {
            position: static;
            width: auto;
          }
        }
      }
    }

    :deep(.swiper-wrapper) {
      .swiper-slide {
        position: relative;
      }
    }

    :deep(.swiper-wrapper) {
      .swiper-slide::after {
        content: '';
        position: absolute;
        bottom: 0;
        left: 0;
        right: 0;
        width: 100%;
        height: 30px;
        background: linear-gradient(0deg, #fff 0%, rgba(255, 255, 255, 0) 100%);
      }
    }
  }

  .swiper-button-prev:after,
  .swiper-button-next:after {
    display: none;
  }

  .swiper-pagination-bullet {
    width: 3.2vw;
    height: 3.2vw;
    background: #fff;
    opacity: 1;
    margin: 0;
  }

  .swiper-pagination {
    position: initial;
    display: flex;
    align-items: center;
    gap: 0 1.6vw;
    margin: 0 2.13vw;
  }

  .swiper-pagination-bullet-active {
    background: #d2337d;
  }

  .swiper-button-prev,
  .swiper-button-next {
    background: #fff;
    border-radius: 50%;
    width: 8vw;
    height: 8vw;
    min-width: 8vw;
    min-height: 8vw;
    top: initial;
    margin-top: initial;
    position: initial;
    transition: background-color 0.3s ease;
  }

  .swiper-button-prev:hover,
  .swiper-button-next:hover {
    box-shadow: (0px 0px 2.665vw rgba(0, 0, 0, 0.3));
    background: #d2337d;

    svg {
      path {
        stroke: white;
      }
    }
  }

  .index-org {
    margin-top: 0;
    margin: 30px 0;

    &-tag {
      max-width: 100%;
      display: flex;
      margin-top: 0;
      box-sizing: border-box;
      padding: 4vw 4.265vw;

      &-in {
        flex: 1;
        color: var(--indexColor1);
        padding: 5px;
        font-size: 24px;
        text-align: center;
        border-top: 2px solid var(--indexColor1);
        border-bottom: 2px solid var(--indexColor1);
        border-left: 2px solid var(--indexColor1);
        transition: all 0.3s;
        cursor: pointer;

        font-size: 4.265vw;
        font-style: normal;
        font-weight: 700;
        line-height: 150%;
        /* 24px */
        letter-spacing: 0.4265vw;

        &:first-child {
          border-radius: 5px 0 0 5px;
        }

        &:last-child {
          border-radius: 0 5px 5px 0;
          border-right: 2px solid var(--indexColor1);
        }

        &:hover,
        &.active {
          color: #fff;
          background: var(--indexColor1);
        }

        &.active {
          position: relative;

          // 三角形
          &::after {
            content: '';
            position: absolute;
            bottom: -16px;
            left: 50%;
            transform: translateX(-50%);
            border: 8px solid transparent;
            border-top-color: var(--indexColor1);
            width: 0;
            height: 0;
            z-index: 1;
          }
        }
      }
    }

    &-content {
      max-width: 100%;
      margin-top: 0;
      box-sizing: border-box;
      padding: 0 2.65vw;

      &-swiper {
        width: 100%;

        &-slie {
          width: 100%;
          display: grid;
          grid-template-columns: repeat(3, 1fr);
          gap: 22px 26px;
          flex-wrap: wrap;
          justify-content: center;
        }
      }

      &-in {
        display: flex;
        align-items: center;
        justify-content: center;
        width: auto;
        height: auto;
        margin: 0;
      }

      &-0 {
        align-items: flex-start !important;
      }
    }
  }

  .kol-video {
    margin-top: 10.665vw;
    padding: 0;
  }

  .video-list {
    display: flex;
    justify-content: center;
    align-items: center;
    box-sizing: border-box;
    padding: 0 5.33vw;

    &>iframe {
      width: 72.533vw;
      height: 40.8vw;
      margin: 2.665vw auto 0;
    }
  }
}
</style>