<script lang="ts" setup>
import { Navigation, Pagination, Mousewheel, Keyboard } from 'swiper'
import { useAppState } from '~/stores/appState'
const appState = useAppState()
appState.setDentistryService('all-ceramic-crowns')


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

useHead({
  title: '全瓷牙冠 | 牙科服務',
  meta: [
    {
      hid: 'description',
      name: 'description',
      content:
        '愛康健提供全瓷牙冠（牙套）服務，全瓷冠又稱全瓷牙冠、全瓷冠假牙、陶瓷假牙，而牙冠（牙套）是修復牙齒的方法，用於覆蓋形狀參差不齊或變色的牙齒。當牙齒因各種原因損壞時、需要修復裂縫或保護脆弱的牙齒時，會建議使用牙冠（牙套）進行修復。',
    },
    {
      hid: 'Keywords',
      name: 'Keywords',
      content:
        '牙套 全瓷冠全瓷牙冠 全瓷冠假牙 陶瓷假牙 假牙 牙冠 愛康健 深圳愛康健 深圳專業牙科中心 愛康健醫院 愛康健口腔醫院 深圳愛康健口腔醫院愛康健 CKJ愛康健齒科集團 深圳口腔專科醫院 愛康健齒科集團 深圳牙科醫院牙科服務內地牙科 深圳口腔專科',
    },
  ],
})

const headerConfig = {
  img: 'https://static.ckjhk.com/ckj-image/7c39b7d07bd1.webp',
  mbImg: 'https://static.ckjhk.com/ckj-image/693b4d5e52e0.webp',
  bg: '',
  pageName: 'scaling-and-polishing-test',
  pcText: [],
  mbText: [],
}

const orthodonticsIntroduceData = {
  title: 'pages.dental-service.all-ceramic-crowns.introduce.title',
  content: 'pages.dental-service.all-ceramic-crowns.introduce.content',
  mbImg: 'https://static.cmereye.com/imgs/2024/05/8a10c52c1402727d.png',
  pcImg: 'https://static.cmereye.com/imgs/2024/05/6bc1522cd9b10464.webp',
  tabNavName: 'pages.dental-service.all-ceramic-crowns.introduce.tabNavName',
}

const foiblesData = {
  title: '全瓷牙冠及全鋯牙冠點揀好？',
  context: {
    span1: '有多種製作牙冠的物料，包括：',
    span2: '金屬、全鋯及全瓷。每種物料各有優點，可讓患者按需要選擇。',
    span3: '以下為你分析全瓷牙冠及全鋯牙冠的優缺點：',
  },
  foiblesLists: [
    {
      title: '全瓷牙冠',
      meritLists: [
        '仿真度最高，透光度高，顏色相似，自然',
        '適合用於前牙，外觀與真牙相似，不影響美觀',
        '可根據需要的堅固度，選擇不同強度的物料',
      ],
      shortcomingLists: ['比金屬牙套的強度較低'],
      img: 'https://static.cmereye.com/imgs/2024/07/94cd54041d3efc00.png',
      mbimg: 'https://static.cmereye.com/imgs/2024/07/94cd54041d3efc00.png',
    },
    {
      title: '烤瓷合金牙冠',
      meritLists: ['內層金屬，外層陶瓷，可以選擇外層顏色，較為美觀'],
      shortcomingLists: [
        '由於有內外兩層，相對較厚，需磨掉較多牙齒',
        '牙套顏色不夠自然',
        '牙套邊緣會顯出金屬黑影，影響外觀',
        '表層陶瓷較金屬容易剝落或斷裂',
      ],
      img: 'https://static.cmereye.com/imgs/2024/07/520fa4ad88956a63.png',
      mbimg: 'https://static.cmereye.com/imgs/2024/07/520fa4ad88956a63.png',
    },
    {
      title: '金屬牙冠',
      meritLists: [
        '耐用度高，適合需要咬合力較強的後牙',
        '損耗度與真牙非常接近',
        '堅固穩定，不用大幅度磨小牙齒，可保留大部分原牙',
      ],
      shortcomingLists: [
        '金屬顏色，不適合用於前牙，影響外觀',
        '價格較為昂貴',
        '有致癌疑慮',
        '較容易發炎或出現過敏',
      ],
      img: 'https://static.cmereye.com/imgs/2024/05/92599038cf25787c.png',
      mbimg: 'https://static.cmereye.com/imgs/2024/05/5cd67bf0be05684e.png',
    },
  ],
}

const stepData = {
  title: '服務流程',
  stepLists: [
    {
      name: '牙科診症',
      text: '由我們的牙醫為您進行口腔X Ray檢查並診斷，建議適合您的治療方案。',
      img: 'https://static.cmereye.com/imgs/2024/05/6fa827c648b84026.png',
    },
    {
      name: '牙科治療',
      text: '牙醫將進行治療牙齒，移除受損或蛀牙部分，為牙冠安裝作準備。',
      img: 'https://static.cmereye.com/imgs/2024/05/205095f005fac9cd.png',
    },
    {
      name: '精準掃描及取模',
      text: '使用先進的3D掃描技術，獲得精確的牙齒和口腔結構數據。取得牙齒的模型，以便製作合適的牙冠。',
      img: 'https://static.cmereye.com/imgs/2024/05/008d4d9e8743b81e.png',
    },
    {
      name: '臨時牙冠',
      text: '在等待永久牙冠製作期間，可能會安裝臨時牙冠保護牙齒。',
      img: 'https://static.cmereye.com/imgs/2024/05/67d95d7a4c7df5a7.png',
    },
    {
      name: '牙冠製作',
      text: '在我們的專科實驗室製作高精密度的牙冠。',
      img: 'https://static.cmereye.com/imgs/2024/05/d3393fb46a8be6d8.png',
    },
    {
      name: '牙冠安裝',
      text: '製作完成後，將進行牙冠試戴，確保完美貼合並進行調整。',
      img: 'https://static.cmereye.com/imgs/2024/05/8d8235d083747ea2.png',
    },
    {
      name: '定期覆診',
      text: '完成牙冠安裝後，將定期覆診及監察的牙冠狀況。',
      img: 'https://static.cmereye.com/imgs/2024/05/6798aa4aafd17ae5.png',
    },
  ],
}
const maintainData = {
  title: '牙冠要如何維護保養？',
  lists: [
    {
      name: '日常清潔',
      text: '每天使用牙線和牙刷清潔，特別注意牙冠周圍的牙齦線。',
      img: 'https://static.cmereye.com/imgs/2024/05/cefd1f712cd0bd43.png',
      mbimg: 'https://static.cmereye.com/imgs/2024/05/8c4d9cc3ce4fa000.png',
    },
    {
      name: '定期檢查',
      text: '定期到牙科診所進行專業清潔和檢查，以確保牙冠及周圍組織的健康。',
      img: 'https://static.cmereye.com/imgs/2024/05/f860909a46a01624.png',
      mbimg: 'https://static.cmereye.com/imgs/2024/05/a58fc9c6cc6cbc79.png',
    },
    {
      name: '避免硬物',
      text: '避免用牙冠咀嚼過硬的食物，以防牙冠破裂或脫落。',
      img: 'https://static.cmereye.com/imgs/2024/05/e80db740bd07665c.png',
      mbimg: 'https://static.cmereye.com/imgs/2024/05/299152af40e09595.png',
    },
  ],
}
const problemData = {
  title: '<span>全瓷/全鋯牙冠</span><span>常見問題</span>',
  lists: [
    {
      Q: '優質牙冠的準則?',
      A: '美觀自然： 色澤逼真，透光性好，與真牙無異。生物相容性好： 不含金屬，不易引起過敏反應，對牙齦無刺激。堅固耐用： 具有良好的抗壓強度和耐磨性，使用壽命長。精準密合： 採用數位化設計和製作，確保牙冠與牙齒完美貼合。',
    },
    {
      Q: '為什麼做牙冠是需要磨牙?',
      A: '提供空間： 牙冠是一種覆蓋在牙齒上的修復體，需要一定的空間才能安裝。如果不磨牙，牙冠會使牙齒變大，影響美觀和咬合。創造固位形： 牙醫需要將牙齒修磨成特定的形狀，例如：略微收斂的圓錐形，以便牙冠能夠牢固地粘接在牙齒上，不易脫落。改善外形和咬合： 如果牙齒有缺損、變形或咬合不良等問題，通過修磨可以改善牙齒的外形和咬合關係，使牙冠更好地發揮功能。\n\n現時部份材料可做成超薄牙冠，加上粘合劑的技術進步，磨牙量可大幅減少。',
    },
    {
      Q: '杜牙根後一定要做牙冠嗎?',
      A: '如果杜牙根後，牙齒的剩餘結構較少，牙齒變得脆弱，容易斷裂，那麼強烈建議做牙冠。牙冠可以提供額外的保護，防止牙齒崩裂。',
    },
  ],
}
let windowWidth = ref(390)

const getWindowWidth = () => {
  windowWidth.value = window.innerWidth
}
onMounted(() => {
  getWindowWidth()
  window.addEventListener('resize', getWindowWidth)
})

const surgicalExtractionOfTeeth = ref(true)
const courseSurgicalExtractionOfTeeth = ref([
  {
    id: 1,
    title: 'CT檢查及診症',
  },
  {
    id: 2,
    title: '牙齒磨小為牙冠預留空間',
  },
  {
    id: 3,
    title: '精準掃描及取模',
  },
  {
    id: 4,
    title: 'CAD/CAM精密電腦輔助設計及製作<br /><i>(最快2小時完成)</i>',
  },
  {
    id: 5,
    title: '安裝牙冠',
  },
])
const courseNonSurgicalToothExtraction = ref([
  {
    id: 1,
    title: 'CT檢查及診症',
  },
  {
    id: 2,
    title: '牙齒磨小為牙冠預留空間',
  },
  {
    id: 3,
    title: '精準掃描及取模',
  },
  {
    id: 4,
    title: '制作及安裝臨時牙冠',
  },
  {
    id: 5,
    title: '牙冠精密製作',
  },
  {
    id: 6,
    title: '安裝牙冠',
  },
])

