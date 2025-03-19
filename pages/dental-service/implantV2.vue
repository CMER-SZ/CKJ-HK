<script lang="ts" setup>
import { useAppState } from '~/stores/appState'
import { Autoplay } from 'swiper'
import { toWhatsApp } from '~/assets/js/common'
import { useElementBounding, useWindowSize } from '@vueuse/core'
import { json } from 'stream/consumers'
const appState = useAppState()
appState.setDentistryService('implant')
useHead({
  title: '種植牙',
  meta: [
    {
      hid: 'description',
      name: 'description',
      content:
        '愛康健提供即剝即種種植牙服務，進口種植牙即減2000元優惠,香港熱線: 6933 8128免費預約掛號,羅湖福田深圳灣口岸分店',
    },
    {
      hid: 'Keywords',
      name: 'Keywords',
      content:
        '愛康健 爱康健 CKJ aikangjian 牙科服務 內地牙科 深圳牙科 深圳愛康健口腔醫院 愛康健齒科集團 美容牙科 高階牙科 醫療券 長者醫療券大灣區試點 種植牙 假牙 金屬牙 缺牙 牙槽骨流失 植牙步驟 微創植牙 傳統植牙 即剝即種 植牙案例 牙醫 牙医 深圳 羅湖 朱咪咪 掛號 親水植體 CT檢查 全口植牙 半口植牙 收費價目表 線上預約 种植牙 種植牙幾錢',
    },
  ],
})

const headerConfig = {
  img: 'https://static.ckjhk.com/ckj-image/0ce172efab96.webp',
  mbImg: 'https://static.ckjhk.com/ckj-image/07c95530a215.webp',
  bg: '',
  pageName: 'implant',
  pcText: ['享受失而復得的喜悅', '重拾完整人生之旅'],
  mbText: ['享受失而復得的喜悅', '重拾完整人生之旅'],
  linkBtn: `https://wa.me/85269338128?text=取得種植牙免費CT檢查`,
}

let windowWidth = ref(1920)

onMounted(() => {
  getWindowWidth()
  window.addEventListener('resize', () => {
    getWindowWidth()
    windowWidth.value = window.innerWidth
  })
  window.addEventListener('contextmenu', function (e) {
    e.preventDefault()
  })
  getWindowWidth()
  windowWidth.value = window.innerWidth
})
const getWindowWidth = () => {
  windowWidth.value = window.innerWidth
}

let implantCaseCurrent = ref(1)
//走马灯事件
const onSlideImplantCaseChange = (swiper: any) => {
  implantCaseCurrent.value = swiper.realIndex + 1
}

let implantCaseCurrentMb = ref(1)
//走马灯事件
const onSlideImplantCaseChangeMb = (swiper: any) => {
  implantCaseCurrentMb.value = swiper.realIndex + 1
}
let implantCaseSwiperRef = {
  slideToLoop: (a) => {},
  slidePrev: () => {},
  slideNext: () => {},
}

const handleLineCur = (_value: number) => {
  implantCaseSwiperRef.slideToLoop(_value - 1)
}

const setImplantCaseSwiperRef = (swiper: any) => {
  implantCaseSwiperRef = swiper
}
const setImplantCaseSwiperRefMb = (swiper: any) => {
  implantCaseSwiperRef = swiper
}
const handleProcessBtn = (_type: string) => {
  implantCaseSwiperRef[_type]()
}

let yaImgCurrtNum = ref(6)
const yaImgFu = (_idx, _type) => {
  if (_type) {
    console.log(_idx, '按住了')
    yaImgCurrtNum.value = _idx
  } else {
    console.log(_idx, '不按了')
    yaImgCurrtNum.value = 6
  }
}

// 植牙6步曲
const implantStepList = [
  {
    id: 1,
    title: '全面口腔檢查',
    img: '	https://statichk.cmermedical.com/ckj/image/c73d9b16c9e4.avif',
  },
  {
    id: 2,
    title: '注射麻醉藥',
    img: 'https://statichk.cmermedical.com/ckj/image/1fa0c1bed6c1.avif',
  },
  {
    id: 3,
    title: '把植體植入顎骨',
    img: 'https://statichk.cmermedical.com/ckj/image/c15bae966799.avif',
  },
  {
    id: 4,
    title: '安裝臨時假牙',
    img: '	https://statichk.cmermedical.com/ckj/image/3895c8fc526e.avif',
  },
  {
    id: 5,
    title: '套上牙冠及微調',
    img: '	https://statichk.cmermedical.com/ckj/image/943073b1e2ce.avif',
  },
  {
    id: 6,
    title: '定期覆診及跟進',
    img: 'https://statichk.cmermedical.com/ckj/image/125ad30de23a.avif',
  },
]

// 植體品牌
const brandList = [
  {
    id: 1,
    title: '瑞士士卓曼BLX',
    img: 'https://static.ckjhk.com/ckj-image/a3c3dd1d9b89.png',
    xjb: 'https://static.ckjhk.com/ckj-image/337cc6af4d75.svg',
    nyd: 'https://static.ckjhk.com/ckj-image/6b8759325963.svg',
    kzh: 'https://static.ckjhk.com/ckj-image/6b8759325963.svg',
  },
  {
    id: 2,
    title: '瑞士士卓曼',
    img: 'https://static.ckjhk.com/ckj-image/4aefa31d905c.png',
    xjb: 'https://static.ckjhk.com/ckj-image/ccd5fcee8b34.svg',
    nyd: 'https://static.ckjhk.com/ckj-image/6b8759325963.svg',
    kzh: 'https://static.ckjhk.com/ckj-image/cef0a6994955.svg',
  },
  {
    id: 3,
    title: '瑞典尼奧斯',
    img: 'https://static.ckjhk.com/ckj-image/7246be98610d.png',
    xjb: 'https://static.ckjhk.com/ckj-image/ccd5fcee8b34.svg',
    nyd: 'https://static.ckjhk.com/ckj-image/6b8759325963.svg',
    kzh: 'https://static.ckjhk.com/ckj-image/cef0a6994955.svg',
  },
  {
    id: 4,
    title: '韓國奧齒泰',
    img: 'https://static.ckjhk.com/ckj-image/730c9574c435.png',
    xjb: 'https://static.ckjhk.com/ckj-image/ccd5fcee8b34.svg',
    nyd: 'https://static.ckjhk.com/ckj-image/cef0a6994955.svg',
    kzh: 'https://static.ckjhk.com/ckj-image/cef0a6994955.svg',
  },
  {
    id: 5,
    title: '美國皓聖',
    img: 'https://static.ckjhk.com/ckj-image/800c5f942ba4.png',
    xjb: 'https://static.ckjhk.com/ckj-image/337cc6af4d75.svg',
    nyd: 'https://static.ckjhk.com/ckj-image/5e8b8a261b54.svg',
    kzh: 'https://static.ckjhk.com/ckj-image/5e8b8a261b54.svg',
  },
  {
    id: 6,
    title: '德國Ankylos',
    img: 'https://static.ckjhk.com/ckj-image/2b1c97492ca5.png',
    xjb: 'https://static.ckjhk.com/ckj-image/ccd5fcee8b34.svg',
    nyd: 'https://static.ckjhk.com/ckj-image/cef0a6994955.svg',
    kzh: 'https://static.ckjhk.com/ckj-image/cef0a6994955.svg',
  },
]