const courseToothExtraction = (str) => {
  if (str === 'Surgical') {
    surgicalExtractionOfTeeth.value = true
    listItem(str)
  } else if (str === 'notSurgical') {
    surgicalExtractionOfTeeth.value = false
    listItem(str)
  }
}

const listItem = (str) => {
  if (str === 'Surgical') {
    return courseSurgicalExtractionOfTeeth.value
  }
  if (str === 'notSurgical') {
    return courseNonSurgicalToothExtraction.value
  }
}
</script>


<template>
  <div>
    <PageHeaderV2 v-if="windowWidth > 768" :headerConfig="headerConfig" />
    <MobileHeaderV2 v-if="windowWidth < 768" :headerConfig="headerConfig">
      <template #xxxxxxxxxxx-home>
        <div class="banner-in-box">
          <div class="banner-content" style="display: flex">
            <div class="content-title">網上預約限定優惠</div>
            <div class="content-price">
              <div>全瓷牙冠</div>
              <div>
                <img src="~/assets/images/2025031317044801.svg" alt="" />
              </div>
            </div>
            <div class="content-subscribe">重拾牙力，耐久自然，性價比首選</div>
          </div>
        </div>
      </template>
    </MobileHeaderV2>
    <PagePcBannerNoHome v-if="windowWidth > 768" :headerConfig="headerConfig">
      <template #xxxxxxxxxxx-home>
        <div class="banner-in-box">
          <div class="banner-image">
            <img src="https://static.ckjhk.com/ckj-image/8e4cc5dc8367.webp" alt="" loading="lazy" />
          </div>
          <div class="banner-content" style="display: flex">
            <div class="content-title">網上預約限定優惠</div>
            <div class="content-price">
              <div>全瓷牙冠</div>
              <div>
                <img src="~/assets/images/2025031317044801.svg" alt="" />
              </div>
            </div>
            <div class="content-subscribe">重拾牙力，耐久自然，性價比首選</div>
          </div>
        </div>
      </template>
    </PagePcBannerNoHome>
    <div class="all-ceramic-crowns">
      <section class="ckj-container all-ceramic-crowns-service">
        <div class="d-flex flex-row align-items-end subheading">
          <span>杜牙根後</span><span>必須做牙冠嗎?</span>
        </div>
        <div class="all-ceramic-crowns-service-content">
          <div>
            <img src="https://static.ckjhk.com/ckj-image/562005c85794.png" alt="" />
          </div>
          <div>
            <img src="https://static.ckjhk.com/ckj-image/f6c3006435b7.png" alt="" />
          </div>
          <div>
            <img src="https://static.ckjhk.com/ckj-image/55f30988628c.png" alt="" />
          </div>
        </div>
        <div class="all-ceramic-crowns-service-content-text">
          <p>杜牙根後牙齒的剩餘結構較少，牙齒變得脆弱容易斷裂。</p>
          <p>牙冠可以提供額外的保護，防止牙齒崩裂。</p>
        </div>
      </section>
      <section class="ckj-container dental-crown">
        <div class="d-flex flex-row align-items-end subheading">
          <span>愛康健牙冠</span><span>收費</span>
        </div>
        <div class="dental-crown-content">
          <div>
            <div>項目</div>
            <div>價錢</div>
          </div>
          <div>
            <div>格萊美全瓷牙冠</div>
            <div>
              <div>¥3,000/顆</div>
              <div>
                <div>網上限定預約優惠</div>
                <div>
                  <img src="https://static.ckjhk.com/ckj-image/7a508b9bfef7.svg" alt="網上限定預約優惠" />
                </div>
              </div>
            </div>
          </div>
          <div>
            <div>E.Max高強度鑄瓷牙冠</div>
            <div>¥3,500/顆</div>
          </div>
          <div>
            <div>德國Wieland全瓷牙冠</div>
            <div>¥4,000/顆</div>
          </div>
          <div>
            <div>奥地利Cercon氧化鋯<br class="d-md-none" />全瓷牙冠</div>
            <div><span>\高強度/</span>&nbsp;&nbsp;&nbsp;&nbsp;¥4,500/顆</div>
          </div>
          <div>
            <div>
              德國Sirona CAD/<br class="d-md-none" />CAM玻璃陶瓷全瓷牙冠
            </div>
            <div><span>\即日完成/</span>&nbsp;&nbsp;&nbsp;&nbsp;¥5,500/顆</div>
          </div>
          <div>
            <div>3M Lava全瓷牙冠</div>
            <div>¥6,800/顆</div>
          </div>
          <div>
            <div>貝美高端全瓷牙冠</div>
            <div>¥8,800/顆</div>
          </div>
        </div>
        <div class="dental-crown-content-text">
          <div>
            <div>
              <img src="https://static.ckjhk.com/ckj-image/cc6b0d3f2d32.png" alt="" />
            </div>
            <div>
              <img src="https://static.ckjhk.com/ckj-image/b63632e09538.png" alt="" />
            </div>
          </div>
          <div>愛康健牙冠價格已包含檢查費、設計費、材料費、安裝費。</div>
        </div>
      </section>
      <div class="bg-customization-process">
        <section class="ckj-container customization-process">
          <div class="d-flex flex-row align-items-end subheading">
            <span>牙冠訂製</span><span>過程</span>
          </div>
          <div class="customization-process-content d-none d-md-flex">
            <div>CT檢查及診症</div>
            <div>牙齒磨小為牙冠預留空間</div>
            <div>精準掃描及取模</div>
            <div>
              <div>CAD/CAM精密電腦輔助<br />設計及製作 (最快2小時完成)</div>
              <div>
                <div>制作及安裝臨時牙冠</div>
                <div>傳統牙冠製作 (2-3日完成)</div>
              </div>
            </div>
            <div>安裝牙冠</div>
          </div>
          <div class="course d-md-none">
            <!-- <div class="course-text">
              拔牙一般無需進行手術，但當牙齒歪生或非常接近<br class="d-md-none" />神經，便有可能要進行手術式脫牙。
            </div> -->
            <div>
              <div>
                <div :class="surgicalExtractionOfTeeth ? 'active-teeth' : ''"
                  @click="courseToothExtraction('Surgical')">
                  CAD/CAM技術牙冠
                </div>
                <div :class="surgicalExtractionOfTeeth ? '' : 'active-teeth'"
                  @click="courseToothExtraction('notSurgical')">
                  傳統牙冠
                </div>
              </div>
              <div>
                <div class="d-none d-md-flex">
                  <img :src="'~/assets/images/2025033111372801.svg'" />
                </div>
                <div class="d-md-none">
                  <img :style="{
                    height: surgicalExtractionOfTeeth ? '260px' : '280px',
                  }" :src="surgicalExtractionOfTeeth
                    ? 'https://static.ckjhk.com/ckj-image/2025040216330802.png'
                    : 'https://static.ckjhk.com/ckj-image/2025040216330801.png'
                    " />
                </div>
                <div>
                  <div v-for="(item, index) in listItem(
                    surgicalExtractionOfTeeth ? 'Surgical' : 'notSurgical'
                  )" :key="index">
                    <div>
                      <div>{{ item.id }}</div>
                      <div>
                        <div v-html="item.title"></div>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="customization-process-text d-none d-md-flex">
            <div>
              CAD/CAM技術製作的牙冠較傳統牙冠更密合，減低長期使用二次蛀牙、痠痛、異味發生率
              👍🏻
            </div>
            <div><img src="~/assets/images/2025040211330101.png" alt="" /></div>
          </div>
          <div class="d-md-none">
            <div v-if="surgicalExtractionOfTeeth" class="customization-process-text">
              <div>
                CAD/CAM技術製作的牙冠較傳統牙冠更密合，減低長期使用二次蛀牙、痠痛、異味發生率
                👍🏻
              </div>
              <div>
                <img src="~/assets/images/2025040211330101.png" alt="" />
              </div>
            </div>
            <div class="customization-process-tradition-text" v-else>
              2-3日完成
            </div>
          </div>
        </section>
      </div>
      <section class="ckj-container species">
        <div class="d-flex flex-row align-items-end subheading">
          <span>牙冠</span><span>種類</span>
        </div>
        <div class="species-content">
          <div>\ 最多人選擇！ /</div>
          <div>烤瓷合金牙冠</div>
          <div>全瓷牙冠</div>
          <div>金屬牙冠</div>
          <div>
            <img src="https://static.ckjhk.com/ckj-image/c53fcc7f7189.png" alt="" />
          </div>
          <div>
            <img src="https://static.ckjhk.com/ckj-image/a5c26ff1c0e5.png" alt="" />
          </div>
          <div>
            <img src="https://static.ckjhk.com/ckj-image/a2e28e94c7c4.png" alt="" />
          </div>
          <div>優點</div>
          <div>
            <ul>
              <li>內層金屬，外層陶瓷</li>
              <li>可以選擇外層顏色，較美觀</li>
            </ul>
          </div>
          <div>
            <ul>
              <li>仿真度最高，顏色自然</li>
              <li>適合用於前牙，美觀</li>
              <li>可根據需要的選擇物料強度</li>
            </ul>
          </div>
          <div>
            <ul>
              <li>耐用度高，適合用於後牙</li>
              <li>損耗度與真牙非常接近</li>
              <li>堅固穩定，原牙改動小</li>
            </ul>
          </div>
          <div>缺點</div>
          <div>
            <ul>
              <li>較厚，需磨掉較多原牙</li>
              <li>顏色不夠自然</li>
              <li>邊緣有金屬黑影，影響外觀</li>
              <li>表層易剝落斷裂</li>
            </ul>
          </div>
          <div>
            <ul>
              <li>強度低於金屬</li>
            </ul>
          </div>
          <div>
            <ul>
              <li>金屬顏色，影響外觀</li>
              <li>價格較貴</li>
              <li>有致癌疑慮</li>
              <li>易發炎或過敏</li>
            </ul>
          </div>
        </div>
      </section>
      <section class="ckj-container crown-maintenance">
        <div class="d-flex flex-row align-items-end subheading">
          <span>牙冠如何</span><span>維護保養?</span>
        </div>
        <div class="crown-maintenance-content">
          <div>
            <div>
              <img src="https://static.ckjhk.com/ckj-image/450744fbe886.png" alt="" />
            </div>
            <div>每日牙線清潔</div>
          </div>
          <div>
            <div>
              <img src="https://static.ckjhk.com/ckj-image/060c3c7295fd.png" alt="" />
            </div>
            <div>定期檢查</div>
          </div>
          <div>
            <div>
              <img src="https://static.ckjhk.com/ckj-image/2f3e9454e843.png" alt="" />
            </div>
            <div>避免咀嚼硬物</div>
          </div>
        </div>
      </section>
      <section class="ckj-container crown-case">
        <div class="d-flex flex-row align-items-end subheading">
          <span>牙冠</span><span>案例</span>
        </div>
        <div class="crown-case-content">
          <div class="crown-case-content-title">
            <div>手術前</div>
            <div>手術後</div>
          </div>
          <div>
            <swiper :modules="[Navigation, Pagination, Mousewheel, Keyboard]" class="mySwiper" @swiper="setSwiperRef">
              <swiper-slide class="swiper-slide-img">
                <div>
                  <img src="https://static.ckjhk.com/ckj-image/c75e70d54395.jpg" alt="" />
                </div>
                <div>
                  <img src="https://static.ckjhk.com/ckj-image/ff29dc67893c.jpg" alt="" />
                </div>
                <div></div>
                <div>
                  <img src="https://static.ckjhk.com/ckj-image/a62ba03ae963.jpg" alt="" />
                </div>
              </swiper-slide>
              <swiper-slide class="swiper-slide-img">
                <div>
                  <img src="https://static.ckjhk.com/ckj-image/43d049eb37e1.jpg" alt="" />
                </div>
                <div>
                  <img src="https://static.ckjhk.com/ckj-image/181ec1cb844f.jpg" alt="" />
                </div>
                <div></div>
                <div></div>
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
        </div>
      </section>
      <section class="ckj-container problem-data">
        <V2ServiceProblem :problemData="problemData" :v2Versions="true" />
      </section>
    </div>
    <!-- <div class="pageIn whitebgColor">
      <div class="index_title pageCon">
        {{ $t('pages.dental-service.title') }}
      </div>
      <ServiceIntroduce :introduceData="orthodonticsIntroduceData" />
      <div class="ltimg">
        <img
          srcset="
            https://static.cmereye.com/imgs/2024/05/f8cf5af81800962b.png  768w,
            https://static.cmereye.com/imgs/2024/05/da662d9a9e97417b.webp
          "
          src="https://static.cmereye.com/imgs/2024/05/da662d9a9e97417b.webp"
        />
      </div>
      <div class="step">
        <div class="dentistryServices-title">
          <div class="dentistryServices-title-in bb">
            {{ stepData.title }}
          </div>
        </div>
        <div class="step-in">
          <div class="step-in-list">
            <div
              class="lists-in"
              v-for="(item, index) in stepData.stepLists.slice(0, 4)"
              :key="index"
            >
              <img :src="item.img" :alt="item.text" :title="item.text" />
              <h3>{{ item.name }}</h3>
              <p>{{ item.text }}</p>
            </div>
            <div class="line"></div>
          </div>
          <div class="step-in-list">
            <div
              class="lists-in"
              v-for="(item, index) in stepData.stepLists.slice(4, 7)"
              :key="index"
            >
              <img :src="item.img" :alt="item.text" :title="item.text" />
              <h3>{{ item.name }}</h3>
              <p>{{ item.text }}</p>
            </div>
            <div class="line"></div>
          </div>
        </div>
      </div>
      <div class="foibles">
        <div class="dentistryServices-title">
          <div class="dentistryServices-title-in bb">
            {{ foiblesData.title }}
          </div>
        </div>
        <div class="foibles-text">
          <p>
            有多種製作牙冠的物料，包括：金屬、烤瓷合金及全瓷。每種物料各有優點，可讓患者按需要選擇。
          </p>
          <p>以下為你分析全瓷牙冠及全鋯牙冠的優缺點：</p>
        </div>
        <div class="foibles-in">
          <div class="list-in">
            <div class="title"></div>
            <div class="img"></div>
            <div class="merit">
              <img
                src="https://static.cmereye.com/imgs/2024/05/5dbd219b6720d596.png"
                alt=""
              />
              <span>優點</span>
            </div>
            <div class="shortcoming">
              <img
                src="https://static.cmereye.com/imgs/2024/05/df82206323e591ae.png"
                alt=""
              />
              <span>缺點</span>
            </div>
          </div>
          <div
            class="list-in"
            v-for="(item, index) in foiblesData.foiblesLists"
            :key="index"
          >
            <div class="title">
              <span>{{ item.title }}</span>
            </div>
            <div class="img">
              <img
                :srcset="`${item.mbimg} 768w, ${item.img}`"
                :src="item.img"
                alt=""
              />
            </div>
            <div class="merit">
              <div class="mbl">
                <img
                  src="https://static.cmereye.com/imgs/2024/05/5dbd219b6720d596.png"
                  alt=""
                />
                <span>優點</span>
              </div>
              <div class="spanLists">
                <span
                  v-for="(meritItem, meritIndex) in item.meritLists"
                  :key="meritIndex"
                >
                  {{ meritItem }}
                </span>
              </div>
            </div>
            <div class="shortcoming">
              <div class="mbl">
                <img
                  src="https://static.cmereye.com/imgs/2024/05/df82206323e591ae.png"
                  alt=""
                />
                <span>缺點</span>
              </div>
              <div class="spanLists">
                <span
                  v-for="(
                    shortcomingItem, shortcomingIndex
                  ) in item.shortcomingLists"
                  :key="shortcomingIndex"
                >
                  {{ shortcomingItem }}
                </span>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="maintain">
        <div class="dentistryServices-title">
          <div class="dentistryServices-title-in bb">
            {{ maintainData.title }}
          </div>
        </div>
        <div class="maintain-in">
          <div
            class="list-in"
            v-for="(item, index) in maintainData.lists"
            :key="index"
          >
            <img
              :srcset="`${item.mbimg} 768w,${item.img}`"
              :src="item.img"
              :alt="item.name"
              :title="item.name"
            />
            <h3>{{ item.name }}</h3>
            <p>{{ item.text }}</p>
          </div>
        </div>
      </div>
    </div> -->
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