// 常見問題
const problemData = {
  title: 'pages.dental-service.implant.problem.title',
  lists: [
    {
      Q: 'pages.dental-service.implant.problem.lists[0].Q',
      A: 'pages.dental-service.implant.problem.lists[0].A',
    },
    {
      Q: 'pages.dental-service.implant.problem.lists[1].Q',
      A: 'pages.dental-service.implant.problem.lists[1].A',
    },
    {
      Q: 'pages.dental-service.implant.problem.lists[2].Q',
      A: 'pages.dental-service.implant.problem.lists[2].A',
    },
    {
      Q: 'pages.dental-service.implant.problem.lists[3].Q',
      A: 'pages.dental-service.implant.problem.lists[3].A',
    },
    {
      Q: 'pages.dental-service.implant.problem.lists[4].Q',
      A: 'pages.dental-service.implant.problem.lists[4].A',
    },
    {
      Q: 'pages.dental-service.implant.problem.lists[5].Q',
      A: 'pages.dental-service.implant.problem.lists[5].A',
    },
    {
      Q: 'pages.dental-service.implant.problem.lists[6].Q',
      A: 'pages.dental-service.implant.problem.lists[6].A',
    },
    {
      Q: 'pages.dental-service.implant.problem.lists[7].Q',
      A: 'pages.dental-service.implant.problem.lists[7].A',
    },
  ],
}
</script>