.ltimg {
  display: flex;
  justify-content: center;
  width: 100%;
  margin-top: 114px;
  padding-bottom: 100px;
  background: url(https://static.cmereye.com/imgs/2024/05/4e7cd0b335c399a0.png) no-repeat;
  background-size: 100% 80%;
  background-position: center 200px;

  img {
    width: 1080px;
  }
}

.step {
  margin-top: 106px;

  &-in {
    width: 100%;
    margin-top: 7px;

    &-list {
      max-width: 1080px;
      margin: 50px auto;
      display: grid;
      gap: 70px;
      grid-template-columns: repeat(4, 1fr);
      position: relative;

      .lists-in {
        width: auto;

        img {
          width: 100%;
        }

        h3 {
          color: var(--indexColor1);
          text-align: center;
          font-family: 'FakePearl-Regular';
          font-size: 23px;
          font-style: normal;
          font-weight: 500;
          line-height: 160%;
          margin-top: 10px;
        }

        p {
          margin-top: 10px;
          color: var(--textColor);
          line-height: 160%;
          /* 30.4px */
          letter-spacing: 3.8px;
          font-size: 19px;
          text-align: center;
        }
      }

      &:nth-of-type(2) {
        max-width: 810px;
        grid-template-columns: repeat(3, 1fr);
      }

      .line {
        width: 100vw;
        height: 0;
        position: absolute;
        left: 50%;
        top: 32%;
        transform: translateX(-50%);
        border-bottom: 1px solid var(--indexColor1);
        z-index: -1;
      }

      &::before {
        content: '';
        position: absolute;
        background: url(https://static.cmereye.com/imgs/2024/05/0245d98d5d39cd83.png) no-repeat;
        background-size: 100% 100%;
        width: 14px;
        height: 21px;
        top: 32%;
        left: -50px;
        transform: translateY(-50%);
      }

      &::after {
        content: '';
        position: absolute;
        background: url(https://static.cmereye.com/imgs/2024/05/0245d98d5d39cd83.png) no-repeat;
        background-size: 100% 100%;
        width: 14px;
        height: 21px;
        top: 32%;
        right: -50px;
        transform: translateY(-50%);
      }
    }
  }
}

.maintain {
  margin-top: 100px;

  &-in {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 112px;
    max-width: 950px;
    width: 100%;
    margin: 20px auto 0;

    .list-in {
      img {
        width: 100%;
      }

      h3 {
        color: var(--Grey-Deep, #4d4d4d);
        text-align: center;
        font-size: 30px;
        font-style: normal;
        font-weight: 500;
        line-height: 160%;
        letter-spacing: 3px;
        margin-top: 5px;
      }

      p {
        color: var(--Grey-Deep, #4d4d4d);
        font-family: 'Noto Sans HK';
        font-size: 20px;
        font-style: normal;
        font-weight: 400;
        line-height: 160%;
        letter-spacing: 5px;
        text-align: center;
      }
    }
  }
}

.foibles {
  margin-top: 100px;

  &-text {
    margin-top: 25px;

    p {
      color: var(--Black, var(--Grey-Deep, #4d4d4d));
      text-align: center;
      font-size: 19px;
      font-style: normal;
      font-weight: 400;
      line-height: 160%;
      /* 30.4px */
      letter-spacing: 3.8px;

      &:last-child {
        color: var(--indexColor1);
      }
    }
  }

  &-in {
    display: grid;
    grid-template-columns: 0.65fr 1fr 1fr 1fr;
    width: 100%;
    max-width: 1499px;
    margin: 120px auto 0;

    .list-in {
      &>div {
        border-bottom: 2px solid #aaa;
        border-right: 2px solid #aaa;
        display: flex;
        justify-content: center;
        flex-direction: column;
      }

      .title {
        color: var(--Grey-Deep, #4d4d4d);
        text-align: center;
        font-size: 23px;
        font-style: normal;
        font-weight: 500;
        line-height: 160%;
        height: 69px;
        background: #ffcecb;
      }

      .img {

        // height: 280px;
        img {
          width: 100%;
          height: 100%;
        }
      }

      .merit {
        color: var(--Grey-Deep, #4d4d4d);
        font-size: 19px;
        font-style: normal;
        font-weight: 400;
        line-height: 160%;
        letter-spacing: 3.8px;
        height: 227px;
        padding: 0 54px;

        .mbl {
          display: none;
        }

        .spanLists {
          display: flex;
          justify-content: center;
          flex-direction: column;
        }

        span {
          padding-left: 15px;
          position: relative;

          &::before {
            content: '·';
            position: absolute;
            left: 0;
            top: 0;
            font-size: 30px;
          }
        }
      }

      .shortcoming {
        color: var(--Grey-Deep, #4d4d4d);
        font-size: 19px;
        font-style: normal;
        font-weight: 400;
        line-height: 160%;
        letter-spacing: 3.8px;
        height: 260px;
        padding: 0 50px;

        .mbl {
          display: none;
        }

        .spanLists {
          display: flex;
          justify-content: center;
          flex-direction: column;
        }

        span {
          padding-left: 15px;
          position: relative;

          &::before {
            content: '·';
            position: absolute;
            left: 0;
            top: 0;
            font-size: 30px;
          }
        }
      }

      &:nth-of-type(1) {
        &>div {
          align-items: center;
        }

        .title {
          border: none;
          background: none;
        }

        .merit {
          font-size: 23px;
          color: var(--indexColor1);
          background: #f4f4f4;
          border-left: 2px solid #aaa;
          flex-direction: row;
          letter-spacing: initial;
          padding: 0;

          img {
            width: 103px;
          }

          span {
            padding-left: 0;

            &::before {
              display: none;
            }
          }
        }

        .shortcoming {
          font-size: 23px;
          background: #f4f4f4;
          border-left: 2px solid #aaa;
          flex-direction: row;
          letter-spacing: initial;
          padding: 0;

          img {
            width: 48px;
          }

          span {
            &::before {
              display: none;
            }
          }
        }
      }

      &:nth-of-type(2) {
        .title {
          position: relative;
          border-left: none;
          border-right: 2px solid rgba(0, 0, 0, 0);
          border-top: 2px solid #aaa;
          border-radius: 40px 0 0 0;
          color: #fff;

          span {
            position: relative;
            z-index: 1;
          }

          &::after {
            content: '';
            position: absolute;
            z-index: 0;
            width: 100%;
            height: calc(100% + 18px);
            left: 50%;
            bottom: -3px;
            transform: translate(-50%, 0);
            box-sizing: initial;
            background: var(--indexColor1);
            border-left: 7px solid var(--indexColor1);
            border-right: 7px solid var(--indexColor1);
            border-radius: 40px 40px 0 0;
          }

          &::before {
            content: '';
            width: 204px;
            height: 103px;
            background: url(https://static.cmereye.com/imgs/2024/05/600b314de50aa2ad.png) no-repeat;
            background-size: 100% 100%;
            position: absolute;
            left: 50%;
            bottom: 80%;
            z-index: 1;
            transform: translateX(-50%);
          }
        }

        .img {
          position: relative;

          &::after {
            content: '';
            position: absolute;
            width: 100%;
            height: calc(100% + 4px);
            left: 50%;
            top: 50%;
            transform: translate(-50%, -50%);
            box-sizing: initial;
            border-left: 7px solid var(--indexColor1);
            border-right: 7px solid var(--indexColor1);
          }
        }

        .merit {
          color: var(--indexColor1);
          position: relative;

          &::after {
            content: '';
            position: absolute;
            width: 100%;
            height: calc(100% + 4px);
            left: 50%;
            top: 50%;
            transform: translate(-50%, -50%);
            box-sizing: initial;
            border-left: 7px solid var(--indexColor1);
            border-right: 7px solid var(--indexColor1);
          }
        }

        .shortcoming {
          position: relative;

          &::after {
            content: '';
            position: absolute;
            width: 100%;
            height: calc(100% + 4px);
            left: 50%;
            top: 50%;
            transform: translate(-50%, -50%);
            box-sizing: initial;
            border-left: 7px solid var(--indexColor1);
            border-right: 7px solid var(--indexColor1);
            border-bottom: 7px solid var(--indexColor1);
          }
        }
      }

      &:nth-of-type(3) {
        .title {
          border-top: 2px solid #aaa;
        }
      }

      &:nth-of-type(4) {
        .title {
          border-top: 2px solid #aaa;
        }
      }
    }
  }
}

@media (min-width: 768px) and (max-width: 1920px) {
  .ltimg {
    margin-top: 5.9375vw;
    padding-bottom: 5.2083vw;
    background-position: center 10.4167vw;

    img {
      width: 56.25vw;
    }
  }

  .step {
    margin-top: 5.5208vw;

    &-in {
      margin-top: 0.3646vw;

      &-list {
        max-width: 56.25vw;
        margin: 2.6042vw auto;
        gap: 3.6458vw;

        .lists-in {
          h3 {
            font-size: 1.1979vw;
            margin-top: 0.5208vw;
          }

          p {
            margin-top: 0.5208vw;
            letter-spacing: 0.1979vw;
            font-size: 0.9896vw;
          }
        }

        &:nth-of-type(2) {
          max-width: 42.1875vw;
        }

        &::before {
          width: 0.7292vw;
          height: 1.0938vw;
          left: -2.6042vw;
        }

        &::after {
          width: 0.7292vw;
          height: 1.0938vw;
          right: -2.6042vw;
        }
      }
    }
  }

  .maintain {
    margin-top: 5.2083vw;

    &-in {
      gap: 5.8333vw;
      max-width: 49.4792vw;
      margin: 1.0417vw auto 0;

      .list-in {
        h3 {
          font-size: 1.5625vw;
          letter-spacing: 0.1563vw;
          margin-top: 0.2604vw;
        }

        p {
          font-size: 1.0417vw;
          letter-spacing: 0.2604vw;
        }
      }
    }
  }

  .foibles {
    margin-top: 5.2083vw;

    &-text {
      margin-top: 1.3021vw;

      p {
        font-size: 0.9896vw;
        letter-spacing: 0.1979vw;
      }
    }

    &-in {
      max-width: 78.0729vw;
      margin: 6.25vw auto 0;

      .list-in {
        .title {
          font-size: 1.1979vw;
          height: 3.5938vw;
        }

        .img {
          height: 14.5833vw;
        }

        .merit {
          font-size: 0.9896vw;
          letter-spacing: 0.1979vw;
          height: 11.8229vw;
          padding: 0 2.8125vw;

          span {
            padding-left: 0.7813vw;

            &::before {
              font-size: 1.5625vw;
            }
          }
        }

        .shortcoming {
          font-size: 0.9896vw;
          letter-spacing: 0.1979vw;
          height: 13.5417vw;
          padding: 0 2.6042vw;

          span {
            padding-left: 0.7813vw;

            &::before {
              font-size: 1.5625vw;
            }
          }
        }

        &:nth-of-type(1) {
          .merit {
            font-size: 1.1979vw;

            img {
              width: 5.3646vw;
            }
          }

          .shortcoming {
            font-size: 1.1979vw;

            img {
              width: 2.5vw;
            }
          }
        }

        &:nth-of-type(2) {
          .title {
            border-radius: 2.0833vw 0 0 0;

            &::after {
              height: calc(100% + 0.9375vw);
              bottom: -0.1563vw;
              border-left: 0.3646vw solid var(--indexColor1);
              border-right: 0.3646vw solid var(--indexColor1);
              border-radius: 2.0833vw 2.0833vw 0 0;
            }

            &::before {
              width: 10.625vw;
              height: 5.3646vw;
            }
          }

          .img {
            &::after {
              height: calc(100% + 0.2083vw);
              border-left: 0.3646vw solid var(--indexColor1);
              border-right: 0.3646vw solid var(--indexColor1);
            }
          }

          .merit {
            &::after {
              height: calc(100% + 0.2083vw);
              border-left: 0.3646vw solid var(--indexColor1);
              border-right: 0.3646vw solid var(--indexColor1);
            }
          }

          .shortcoming {
            &::after {
              height: calc(100% + 0.2083vw);
              border-left: 0.3646vw solid var(--indexColor1);
              border-right: 0.3646vw solid var(--indexColor1);
              border-bottom: 0.3646vw solid var(--indexColor1);
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

  .ltimg {
    margin-top: 50px;
    padding: 0 0 60px 10px;
  }

  .step {
    &-in {
      padding: 0 30px;
      margin-top: 45px;

      &-list {
        grid-template-columns: repeat(2, 1fr);
        gap: 30px;
        margin: 30px auto;

        .lists-in {
          h3 {
            font-size: 16px;
          }

          p {
            font-family: 'Noto Sans HK';
            font-size: 16px;
            font-style: normal;
            font-weight: 400;
            line-height: 200%;
            /* 32px */
            letter-spacing: 1.6px;
            text-align: left;
            margin-top: 5px;
          }

          &:nth-of-type(2) {
            p {
              text-align: center;
            }
          }
        }

        &:nth-of-type(2) {
          grid-template-columns: repeat(2, 1fr);
        }

        .line {
          display: none;
        }

        &::before,
        &::after {
          display: none;
        }
      }
    }
  }

  .maintain {
    padding: 0 30px;

    &-in {
      grid-template-columns: repeat(2, 1fr);
      gap: 30px 45px;
      margin-top: 45px;

      .list-in {
        h3 {
          font-size: 20px;
        }

        p {
          letter-spacing: 3.75px;
          font-size: 15px;
        }
      }
    }
  }

  .foibles {
    &-text {
      margin-top: 45px;
      display: flex;
      flex-direction: column;
      align-items: center;

      p {
        width: 100%;
        padding: 0 40px;
        font-size: 16px;

        &:last-child {
          width: 80%;
        }
      }
    }

    &-in {
      grid-template-columns: 1fr;
      padding: 0 30px;
      margin: 100px auto 0;

      .list-in {
        &>div {
          border-bottom: 1px solid #aaa;
          border-right: 1px solid #aaa;
        }

        .title {
          height: 38px;
          font-size: 15px;
        }

        .img {
          // height: 126px;
        }

        .merit {
          height: auto;
          font-size: 12px;
          padding: 0;
          min-height: 103px;
          flex-direction: row;
          letter-spacing: 1.2px;

          .mbl {
            display: flex;
            width: 60px;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            border-right: 1px solid #aaa;
            background: #f4f4f4;

            img {
              width: 36px;
              margin-bottom: 5px;
            }

            span {
              color: var(--indexColor1);
              text-align: center;
              font-size: 16px;
              font-style: normal;
              font-weight: 500;
              line-height: 130%;
              padding-left: 0;
              letter-spacing: initial;

              &::before {
                display: none;
              }
            }
          }

          .spanLists {
            flex: 1;
            padding: 20px 12px;
          }

          span {
            padding-left: 10px;

            &::before {
              font-size: 20px;
            }
          }
        }

        .shortcoming {
          height: auto;
          font-size: 12px;
          padding: 0;
          min-height: 103px;
          flex-direction: row;
          letter-spacing: 1.2px;

          .mbl {
            display: flex;
            width: 60px;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            border-right: 1px solid #aaa;
            background: #f4f4f4;

            img {
              width: 32px;
              margin-bottom: 5px;
            }

            span {
              color: #4c4c4c;
              text-align: center;
              font-size: 16px;
              font-style: normal;
              font-weight: 500;
              line-height: 130%;
              padding-left: 0;
              letter-spacing: initial;

              &::before {
                display: none;
              }
            }
          }

          .spanLists {
            flex: 1;
            padding: 20px 12px;
          }

          span {
            padding-left: 10px;

            &::before {
              font-size: 20px;
            }
          }
        }

        &:nth-of-type(1) {
          display: none;
        }

        &:nth-of-type(2) {
          border-left: 1px solid #aaa;

          .title {
            border-radius: 20px 20px 0 0;

            &::after {
              border-left: 5px solid var(--indexColor1);
              border-right: 5px solid var(--indexColor1);
              border-radius: 25px 25px 0 0;
              bottom: -2px;
            }

            &::before {
              width: 125px;
              bottom: 90%;
              height: calc(103 / 204 * 125px);
            }
          }

          .img {
            &::after {
              border-left: 4px solid var(--indexColor1);
              border-right: 4px solid var(--indexColor1);
            }
          }

          .merit {
            &::after {
              border-left: 4px solid var(--indexColor1);
              border-right: 4px solid var(--indexColor1);
            }
          }

          .shortcoming {
            &::after {
              border-left: 4px solid var(--indexColor1);
              border-right: 4px solid var(--indexColor1);
              border-bottom: 4px solid var(--indexColor1);
            }
          }
        }

        &:nth-of-type(3) {
          border-left: 1px solid #aaa;

          .title {
            border-top: none;
          }
        }

        &:nth-of-type(4) {
          border-left: 1px solid #aaa;

          .title {
            border-top: none;
          }
        }
      }
    }
  }
}
</style>

<style lang="scss" scoped>
@media screen and (min-width: 992px) {
  .all-ceramic-crowns-service {
    margin-top: 45px;
    padding: 30px 0;

    .all-ceramic-crowns-service-content {
      margin: 20px 0;
      display: flex;
      gap: 0 42px;
    }

    .all-ceramic-crowns-service-content-text {
      color: var(--Grey-Dark, #333);
      text-align: center;
      font-family: 'Noto Sans HK';
      font-size: 20px;
      font-style: normal;
      font-weight: 400;
      line-height: 160%;
      /* 32px */
      letter-spacing: 4px;
    }
  }

  .dental-crown {
    padding: 30px 0 45px;

    .dental-crown-content {
      margin-top: 20px;
      border-radius: 20px;
      overflow: hidden;
      box-shadow: 0px 6.761px 6.761px 0px rgba(77, 77, 77, 0.2);

      &>div {
        display: flex;
        justify-content: space-between;
        box-sizing: border-box;
        padding: 20px 35px;
        align-items: center;

        &>div:nth-child(1) {
          color: var(--Grey-Dark, #333);
          font-family: 'Noto Sans HK';
          font-size: 24px;
          font-style: normal;
          font-weight: 700;
          line-height: normal;
          letter-spacing: 2.4px;
        }

        &>div:nth-child(2) {
          color: var(--Brand-Color, #f8298a);
          font-family: 'Noto Sans HK';
          font-size: 24px;
          font-style: normal;
          font-weight: 700;
          line-height: normal;
          letter-spacing: 2.4px;

          &>span {
            color: var(--Blue-Deep, #00aeff);
            text-align: right;
            font-family: 'Noto Sans HK';
            font-size: 24px;
            font-style: normal;
            font-weight: 700;
            line-height: normal;
            letter-spacing: 2.4px;
          }
        }
      }

      &>div:nth-child(odd) {
        background: var(--Palest-Pink, #fff7f8);
      }

      &>div:nth-child(1) {
        background: var(--Brand-Color, #f8298a);

        &>div {
          color: #fff;
        }
      }

      &>div:nth-child(2) {
        &>div:nth-child(1) {
          color: var(--Brand-Color, #f8298a);
        }

        &>div:nth-child(2) {
          display: flex;
          flex-direction: column;
          align-items: flex-end;

          &>div:nth-child(2) {
            display: flex;
            align-items: center;
            gap: 0 15px;

            &>div:nth-child(1) {
              background: url('~/assets/images/2025040116505101.svg') no-repeat;
              background-size: contain;
              width: 258px;
              height: 41px;
              display: flex;
              align-items: center;
              justify-content: center;
              color: #fff;
            }
          }
        }
      }
    }

    .dental-crown-content-text {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 0 17px;
      margin-top: 20px;

      &>div:nth-child(1) {
        display: flex;
        position: relative;

        &>div {
          width: 82px;
          height: 82px;

          &>img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            filter: drop-shadow(0px 0px 12.347px rgba(0, 0, 0, 0.25));
          }
        }

        &>div:nth-child(2) {
          position: relative;
          z-index: 5;
          top: 14px;
          left: -7px;
        }
      }

      &>div:nth-child(2) {
        color: var(--Grey-Dark, #333);
        text-align: justify;
        font-family: 'Noto Sans TC';
        font-size: 20px;
        font-style: normal;
        font-weight: 700;
        line-height: 160%;
        /* 32px */
        letter-spacing: 2px;
      }
    }
  }

  .bg-customization-process {
    background: linear-gradient(0deg,
        rgba(255, 241, 240, 0) 0%,
        rgba(255, 241, 240, 0.7) 1.5%,
        rgba(255, 241, 240, 0.7) 42.99%,
        rgba(255, 241, 240, 0) 100%);
  }

  .customization-process {
    padding: 30px 0;

    .customization-process-content {
      margin-top: 20px;
      display: flex;
      flex-direction: column;
      gap: 40px 0;
      align-items: center;

      &>div:not(:nth-child(4)) {
        border-radius: 20px;
        background: var(--Pink-Mid, #f670ae);
        box-shadow: 0px 4px 4px 0px rgba(77, 77, 77, 0.2);
        width: 350px;
        padding: 10px 0;
        display: flex;
        align-items: center;
        justify-content: center;
        color: #fff;
        text-align: center;
        font-family: 'Noto Sans TC';
        font-size: 20px;
        font-style: normal;
        font-weight: 700;
        line-height: 160%;
        /* 32px */
        letter-spacing: 2px;
        position: relative;
      }

      &>div:nth-child(1)::after,
      &>div:nth-child(2)::after {
        position: absolute;
        content: '';
        width: 18px;
        height: 25px;
        background: url('https://static.ckjhk.com/ckj-image/2025041010261301.png') no-repeat;
        background-size: contain;
        bottom: -65%;
        left: 50%;
        transform: translateX(-50%);
        z-index: -1;
      }

      &>div:nth-child(3)::after {
        position: absolute;
        content: '';
        width: 58px;
        height: 85px;
        background: url('https://static.ckjhk.com/ckj-image/2025041010261302.png') no-repeat;
        background-size: contain;
        bottom: -115%;
        left: -20%;
      }

      &>div:nth-child(3)::before {
        position: absolute;
        content: '';
        width: 51px;
        height: 58px;
        background: url('https://static.ckjhk.com/ckj-image/2025041010261303.png') no-repeat;
        background-size: contain;
        bottom: -61%;
        right: -20%;
        transform: rotate(0deg);
      }

      &>div:nth-child(4) {
        display: flex;
        gap: 0 120px;
        align-items: center;
        position: relative;

        &>div:nth-child(1) {
          border-radius: 20px;
          background: var(--Brand-Color, #f8298a);
          box-shadow: 0px 4px 4px 0px rgba(77, 77, 77, 0.2);
          color: #fff;
          text-align: center;
          font-family: 'Noto Sans TC';
          font-size: 20px;
          font-style: normal;
          font-weight: 700;
          line-height: 160%;
          /* 32px */
          letter-spacing: 2px;
          box-sizing: border-box;
          padding: 10px 35px;
        }

        &>div:nth-child(2) {
          display: flex;
          flex-direction: column;
          gap: 40px 0;

          &>div {
            border-radius: 20px;
            background: var(--Blue-Deep, #00aeff);
            box-shadow: 0px 4px 4px 0px rgba(77, 77, 77, 0.2);
            color: #fff;
            text-align: center;
            font-family: 'Noto Sans TC';
            font-size: 20px;
            font-style: normal;
            font-weight: 700;
            line-height: 160%;
            /* 32px */
            letter-spacing: 2px;
            box-sizing: border-box;
            padding: 10px 45px;
            position: relative;
          }

          &>div:nth-child(1)::after {
            position: absolute;
            content: '';
            width: 18px;
            height: 25px;
            background: url('https://static.ckjhk.com/ckj-image/a17694c1f8a8.svg') no-repeat;
            background-size: contain;
            bottom: -65%;
            left: 50%;
            transform: translateX(-50%);
          }
        }
      }

      &>div:nth-child(4)::after {
        position: absolute;
        content: '';
        width: 51px;
        height: 84px;
        background: url('https://static.ckjhk.com/ckj-image/2025041010261304.png') no-repeat;
        background-size: contain;
        bottom: -55%;
        left: 21%;
      }

      &>div:nth-child(4)::before {
        position: absolute;
        content: '';
        width: 51px;
        height: 58px;
        background: url('https://static.ckjhk.com/ckj-image/2025041010261303.png') no-repeat;
        background-size: contain;
        bottom: -55%;
        right: 21%;
        transform: rotate(90deg);
      }
    }

    .customization-process-text {
      margin-top: 20px;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 0 28px;

      &>div:nth-child(1) {
        max-width: 470px;
        color: var(--Grey-Dark, #333);
        text-align: justify;
        font-family: 'Noto Sans TC';
        font-size: 20px;
        font-style: normal;
        font-weight: 700;
        line-height: 160%;
        /* 32px */
        letter-spacing: 2px;
      }

      &>div:nth-child(2) {
        width: 232.228px;
        height: auto;

        &>img {
          width: 100%;
          height: 100%;
          object-fit: cover;
        }
      }
    }
  }

  .species {
    padding: 30px 0;

    .species-content {
      display: grid;
      grid-template-columns: repeat(3, 1fr);

      &>div:nth-child(1),
      &>div:nth-child(8),
      &>div:nth-child(12) {
        grid-column: span 3;
        text-align: center;
      }

      &>div {
        display: flex;
        align-items: center;
        justify-content: center;
      }

      &>div:nth-child(1) {
        color: var(--Theme-Color, #fc1682);
        text-align: center;
        font-family: 'Noto Sans TC';
        font-size: 20px;
        font-style: normal;
        font-weight: 700;
        line-height: 160%;
        /* 32px */
        letter-spacing: 2px;
      }

      &>div:nth-child(2) {
        color: var(--Grey-Dark, #333);
        text-align: center;
        font-family: 'Noto Sans TC';
        font-size: 20px;
        font-style: normal;
        font-weight: 700;
        line-height: 160%;
        /* 32px */
        letter-spacing: 2px;
        border-radius: 20px 0px 0px 0px;
        background: var(--Grey-Midlight, #adadad);
        padding: 5px 0;
        position: relative;
        z-index: 5;
        width: 105%;
        right: 0%;
      }

      &>div:nth-child(3) {
        padding: 5px 0;
        color: var(--White, #fff);
        text-align: center;
        font-family: 'Noto Sans TC';
        font-size: 20px;
        font-style: normal;
        font-weight: 700;
        line-height: 160%;
        /* 32px */
        letter-spacing: 2px;
        border-radius: 20px 20px 0px 0px;
        background: var(--Brand-Color, #f8298a);
        position: relative;
        z-index: 8;
      }

      &>div:nth-child(4) {
        color: var(--Grey-Dark, #333);
        text-align: center;
        font-family: 'Noto Sans TC';
        font-size: 20px;
        font-style: normal;
        font-weight: 700;
        line-height: 160%;
        /* 32px */
        letter-spacing: 2px;
        border-radius: 0px 20px 0px 0px;
        background: var(--Grey-Midlight, #adadad);
        padding: 5px 0;
        position: relative;
        z-index: 5;
        width: 105%;
        left: -5%;
      }

      &>div:nth-child(6) {
        border-left: 5px solid var(--Brand-Color, #f8298a);
        border-right: 5px solid var(--Brand-Color, #f8298a);

        &>img {
          width: 100%;
          height: 100%;
          object-fit: cover;
        }
      }

      &>div:nth-child(8),
      &>div:nth-child(12) {
        background: var(--Brand-Color, #f8298a);
        color: var(--White, #fff);
        text-align: center;
        font-family: 'Noto Sans TC';
        font-size: 20px;
        font-style: normal;
        font-weight: 700;
        line-height: 160%;
        /* 32px */
        letter-spacing: 2px;
        box-sizing: border-box;
        padding: 5px 0;
      }

      &>div:nth-child(9),
      &>div:nth-child(10),
      &>div:nth-child(11),
      &>div:nth-child(13),
      &>div:nth-child(14),
      &>div:nth-child(15) {
        box-sizing: border-box;
        padding: 10px;

        ul {
          li {
            color: #4c4c4c;
            text-align: justify;
            font-family: 'Noto Sans HK';
            font-size: 18px;
            font-style: normal;
            font-weight: 400;
            line-height: 200%;
            /* 36px */
            letter-spacing: 1.8px;
            list-style: disc;
          }
        }
      }

      &>div:nth-child(9),
      &>div:nth-child(13) {
        border-left: 2px solid var(--Grey-Lightest, #f2f2f2);
      }

      &>div:nth-child(10),
      &>div:nth-child(14) {
        border-left: 2px solid var(--Grey-Lightest, #f2f2f2);
        border-right: 2px solid var(--Grey-Lightest, #f2f2f2);
      }

      &>div:nth-child(11),
      &>div:nth-child(15) {
        border-right: 2px solid var(--Grey-Lightest, #f2f2f2);
      }

      &>div:nth-child(13),
      &>div:nth-child(14),
      &>div:nth-child(15) {
        border-bottom: 2px solid var(--Grey-Lightest, #f2f2f2);
      }

      &>div:nth-child(13) {
        border-radius: 0px 0px 0px 20px;
      }

      &>div:nth-child(15) {
        border-radius: 0px 0px 20px 0;
      }

      &>div:nth-child(12) {
        background: var(--Blue-Deep, #00aeff);
      }
    }
  }

  .crown-maintenance {
    padding: 30px 0;

    .crown-maintenance-content {
      margin-top: 20px;
      display: flex;
      gap: 0 7px;
      justify-content: center;
      align-items: flex-start;

      &>div {
        width: 140px;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        gap: 7px 0;

        &>div:nth-child(1) {
          width: 100px;
          height: 100px;

          &>img {
            width: 100%;
            height: 100%;
            object-fit: cover;
          }
        }

        &>div:nth-child(2) {
          color: var(--Grey-Dark, #333);
          text-align: center;
          font-family: 'Noto Sans HK';
          font-size: 18px;
          font-style: normal;
          font-weight: 400;
          line-height: 200%;
          /* 36px */
          letter-spacing: 1.8px;
        }
      }
    }
  }

  .crown-case {
    padding: 30px 0;

    .crown-case-content {
      margin-top: 15px;

      .crown-case-content-title {
        display: flex;
        justify-content: center;
        margin-bottom: 15px;
        gap: 0 54px;

        &>div {
          width: 453px;
          display: flex;
          align-items: center;
          justify-content: center;
          color: var(--Blue-Deep, #00aeff);
          text-align: center;
          font-family: 'Noto Sans HK';
          font-size: 30px;
          font-style: normal;
          font-weight: 700;
          line-height: normal;
          letter-spacing: 3px;
        }

        &>div:nth-child(2) {
          color: var(--Brand-Color, #f8298a);
        }
      }

      .swiper-slide-img {
        display: flex;
        gap: 15px 54px;
        justify-content: flex-end;
        flex-wrap: wrap;

        &>div {
          width: 453px;
          height: 240px;

          &>img {
            width: 100%;
            height: 100%;
            object-fit: cover;
          }
        }
      }

      .crown-case-content-btn {
        display: flex;
        align-items: center;
        justify-content: center;
        margin-top: 15px;
        gap: 0 15px;

        &>div:nth-child(2) {
          display: flex;
          align-items: center;
          justify-content: center;
          gap: 0 15px;

          &>div {
            width: 18px;
            height: 18px;
            overflow: hidden;
            border-radius: 50%;
            background: var(white, #fff);
            box-shadow: 0px 5.333px 5.333px rgba(77, 77, 77, 0.2);
          }
        }

        &>div:nth-child(1),
        &>div:nth-child(3) {
          width: 30px;
          height: 30px;
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
  }

  .problem-data {
    padding: 30px 0;

    :deep(.problem) {
      margin-top: 20px;
    }
  }

  :deep(.index-dentalServices) {
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
    top: 3vw;
    left: 49%;
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
      padding: 0.859375vw 4.7135vw;
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

    .content-price,
    .content-subscribe {
      width: 100%;
      background: #fff;
      box-sizing: border-box;
      padding: 1.0465vw;
      display: flex;
      gap: 0 0.52vw;
      min-height: 2.68135vw;
      box-sizing: border-box;
      padding: 0.52vw;
      align-items: center;
      font-family: 'Noto Sans HK';
      font-size: 1.927vw;
      font-style: normal;
      font-weight: 900;
      line-height: 2.2222vw;
      /* 114.286% */
      letter-spacing: 0.29165vw;
      justify-content: center;

      &>div:nth-child(1) {
        position: relative;
        color: var(--Grey-Dark, #333);
        text-align: right;
        text-shadow: 1.3px 1.333px 1.333px #faeaf2,
          1.33px -1.333px 1.333px #faeaf2, -1.33px 1.333px 1.333px #faeaf2,
          -1.33px -1.333px 1.333px #faeaf2;
        font-family: 'Noto Sans HK';
        font-size: 1.927vw;
        font-style: normal;
        font-weight: 900;
        line-height: 2.2222vw;
        /* 114.286% */
        letter-spacing: 0.29165vw;
        top: auto;
      }

      &>div:nth-child(2) {
        width: 10.252083vw;

        &>svg {
          width: 100%;
          height: 100%;
          object-fit: cover;
        }
      }
    }

    .content-subscribe {
      box-shadow: 0px 5.333px 5.333px rgba(77, 77, 77, 0.2);
      border-radius: 0px 0px 13.333px 13.333px;
      color: var(--Grey-Dark, #333);
      text-align: center;
      text-shadow: 0px 1.111px 1.111px rgba(0, 0, 0, 0.25);
      font-family: 'Noto Sans HK';
      font-size: 1.38890625vw;
      font-style: normal;
      font-weight: 900;
      line-height: 1.157vw;
      /* 83.333% */
      letter-spacing: 0.1369vw;
    }
  }
}

@media screen and (max-width: 991px) {
  .all-ceramic-crowns {
    margin: 8vw 0;
  }

  .all-ceramic-crowns-service {
    margin: 8vw 0;

    .all-ceramic-crowns-service-content {
      display: flex;
      justify-content: center;
      padding: 4vw 0;
      gap: 0 8.665vw;

      &>div {
        width: 24vw;
        height: 32.109vw;
        overflow: hidden;

        &>img {
          width: 100%;
          height: 100%;
          object-fit: cover;
        }
      }
    }

    .all-ceramic-crowns-service-content-text {
      padding: 0 5.333vw;

      &>p {
        display: inline;
      }

      color: var(--Grey-Dark, #333);
      text-align: justify;
      font-family: 'Noto Sans HK';
      font-size: 3.733vw;
      font-style: normal;
      font-weight: 500;
      line-height: 150%;
      /* 21px */
      letter-spacing: -0.1865vw
    }
  }

  .dental-crown {
    margin: 8vw 0;
    position: relative;
    z-index: 1;
    padding-bottom: 4vw;

    .dental-crown-content {
      border-radius: 1.33vw;
      overflow: hidden;
      box-sizing: border-box;
      margin: 4vw 5.333vw;
      box-shadow: 0px 6.761px 6.761px 0px rgba(77, 77, 77, 0.2);

      &>div {
        display: flex;
        justify-content: space-between;
        box-sizing: border-box;
        padding: 7px 23px;
        align-items: center;
        position: relative;


        &>div:nth-child(1) {
          color: var(--Grey-Dark, #333);
          font-family: 'Noto Sans HK';
          font-size: 4.265vw;
          font-style: normal;
          font-weight: 700;
          line-height: normal;
          letter-spacing: 0.4265vw;
        }

        &>div:nth-child(2) {
          color: var(--Brand-Color, #f8298a);
          text-align: right;
          font-family: 'Noto Sans HK';
          font-size: 4.265vw;
          font-style: normal;
          font-weight: 700;
          line-height: normal;
          letter-spacing: 0.2.133vw;
          display: flex;
          flex-direction: column;

          &>span {
            color: var(--Blue-Deep, #00aeff);
            text-align: right;
            font-family: 'Noto Sans HK';
            font-size: 4.265vw;
            font-style: normal;
            font-weight: 700;
            line-height: normal;
            letter-spacing: 0.2.133vw;
          }
        }
      }

      &>div:nth-child(odd) {
        background: var(--Palest-Pink, #fff7f8);
      }

      &>div:nth-child(1) {
        background: var(--Brand-Color, #f8298a);

        &>div {
          color: #fff;
        }
      }

      &>div:nth-child(2) {
        height: 70px;
        align-items: flex-start;

        &>div:nth-child(1) {
          color: var(--Brand-Color, #f8298a);
        }

        &>div:nth-child(2) {
          display: flex;
          flex-direction: column;
          align-items: flex-end;

          &>div:nth-child(2) {
            display: flex;
            align-items: center;
            gap: 0 4vw;

            &>div:nth-child(1) {
              position: absolute;
              background: url('~/assets/images/2025040116505101.svg') no-repeat;
              background-size: cover;
              width: 44.933vw;
              height: 6.933vw;
              display: flex;
              align-items: center;
              justify-content: center;
              color: #fff;
              color: var(--White, #fff);
              text-align: right;
              font-family: 'Noto Sans HK';
              font-size: 4.265vw;
              font-style: normal;
              font-weight: 700;
              line-height: normal;
              letter-spacing: 0px;
              box-sizing: border-box;
              padding: 3px 0;
              left: 5%;
              bottom: 12%;
            }

            &>div:nth-child(2) {
              width: 28.8vw;
              height: 7.84vw;
              margin-top: 3.33vw;

              &>img {
                width: 100%;
                height: 100%;
                object-fit: cover;
              }
            }
          }
        }
      }
    }

    .dental-crown-content-text {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 0 2.665vw;
      margin: 5.333vw 5.333vw 0;

      &>div:nth-child(1) {
        display: flex;
        position: relative;

        &>div {
          width: 53.129px;
          height: 53.129px;

          &>img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            filter: drop-shadow(0px 0px 12.347px rgba(0, 0, 0, 0.25));
          }
        }

        &>div:nth-child(2) {
          position: relative;
          z-index: 5;
          top: 3.733vw;
          left: -1.865vw
        }
      }

      &>div:nth-child(2) {
        color: var(--Grey-Dark, #333);
        text-align: justify;
        font-family: 'Noto Sans HK';
        font-size: 3.733vw;
        font-style: normal;
        font-weight: 500;
        line-height: 150%;
        /* 21px */
        letter-spacing: -0.1865vw
      }
    }
  }

  .bg-customization-process {
    background: linear-gradient(0deg,
        rgba(255, 241, 240, 0) 0%,
        rgba(255, 241, 240, 0.7) 12.5%,
        rgba(255, 241, 240, 0.7) 81.99%,
        rgba(255, 241, 240, 0) 100%);
  }

  .customization-process {
    margin: 8vw 0;

    .customization-process-content {
      margin-top: 5.333vw;
    }

    .course {
      margin-top: 5.333vw;
      background: linear-gradient(0deg,
          rgba(255, 241, 240, 0) 0%,
          rgba(255, 241, 240, 0.7) 1.5%,
          rgba(255, 241, 240, 0.7) 81.99%,
          rgba(255, 241, 240, 0) 100%),
        #fff;
      box-sizing: border-box;

      .course-text {
        color: var(--Grey-Deep, #4d4d4d);
        text-align: center;
        font-family: 'Noto Sans HK';
        font-size: 3.733vw;
        font-style: normal;
        font-weight: 500;
        line-height: 150%;
        /* 21px */
        letter-spacing: -0.1865vw
      }

      &>div:nth-child(1) {
        margin-top: 2.665vw;
        box-sizing: border-box;
        padding: 0 5.333vw;
        &>div:nth-child(1) {
          display: flex;
          box-sizing: border-box;
          border-radius: 1.33vw;
          overflow: hidden;
          background: var(--White, #fff);

          &>div {
            padding: 2.133vw 2.665vw;
            color: var(--Grey-Mid, #666);
            text-align: center;
            font-family: 'Noto Sans HK';
            font-size: 4.265vw;
            font-style: normal;
            font-weight: 700;
            line-height: normal;
            letter-spacing: 0.4265vw;
          }

          &>div:nth-child(1) {
            flex: 5.4;
          }

          &>div:nth-child(2) {
            flex: 4.5;
          }

          .active-teeth {
            color: var(--White, #fff);
            text-align: center;
            font-family: 'Noto Sans HK';
            font-size: 4.265vw;
            font-style: normal;
            font-weight: 700;
            line-height: normal;
            letter-spacing: 0.4265vw;
            padding: 2.133vw 2.665vw;
            border: 1px solid var(--Brand-Color, #f8298a);
            background: var(--Brand-Color, #f8298a);
            transition: all 0.3s ease-in-out;
          }
        }

        &>div:nth-child(2) {
          display: flex;
          gap: 0 2.665vw;
          align-items: flex-start;
          margin-top: 2.665vw;

          &>div:nth-child(2) {
            width: 7.2vw;
            height: 260px;

            &>img {
              width: 100%;
              height: 100%;
              object-fit: cover;
            }
          }

          &>div:nth-child(3) {
            display: flex;
            flex-direction: column;
            gap: 2.23vw 0;
            width: 100%;

            &>div {
              background: var(--White, #fff);

              &>div {
                display: flex;
                gap: 0 2.665vw;
                box-sizing: border-box;
                padding: 2.665vw;

                &>div:nth-child(1) {
                  color: var(--Theme-Color, #fc1682);
                  font-family: 'Noto Sans HK';
                  font-size: 4.265vw;
                  font-style: normal;
                  font-weight: 700;
                  line-height: 150%;
                  /* 6.4vw */
                }

                &>div:nth-child(2) {
                  &>div {
                    color: var(--Grey-Dark, #333);
                    text-align: justify;
                    font-family: 'Noto Sans HK';
                    font-size: 4.265vw;
                    font-style: normal;
                    font-weight: 500;
                    line-height: 150%;

                    /* 6.4vw */
                    :deep(i) {
                      font-style: normal;
                      color: var(--Brand-Color, #f8298a);
                      font-family: 'Noto Sans HK';
                      font-size: 4.265vw;
                      font-style: normal;
                      font-weight: 700;
                      line-height: 150%;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }

    .customization-process-text {
      display: flex;
      box-sizing: border-box;
      padding: 0 5.333vw 1.33vw;
      gap: 0 12px;
      margin-top: 2.665vw;

      &>div:nth-child(1) {
        max-width: 186px;
        color: var(--Grey-Dark, #333);
        text-align: justify;
        font-family: 'Noto Sans HK';
        font-size: 12px;
        font-style: normal;
        font-weight: 500;
        line-height: 150%;
        /* 18px */
        letter-spacing: 0.6px;
      }

      &>div:nth-child(2) {
        width: 128.857px;
        height: 60.811px;

        &>img {
          width: 100%;
          height: 100%;
          object-fit: contain;
        }
      }
    }

    .customization-process-tradition-text {
      color: var(--Grey-Dark, #333);
      text-align: center;
      font-family: 'Noto Sans HK';
      font-size: 4.265vw;
      font-style: normal;
      font-weight: 700;
      line-height: normal;
      letter-spacing: 0.4265vw;
      margin-top: 2.665vw;
    }
  }

  .species {
    margin: 8vw 0;

    .species-content {
      position: relative;
      z-index: 1;
      margin-top: 2.665vw;
      display: grid;
      grid-template-columns: repeat(3, 1fr);

      &>div:nth-child(1),
      &>div:nth-child(8),
      &>div:nth-child(12) {
        grid-column: span 3;
        text-align: center;
      }

      &>div {
        display: flex;
        justify-content: center;
        align-items: flex-start;
      }

      &>div:nth-child(1) {
        color: var(--Theme-Color, #fc1682);
        text-align: center;
        font-family: 'Noto Sans TC';
        font-size: 5.333vw;
        font-style: normal;
        font-weight: 700;
        line-height: 160%;
        /* 32px */
        letter-spacing: 2px;
      }

      &>div:nth-child(2) {
        color: var(--Grey-Dark, #333);
        text-align: center;
        font-family: 'Noto Sans HK';
        font-size: 3.733vw;
        font-style: normal;
        font-weight: 500;
        line-height: 150%;
        /* 21px */
        letter-spacing: -0.1865vw;
        border-radius: 5.333vw 0px 0px 0px;
        background: var(--Grey-Midlight, #adadad);
        padding: 1.33vw 0;
        position: relative;
        z-index: 5;
        width: 105%;
        right: 0%;
      }

      &>div:nth-child(3) {
        padding: 1.33vw 0;
        color: var(--White, #fff);
        text-align: center;
        font-family: 'Noto Sans HK';
        font-size: 3.733vw;
        font-style: normal;
        font-weight: 500;
        line-height: 150%;
        /* 21px */
        letter-spacing: -0.1865vw;
        border-radius: 2.665vw 2.665vw 0px 0px;
        background: var(--Brand-Color, #f8298a);
        position: relative;
        z-index: 8;
      }

      &>div:nth-child(4) {
        color: var(--Grey-Dark, #333);
        text-align: center;
        font-family: 'Noto Sans HK';
        font-size: 3.733vw;
        font-style: normal;
        font-weight: 500;
        line-height: 150%;
        /* 21px */
        letter-spacing: -0.1865vw; 
        border-radius: 0px 2.665vw 0px 0px;
        background: var(--Grey-Midlight, #adadad);
        padding: 1.33vw 0;
        position: relative;
        z-index: 5;
        width: 105%;
        left: -5%;
      }

      &>div:nth-child(6) {
        border-left: 1.33vw solid var(--Brand-Color, #f8298a);
        border-right: 1.33vw solid var(--Brand-Color, #f8298a);

        &>img {
          width: 100%;
          height: 100%;
          object-fit: cover;
        }
      }

      &>div:nth-child(8),
      &>div:nth-child(12) {
        background: var(--Brand-Color, #f8298a);
        color: var(--White, #fff);
        text-align: center;
        font-family: 'Noto Sans TC';
        font-size: 5.333vw;
        font-style: normal;
        font-weight: 700;
        line-height: 160%;
        /* 32px */
        letter-spacing: 2px;
        box-sizing: border-box;
        padding: 1.33vw 0;
      }

      &>div:nth-child(9),
      &>div:nth-child(10),
      &>div:nth-child(11),
      &>div:nth-child(13),
      &>div:nth-child(14),
      &>div:nth-child(15) {
        box-sizing: border-box;
        padding: 2.665vw;
        padding-left: 22px;

        ul {
          li {
            color: #4c4c4c;
            text-align: justify;
            font-family: 'Noto Sans HK';
            font-size: 12px;
            font-style: normal;
            font-weight: 400;
            line-height: 150%;
            /* 18px */
            letter-spacing: 0.6px;
            list-style: disc;
          }
        }
      }

      &>div:nth-child(9),
      &>div:nth-child(13) {
        border-left: 2px solid var(--Grey-Lightest, #f2f2f2);
      }

      &>div:nth-child(10),
      &>div:nth-child(14) {
        border-left: 2px solid var(--Grey-Lightest, #f2f2f2);
        border-right: 2px solid var(--Grey-Lightest, #f2f2f2);
      }

      &>div:nth-child(11),
      &>div:nth-child(15) {
        border-right: 2px solid var(--Grey-Lightest, #f2f2f2);
      }

      &>div:nth-child(13),
      &>div:nth-child(14),
      &>div:nth-child(15) {
        border-bottom: 2px solid var(--Grey-Lightest, #f2f2f2);
      }

      &>div:nth-child(13) {
        border-radius: 0px 0px 0px 0px;
      }

      &>div:nth-child(15) {
        border-radius: 0px 0px 0px 0;
      }

      &>div:nth-child(12) {
        background: var(--Blue-Deep, #00aeff);
      }
    }
  }

  .crown-maintenance {
    margin: 8vw 0;

    .crown-maintenance-content {
      margin: 2.665vw 8vw 0;
      display: flex;
      gap: 0 40px;
      justify-content: center;

      &>div {
        max-width: 74px;

        &>div:nth-child(1) {
          width: 70px;
          height: 70px;

          &>img {
            width: 100%;
            height: 100%;
            object-fit: cover;
          }
        }

        &>div:nth-child(2) {
          white-space: nowrap;
          color: var(--Grey-Dark, #333);
          text-align: center;
          font-family: 'Noto Sans HK';
          font-size: 3.733vw;
          font-style: normal;
          font-weight: 500;
          line-height: 150%;
          /* 21px */
          letter-spacing: -0.1865vw
        }
      }
    }
  }

  .crown-case {
    margin: 8vw 0;

    .crown-case-content {
      margin-top: 5.333vw;
      padding: 0 12px;

      .crown-case-content-title {
        display: flex;
        justify-content: center;
        margin-bottom: 4vw;
        gap: 0 54px;

        &>div {
          width: 453px;
          display: flex;
          align-items: center;
          justify-content: center;
          color: var(--Blue-Deep, #00aeff);
          text-align: center;
          font-family: 'Noto Sans HK';
          font-size: 18px;
          font-style: normal;
          font-weight: 700;
          line-height: normal;
          letter-spacing: 1.2.133vw;
        }

        &>div:nth-child(2) {
          color: var(--Brand-Color, #f8298a);
        }
      }

      .swiper-slide-img {
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        gap: 2.665vw;
        justify-content: flex-end;
        justify-items: center;

        &>div {
          width: 42.665vw;
          height: 22.665vw;

          &>img {
            width: 100%;
            height: 100%;
            object-fit: cover;
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
            width: 12px;
            height: 12px;
            overflow: hidden;
            border-radius: 50%;
            background: var(white, #fff);
            box-shadow: 0px 5.333px 5.333px rgba(77, 77, 77, 0.2);
          }
        }

        &>div:nth-child(1),
        &>div:nth-child(3) {
          width: 5.333vw;
          height: 5.333vw;
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
  }

  :deep(.index-dentalServices) {
    padding: 0 0;
    margin: 8vw 0 45px;
  }

  .banner-in-box {
    position: absolute;
    bottom: 0;
    left: 0;
    height: 100vw;
    width: 100%;
    z-index: 22;
    box-sizing: border-box;
    padding-bottom: 35px;
    top: 0;
    bottom: 0;
    transform: translateY(0px);
  }

  .banner-image {
    display: none !important;
    position: absolute;
    z-index: 10;
    width: 166px;
    height: 46px;
    top: 0;
    left: 15%;

    &>img {
      width: 100%;
      height: 100%;
      object-fit: contain;
    }
  }

  .banner-content {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    position: absolute;

    &>div {
      display: flex;
      align-items: flex-end;
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
      padding: 0.859375vw 4.7135vw;
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

    .content-price,
    .content-subscribe {
      width: 100%;
      background: #fff;
      box-sizing: border-box;
      padding: 1.0465vw;
      display: flex;
      gap: 0 0.52vw;
      min-height: 2.68135vw;
      box-sizing: border-box;
      padding: 0.52vw;
      align-items: center;
      font-family: 'Noto Sans HK';
      font-size: 1.927vw;
      font-style: normal;
      font-weight: 900;
      line-height: 2.2222vw;
      /* 114.286% */
      letter-spacing: 0.29165vw;
      justify-content: center;

      &>div:nth-child(1) {
        position: relative;
        color: var(--Grey-Dark, #333);
        text-align: right;
        text-shadow: 1.3px 1.333px 1.333px #faeaf2,
          1.33px -1.333px 1.333px #faeaf2, -1.33px 1.333px 1.333px #faeaf2,
          -1.33px -1.333px 1.333px #faeaf2;
        font-family: 'Noto Sans HK';
        font-size: 1.927vw;
        font-style: normal;
        font-weight: 900;
        line-height: 2.2222vw;
        /* 114.286% */
        letter-spacing: 0.29165vw;
        top: auto;
      }

      &>div:nth-child(2) {
        width: 10.252083vw;

        &>svg {
          width: 100%;
          height: 100%;
          object-fit: cover;
        }
      }
    }

    position: relative;
    align-items: flex-start;
    justify-content: flex-end;
    width: 86.665vw;
    left: 50%;
    top: auto;
    bottom: -65%;
    border-radius: 2.665vw;
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
      border-radius: 2.665vw 2.665vw 0px 0px;
      background: var(--Liner-purple,
          linear-gradient(269deg,
            var(--Brand-Color, #fc1682) 10.21%,
            #710d54 122.73%));
      padding: 16.1.33vw 0;
      color: var(--White, #fff);
      text-align: center;
      text-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
      font-family: 'Noto Sans HK';
      font-size: 6.4vw;
      font-style: normal;
      font-weight: 700;
      line-height: 142%;
      /* 83.333% */
      letter-spacing: 2.4px;
    }

    .content-price,
    .content-subscribe {
      min-height: auto;
      gap: 0 2.133vw;
      padding: 2.65vw 0 0 0;
      font-family: 'Noto Sans HK';
      font-size: 4.265vw;
      font-style: normal;
      font-weight: 900;
      line-height: 3.73vw;
      letter-spacing: 0.82vw;

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

      &>div:nth-child(2) {
        width: 40.265vw;
        height: auto;

        &>img {
          width: 100%;
          height: 100%;
          object-fit: contain;
        }
      }
    }

    .content-subscribe {
      padding: 1vw 0 2.65vw 0;
    }

    .price-style {
      width: 153px;
      height: 24vw;

      &>img {
        width: 100%;
        height: 100%;
        object-fit: cover;
      }
    }
  }
}
</style>