<template>
  <div>
    <PageHeader v-if="windowWidth < 768" :headerConfig="headerConfig">
      <template #xxxxxxxxxxx-home>
        <div class="banner-in-box">
          <div class="banner-image">
            <img
              src="https://static.ckjhk.com/ckj-image/ae23253936c1.webp"
              alt=""
              loading="lazy"
            />
          </div>
          <div class="banner-content" style="display: flex">
            <div class="content-title">網上預約限定優惠</div>
            <div class="content-price">
              <div>歐美<br />種植牙</div>
              <div>
                <img src="~/assets/images/2025031216072401.svg" alt="" />
              </div>
            </div>
            <div class="content-subscribe">
              <span>星級客戶</span>
              <span>朱咪咪<i>小姐</i></span>
            </div>
          </div>
        </div>
      </template>
    </PageHeader>
    <PageNewHeaderMenu v-if="windowWidth > 768" :headerConfig="headerConfig" />
    <PagePcBannerNoHome v-if="windowWidth > 768" :headerConfig="headerConfig">
      <template #xxxxxxxxxxx-home>
        <div class="banner-in-box">
          <div class="banner-image">
            <img
              src="https://static.ckjhk.com/ckj-image/ae23253936c1.webp"
              alt=""
              loading="lazy"
            />
          </div>
          <div class="banner-content" style="display: flex">
            <div class="content-title">網上預約限定優惠</div>
            <div class="content-price">
              <div>歐美<br />種植牙</div>
              <div>
                <img src="~/assets/images/2025031216072401.svg" alt="" />
              </div>
            </div>
            <div class="content-subscribe">
              <span>星級客戶</span>
              <span>朱咪咪<i>小姐</i></span>
            </div>
          </div>
        </div>
      </template>
    </PagePcBannerNoHome>
    <!-- 内容区 -->
    <container>
      <section class="container implant-step">
        <div class="implant-title-subheading">\ <i>植牙6步曲</i> /</div>
        <div class="implant-step-context" id="implantStep">
          <div
            class="implant-step-item"
            v-for="(item, index) in implantStepList"
            :key="index"
          >
            <div>{{ item.id }}</div>
            <div>
              <img :src="item.img" :alt="item.title" />
            </div>
            <div>{{ item.title }}</div>
          </div>
        </div>
      </section>
      <section class="container seven-advantages">
        <div class="d-flex flex-row mb-3 align-items-end subheading">
          <span>愛康健種植7大</span><span>優勢</span>
        </div>
        <div class="seven-advantages-content">
          <div>
            <div>
              <div>
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  width="35"
                  height="36"
                  viewBox="0 0 35 36"
                  fill="none"
                >
                  <path
                    d="M34.6618 17.6861C21 19.7159 19.3606 21.3553 17.3309 35.017C15.3011 21.3553 13.6617 19.7159 0 17.6861C13.6617 15.6564 15.3011 14.017 17.3309 0.355225C19.3606 14.017 21 15.6564 34.6618 17.6861Z"
                    fill="#F8298A"
                  />
                </svg>
              </div>
              <div>種植專家方案</div>
            </div>
            <div>
              <div>
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  width="35"
                  height="36"
                  viewBox="0 0 35 36"
                  fill="none"
                >
                  <path
                    d="M34.6618 17.6861C21 19.7159 19.3606 21.3553 17.3309 35.017C15.3011 21.3553 13.6617 19.7159 0 17.6861C13.6617 15.6564 15.3011 14.017 17.3309 0.355225C19.3606 14.017 21 15.6564 34.6618 17.6861Z"
                    fill="#00AEFF"
                  />
                </svg>
              </div>
              <div>個性化定制</div>
            </div>
            <div>
              <div>
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  width="35"
                  height="36"
                  viewBox="0 0 35 36"
                  fill="none"
                >
                  <path
                    d="M34.6618 17.6861C21 19.7159 19.3606 21.3553 17.3309 35.017C15.3011 21.3553 13.6617 19.7159 0 17.6861C13.6617 15.6564 15.3011 14.017 17.3309 0.355225C19.3606 14.017 21 15.6564 34.6618 17.6861Z"
                    fill="#F8298A"
                  />
                </svg>
              </div>
              <div>自選植體</div>
            </div>
          </div>
          <div>
            <div>
              <div>
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  width="35"
                  height="36"
                  viewBox="0 0 35 36"
                  fill="none"
                >
                  <path
                    d="M34.6618 17.6861C21 19.7159 19.3606 21.3553 17.3309 35.017C15.3011 21.3553 13.6617 19.7159 0 17.6861C13.6617 15.6564 15.3011 14.017 17.3309 0.355225C19.3606 14.017 21 15.6564 34.6618 17.6861Z"
                    fill="#00AEFF"
                  />
                </svg>
              </div>
              <div>自選牙冠顏色</div>
            </div>
            <div>
              <div>
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  width="35"
                  height="36"
                  viewBox="0 0 35 36"
                  fill="none"
                >
                  <path
                    d="M34.6618 17.6861C21 19.7159 19.3606 21.3553 17.3309 35.017C15.3011 21.3553 13.6617 19.7159 0 17.6861C13.6617 15.6564 15.3011 14.017 17.3309 0.355225C19.3606 14.017 21 15.6564 34.6618 17.6861Z"
                    fill="#F8298A"
                  />
                </svg>
              </div>
              <div>微創無痛舒適</div>
            </div>
            <div>
              <div>
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  width="35"
                  height="36"
                  viewBox="0 0 35 36"
                  fill="none"
                >
                  <path
                    d="M34.6618 17.6861C21 19.7159 19.3606 21.3553 17.3309 35.017C15.3011 21.3553 13.6617 19.7159 0 17.6861C13.6617 15.6564 15.3011 14.017 17.3309 0.355225C19.3606 14.017 21 15.6564 34.6618 17.6861Z"
                    fill="#00AEFF"
                  />
                </svg>
              </div>
              <div>香港醫療品質</div>
            </div>
            <div>
              <div>
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  width="35"
                  height="36"
                  viewBox="0 0 35 36"
                  fill="none"
                >
                  <path
                    d="M34.6618 17.6861C21 19.7159 19.3606 21.3553 17.3309 35.017C15.3011 21.3553 13.6617 19.7159 0 17.6861C13.6617 15.6564 15.3011 14.017 17.3309 0.355225C19.3606 14.017 21 15.6564 34.6618 17.6861Z"
                    fill="#F8298A"
                  />
                </svg>
              </div>
              <div>一站式售後保障</div>
            </div>
          </div>
        </div>
      </section>
      <section class="container brand-list">
        <div class="d-flex flex-row mb-3 align-items-end subheading">
          <span>植體品牌</span><span>系列</span>
        </div>
        <div class="brand-context" id="brand-context">
          <div
            class="brand-item-list"
            v-for="(item, index) in brandList"
            :key="index"
          >
            <div>
              <img :src="item.img" :alt="item.title" />
            </div>
            <div>{{ item.title }}</div>
            <div>
              <div>
                <div>性價比</div>
                <div>
                  <img :src="item.xjb" alt="性價比" />
                </div>
              </div>
              <div>
                <div>耐用度</div>
                <div>
                  <img :src="item.nyd" alt="耐用度" />
                </div>
              </div>
              <div>
                <div>客製化</div>
                <div>
                  <img :src="item.kzh" alt="客製化" />
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
      <section class="container extra-charge">
        <div class="d-flex flex-row mb-3 align-items-end subheading">
          <span>額外</span><span>項目</span>
        </div>
        <div class="extra-charge-context">
          <div>
            <div>項目</div>
            <div>價錢</div>
          </div>
          <div>
            <div>牙齦移植術</div>
            <div>￥3000</div>
          </div>
          <div>
            <div>3D數碼種植導板</div>
            <div>￥1500/顆</div>
          </div>
          <div>
            <div>上頜竇底提升術</div>
            <div>￥5000起</div>
          </div>
          <div>
            <div>植體取出術</div>
            <div>￥1000/顆</div>
          </div>
          <div>
            <div>植體牙周維護</div>
            <div>￥300/顆</div>
          </div>
          <div>
            <div>馬龍橋種植支架</div>
            <div>￥10000/半口</div>
          </div>
        </div>
      </section>
      <section class="container implant-git">
        <div class="d-flex flex-row mb-3 align-items-end subheading">
          <span>「即刻植牙」</span><span>技術</span>
        </div>
        <div class="implant-git-image">
          <div>
            <img
              src="https://static.cmereye.com/imgs/2024/04/bd2194046affe383.gif"
              alt=""
            />
          </div>
          <div>
            是一種先進技術，在拔除患牙同時，立即將植體放入拔牙窩內，<span
              >可縮短50%的骨癒合時間。</span
            >
          </div>
        </div>
      </section>
      <section class="container technical-category">
        <div class="d-flex flex-row mb-3 align-items-end subheading">
          <span>植牙</span><span>技術及類別</span>
        </div>
        <div class="technical-category-table">
          <div></div>
          <div>微創植牙</div>
          <div>傳統植牙</div>
          <div></div>
          <div>
            <img
              src="https://static.ckjhk.com/ckj-image/2025031717580401.png"
              alt=""
            />
          </div>
          <div>
            <img
              src="https://static.ckjhk.com/ckj-image/2025031717580402.png"
              alt=""
            />
          </div>
          <div>傷口大小</div>
          <div>很小</div>
          <div>較大</div>
          <div>腫脹不適</div>
          <div>很小</div>
          <div>較大</div>
          <div>手術速度</div>
          <div>非常快</div>
          <div>緩慢</div>
          <div>復原速度</div>
          <div>非常快</div>
          <div>緩慢</div>
          <div>特點</div>
          <div>
            <ul>
              <li>透過電腦導航將植牙放到牙骨裡面</li>
              <li>不用開刀縫針，減低感染風險</li>
              <li>補骨需求小</li>
            </ul>
          </div>
          <div>
            以傳統刀切口，需等待數個月植牙組織與人體結合傷口大需縫合，癒合時間較長
          </div>
        </div>
      </section>
      <div
        class="affiliation-title d-flex flex-row mb-3 align-items-end subheading"
      >
        <span>香港上市醫療公司</span><span>管理</span>
      </div>
      <div class="affiliation-bg">
        <section class="container affiliation">
          <div class="affiliation-context">
            <div>
              <img
                src="https://static.ckjhk.com/ckj-image/2025031809094001.png"
                alt=""
              />
            </div>
            <div>
              <p>
                香港醫療制度監督，臨床5年以上牙醫種牙，<span>成功率超過98%</span>。具備龐大經驗實力牙醫專科院長把關，已具備完善一站式售後服務。
              </p>
              <p>
                <img
                  src="https://static.ckjhk.com/ckj-image/2025031809230501.svg"
                  alt=""
                />
              </p>
              <ul>
                <li>
                  <div>
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      width="22"
                      height="23"
                      viewBox="0 0 22 23"
                      fill="none"
                    >
                      <path
                        d="M10.7108 5.75487C10.7108 5.75487 6.7306 5.53346 5.42693 3.90162C4.12326 2.26977 5.38579 1.35681 6.67575 1.57822C7.9657 1.79963 9.53054 2.98897 10.7108 5.75487Z"
                        stroke="#F8298A"
                        stroke-width="2"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                      />
                      <path
                        d="M10.7354 5.75487C10.7354 5.75487 14.9487 5.53346 16.2523 3.90162C17.556 2.26977 16.2935 1.35681 15.0035 1.57822C13.7136 1.79963 11.9156 2.98897 10.7354 5.75487Z"
                        stroke="#F8298A"
                        stroke-width="2"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                      />
                      <path
                        d="M19.2261 9.40967H2.24219V21.5455H19.2261V9.40967Z"
                        stroke="#F8298A"
                        stroke-width="2"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                      />
                      <path
                        d="M20.47 5.76245H1V9.4096H20.47V5.76245Z"
                        stroke="#F8298A"
                        stroke-width="2"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                      />
                      <path
                        d="M10.7354 21.5454V5.75488"
                        stroke="#F8298A"
                        stroke-width="2"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                      />
                    </svg>
                  </div>
                  <div>預約即享免費CT檢查</div>
                </li>
                <li>
                  <div>
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      width="22"
                      height="23"
                      viewBox="0 0 22 23"
                      fill="none"
                    >
                      <path
                        d="M10.7108 5.75487C10.7108 5.75487 6.7306 5.53346 5.42693 3.90162C4.12326 2.26977 5.38579 1.35681 6.67575 1.57822C7.9657 1.79963 9.53054 2.98897 10.7108 5.75487Z"
                        stroke="#F8298A"
                        stroke-width="2"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                      />
                      <path
                        d="M10.7354 5.75487C10.7354 5.75487 14.9487 5.53346 16.2523 3.90162C17.556 2.26977 16.2935 1.35681 15.0035 1.57822C13.7136 1.79963 11.9156 2.98897 10.7354 5.75487Z"
                        stroke="#F8298A"
                        stroke-width="2"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                      />
                      <path
                        d="M19.2261 9.40967H2.24219V21.5455H19.2261V9.40967Z"
                        stroke="#F8298A"
                        stroke-width="2"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                      />
                      <path
                        d="M20.47 5.76245H1V9.4096H20.47V5.76245Z"
                        stroke="#F8298A"
                        stroke-width="2"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                      />
                      <path
                        d="M10.7354 21.5454V5.75488"
                        stroke="#F8298A"
                        stroke-width="2"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                      />
                    </svg>
                  </div>
                  <div>免費拔鬆動牙</div>
                </li>
                <li>
                  <div>
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      width="22"
                      height="23"
                      viewBox="0 0 22 23"
                      fill="none"
                    >
                      <path
                        d="M10.7108 5.75487C10.7108 5.75487 6.7306 5.53346 5.42693 3.90162C4.12326 2.26977 5.38579 1.35681 6.67575 1.57822C7.9657 1.79963 9.53054 2.98897 10.7108 5.75487Z"
                        stroke="#F8298A"
                        stroke-width="2"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                      />
                      <path
                        d="M10.7354 5.75487C10.7354 5.75487 14.9487 5.53346 16.2523 3.90162C17.556 2.26977 16.2935 1.35681 15.0035 1.57822C13.7136 1.79963 11.9156 2.98897 10.7354 5.75487Z"
                        stroke="#F8298A"
                        stroke-width="2"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                      />
                      <path
                        d="M19.2261 9.40967H2.24219V21.5455H19.2261V9.40967Z"
                        stroke="#F8298A"
                        stroke-width="2"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                      />
                      <path
                        d="M20.47 5.76245H1V9.4096H20.47V5.76245Z"
                        stroke="#F8298A"
                        stroke-width="2"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                      />
                      <path
                        d="M10.7354 21.5454V5.75488"
                        stroke="#F8298A"
                        stroke-width="2"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                      />
                    </svg>
                  </div>
                  <div>領取2000元進口種植牙現金券</div>
                </li>
              </ul>
            </div>
          </div>
        </section>
      </div>
    </container>
    <ServiceProblem :problem-data="problemData" />
    <!-- 聯絡我們 -->
    <NewAddress />
    <ContactForm-new2 />
    <PageFooter />
    <!-- <PageNavbar
      :showDialogBox="top < (height / 3) * 2 && bottom > height / 3"
    /> -->
    <PageNewNavbarSide v-if="windowWidth > 768" />
    <PageNavbar v-else />
  </div>
</template>

<style lang="scss" scoped>
@media screen and (min-width: 922px) {
  :deep(.problem) {
    margin-top: 45px;
  }
  .banner-in-box {
    display: block;
    position: absolute;
    top: 50%;
    left: 0;
    transform: translateY(-50%);
    height: 20.83vw;
    width: 55%;
    z-index: 10;
  }
  .banner-image {
    position: absolute;
    z-index: 10;
    width: 9.0625vw;
    height: 9.0625vw;
    top: 8%;
    left: 75%;
    & > img {
      width: 100%;
      height: 100%;
      object-fit: contain;
    }
  }
  .banner-content {
    display: flex;
    flex-direction: column;
    border-radius: 0.694vw 0.694vw 0px 0px;
    background: #fff;
    width: 23.9583vw;
    position: absolute;
    top: 50%;
    left: 60%;
    transform: translate(-50%, -50%);
    .content-title {
      border-radius: 0.694vw 0.694vw 0px 0px;
      background: var(
        --Liner-purple,
        linear-gradient(
          269deg,
          var(--Brand-Color, #fc1682) 10.21%,
          #710d54 122.73%
        )
      );
      box-sizing: border-box;
      padding: 0.859375vw 4.7135vw;
      color: var(--White, #fff);
      text-align: center;
      text-shadow: 0px 0.27vw 0.27vw rgba(0, 0, 0, 0.25);
      font-family: 'Noto Sans HK';
      font-size: 1.665vw;
      font-style: normal;
      font-weight: 700;
      line-height: 1.389vw; /* 83.333% */
      letter-spacing: 0.1354vw;
      z-index: 6;
    }

    .price-style {
      width: 19.0625vw;
      height: 11.145vw;
      & > img {
        width: 100%;
        height: 100%;
        object-fit: contain;
      }
    }
    .content-price {
      display: flex;
      gap: 0 0.52vw;
      min-height: 5.833vw;
      box-sizing: border-box;
      padding: 0.52vw;
      align-items: center;
      font-family: 'Noto Sans HK';
      font-size: 1.7442vw;
      font-style: normal;
      font-weight: 900;
      line-height: 2.2222vw; /* 114.286% */
      letter-spacing: 0.29165vw;
      border-radius: 0px 0px 10px 10px;
      background: var(--White, #fff);
      box-shadow: 0px 4px 4px rgba(77, 77, 77, 0.2);
      & > div:nth-child(1) {
        color: var(--Grey-Dark, #333);
        text-align: right;
        text-shadow: 1.3px 1.333px 1.333px #faeaf2,
          1.33px -1.333px 1.333px #faeaf2, -1.33px 1.333px 1.333px #faeaf2,
          -1.33px -1.333px 1.333px #faeaf2;
        font-family: 'Noto Sans HK';
        font-size: 1.744vw;
        font-style: normal;
        font-weight: 900;
        line-height: 2.2222vw; /* 114.286% */
        letter-spacing: 0.29165vw;
      }
      & > div:nth-child(2) {
        width: 15.2604vw;
        & > svg {
          width: 100%;
          height: 100%;
          object-fit: cover;
        }
      }
    }
    .content-subscribe {
      display: flex;
      flex-direction: column;
      align-items: center;
      width: fit-content;
      position: absolute;
      color: var(--Theme-Color, #fc1682);
      text-align: center;
      font-family: 'FakePearl-Regular';
      font-size: clamp(20px, 2.083vw, 40px);
      font-style: normal;
      font-weight: 400;
      line-height: 100%; /* 64px */
      box-sizing: border-box;
      padding: 0;
      z-index: 7;
      left: auto;
      right: -50%;
      bottom: 10px;
      gap: 7px 0;
      & > span {
        color: var(--Grey-Dark, #333);
        text-align: center;
        font-family: 'Noto Sans HK';
        font-size: 23.077px;
        font-style: normal;
        font-weight: 700;
        line-height: 120%; /* 27.692px */
        letter-spacing: 2.308px;
        i {
          font-style: normal;
        }
      }
      & > span:nth-child(2) {
        border-radius: 28.846px;
        background: var(--New-Theme-Color, #d2337d);
        box-shadow: 0px 0px 11.538px 0px rgba(0, 0, 0, 0.25);
        box-sizing: border-box;
        padding: 5px 14px;
        color: var(--White, #fff);
        font-family: 'Noto Sans HK';
        font-size: 25.962px;
        font-style: normal;
        font-weight: 700;
        line-height: normal;
        letter-spacing: 2.596px;
        i {
          color: var(--White, #fff);
          font-family: 'Noto Sans HK';
          font-size: 23.077px;
          font-style: normal;
          font-weight: 400;
          line-height: 34.615px;
          letter-spacing: 2.308px;
        }
      }
    }
  }

  .container {
    max-width: 960px !important;
    margin: 0 auto;
  }

  .banner {
    background: url(https://static.ckjhk.com/ckj-image/0ce172efab96.webp)
      no-repeat;
    background-size: cover;
    height: 20.833vw;
    width: 100%;
    margin-top: 70px;
    position: relative;
  }

  .banner-context {
    position: relative;
    width: 60%;
    height: 100%;
    // margin-top: 5vw;
    display: flex;
    align-items: center;
    justify-content: flex-end;

    .banner-image {
      position: absolute;
      width: 10.9375vw;
      height: 10.9375vw;
      top: 0.3625vw;
      right: 7vw;

      & > img {
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
      overflow: hidden;
      border-radius: 13.333px;
      width: 23.9583vw;
      height: 8.9533vw;
      background: #fff;
      margin-right: 14vw;
      box-shadow: 0px 5.333px 5.333px rgba(77, 77, 77, 0.2);

      .content-title {
        background: var(
          --Liner-purple,
          linear-gradient(
            269deg,
            var(--Brand-Color, #fc1682) 10.21%,
            #710d54 122.73%
          )
        );
        color: var(--White, #fff);
        text-align: center;
        text-shadow: 0px 5.333px 5.333px rgba(0, 0, 0, 0.25);
        font-family: 'Noto Sans HK';
        font-size: 1.665vw;
        font-style: normal;
        font-weight: 700;
        line-height: 1.388vw;
        letter-spacing: 3.2px;
        box-sizing: border-box;
        padding: 0.8645vw 0;
        width: 100%;
        min-height: 3.1353125vw;
      }

      .content-price {
        display: flex;
        gap: 0 0.52vw;
        align-items: center;
        box-sizing: border-box;
        padding: 0.52vw;

        & > div:nth-child(1) {
          color: var(--Grey-Dark, #333);
          font-size: 1.744vw;
          text-align: right;
          text-shadow: 1.3px 1.333px 1.333px #faeaf2,
            1.33px -1.333px 1.333px #faeaf2, -1.33px 1.333px 1.333px #faeaf2,
            -1.33px -1.333px 1.333px #faeaf2;
        }

        & > div:nth-child(2) {
          width: 15.2604vw;

          & > img {
            width: 100%;
            height: auto;
            object-fit: cover;
          }
        }
      }

      .content-subscribe {
        position: absolute;
        display: flex;
        align-items: center;
        flex-direction: column;
        justify-content: center;
        right: 2vw;
        top: 40%;
        gap: 0.364vw 0;

        & > span:nth-child(1) {
          color: var(--Grey-Dark, #333);
          text-align: center;
          font-family: 'Noto Sans HK';
          font-size: 23.077px;
          font-style: normal;
          font-weight: 700;
          line-height: 120%;
          /* 27.692px */
          letter-spacing: 2.308px;
        }

        & > span:nth-child(2) {
          border-radius: 28.846px;
          background: var(--Brand-Color, #f8298a);
          box-shadow: 0px 0px 11.538px 0px rgba(0, 0, 0, 0.25);
          color: var(--White, #fff);
          font-family: 'Noto Sans HK';
          font-size: 25.962px;
          font-style: normal;
          font-weight: 700;
          line-height: normal;
          letter-spacing: 2.596px;

          & > i {
            color: var(--White, #fff);
            font-family: 'Noto Sans HK';
            font-size: 23.077px;
            font-style: normal;
            font-weight: 400;
            line-height: 34.615px;
            letter-spacing: 2.308px;
          }

          box-sizing: border-box;
          padding: 0.3125vw 0.729165vw;
        }
      }
    }
  }

  .implant-step {
    margin-top: 45px;
    margin-bottom: 45px;

    .implant-step-context {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 1.823vw 1.5625vw;
      box-sizing: border-box;
      padding: 30px 0;
    }

    .implant-step-item {
      display: flex;
      flex-direction: column;
      align-items: center;
      position: relative;

      & > div:nth-child(1) {
        background: url(https://static.cmereye.com/imgs/2024/11/3b0a5e9326c68638.png)
          no-repeat;
        background-size: cover;
        width: 3.4375vw;
        height: 3.4375vw;
        display: flex;
        align-items: center;
        justify-content: center;
        color: var(--White, #fff);
        font-family: 'Noto Sans HK';
        font-size: 1.771vw;
        font-style: normal;
        font-weight: 700;
        line-height: normal;
        letter-spacing: 3.4px;
        position: absolute;
        top: -0.49vw;
        left: -0.49vw;
        z-index: 5;
      }

      & > div:nth-child(2) {
        & > img {
          width: 100%;
          height: 100%;
          object-fit: cover;
        }
      }

      & > div:nth-child(3) {
        margin-top: 0.52vw;
        width: 100%;
        color: var(--Grey-Dark, #333);
        font-family: 'Noto Sans HK';
        font-size: 20px;
        font-style: normal;
        font-weight: 400;
        line-height: 160%;
        /* 32px */
        letter-spacing: 4px;
      }
    }
  }

  .implant-title-subheading {
    & > i {
      color: var(--Brand-Color, #f8298a);

      /* 桌面版/PC-H2 */
      font-family: 'Noto Sans HK';
      font-size: 30px;
      font-style: normal;
      font-weight: 700;
      line-height: normal;
      letter-spacing: 3px;
    }

    color: var(--Grey-Deep, #4d4d4d);
    text-align: center;

    /* 桌面版/PC-H2 */
    font-family: 'Noto Sans HK';
    font-size: 30px;
    font-style: normal;
    font-weight: 700;
    line-height: normal;
    letter-spacing: 3px;
  }

  .seven-advantages-content {
    display: flex;
    flex-direction: column;

    & > div {
      width: 100%;

      & > div {
        display: flex;
        align-items: center;
        gap: 0 10px;

        & > div:nth-child(2) {
          color: var(--Grey-Dark, #333);
          font-family: 'Noto Sans HK';
          font-size: 24.113px;
          font-style: normal;
          font-weight: 500;
          line-height: 60.281px;
          letter-spacing: 2.411px;
        }
      }
    }

    & > div:nth-child(1) {
      display: flex;
      flex-direction: column;
      align-items: flex-start;

      & > div:nth-child(2) {
        margin-left: 20px;
      }

      & > div:nth-child(3) {
        margin-left: 48px;
      }
    }

    & > div:nth-child(2) {
      display: flex;
      flex-direction: column;
      align-items: flex-end;

      & > div:nth-child(2) {
        margin-right: 30px;
      }

      & > div:nth-child(3) {
        margin-right: 64px;
      }

      & > div:nth-child(4) {
        margin-right: 80px;
      }
    }

    background: url('https://static.ckjhk.com/ckj-image/2025031715453001.png')
      no-repeat;
    background-size: cover;
    width: 30.972vw;
    height: 21.85vw;
    background-position: center;
    margin: 0 auto;
    justify-content: center;
    background-position-x: -2vw;
  }

  .brand-list {
    margin: 45px auto;
  }

  .brand-context {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px 40px;
  }

  .brand-item-list {
    display: flex;
    flex-direction: column;
    align-items: center;

    & > div:nth-child(2) {
      color: var(--White, #fff);
      text-align: center;

      /* 桌面版/PC-H3 */
      font-family: 'Noto Sans HK';
      font-size: 24px;
      font-style: normal;
      font-weight: 700;
      line-height: normal;
      letter-spacing: 2.4px;
      border-radius: 40px;
      background: var(--Brand-Color, #f8298a);
      box-sizing: border-box;
      padding: 6px 40px;
      margin: 5px auto 10px;
    }

    & > div:nth-child(3) {
      display: flex;
      flex-direction: column;

      & > div {
        display: flex;
        align-items: center;
        gap: 0 20px;

        & > div:nth-child(1) {
          color: var(--Grey-Dark, #333);
          font-family: 'Noto Sans HK';
          font-size: 24px;
          font-style: normal;
          font-weight: 700;
          line-height: normal;
          letter-spacing: 2.4px;
        }
      }

      & > div:nth-child(1) {
        & > div:nth-child(1) {
          color: #01a853;
        }
      }
    }
  }

  .extra-charge-context {
    border-radius: 5px;
    margin: 20px auto 0;
    overflow: hidden;

    & > div {
      box-sizing: border-box;
      padding: 18px 35px;
      display: flex;
      justify-content: space-between;

      & > div:nth-child(1) {
        color: var(--Grey-Dark, #333);
        font-family: 'Noto Sans HK';
        font-size: 24px;
        font-style: normal;
        font-weight: 700;
        line-height: normal;
        letter-spacing: 2.4px;
      }

      & > div:nth-child(2) {
        color: var(--Brand-Color, #f8298a);
        text-align: right;
        font-family: 'Noto Sans HK';
        font-size: 24px;
        font-style: normal;
        font-weight: 700;
        line-height: normal;
        letter-spacing: 2.4px;
      }
    }

    & > div:first-child {
      background: var(--Brand-Color, #f8298a);

      & > div {
        color: #fff;
      }
    }

    & > div:nth-child(odd):not(:first-child) {
      background-color: #fff7f8;
    }

    & > div:nth-child(even):not(:first-child) {
      background-color: #fff;
    }
  }

  .implant-git {
    margin: 45px auto;
  }

  .implant-git-image {
    & > div:nth-child(1) {
      max-width: 552px;
      width: 100%;
      margin: 0 auto;
    }

    & > div:nth-child(2) {
      color: var(--Grey-Mid, #666);
      text-align: center;
      font-family: 'Noto Sans HK';
      font-size: 18px;
      font-style: normal;
      font-weight: 400;
      line-height: 200%;
      letter-spacing: 1.8px;

      span {
        color: var(--Brand-Color, #f8298a);
        font-family: 'Noto Sans HK';
        font-size: 18px;
        font-style: normal;
        font-weight: 400;
        line-height: 200%;
        letter-spacing: 1.8px;
      }
    }
  }

  .technical-category-table {
    display: grid;
    grid-template-columns: repeat(3, 1fr);

    & > div {
      color: var(--Grey-Deep, #4d4d4d);
      text-align: center;
      font-family: 'Noto Sans HK';
      font-size: 18px;
      font-style: normal;
      font-weight: 400;
      line-height: 200%;
      /* 36px */
      letter-spacing: 1.8px;
      display: flex;
      align-items: center;
      justify-content: center;
      border: 1px solid var(--Grey-Lightest, #f2f2f2);
      background: var(--White, #fff);

      & > ul {
        display: flex;
        flex-direction: column;
        align-items: flex-start;

        li {
          list-style: revert-layer;
        }
      }
    }

    & > div:nth-child(2),
    & > div:nth-child(3) {
      border-radius: 10px 10px 0px 0px;
      border-top: 3px solid var(--Brand-Color, #f8298a);
      color: var(--White, #fff);
      text-align: center;
      font-family: 'Noto Sans HK';
      font-size: 24px;
      font-style: normal;
      font-weight: 700;
      line-height: normal;
      letter-spacing: 2.4px;
      box-sizing: border-box;
      padding: 10px 0;
      background: #f8298a;
      width: 400px;
      border-top: none !important;
      border-bottom: none !important;
    }

    & > div:nth-child(3) {
      border-radius: 10px 10px 0px 0px;
      background: var(--Blue-Deep, #00aeff);
      border-top: 3px solid var(--Blue-Deep, #00aeff);
    }

    & > div:nth-child(20) {
      border-bottom: 3px solid var(--Brand-Color, #f8298a);
    }

    & > div:nth-child(3n + 2) {
      border-left: 3px solid var(--Brand-Color, #f8298a);
      border-right: 3px solid var(--Brand-Color, #f8298a);
    }

    & > div:nth-child(3n + 1) {
      max-width: 160px;
      background: #f8298a;
      color: var(--White, #fff);
      text-align: center;
      font-family: 'Noto Sans HK';
      font-size: 18px;
      font-style: normal;
      font-weight: 700;
      line-height: 200%;
      /* 36px */
      letter-spacing: 1.8px;
      box-sizing: border-box;
      padding: 10px 20px;
      display: flex;
      align-items: center;
      justify-content: center;
      border: none;
    }

    & > div:nth-child(19) {
      border-radius: 0px 0px 0 10px;
    }

    & > div:nth-child(21) {
      box-sizing: border-box;
      padding: 10px 20px;
    }

    & > div:nth-child(1),
    & > div:nth-child(4) {
      background: #fff !important;
    }

    & > div:nth-child(5),
    & > div:nth-child(6) {
      border-top: none !important;
      border-bottom: none !important;
    }
  }

  .affiliation-title {
    margin-top: 45px !important;
  }

  .affiliation-bg {
    background: linear-gradient(
      189deg,
      rgba(255, 255, 255, 0) 0.34%,
      var(--Pink-Pale, #ffe9ec) 113.4%
    );

    margin: 45px auto;

    .affiliation {
      max-width: 960px;
      margin: 0 auto;
    }

    .affiliation-context {
      display: flex;
      margin: 20px 0 0;
      justify-content: center;
      align-items: center;
      gap: 0 1.77vw;

      & > div:nth-child(1) {
        min-width: 28.02vw;
        height: 18.4375vw;
        max-width: 553px;

        & > img {
          width: 100%;
          height: 100%;
          object-fit: cover;
        }
      }

      & > div:nth-child(2) {
        display: flex;
        flex-direction: column;
        max-width: 25.53vw;

        & > p:nth-child(1) {
          color: var(--Grey-Mid, #666);
          text-align: justify;
          font-family: 'Noto Sans HK';
          font-size: 1.046vw;
          font-style: normal;
          font-weight: 400;
          line-height: 160%;
          letter-spacing: 4px;

          & > span {
            color: var(--Brand-Color, #f8298a);
            font-family: 'Noto Sans HK';
            font-size: 1.046vw;
            font-style: normal;
            font-weight: 700;
            line-height: 160%;
            letter-spacing: 4px;
          }
        }

        & > p:nth-child(2) {
          margin: 1.5625vw 0;
          width: 13.75vw;
          height: 1.875vw;

          & > svg {
            width: 100%;
            height: 100%;
            object-fit: cover;
          }
        }

        & > ul {
          padding-left: 0;
          li {
            display: flex;
            align-items: center;
            gap: 0.26vw 0.44vw;
            color: var(--Grey-Dark, #333);

            /* 桌面版/PC-頂部目錄 */
            font-family: 'Noto Sans TC';
            font-size: 1.046vw;
            font-style: normal;
            font-weight: 700;
            line-height: 160%;
            /* 32px */
            letter-spacing: 2px;
          }
        }
      }
    }
  }

  .subheading {
    box-sizing: border-box;
    width: fit-content;
    margin: 0 auto;
    padding: 0 10px;
    position: relative;
    background: #fff;

    span {
      position: relative;
      z-index: 10;
      color: var(--Grey-Dark, #333);

      /* 桌面版/PC-H3 */
      font-family: 'Noto Sans HK';
      font-size: 24px;
      font-style: normal;
      font-weight: 700;
      line-height: normal;
      letter-spacing: 2.4px;
    }

    span:not(:last-child) {
      color: var(--New-Theme-Color, #d2337d);

      /* 桌面版/PC-H2 */
      font-family: 'Noto Sans HK';
      font-size: 30px;
      font-style: normal;
      font-weight: 700;
      line-height: normal;
      letter-spacing: 3px;
    }
  }

  .subheading::after {
    content: '';
    position: absolute;
    top: 50%;
    left: 50%;
    width: 180%;
    height: 2px;
    background: var(--Pink-Pale, #ffe9ec);
    transform: translate(-50%, -50%);
    z-index: -1;
  }
}

@media screen and (max-width: 922px) {
  .banner {
    margin-top: 17.065vw;
    background: url('https://static.ckjhk.com/ckj-image/2025031810002701.png')
      no-repeat;
    width: 100vw;
    height: 100vw;
    background-size: cover;

    .banner-context {
      display: flex;
      flex-direction: column;
      align-items: center;
      width: 100%;
      height: 100%;
      justify-content: flex-end;
      position: relative;

      .banner-content {
        border-radius: 10px;
        background: #fff;
        overflow: hidden;
        max-width: 86.665vw;
        margin: 0 auto 4vw;

        .content-title {
          color: var(--White, #fff);
          text-align: center;
          text-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
          font-family: 'Noto Sans HK';
          font-size: 24px;
          font-style: normal;
          font-weight: 700;
          line-height: 20px;
          /* 83.333% */
          letter-spacing: 2.4px;
          box-sizing: border-box;
          padding: 12px 0;
          background: var(
            --Liner-purple,
            linear-gradient(
              269deg,
              var(--Brand-Color, #fc1682) 10.21%,
              #710d54 122.73%
            )
          );
        }

        .content-price {
          display: flex;
          gap: 0 2.13vw;
          align-items: center;
          box-sizing: border-box;
          padding: 2.65vw;

          & > div:nth-child(1) {
            color: var(--Grey-Dark, #333);
            text-align: right;
            font-family: 'Noto Sans HK';
            font-style: normal;
            font-weight: 900;
            line-height: 8.53vw;
            letter-spacing: 4.2px;
            color: var(--Grey-Dark, #333);
            font-size: 7.465vw;
            text-align: right;
            text-shadow: 1.3px 1.333px 1.333px #faeaf2,
              1.33px -1.333px 1.333px #faeaf2, -1.33px 1.333px 1.333px #faeaf2,
              -1.33px -1.333px 1.333px #faeaf2;
          }

          & > div:nth-child(2) {
            width: 50.665vw;
            height: 11.065vw;

            & > img {
              width: 100%;
              height: 100%;
              object-fit: cover;
            }
          }
        }
      }

      .banner-image {
        display: none;
        opacity: 0;
      }

      .content-subscribe {
        position: absolute;
        display: flex;
        flex-direction: column;
        align-items: center;
        top: 45vw;
        left: 12vw;

        & > span:nth-child(1) {
          color: var(--Grey-Dark, #333);
          text-align: center;
          font-family: 'Noto Sans HK';
          font-size: 16px;
          font-style: normal;
          font-weight: 700;
          line-height: 120%;
          /* 19.2px */
          letter-spacing: 1.6px;
        }

        & > span:nth-child(2) {
          border-radius: 20px;
          background: var(--Brand-Color, #f8298a);

          /* 圍邊陰影 */
          box-shadow: 0px 0px 8px 0px rgba(0, 0, 0, 0.25);
          box-sizing: border-box;
          padding: 1.065vw 2.65vw;
          color: var(--White, #fff);
          font-family: 'Noto Sans HK';
          font-size: 18px;
          font-style: normal;
          font-weight: 700;
          line-height: normal;
          letter-spacing: 1.8px;

          & > i {
            color: var(--White, #fff);
            font-family: 'Noto Sans HK';
            font-size: 16px;
            font-style: normal;
            font-weight: 400;
            line-height: 24px;
            letter-spacing: 1.6px;
          }
        }
      }
    }
  }

  .implant-step {
    margin-top: 28px;
    display: flex;
    flex-direction: column;

    .implant-title-subheading {
      margin-bottom: 5.865vw;

      & > i {
        color: var(--Brand-Color, #f8298a);
        font-family: 'Noto Sans HK';
        font-size: 18px;
        font-style: normal;
        font-weight: 700;
        line-height: normal;
        letter-spacing: 1.8px;
      }

      color: var(--Grey-Mid, #666);
      text-align: center;
      font-family: 'Noto Sans HK';
      font-size: 18px;
      font-style: normal;
      font-weight: 700;
      line-height: normal;
      letter-spacing: 1.8px;
    }

    .implant-step-context {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 7.2vw 4.8vw;

      .implant-step-item {
        position: relative;

        & > div:nth-child(1) {
          position: absolute;
          z-index: 5;
          top: -1.06vw;
          left: -1.06vw;
          color: var(--White, #fff);
          font-family: 'Noto Sans HK';
          font-size: 18px;
          font-style: normal;
          font-weight: 700;
          line-height: normal;
          letter-spacing: 1.8px;
          background: url(https://static.cmereye.com/imgs/2024/11/3b0a5e9326c68638.png)
            no-repeat;
          background-size: cover;
          width: 8vw;
          height: 8vw;
          display: flex;
          align-items: center;
          justify-content: center;
        }

        & > div:nth-child(3) {
          color: var(--Grey-Dark, #333);
          /* 手機版/MB-Small Text */
          font-family: 'Noto Sans HK';
          font-size: 14px;
          font-style: normal;
          font-weight: 350;
          line-height: 120%;
          margin-top: 0.1vw;
        }
      }
    }
  }

  .seven-advantages {
    margin-top: 6.983vw;

    .subheading {
      position: relative;
    }

    .subheading::after {
      content: 'Superiorities';
      position: absolute;
      color: var(--Grey-Light, #e6e6e6);
      font-family: 'Noto Sans HK';
      font-size: 16px;
      font-style: normal;
      font-weight: 500;
      line-height: 150%;
      top: 50%;
      transform: translateY(-50%);
      left: 65%;
    }

    .seven-advantages-content {
      background: url(https://static.ckjhk.com/ckj-image/2025031810575101.png)
        no-repeat;
      background-size: cover;
      background-position-x: -14vw;
      width: 100%;
      height: 100vw;
      display: flex;
      flex-direction: column;
      box-sizing: border-box;
      padding: 2.65vw 2.65vw 2.65vw 0;

      & > div {
        width: 100%;

        & > div {
          display: flex;
          align-items: center;
          gap: 0 1.6vw;

          & > div:nth-child(2) {
            color: var(--Grey-Dark, #333);
            font-family: 'Noto Sans HK';
            font-size: 16px;
            font-style: normal;
            font-weight: 500;
            line-height: 40px;
            letter-spacing: 1.6px;
          }
        }
      }

      & > div:nth-child(1) {
        display: flex;
        flex-direction: column;
        align-items: flex-end;
        width: fit-content;
      }

      & > div:nth-child(2) {
        display: flex;
        flex-direction: column;
        align-items: flex-end;

        & > div:nth-child(2) {
          margin-right: 5.86vw;
        }

        & > div:nth-child(3) {
          margin-right: 11.2vw;
        }

        & > div:nth-child(4) {
          margin-right: 14.2vw;
        }
      }
    }
  }

  .brand-list {
    margin-top: 9.33vw;

    .subheading {
      position: relative;
    }

    .subheading::after {
      content: 'Brand';
      color: var(--Grey-Light, #e6e6e6);
      font-family: 'Noto Sans HK';
      font-size: 16px;
      font-style: normal;
      font-weight: 500;
      line-height: 150%;
      position: absolute;
      top: 50%;
      transform: translateY(-50%);
      left: 45%;
    }

    .brand-context {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 4vw 6.4vw;

      .brand-item-list {
        display: flex;
        flex-direction: column;
        align-items: center;

        & > div:nth-child(2) {
          color: var(--White, #fff);
          font-family: 'Noto Sans HK';
          font-size: 4.265vw;
          font-style: normal;
          font-weight: 700;
          line-height: normal;
          letter-spacing: 0.4265vw;
          box-sizing: border-box;
          padding: 0.53vw 5.33vw;
          border-radius: 20px;
          background: var(--Brand-Color, #f8298a);
          margin-bottom: 1.865vw;
        }

        & > div:nth-child(3) {
          display: flex;
          flex-direction: column;

          & > div {
            display: flex;
            gap: 0 1.865vw;

            & > div:nth-child(2) {
              width: 22.4vw;
              height: 4.265vw;

              & > svg {
                width: 100%;
                height: 100%;
                object-fit: cover;
              }
            }
          }
        }
      }
    }
  }

  .extra-charge {
    margin-top: 6.665vw;

    .extra-charge-context {
      background: var(--White, #fff);
      border-radius: 10px;
      box-shadow: 0px 4px 4px 0px rgba(77, 77, 77, 0.2);
      overflow: hidden;

      & > div {
        display: flex;
        justify-content: space-between;
        box-sizing: border-box;
        padding: 2.65vw 8.8vw;

        & > div:nth-child(1) {
          color: var(--Grey-Dark, #333);
          font-family: 'Noto Sans HK';
          font-size: 16px;
          font-style: normal;
          font-weight: 700;
          line-height: normal;
          letter-spacing: 1.6px;
        }

        & > div:nth-child(2) {
          color: var(--Brand-Color, #f8298a);
          text-align: right;
          font-family: 'Noto Sans HK';
          font-size: 16px;
          font-style: normal;
          font-weight: 700;
          line-height: normal;
          letter-spacing: 0.8px;
        }
      }

      & > div:nth-child(1) {
        background: var(--Brand-Color, #f8298a);

        & > div {
          color: #fff;
        }
      }

      & > div:nth-child(odd):not(:first-child) {
        background-color: #fff7f8;
      }

      & > div:nth-child(even):not(:first-child) {
        background-color: #fff;
      }
    }
  }

  .implant-git {
    margin-top: 8.53vw;

    .implant-git-image {
      & > div:nth-child(1) {
        display: flex;
        align-items: center;
        justify-content: center;
        width: 46.13vw;
        height: 46.13vw;
        margin: 5.33vw auto;
      }

      & > div:nth-child(2) {
        box-sizing: border-box;
        padding: 0 2.65vw;
        color: var(--Grey-Mid, #666);
        text-align: justify;
        font-family: 'Noto Sans HK';
        font-size: 14px;
        font-style: normal;
        font-weight: 400;
        line-height: 150%;

        /* 21px */
        & > span {
          color: var(--Brand-Color, #f8298a);
          font-family: 'Noto Sans HK';
          font-size: 14px;
          font-style: normal;
          font-weight: 700;
          line-height: 150%;
        }
      }
    }
  }

  .technical-category {
    margin-top: 8.53vw;

    .subheading {
      position: relative;
    }

    .subheading::after {
      content: 'Types';
      color: var(--Grey-Light, #e6e6e6);
      font-family: 'Noto Sans HK';
      font-size: 16px;
      font-style: normal;
      font-weight: 500;
      line-height: 150%;
      letter-spacing: 1.6px;
      position: absolute;
      top: 50%;
      transform: translateY(-50%);
      left: 50%;
    }

    .technical-category-table {
      display: grid;
      grid-template-columns: repeat(3, 1fr);

      & > div:nth-child(3n + 1) {
        max-width: 18.6vw;
        background: var(--Theme-Color, #fc1682);
        box-sizing: border-box;
        padding: 2.13vw 0;
        color: var(--White, #fff);
        text-align: center;
        font-family: 'Noto Sans HK';
        font-size: 3.2vw;
        font-style: normal;
        font-weight: 500;
        line-height: 120%;
        display: flex;
        align-items: center;
        justify-content: center;
      }

      & > div:nth-child(1),
      & > div:nth-child(4) {
        background: transparent !important;
      }

      & > div:nth-child(3n + 2) {
        width: 37.465vw;
        border-right: 4px solid var(--Brand-Color, #f8298a);
        border-left: 4px solid var(--Brand-Color, #f8298a);
        display: flex;
        align-items: center;
        justify-content: center;
        border-top: 1px solid var(--Skin, #fff1f0);
        border-bottom: 1px solid var(--Skin, #fff1f0);
        color: var(--Grey-Deep, #4d4d4d);
        font-family: 'Noto Sans HK';
        font-size: 3.2vw;
        font-style: normal;
        font-weight: 350;
        line-height: 150%;
      }

      & > div:nth-child(3n + 3) {
        width: 37.465vw;
        display: flex;
        align-items: center;
        justify-content: center;
        border-top: 1px solid var(--Skin, #fff1f0);
        border-bottom: 1px solid var(--Skin, #fff1f0);
        color: var(--Grey-Deep, #4d4d4d);
        font-family: 'Noto Sans HK';
        font-size: 3.2vw;
        font-style: normal;
        font-weight: 350;
        line-height: 150%;
      }

      & > div:nth-child(20) {
        border-bottom: 4px solid var(--Brand-Color, #f8298a);
        box-sizing: border-box;
        padding: 2.66vw 0.6vw 2.66vw 6.66vw;

        ul > li {
          color: var(--Grey-Deep, #4d4d4d);
          font-family: 'Noto Sans HK';
          font-size: 3.2vw;
          font-style: normal;
          font-weight: 350;
          line-height: 150%;
          list-style: disc;
        }
      }

      & > div:nth-child(21) {
        padding: 2.66vw;
      }

      & > div:nth-child(2),
      & > div:nth-child(3) {
        border-radius: 10px 10px 0px 0px;
        background: var(--Theme-Color, #fc1682);
        box-sizing: border-box;
        padding: 1.3vw 0;
        color: var(--White, #fff);
        text-align: center;
        font-family: 'Noto Sans HK';
        font-size: 4.265vw;
        font-style: normal;
        font-weight: 700;
        line-height: normal;
        letter-spacing: 0.4265vw;
      }

      & > div:nth-child(3) {
        background: var(--Blue-Deep, #00aeff);
      }

      & > div:nth-child(7) {
        border-radius: 10px 0px 0px 0px;
        background: var(--Brand-Color, #f8298a);
      }

      & > div:nth-child(2),
      & > div:nth-child(3),
      & > div:nth-child(5),
      & > div:nth-child(6) {
        border: 0px !important;
      }
    }
  }

  .affiliation-title {
    margin-top: 8.53vw;
    margin-left: 3.2vw;
  }

  .affiliation-bg {
    .affiliation {
      padding: 0;

      .affiliation-context {
        & > div:nth-child(2) {
          display: flex;
          flex-direction: column;
          margin-top: 3.2vw;
          background: linear-gradient(
            180deg,
            rgba(255, 255, 255, 0) 53.61%,
            var(--Pink-Pale, #ffe9ec) 101.8%
          );
          align-items: center;
          padding-bottom: 4.26vw;

          & > p:nth-child(1) {
            box-sizing: border-box;
            padding: 0 8vw;
            color: var(--Grey-Mid, #666);
            text-align: justify;
            font-family: 'Noto Sans HK';
            font-size: 3.2vw;
            font-style: normal;
            font-weight: 400;
            line-height: 150%;

            & > span {
              color: var(--Brand-Color, #f8298a);
              font-family: 'Noto Sans HK';
              font-size: 3.2vw;
              font-style: normal;
              font-weight: 700;
              line-height: 150%;
            }
          }

          & > p:nth-child(2) {
            box-sizing: border-box;
            margin: 1.865vw 0;
            width: 43.413vw;
            height: 5.96vw;

            & > img {
              width: 100%;
              height: 100%;
              object-fit: cover;
            }
          }

          ul {
            display: flex;
            flex-direction: column;
            gap: 2.65vw 0;

            li {
              display: flex;
              gap: 0 1.73vw;
              align-items: center;
              color: var(--Grey-Dark, #333);
              font-family: 'Noto Sans HK';
              font-size: 3.73vw;
              font-style: normal;
              font-weight: 500;
              line-height: 6.4vw;
              /* 171.429% */
              letter-spacing: 0.37vw;
            }
          }
        }
      }
    }
  }

  .subheading {
    box-sizing: border-box;
    padding-left: 12px;
    border-left: 2px solid var(--Pink-Pale, #ffe9ec);

    span {
      color: var(--Grey-Dark, #333);
      font-family: 'Noto Sans HK';
      font-size: 18px;
      font-style: normal;
      font-weight: 500;
      line-height: 170%;
      letter-spacing: 1.8px;
    }

    span:not(:last-child) {
      color: var(--New-Theme-Color, #d2337d);
      font-family: 'Noto Sans HK';
      font-size: 21px;
      font-style: normal;
      font-weight: 700;
      line-height: 150%;
      /* 31.5px */
      letter-spacing: 2.1px;
    }
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
    & > img {
      width: 100%;
      height: 100%;
      object-fit: contain;
    }
  }
  .banner-content {
    position: relative;
    align-items: flex-start;
    justify-content: flex-end;
    width: 86.665vw;
    left: 50%;
    top: auto;
    bottom: -65%;
    border-radius: 10px;
    transform: translate(-50%, 0%);
    .content-title {
      color: var(--White, #fff);
      text-align: right;
      font-size: 40px;
      font-style: normal;
      font-weight: 600;
      line-height: 100%; /* 72px */
      letter-spacing: 2.7px;
      position: relative;
      z-index: 6;
      bottom: 0;
      width: 100%;
      border-radius: 10px 10px 0px 0px;
      background: var(
        --Liner-purple,
        linear-gradient(
          269deg,
          var(--Brand-Color, #fc1682) 10.21%,
          #710d54 122.73%
        )
      );
      padding: 16.5px 0;
      color: var(--White, #fff);
      text-align: center;
      text-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
      font-family: 'Noto Sans HK';
      font-size: 24px;
      font-style: normal;
      font-weight: 700;
      line-height: 20px; /* 83.333% */
      letter-spacing: 2.4px;
    }
    .content-price {
      min-height: 22.665vw;
      gap: 0 8px;
      padding: 2.65vw;
      border-radius: 0px 0px 10px 10px;
      background: var(--White, #fff);
      box-shadow: 0px 4px 4px rgba(77, 77, 77, 0.2);
      & > div:nth-child(1) {
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
      }

      & > div:nth-child(2) {
        width: 58.665vw;
        height: 13.0665vw;
        & > svg {
          width: 100%;
          height: 100%;
          object-fit: cover;
        }
      }
    }
    .price-style {
      width: 153px;
      height: 90px;
      & > img {
        width: 100%;
        height: 100%;
        object-fit: cover;
      }
    }
    .content-subscribe {
      left: 0;
      top: -60%;
      right: auto;
      bottom: auto;
      position: absolute;
      z-index: 10;
      box-sizing: border-box;
      color: var(--Grey-Dark, #333);
      text-align: center;
      font-family: 'Noto Sans HK';
      font-size: 16px;
      font-style: normal;
      font-weight: 700;
      line-height: 120%; /* 19.2px */
      letter-spacing: 1.6px;
      gap: 5px 0;
      padding: 4px 10px;
      & > span:nth-child(2) {
        color: var(--White, #fff);
        font-family: 'Noto Sans HK';
        font-size: 18px;
        font-style: normal;
        font-weight: 700;
        line-height: normal;
        letter-spacing: 1.8px;
        & > i {
          font-size: 16px;
          line-height: 24px;
          letter-spacing: 1.6px;
        }
      }
    }
  }
}
</style>