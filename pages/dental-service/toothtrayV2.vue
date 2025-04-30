<script lang="ts" setup>
import { Swiper, SwiperSlide } from 'swiper/vue'
import { Autoplay, Navigation, Pagination } from 'swiper'
import { useAppState } from '~/stores/appState'
import type { CollapseModelValue } from 'element-plus'
import { Scrollbar } from 'swiper'
const appState = useAppState()
appState.setDentistryService('toothtray')
useHead({
  title: '牙托假牙',
  meta: [
    {
      hid: 'description',
      name: 'description',
      content:
        '愛康健提供牙托訂製服務。牙托即活動式假牙，分為局部及全口牙托兩種，可改善缺牙的影響,香港熱線: 6933 8128免費預約掛號,羅湖福田深圳灣口岸分店',
    },
    {
      hid: 'Keywords',
      name: 'Keywords',
      content:
        '愛康健 爱康健 CKJ aikangjian 牙科服務 內地牙科 深圳牙科 深圳愛康健口腔醫院 愛康健齒科集團 美容牙科 高階牙科 醫療券 長者醫療券大灣區試點假牙 金屬牙 缺牙 牙槽骨流失 植牙步驟 微創植牙 傳統植牙 即剝即種 植牙案例 牙醫 牙医 深圳 羅湖 朱咪咪 掛號 親水植體 CT檢查 收費 價目表 線上預約 牙托 全口牙托 局部牙托 活動式假牙 假牙 固定式假牙 牙托 牙橋 假牙托 牙齒修復 牙齒美觀 活動式假牙 可拆卸假牙 便宜',
    },
  ],
})

const orthodonticsIntroduceData = {
  title: 'pages.dental-service.toothtray.introduce.title',
  content: 'pages.dental-service.toothtray.introduce.content',
  mbImg: 'https://static.cmereye.com/imgs/2024/09/0fbecf869a4e73a4.png',
  pcImg: 'https://static.cmereye.com/imgs/2023/05/eff373fe8976c4f0.jpg',
  tabNavName: 'pages.dental-service.toothtray.introduce.tabNavName',
}

const headerConfig = {
  img: 'https://static.ckjhk.com/ckj-image/e8921f9c1eb9.webp',
  mbImg: 'https://static.ckjhk.com/ckj-image/c83d6774564e.webp',
  bg: '',
  pageName: 'scaling-and-polishing-test',
  pcText: [],
  mbText: [],
}

const reasonData = {
  title: '全口牙托及局部牙托',
  imgUrl: 'https://static.cmereye.com/static/ckj/imgs/toothtray/reasonimg.webp',
  reasonLists: [
    {
      title: 'pages.dental-service.toothtray.reason.lists[0].context',
      context: 'pages.dental-service.toothtray.reason.lists[1].context',
    },
    {
      title: 'pages.dental-service.toothtray.reason.lists[2].context',
      context: 'pages.dental-service.toothtray.reason.lists[3].context',
    },
  ],
}

const contrastData = {
  title: {
    span1: '固定式假牙',
    span2: '活動式假牙點揀好？',
  },
  context:
    '固定式假牙與活動式假牙各有其優缺點及適用的情況，通常會經由牙醫評估口內缺牙的情況及剩下牙齒的狀況，再進一步進行全面的考量及建議。',
  tableRemark: '以下為你分析固定式/活動式假牙的優缺點：',
  table: {
    title: [
      ['類別'],
      ['適用', '人士'],
      ['物料'],
      ['優點'],
      ['缺點'],
      ['清潔', '方法'],
      ['價錢'],
    ],
    data: [
      {
        th: '固定式假牙',
        td: [
          {
            name: '牙套',
            bg: 'https://static.cmereye.com/static/ckj/imgs/toothtray/contrast1.jpg',
          },
          {
            name: '牙橋',
            bg: 'https://static.cmereye.com/static/ckj/imgs/toothtray/contrast2.jpg',
          },
        ],
        content: [
          {
            l: ['牙根健康', '牙齒損耗範圍太大', '已接受杜牙根治療'],
            r: ['缺牙兩旁尚有健康牙齒', '牙齒連牙根被全隻拔起'],
            c: [],
          },
          {
            l: ['全金屬、全鋯、全瓷'],
            r: ['全金屬、全鋯、全瓷'],
            c: [],
          },
          {
            l: ['保留真牙牙根'],
            r: ['提高假牙穩定度'],
            c: [],
          },
          {
            l: ['需修磨牙齒'],
            r: ['需修磨兩側牙齒，若其中一顆牙齒出現問題，需重新製作整組牙橋'],
            c: [],
          },
          {
            l: [],
            r: [],
            c: ['日常早晚刷牙', '使用牙橋專用牙線'],
          },
          {
            l: [],
            r: [],
            c: ['價格比種植牙便宜'],
          },
        ],
      },
      {
        th: '活動定式假牙',
        td: [
          {
            name: '局部牙托',
            bg: 'https://static.cmereye.com/static/ckj/imgs/toothtray/contrast3.jpg',
          },
          {
            name: '全口牙托',
            bg: 'https://static.cmereye.com/static/ckj/imgs/toothtray/contrast4.jpg',
          },
        ],
        content: [
          {
            l: ['口腔內尚有健康牙齒'],
            r: ['口腔內已沒有健康牙齒'],
            c: [],
          },
          {
            l: ['金屬支架或金屬勾', '牙齒部分多由塑膠材料製造'],
            r: ['塑膠支架', '牙齒部分多由塑膠製造'],
            c: [],
          },
          {
            l: ['自由裝取'],
            r: ['自由裝取'],
            c: [],
          },
          {
            l: ['容易磨損口腔內璧，造成潰瘍及疼痛', '適應期較長'],
            r: ['咬合感覺與真牙的感覺相差甚大，適應期長', '假牙容易晃動及移位'],
            c: [],
          },
          {
            l: [],
            r: [],
            c: ['軟毛牙刷輕刷牙托表面', '假牙清潔片輔助清潔'],
          },
          {
            l: [],
            r: [],
            c: ['是最便宜的重建牙齒方法'],
          },
        ],
      },
    ],
  },
}
const contrastItem1 = contrastData.table.data[0]
const contrastItem2 = contrastData.table.data[1]

const problemData = {
  title: '<span>假牙</span><span>常見問題</span>',
  lists: [
    {
      Q: 'pages.dental-service.toothtray.problem.lists[0].Q',
      A: 'pages.dental-service.toothtray.problem.lists[0].A',
    },
    {
      Q: 'pages.dental-service.toothtray.problem.lists[3].Q',
      A: 'pages.dental-service.toothtray.problem.lists[3].A',
    },
    {
      Q: 'pages.dental-service.toothtray.problem.lists[1].Q',
      A: 'pages.dental-service.toothtray.problem.lists[1].A',
    },
    {
      Q: 'pages.dental-service.toothtray.problem.lists[2].Q',
      A: 'pages.dental-service.toothtray.problem.lists[2].A',
    },
    {
      Q: 'pages.dental-service.toothtray.problem.lists[4].Q',
      A: 'pages.dental-service.toothtray.problem.lists[4].A',
    },
  ],
}

const processData: any = {
  title: '定製流程',
  lists: [
    {
      type: 'h2',
      data: [
        {
          text: '牙橋及牙套',
        },
        {
          text: '活動式牙托',
        },
      ],
    },
    {
      type: 'h3',
      data: [
        {
          text: '步驟一：初診與評估',
        },
      ],
    },
    {
      type: 'text',
      data: [
        {
          context: [
            {
              name: '諮詢與診斷：',
              text: '醫生將詳細評估患者的口腔健康狀況，了解具體需求、預算和期望效果。',
            },
            {
              name: '牙齒準備：',
              text: '醫生會對牙齒進行磨削，以便為牙橋及牙套提供足夠空間。',
            },
          ],
        },
        {
          context: [
            {
              name: '需求評估：',
              text: '在您的首次來訪時，我們的牙醫將與您進行深入的交談，了解具體需求及預算。',
            },
            {
              name: '口腔檢查：',
              text: '進行全面的口腔檢查，評估您的牙齦、牙齒狀態及任何可能影響牙托設計的問題。',
            },
          ],
        },
      ],
    },
    {
      type: 'h3',
      data: [
        {
          text: '步驟二：牙齒印模',
        },
      ],
    },
    {
      type: 'text',
      data: [
        {
          context: [
            {
              name: '製作印模：',
              text: '使用專業材料對磨削後的牙齒及相鄰牙齒進行精確印模，以用於牙套的製作。',
            },
            {
              name: '咬合記錄：',
              text: '記錄您的咬合方式，以確保牙托在您咬合時能提供適當的支持和保護。',
            },
            {
              name: '製作臨時牙套：',
              text: '在牙套製作期間，牙醫會安裝臨時牙套以保護磨削過的牙齒。',
            },
          ],
        },
        {
          context: [
            {
              name: '牙齒印模：',
              text: '使用先進的牙齒印模材料，為您的牙齒製作精確的模型，確保牙托能夠完美契合您的牙齒。',
            },
            {
              name: '咬合記錄：',
              text: '記錄您的咬合方式，以確保牙托在您咬合時能提供適當的支持和保護。',
            },
          ],
        },
      ],
    },
    {
      type: 'h3',
      data: [
        {
          text: '步驟三：牙橋及牙套製作',
        },
      ],
    },
    {
      type: 'text',
      data: [
        {
          context: [
            {
              name: '專業製作：',
              text: '根據患者選擇的材料精準製作牙橋及牙套。',
            },
          ],
        },
        {
          context: [
            {
              name: '專業製作：',
              text: '使用高品質的材料製作牙托，以確保牙托的耐用性、安全性和舒適性。',
            },
            {
              name: '個性化調整：',
              text: '根據需要，牙托可以進行個性化的調整，如顏色選擇、厚度調整等，以適應不同的需求或個人偏好。',
            },
          ],
        },
      ],
    },
    {
      type: 'h3',
      data: [
        {
          text: '步驟四：牙橋及牙套安裝及指導',
        },
      ],
    },
    {
      type: 'text',
      data: [
        {
          context: [
            {
              name: '試戴及安裝：',
              text: '製作完成後，患者需要進行試戴及安裝，確保其貼合性、美觀效果和舒適度。',
            },
          ],
        },
        {
          context: [
            {
              name: '試戴：',
              text: '牙托製作完成後，患者需要進行試戴，確保牙托的舒適度和功能性。',
            },
            {
              name: '細節調整：',
              text: '根據試戴結果進行調整，以確保牙托能最佳貼合和舒適。',
            },
          ],
        },
      ],
    },
    {
      type: 'h3',
      data: [
        {
          text: '步驟五：使用指導與後續跟進',
        },
      ],
    },
    {
      type: 'text',
      data: [
        {
          context: [
            {
              name: '護理指導：',
              text: '提供牙橋及牙套使用指導，以確保正常使用壽命。',
            },
            {
              name: '後續跟進：',
              text: '定期安排回診，檢查牙橋及牙套的狀態和口腔健康，及時調整或保養。',
            },
          ],
        },
        {
          context: [
            {
              name: '使用指導：',
              text: '提供如何正確佩戴和保養牙托的指導，確保患者獲得最佳使用效果。',
            },
            {
              name: '後續跟進：',
              text: '定期安排回診，檢查牙托的狀態和口腔健康，及時調整或保養牙·托。',
            },
          ],
        },
      ],
    },
  ],
}
const advantageData = {
  title: '為什麼選擇愛康健的定製牙托？',
  lists: [
    {
      img: 'https://static.cmereye.com/static/ckj/imgs/toothtray/advantage1.svg',
      name: '專業製作',
      text: '愛康健的假牙由資深修復科醫生根據患者的牙齒模型精確製作，確保每一個假牙都能完美貼合。',
    },
    {
      img: 'https://static.cmereye.com/static/ckj/imgs/toothtray/advantage2.svg',
      name: '高品質材料',
      text: '愛康健使用高品質材料製作假牙，確保假牙耐用且對身體安全無害。',
    },
    {
      img: 'https://static.cmereye.com/static/ckj/imgs/toothtray/advantage3.svg',
      name: '專業保養及\n緊急維修服務',
      text: '愛康健提供專業假牙保養及緊急維修服務，讓假牙延長其使用壽命。',
    },
    {
      img: 'https://static.ckjhk.com/ckj-image/2025040713584801.webp',
      name: '醫療券付款',
      text: '愛康健收費合理且接受長者醫療券付款，節省長者醫療開支。',
    },
  ],
}
const testimonials = ref([
  {
    img: 'https://static.cmereye.com/static/ckj/imgs/toothtray/Ellipse203.png',
    name: '明叔',
    jos: '小巴司機',
    context:
      '年紀大有幾隻牙磨損特別嚴重。選擇咗全瓷牙套，現在笑口常開，食嘢無難度。',
  },
  {
    img: 'https://static.cmereye.com/static/ckj/imgs/toothtray/Ellipse202.png',
    name: 'May姐',
    jos: '準奶奶',
    context: '屋企辦喜事，補返隻缺牙見親戚朋友都有體面啲，影相都靚啲。',
  },
  {
    img: 'https://static.cmereye.com/static/ckj/imgs/toothtray/Ellipse204.png',
    name: '黃伯伯',
    jos: '長壽長者',
    context:
      '以前都整過假牙，但戴到好唔舒服。愛康健醫生手勢好好多，排牙好貼服，掂呀。',
  },
])

let windowWidth = ref(390)
const getWindowWidth = () => {
  windowWidth.value = window.innerWidth
}

const implantStepList = [
  {
    id: 1,
    title: '準備',
    text: '全口檢查、<br class="d-lg-none" />記錄咬合狀態',
    img: 'https://static.ckjhk.com/ckj-image/7950b39a3f66.png',
    ifImage: true,
  },
  {
    id: 2,
    title: '製作',
    text: '取模及製作、<br class="d-lg-none" />即日試戴及調整',
    img: 'https://static.ckjhk.com/ckj-image/c2f157aac13a.png',
    ifImage: true,
  },
  {
    id: 3,
    title: '覆診',
    text: '了解實際配戴<br class="d-lg-none" />情形作出微調',
    img: 'https://static.ckjhk.com/ckj-image/6bc729ce04d9.png',
    ifImage: true,
  },
]


const cutTab = ref(false)
const cutTabCustomMade = () => {
  cutTab.value = !cutTab.value
}
const activeIndex = ref(null)
const flow_custom_made_tab_lists = ref([
  {
    id: 1,
    title: '初診與評估',
    content: [
      {
        sonTitle: '諮詢與診斷：',
        sonText: '醫生將詳細評估患者的口腔健康狀況，了解具體需求、預算和期望效果。',
      },
      {
        sonTitle: '牙齒準備：',
        sonText: '醫生會對牙齒進行磨削，以便為牙橋及牙套提供足夠空間。',
      }
    ]
  },
  {
    id: 2,
    title: '牙齒印模',
    content: [
      {
        sonTitle: '製作印模：',
        sonText: '使用專業材料對磨削後的牙齒及相鄰牙齒進行精確印模，以用於牙套的製作。',
      },
      {
        sonTitle: '咬合記錄：',
        sonText: '記錄您的咬合方式，以確保牙托在您咬合時能提供適當的支持和保護。',
      },
      {
        sonTitle: '製作臨時牙套：',
        sonText: '在牙套製作期間，牙醫會安裝臨時牙套以保護磨削過的牙齒。',
      }
    ]
  },
  {
    id: 3,
    title: '牙橋及牙套製作',
    content: [
      {
        sonTitle: '製作牙橋：',
        sonText: '根據患者選擇的材料精準製作牙橋，以提供更舒適的咬合。',
      },
    ]
  },
  {
    id: 4,
    title: '牙橋及牙套安裝及指導',
    content: [
      {
        sonTitle: '試戴及安裝：',
        sonText: '製作完成後，患者需要進行試戴及安裝，確保其貼合性、美觀效果和舒適度。',
      },
      // {
      //   sonTitle: '牙齒準備：',
      //   sonText: '醫生會對牙齒進行磨削，以便為牙橋及牙套提供足夠空間。',
      // }
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
        sonText: '定期安排回診，檢查牙橋及牙套的狀態和口腔健康，及時調整或保養。',
      }
    ]
  }
])

const flow_custom_made_tab_lists_two = ref([
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


const expandedHeight = ref(0)

const numExpandedHeight = () => {
  return windowWidth.value > 768 ? expandedHeight.value = 200 : expandedHeight.value = 135
}

const numColorBlockHeight = () => {
  return windowWidth.value > 768 ? 60 : expandedHeight.value = 0
}

const toggleContent = (index: any) => {
  activeIndex.value = activeIndex.value === index ? null : index;
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
  if (swiperRef.activeIndex >= testimonials.value.length - 1) {
    swiperRef.slideTo(0)
  }
  swiperRef.slideNext()
  handleProcessBtnClick()
}
const subNum = () => {
  if (swiperRef.activeIndex <= 0) {
    swiperRef.slideTo(testimonials.value.length - 1)
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


const typesOfDentures = ref(false)

const isTypesOfDentures = () => {
  typesOfDentures.value = !typesOfDentures.value
}
const scrollContainer = ref<HTMLElement | null>(null)
const scrollRight = () => {
  if (scrollContainer.value) {
    scrollContainer.value.scrollLeft += 194;
  }
}
const scrollLeft = () => {
  if (scrollContainer.value) {
    scrollContainer.value.scrollLeft -= 194;
  }
}

const scrollActiveIndex = ref(1)
const scrollToItem = (i: number) => {
  scrollActiveIndex.value = i
  if (scrollContainer.value) {
    scrollContainer.value.scrollLeft = i * 194;
  }
}


onMounted(() => {
  scrollActiveIndex.value = 1
  getWindowWidth()
  numExpandedHeight()
  window.addEventListener('resize', getWindowWidth)
})
</script>

<template>
  <div style="overflow: hidden; width: 100%">
    <PageHeaderV2 v-if="windowWidth > 768" :headerConfig="headerConfig" />
    <MobileHeaderV2 v-if="windowWidth < 768" :headerConfig="headerConfig">
      <template #xxxxxxxxxxx-home>
        <div class="banner-in-box">
          <div class="banner-content" style="display: flex">
            <div class="content-title">讓牙齒更加整齊、美觀、舒適</div>
            <div class="content-price">
              <div>假牙及牙橋</div>
            </div>
          </div>
        </div>
      </template>
    </MobileHeaderV2>
    <PagePcBannerNoHome v-if="windowWidth > 768" :headerConfig="headerConfig">
      <template #xxxxxxxxxxx-home>
        <div class="banner-in-box">
          <div class="banner-content" style="display: flex">
            <div class="content-title">讓牙齒更加整齊、美觀、舒適</div>
            <div class="content-price">
              <div>假牙及牙橋</div>
            </div>
          </div>
        </div>
      </template>
    </PagePcBannerNoHome>

    <div class="tooth_tray">
      <section class="ckj-container  tooth_tray_comparison">
        <div class="root-canal-therapy-title d-flex flex-row  d-none d-lg-flex align-items-end subheading">
          <span style="color: var(--Brand-Color, #F8298A);font-size: 30px;">活動式假牙</span><span
            style="font-size: 24px;color: var(--Grey-Dark, #333);">VS</span><span
            style="color: var(--Brand-Color, #F8298A);font-size: 30px;">固定式假牙</span>
        </div>
        <div class="d-flex flex-row  d-lg-none align-items-end subheading">
          <span style="font-size: 18px;color: var(--Brand-Color, #F8298A);">活動式假牙</span><span
            style="font-size: 16px;color: var(--Grey-Dark, #333);">VS</span><span
            style="color: var(--Brand-Color, #F8298A);font-size: 18px;line-height: 150%;">固定式假牙</span>
        </div>
        <div class="tooth_tray_content">
          <div><span>活動式假牙</span>與<span>固定式假牙</span>各有其優缺點及適用的情況，通常會經由牙醫評估口內缺牙的情況及剩下牙齒的狀況，再進一步進行全面的考量及建議。</div>
        </div>
      </section>
      <section class="ckj-container  tooth_tray_new_technique">
        <div class="tooth_tray_new_steps">
          <div><span>\ 假牙新技術 /</span> </div>
        </div>
        <div class="tooth_tray_table">
          <div></div>
          <div>日本BPS</div>
          <div></div>
          <div></div>
          <div>真空吸附式假牙</div>
          <div>傳統假牙</div>
          <div></div>
          <div><img src="https://static.ckjhk.com/ckj-image/2df378e77d0a.png" alt=""></div>
          <div><img src="https://static.ckjhk.com/ckj-image/c2eaa183af99.png" alt=""></div>
          <div>穩固性</div>
          <div>穩固</div>
          <div>易鬆動</div>
          <div>舒適度</div>
          <div>輕薄</div>
          <div>厚重</div>
          <div>美觀</div>
          <div>自然</div>
          <div>呆板</div>
          <div>咀嚼功能</div>
          <div>有牙力</div>
          <div>有牙力</div>
          <div>發音</div>
          <div>清晰</div>
          <div>含糊</div>
          <div>清潔難度</div>
          <div>較易、無需黏著劑 </div>
          <div>較麻煩</div>
          <div>骨質要求</div>
          <div>適合牙槽骨萎縮人士</div>
          <div>需評估</div>
          <div>價格</div>
          <div>較高</div>
          <div>較低</div>
        </div>
      </section>
      <section class="ckj-container tooth_tray_share_food">
        <div class="tooth_tray_new_steps">
          <div><span>\ 用真空吸附式假牙可有效地享用美食 /</span> </div>
        </div>
        <div class="tooth_tray_share_food_content">
          愛康健齒科於2007年引入日本BPS真空吸附式假牙技術，是深圳首間私營機構提供吸附式假牙服務。<br
            class="d-flex  d-none d-lg-flex" />18年資深製作經驗，頂級技術能達到最佳舒適度、穩固性及咀嚼功能。
        </div>
      </section>
      <section class="ckj-container tooth_tray_service">
        <div class="d-flex flex-row  d-none d-lg-flex align-items-end subheading">
          <span style="color: var(--Grey-Dark, #333);font-size:24px;">愛康健提供</span><span
            style="color: var(--Brand-Color, #F8298A);font-size:30px;line-height: 130%;">特快即日完成假牙服務</span>
        </div>
        <div class="d-flex flex-row  d-lg-none align-items-end subheading">
          <span style="font-size: 16px;color: var(--Grey-Dark, #333);">愛康健提供</span><span
            style="color:var(--Brand-Color, #F8298A);font-size: 18px;line-height: 140%;">特快即日完成假牙服務</span>
        </div>
        <div class="tooth_tray_step">
          <div class="fillings-step-item" v-for="(item, index) in implantStepList.slice(0, 5)" :key="index">
            <div>{{ item.id }}</div>
            <div>
              <img :src="item.img" :alt="item.title" />
            </div>
            <div>
              <span>{{ item.title }}</span>
              <span v-html="item.text"></span>
            </div>
          </div>
        </div>
        <div class="tooth_tray_btn">
          <PageAnimBtnTypeTwo :str="'立即查詢預約'" />
        </div>
      </section>
      <section class="ckj-container tooth_tray_compare_kind">
        <div class="d-flex flex-row  d-none d-lg-flex align-items-end subheading">
          <span style="color: var(--Grey-Dark, #333);font-size:24px;">假牙及牙橋</span><span
            style="color: var(--Brand-Color, #F8298A);font-size:30px;line-height: 130%;">種類比較</span>
        </div>
        <div class="d-flex flex-row  d-lg-none align-items-end subheading"><span
            style="color: var(--Brand-Color, #F8298A);font-size: 18px;line-height: 150%;">種類比較</span>
        </div>
        <div class="tooth_tray_compare_kind_tab">
          <div class="tooth_tray_compare_kind_btn"
            :class="[typesOfDentures ? 'tooth_tray_compare_kind_btn_active' : '']" @click="isTypesOfDentures">固定式假牙
          </div>
          <div class="tooth_tray_compare_kind_btn"
            :class="[typesOfDentures ? '' : 'tooth_tray_compare_kind_btn_active']" @click="isTypesOfDentures">活動式假牙
          </div>
        </div>
        <div class="tooth_tray_compare_kind_table">
          <div class="table_row_one">類別</div>
          <div v-if="typesOfDentures" class="table_pink_title_box">牙套</div>
          <div v-if="typesOfDentures" class="table_pink_title_box">牙橋</div>
          <div v-if="!typesOfDentures" class="table_blue_title_box">局部牙托</div>
          <div v-if="!typesOfDentures" class="table_blue_title_box">全口牙托</div>
          <div v-if="typesOfDentures" class="table_img_box"><img
              src="https://static.ckjhk.com/ckj-image/38eaaaf7a9d8.png" alt=""></div>
          <div v-if="typesOfDentures" class="table_img_box"><img
              src="https://static.ckjhk.com/ckj-image/a0f40df6ff84.png" alt=""></div>
          <div v-if="!typesOfDentures" class="table_img_box"><img
              src="https://static.ckjhk.com/ckj-image/a1b900a60f44.png" alt=""></div>
          <div v-if="!typesOfDentures" class="table_img_box"><img
              src="https://static.ckjhk.com/ckj-image/2d5e51390162.png" alt=""></div>
          <div class="table_row_one">適用人士</div>
          <div v-if="typesOfDentures" class="table_box_general">
            <span>牙根健康</span>
            <span>牙齒損耗範圍太大</span>
            <span>已接受杜牙根治療</span>
          </div>
          <div v-if="typesOfDentures" class="table_box_general">
            <span>缺牙兩旁尚有健康牙齒</span>
            <span>已拔走整隻牙齒</span>
          </div>
          <div v-if="!typesOfDentures" class="table_box_general">
            <span>口腔內尚有健康牙齒</span>
          </div>
          <div v-if="!typesOfDentures" class="table_box_general">
            <span>口腔內已無健康牙齒</span>
          </div>
          <div class="table_row_one">物料</div>
          <div v-if="typesOfDentures" class="table_two_col">全金屬、全鋯、全瓷</div>
          <div v-if="!typesOfDentures" class="table_two_col">
            <span>金屬支架或金屬勾</span>
            <span>牙齒部分多由塑膠材料製造</span>
          </div>
          <div class="table_row_one">優點</div>
          <div v-if="typesOfDentures" class="table_box_general">
            <span>保留真牙牙根</span>
          </div>
          <div v-if="typesOfDentures" class="table_box_general">
            <span>提高假牙穩定度</span>
          </div>
          <div v-if="!typesOfDentures" class="table_two_col">自由裝取</div>
          <div class="table_row_one">缺點</div>
          <div v-if="typesOfDentures" class="table_box_general">需修磨牙齒</div>
          <div v-if="typesOfDentures" class="table_box_general"><span>需修磨兩側牙齒，若其中一顆牙齒出現問題，需重新製作整組牙橋</span></div>
          <div v-if="!typesOfDentures" class="table_box_general">
            <span>易磨損口腔內璧，造成潰瘍及疼痛</span>
            <span>適應期較長</span>
          </div>
          <div v-if="!typesOfDentures" class="table_box_general">
            <span>咬合感覺與真牙的感覺相差甚大，適應期長</span>
            <span>易晃動及移位</span>
          </div>
          <div class="table_row_one">清潔方法</div>
          <div v-if="typesOfDentures" class="table_two_col">
            <span>缺牙兩旁尚有健康牙齒</span>
            <span>已拔走整隻牙齒</span>
          </div>
          <div v-if="!typesOfDentures" class="table_two_col">
            <span>軟毛牙刷輕刷牙托表面</span>
            <span>假牙清潔片輔助清潔</span>
          </div>
          <div class="table_row_one">傷口大小</div>
          <div v-if="typesOfDentures" class="table_two_col">價格比種植牙便宜</div>
          <div v-if="!typesOfDentures" class="table_two_col">最便宜的重建牙齒方法</div>
        </div>
      </section>
      <section class="tooth_tray_flow_custom_made_bg">
        <section class="ckj-container  tooth_tray_flow_custom_made">
          <div class="d-flex flex-row  d-none d-lg-flex align-items-end subheading">
            <span style="color: var(--Grey-Dark, #333);font-size:24px;">牙橋及活動假牙</span><span
              style="color: var(--Brand-Color, #F8298A);font-size:30px;line-height: 130%;">訂製流程</span>
          </div>
          <div class="d-flex flex-row  d-lg-none align-items-end subheading">
            <span style="color: var(--Grey-Dark, #333);font-size:16px;line-height: 140%;">牙橋及活動假牙</span><span
              style="color: var(--Brand-Color, #F8298A);font-size:18px;line-height: 130%;">訂製流程</span>
          </div>
          <div class="tooth_tray_flow_custom_made_content">
            <div class="flow_custom_made_tab">
              <div class="flow_custom_made_tab_text" :class="[!cutTab ? 'flow_custom_made_tab_active' : '']"
                @click="cutTabCustomMade">固定式假牙</div>
              <div class="flow_custom_made_tab_text" :class="[cutTab ? 'flow_custom_made_tab_active' : '']"
                @click="cutTabCustomMade">活動式假牙</div>
            </div>
            <div class="flow_custom_made_tab_collapse">
              <div class="wrapper" v-if="!cutTab">
                <div v-for="(section, index) in flow_custom_made_tab_lists" :key="section.id"
                  class="flow_custom_made_tab_item">
                  <div class="color-block d-flex flex-row  d-none d-lg-flex"
                    :class="activeIndex === index ? 'color-block-active' : ''"
                    :style="{ height: activeIndex === index ? `${numExpandedHeight()}px` : '50px' }">
                  </div>
                  <div class="color-block d-flex flex-row  d-lg-none"
                    :class="activeIndex === index ? 'color-block-active' : ''"
                    :style="{ height: activeIndex === index ? `${numExpandedHeight() + 40}px` : '40px' }">
                  </div>
                  <div @click="toggleContent(index)" class="flow_custom_made_tab_item-container">
                    <div class="flow_custom_made_tab_item-header">
                      <div>{{ section.id }}</div>
                      <div>{{ section.title }}</div>
                      <div>{{ activeIndex === index ? '-' : '+' }}</div>
                    </div>
                    <div v-show="activeIndex === index" class="flow_custom_made_tab_item-content"
                      :style="{ height: activeIndex === index ? `${numExpandedHeight() - numColorBlockHeight()}px` : '' }">
                      <div v-for="item in section.content" :key="item.sonTitle">
                        <strong>{{ item.sonTitle }}</strong> {{ item.sonText }}
                      </div>
                    </div>
                  </div>
                </div>
              </div>
              <div class="wrapper" v-if="cutTab">
                <div v-for="(section, index) in flow_custom_made_tab_lists_two" :key="section.id"
                  class="flow_custom_made_tab_item">
                  <div class="color-block d-flex flex-row  d-none d-lg-flex"
                    :class="activeIndex === index ? 'color-block-active' : ''"
                    :style="{ height: activeIndex === index ? `${numExpandedHeight()}px` : '50px' }">
                  </div>
                  <div class="color-block d-flex flex-row  d-lg-none"
                    :class="activeIndex === index ? 'color-block-active' : ''"
                    :style="{ height: activeIndex === index ? `${numExpandedHeight() + 40}px` : '40px' }">
                  </div>
                  <div @click="toggleContent(index)" class="flow_custom_made_tab_item-container">
                    <div class="flow_custom_made_tab_item-header">
                      <div>{{ section.id }}</div>
                      <div>{{ section.title }}</div>
                      <div>{{ activeIndex === index ? '-' : '+' }}</div>
                    </div>
                    <div v-show="activeIndex === index" class="flow_custom_made_tab_item-content"
                      :style="{ height: activeIndex === index ? `${numExpandedHeight() - numColorBlockHeight()}px` : '' }">
                      <div v-for="item in section.content" :key="item.sonTitle">
                        <strong>{{ item.sonTitle }}</strong> {{ item.sonText }}
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </section>
      </section>

      <section class="ckj-container  tooth_tray_flow_advantage">
        <div class="d-flex flex-row  d-none d-lg-flex align-items-end subheading">
          <span style="color: var(--Grey-Dark, #333);font-size:24px;">愛康健訂製活動假牙及牙橋</span><span
            style="color: var(--Brand-Color, #F8298A);font-size:30px;line-height: 130%;">4大優勢</span>
        </div>
        <div class="d-flex flex-row  d-lg-none align-items-end subheading">
          <span style="color: var(--Grey-Dark, #333);font-size:16px;line-height: 140%;">愛康健訂製活動假牙及牙橋</span><span
            style="color: var(--Brand-Color, #F8298A);font-size:18px;line-height: 130%;">4大優勢</span>
        </div>
        <div class="tooth_tray_flow_advantage_content" ref="scrollContainer">
          <div>
            <div><img src="https://static.ckjhk.com/ckj-image/63632ee0bbad.png" alt=""></div>
            <div>專業製作</div>
            <div>愛康健的假牙由資深修復科醫生根據患者的牙齒模型精確製作，確保每一個假牙都能完美貼合。</div>
          </div>
          <div>
            <div><img src="https://static.ckjhk.com/ckj-image/79333a685481.png" alt=""></div>
            <div>高品質材料</div>
            <div>愛康健使用高品質材料製作假牙，確保假牙耐用且對身體安全無害。</div>
          </div>
          <div>
            <div><img src="https://static.ckjhk.com/ckj-image/55f9455f1f26.png" alt=""></div>
            <div>緊急維修<span>及保養</span></div>
            <div>愛康健提供專業假牙保養及緊急維修服務，讓假牙延長其使用壽命。</div>
          </div>
          <div>
            <div><img src="https://static.ckjhk.com/ckj-image/455161bc70d5.png" alt=""></div>
            <div>醫療券付款</div>
            <div>愛康健收費合理且接受長者醫療券付款，節省長者醫療開支。</div>
          </div>
        </div>
        <div class="tooth_tray_flow_advantage_scroll_button_wrapper">
          <div @click="scrollLeft"></div>
          <div :class="scrollActiveIndex == 1 ? 'scroll_button_active scroll_button' : 'scroll_button'"
            @click="scrollToItem(1)"></div>
          <div :class="scrollActiveIndex == 2 ? 'scroll_button_active scroll_button' : 'scroll_button'"
            @click="scrollToItem(2)"></div>
          <div :class="scrollActiveIndex == 3 ? 'scroll_button_active scroll_button' : 'scroll_button'"
            @click="scrollToItem(3)"></div>
          <div :class="scrollActiveIndex == 4 ? 'scroll_button_active scroll_button' : 'scroll_button'"
            @click="scrollToItem(4)"></div>
          <div @click="scrollRight"></div>
        </div>
      </section>

      <section class="ckj-container  tooth_tray_flow_share">
        <div class="d-flex flex-row align-items-end subheading">
          <span>客戶</span><span>分享</span>
        </div>
        <div class="tooth_tray_flow_share_content">
          <div>“</div>
          <div>解決缺牙問題我揀愛康健！</div>
          <div>”</div>
        </div>
      </section>
      <section class="tooth_tray_flow_share_bg">
        <Swiper :slidesPerView="windowWidth > 768 ? 3 : 2" :spaceBetween="windowWidth > 768 ? 30 : 14" @swiper="setSwiperRef" :navigation="{
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev'
        }" :autoplay="{ delay: 3000, disableOnInteraction: false }" :pagination="{
          el: '.swiper-pagination',
          clickable: true
        }" class="testimonial-swiper">
          <swiper-slide v-for="(item, index) in testimonials" :key="index">
            <div class="swiper_share_item">
              <img :src="item.img" />
              <h3>{{ item.jos }}</h3>
              <p>{{ item.name }}</p>
              <p>{{ item.context }}</p>
            </div>
          </swiper-slide>
        </Swiper>
        <!-- Navigation -->
        <div class="flex justify-center mt-4">
          <div class="swiper-button-prev" @click="subNum">
            <svg width=" 13" height="18" viewBox="0 0 13 18" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M10 15L2.5 8.99931L10 3" stroke="#D2337D" stroke-width="4" stroke-miterlimit="10"
                stroke-linecap="square" stroke-linejoin="round" />
            </svg>
          </div>
          <div class="swiper-pagination">
            <div v-for="(item, index) in testimonials" :key="index" @click="handleLineCurStrength(index + 1)"
              :class="index == 0 ? 'swiper-pagination-bullet-active' : ''" class="swiper-pagination-bullet"></div>
          </div>
          <div class="swiper-button-next" @click="addNum">
            <svg width="13" height="18" viewBox="0 0 13 18" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M3 15L10.5 8.99931L3 3" stroke="#D2337D" stroke-width="4" stroke-miterlimit="10"
                stroke-linecap="square" stroke-linejoin="round" />
            </svg>
          </div>
        </div>
      </section>
      <section class="ckj-container tooth_tray_flow_problem">
        <div>
          <V2ServiceProblem :problem-data="problemData" :v2-versions="true" />
        </div>
      </section>

    </div>
    <BranchAddress />
    <AppointmentFormV2 />
    <FooterV2 />
    <AsideV2 />
  </div>
</template>

<style lang="scss" scoped>
@media screen and (min-width: 992px) {
  .tooth_tray {
    margin-top: 30px;
  }

  .tooth_tray_comparison {
    box-sizing: border-box;
    padding: 30px 0;

    .tooth_tray_content {
      margin-top: 20px;

      &>div {
        color: var(--Grey-Deep, #4D4D4D);

        /* 桌面版/PC-20Pt字 */
        font-family: "Noto Sans HK";
        font-size: 20px;
        font-style: normal;
        font-weight: 400;
        line-height: 160%;
        letter-spacing: 4px;

        &>span {
          color: var(--Brand-Color, #F8298A);
          text-align: justify;
        }
      }
    }
  }

  .tooth_tray_new_technique {
    box-sizing: border-box;
    padding: 30px 0 0;


    .tooth_tray_table {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      box-sizing: border-box;
      padding: 0 40px;

      &>div:nth-child(3n + 1) {
        width: 200px;
        border: 1px solid var(--Brand-Color, #F8298A);
        background: var(--Brand-Color, #F8298A);
        display: flex;
        align-items: center;
        justify-content: center;
        color: var(--White, #FFF);
        text-align: center;
        font-family: "Noto Sans HK";
        font-size: 18px;
        font-style: normal;
        font-weight: 700;
        line-height: 100%;
        letter-spacing: 1.8px;
        box-sizing: border-box;
        padding: 10px 0;
        border-bottom: 3px solid var(--Brand-Color, #F8298A);
      }

      &>div:nth-child(3n + 2),
      &>div:nth-child(3n + 3) {
        width: 380px;
        background: var(--White, #fff);
        color: var(--Grey-Dark, #333);
        text-align: center;
        font-family: "Noto Sans HK";
        font-size: 14px;
        font-style: normal;
        font-weight: 350;
        line-height: 18px;
        display: flex;
        align-items: center;
        justify-content: center;
      }

      &>div:nth-child(1),
      &>div:nth-child(2),
      &>div:nth-child(3),
      &>div:nth-child(4),
      &>div:nth-child(7) {
        background: transparent;
        border: none;
      }

      &>div:nth-child(10) {
        border-radius: 10px 0px 0px 0px;
        border-top: 3px solid var(--Brand-Color, #F8298A);
      }

      &>div:nth-child(31) {
        border-radius: 0px 0px 0px 10px;
      }

      &>div:nth-child(2) {
        color: var(--Brand-Color, #F8298A);
        text-align: center;
        font-family: "Noto Sans HK";
        font-size: 28px;
        font-style: normal;
        font-weight: 700;
        line-height: normal;
        margin-bottom: 20px;
      }

      &>div:nth-child(5) {
        border-radius: 10px 10px 0px 0px;
        border-top: 7px solid var(--Brand-Color, #F8298A);
        background: var(--Brand-Color, #F8298A);
        color: var(--White, #FFF);
        text-align: center;
        font-family: "Noto Sans HK";
        font-size: 24px;
        font-style: normal;
        font-weight: 700;
        line-height: 120%;
        letter-spacing: 2.4px;
        display: flex;
        align-items: center;
        justify-content: center;
        box-sizing: border-box;
        padding: 10px 0;
        position: relative;
      }

      &>div:nth-child(5)::after {
        content: "";
        position: absolute;
        top: -24px;
        left: 50%;
        transform: translateX(-50%);
        width: 44px;
        height: 28px;
        background: url(/_nuxt/assets/images/group3910.svg) no-repeat;
        background-size: contain;
        z-index: 1;
      }

      &>div:nth-child(6) {
        border-radius: 20px 10px 0px 0px;
        background: var(--Blue-Deep, #00AEFF);
        color: var(--White, #FFF);
        text-align: center;
        font-family: "Noto Sans HK";
        font-size: 24px;
        font-style: normal;
        font-weight: 700;
        line-height: 120%;
        letter-spacing: 2.4px;
        display: flex;
        align-items: center;
        justify-content: center;
        box-sizing: border-box;
        padding: 10px 0;
      }

      &>div:nth-child(8),
      &>div:nth-child(9) {
        width: 100%;
        height: 100%;

        &>img {
          width: 100%;
          height: 100%;
          object-fit: cover;
        }
      }

      &>div:nth-child(11),
      &>div:nth-child(12),
      &>div:nth-child(14),
      &>div:nth-child(15),
      &>div:nth-child(17),
      &>div:nth-child(18),
      &>div:nth-child(20),
      &>div:nth-child(21),
      &>div:nth-child(23),
      &>div:nth-child(24),
      &>div:nth-child(26),
      &>div:nth-child(27),
      &>div:nth-child(32) {
        position: relative;
      }

      &>div:nth-child(12),
      &>div:nth-child(15),
      &>div:nth-child(18),
      &>div:nth-child(21),
      &>div:nth-child(24),
      &>div:nth-child(27),
      &>div:nth-child(30) {
        border-right: 3px solid var(--Grey-Lightest, #F2F2F2);
      }

      &>div:nth-child(11)::after,
      &>div:nth-child(12)::after,
      &>div:nth-child(14)::after,
      &>div:nth-child(15)::after,
      &>div:nth-child(17)::after,
      &>div:nth-child(18)::after,
      &>div:nth-child(20)::after,
      &>div:nth-child(21)::after,
      &>div:nth-child(23)::after,
      &>div:nth-child(24)::after,
      &>div:nth-child(26)::after,
      &>div:nth-child(27)::after,
      &>div:nth-child(32)::after {
        content: '';
        position: absolute;
        bottom: 0;
        left: 0;
        width: 100%;
        height: 3px;
        background: var(--Grey-Lightest, #F2F2F2);
      }

      &>div:nth-child(5),
      &>div:nth-child(8),
      &>div:nth-child(11),
      &>div:nth-child(14),
      &>div:nth-child(17),
      &>div:nth-child(20),
      &>div:nth-child(23),
      &>div:nth-child(26),
      &>div:nth-child(29) {
        border-left: 7px solid var(--Brand-Color, #F8298A);
        border-right: 7px solid var(--Brand-Color, #F8298A);
      }

      &>div:nth-child(29) {
        border-bottom: 7px solid var(--Brand-Color, #F8298A);
      }

      &>div:nth-child(33) {
        border: 7px solid var(--Blue-Deep, #00AEFF);
        border-radius: 0px 0px 10px 0px;
      }

    }
  }

  .tooth_tray_share_food {
    box-sizing: border-box;
    padding: 20px 0 30px;

    .tooth_tray_share_food_content {
      color: var(--Grey-Deep, #4D4D4D);
      text-align: center;
      font-family: "Noto Sans HK";
      font-size: 18px;
      font-style: normal;
      font-weight: 400;
      line-height: 200%;
      letter-spacing: 1.8px;
    }
  }

  .tooth_tray_service {
    box-sizing: border-box;
    padding: 30px 0;

    .tooth_tray_step {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 1.823vw 1.5625vw;
      box-sizing: border-box;
      padding: 35px 0 30px;

      .fillings-step-item {
        display: flex;
        flex-direction: column;
        align-items: center;
        position: relative;

        &>div:nth-child(1) {
          background: url(https://static.cmereye.com/imgs/2024/11/3b0a5e9326c68638.png) no-repeat;
          background-size: cover;
          width: 58px;
          height: 58px;
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

        &>div:nth-child(2) {
          &>img {
            width: 100%;
            height: 100%;
            object-fit: cover;
          }

          position: relative;
        }

        &>div:nth-child(2)::after {
          content: '';
          position: absolute;
          width: 21px;
          height: 63px;
          background: url('~/assets/images/2025040208530601.png') no-repeat;
          background-size: cover;
          top: 50%;
          right: -15px;
          z-index: -1;
          transform: translateY(-50%);
        }

        &>div:nth-child(3) {
          margin-top: 9px;
          width: 100%;
          display: flex;
          flex-direction: column;
          align-items: center;
          justify-content: center;
          box-sizing: border-box;

          &>span:nth-child(1) {
            color: var(--Brand-Color, #F8298A);
            text-align: center;
            font-family: "Noto Sans HK";
            font-size: 18px;
            font-style: normal;
            font-weight: 700;
            line-height: 200%;
            letter-spacing: 1.8px;
          }

          &>span:nth-child(2) {
            color: var(--Grey-Mid, #666);
            text-align: center;
            font-family: "Noto Sans HK";
            font-size: 18px;
            font-style: normal;
            font-weight: 400;
            line-height: 200%;
            letter-spacing: 1.8px;
          }
        }
      }

      .fillings-step-item:last-child {
        &>div:nth-child(2)::after {
          display: none;
        }
      }
    }

    .tooth_tray_btn {
      margin: 15px auto;
      display: flex;
      justify-content: center;
      align-items: center;
    }
  }

  .tooth_tray_compare_kind {
    box-sizing: border-box;
    padding: 30px 0;

    .tooth_tray_compare_kind_table {
      margin-top: 20px;
      display: grid;
      grid-template-columns: repeat(5, 1fr);

      &>div {
        width: 210px;
        border-bottom: 0.2px solid var(--Grey-Light, #E6E6E6);
        border-right: 0.2px solid var(--Grey-Light, #E6E6E6);
        box-sizing: border-box;
        padding: 5px 12px;
        display: flex;
        align-items: center;
        justify-content: center;
        color: var(--Grey-Dark, #333);
        font-family: "Noto Sans HK";
        font-size: 18px;
        font-style: normal;
        font-weight: 400;
        line-height: 200%;
        letter-spacing: 1.8px;
        flex-direction: column;

        span {
          display: flex;
          align-items: center;
          justify-content: flex-start;
          color: var(--Grey-Dark, #333);
          font-family: "Noto Sans HK";
          font-size: 18px;
          font-style: normal;
          font-weight: 400;
          line-height: 200%;
          letter-spacing: 1.8px;
          width: 100%;
          padding-left: 12px;
          position: relative;
        }

        span::before {
          content: '·';
          position: absolute;
          left: -10px;
          top: 20px;
          transform: translateY(-50%);
          color: var(--Grey-Dark, #333);
          font-family: "Noto Sans HK";
          font-size: 18px;
          font-style: normal;
          font-weight: 400;
          line-height: 160%;
          letter-spacing: 1.8px;
        }
      }

      &>div:nth-child(1) {
        grid-row: span 2;
      }

      .table_two_col {
        grid-column: span 2;
        width: calc(210px * 2);
        display: flex;
        align-items: center;
        justify-content: center;

        &>span {
          width: fit-content;
          display: flex;
          justify-content: center;
        }
      }

      .table_img_box {
        padding: 0;
        width: 100%;
        height: 100%;
        overflow: hidden;

        &>img {
          width: 100%;
          height: 100%;
          object-fit: cover;
          transform: scale(1.01);
        }
      }

      .table_row_one {
        width: 120px;
        border: 1px solid var(--Pink-Mid, #F670AE);
        background: var(--Brand-Color, #F8298A);
        color: var(--White, #FFF);
        text-align: center;
        font-family: "Noto Sans HK";
        font-size: 18px;
        font-style: normal;
        font-weight: 700;
        line-height: 200%;
        letter-spacing: 1.8px;
        display: flex;
        align-items: center;
        justify-content: center;
      }

      &>div:nth-child(1) {
        border-radius: 20px 0px 0px 0px;
      }

      .table_pink_title_box {
        border: 1px solid var(--Grey-Light, #E6E6E6);
        background: var(--Pink-Mid, #F670AE);
        color: var(--White, #FFF);
        text-align: center;
        font-family: "Noto Sans HK";
        font-size: 18px;
        font-style: normal;
        font-weight: 700;
        line-height: 200%;
        letter-spacing: 1.8px;
      }

      .table_blue_title_box {
        border: 1px solid var(--Grey-Light, #E6E6E6);
        background: var(--Blue-Deep, #00AEFF);
        color: var(--White, #FFF);
        text-align: center;
        font-family: "Noto Sans HK";
        font-size: 18px;
        font-style: normal;
        font-weight: 700;
        line-height: 200%;
        letter-spacing: 1.8px;
      }

      &>div:nth-child(5) {
        border-radius: 0px 20px 0px 0px;
      }

      &>div:nth-child(30) {
        border-radius: 0px 0px 0px 20px;
      }

      &>div:nth-child(32) {
        border-radius: 0px 0px 20px 0px;
      }
    }
  }

  .tooth_tray_flow_custom_made_bg {
    background: linear-gradient(0deg, rgba(255, 241, 240, 0.00) 0%, rgba(255, 241, 240, 0.70) 12.5%, rgba(255, 241, 240, 0.70) 81.99%, rgba(255, 241, 240, 0.00) 100%);

    .tooth_tray_flow_custom_made {
      box-sizing: border-box;
      padding: 30px 0;

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
          border: 1px solid transparent;
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
          border-right: 1px solid var(--Grey-Light, #E6E6E6);
          border-radius: 10px 0 0 10px;
          border: 1px solid var(--Grey-Light, #E6E6E6);
          border-right: none;
        }

        .flow_custom_made_tab_text:nth-child(2) {
          border-left: 1px solid var(--Grey-Light, #E6E6E6);
          border-radius: 0 10px 10px 0;
          border: 1px solid var(--Grey-Light, #E6E6E6);
          border-left: none;
        }


      }

      .flow_custom_made_tab_collapse {
        .wrapper {
          animation: identifier 0.5s ease forwards;
        }

        .flow_custom_made_tab_item {
          margin: 10px 0;
          display: flex;
          width: 100%;
          gap: 0 10px;
        }

        .flow_custom_made_tab_item:nth-child(1) {
          .color-block {
            opacity: 0.2;
            clip-path: polygon(50% 0%, 100% 0, 100% 85%, 50% 100%, 0 85%, 0 0);
          }
        }

        .flow_custom_made_tab_item:nth-child(2) {
          .color-block {
            opacity: 0.4;
          }
        }

        .flow_custom_made_tab_item:nth-child(3) {
          .color-block {
            opacity: 0.6;
          }
        }

        .flow_custom_made_tab_item:nth-child(4) {
          .color-block {
            opacity: 0.8;
          }
        }

        .flow_custom_made_tab_item:nth-child(5) {
          .color-block {
            opacity: 1;
          }
        }

        .flow_custom_made_tab_item-container {
          width: 100%;
          display: flex;
          flex-direction: column;
        }

        .flow_custom_made_tab_item-header {
          width: 100%;
          display: flex;
          align-items: center;
          cursor: pointer;
          border-radius: 0px 10px 10px 0px;
          background: var(--White, #FFF);
          height: 50px;
          box-sizing: border-box;
          padding: 9px 15px;
          display: flex;
          align-items: center;
          justify-content: flex-start;
          gap: 0 9px;
          position: relative;

          &>div:nth-child(1) {
            color: var(--Theme-Color, #FC1682);

            /* 桌面版/PC-18Pt字（粗） */
            font-family: "Noto Sans HK";
            font-size: 18px;
            font-style: normal;
            font-weight: 700;
            line-height: 200%;
            /* 36px */
            letter-spacing: 1.8px;
          }

          &>div:nth-child(2) {
            color: var(--Grey-Dark, #333);
            text-align: justify;
            font-family: "Noto Sans HK";
            font-size: 18px;
            font-style: normal;
            font-weight: 700;
            line-height: 200%;
            letter-spacing: 1.8px;
          }

          &>div:nth-child(3) {
            position: absolute;
            right: 15px;
            top: 50%;
            transform: translateY(-50%);
            font-size: 28px;
            color: var(--Theme-Color, #FC1682);
            font-weight: 900;
            transition: all 0.3s ease;
          }
        }

        .color-block {
          width: 10px;
          width: 43px;
          height: 55px;
          background-color: #ff60a7;
          transition: all 0.3s ease;
          clip-path: polygon(50% 15%, 100% 0, 100% 85%, 50% 100%, 0 85%, 0 0);
        }

        .color-block-active {
          transition: all 0.3s ease;
          clip-path: polygon(50% 5%, 100% 0, 100% 90%, 50% 100%, 0 90%, 0 0);
        }

        .flow_custom_made_tab_item-header span {
          margin-left: 10px;
          font-size: 16px;
        }

        .flow_custom_made_tab_item-content {
          margin-top: 10px;
          padding: 15px;
          transition: all 0.3s ease;
          border-radius: 10px;
          background: var(--White, #FFF);

          &>div {
            strong {
              color: var(--Theme-Color, #FC1682);
              text-align: justify;
              font-family: "Noto Sans HK";
              font-size: 18px;
              font-style: normal;
              font-weight: 700;
              line-height: 200%;
              letter-spacing: 1.8px;
            }

            color: var(--Grey-Deep, #4D4D4D);
            font-family: "Noto Sans HK";
            font-size: 18px;
            font-style: normal;
            font-weight: 700;
            line-height: 200%;
            letter-spacing: 1.8px;
          }
        }
      }
    }
  }

  .tooth_tray_flow_advantage {
    box-sizing: border-box;
    padding: 30px 0;

    .tooth_tray_flow_advantage_content {
      margin-top: 20px;
      display: flex;
      gap: 0 30px;

      &>div {
        width: 217px;
        height: 365px;
        border-radius: 10px;
        border: 2px solid var(--Pink-Mid, #FFA5CF);
        background: linear-gradient(194deg, #FEE6F1 3.13%, rgba(254, 230, 241, 0.00) 49.04%), var(--White, #FFF);
        box-sizing: border-box;
        padding: 15px 20px 20px;
        display: flex;
        flex-direction: column;

        &>div:nth-child(1) {
          width: 120px;
          height: 120px;
          display: flex;
          align-items: center;
          justify-content: center;
          margin: 0 auto;

          &>img {
            width: 100%;
            height: 100%;
            object-fit: cover;
          }

        }

        &>div:nth-child(2) {
          margin: 5px 0;
          color: var(--Theme-Color, #FC1682);
          text-align: center;
          font-family: "Noto Sans HK";
          font-size: 24px;
          font-style: normal;
          font-weight: 700;
          line-height: 120%;
          letter-spacing: 2.4px;

          span {
            font-size: 18px;
            letter-spacing: 1.8px;
          }
        }

        &>div:nth-child(3) {
          color: var(--Grey-Dark, #333);
          text-align: justify;
          font-family: "Noto Sans HK";
          font-size: 17px;
          font-style: normal;
          font-weight: 400;
          line-height: 200%;
          letter-spacing: 1.8px;
        }
      }

      &>div:last-child {
        &>div:nth-child(2) {
          color: var(--GHV-Green, #01A853);
        }
      }
    }


  }

  .tooth_tray_flow_share {
    box-sizing: border-box;
    padding: 30px 0;

    .tooth_tray_flow_share_content {
      margin-top: 30px;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 0 5px;

      &>div:nth-child(2) {
        color: var(--Theme-Color, #FC1682);
        text-align: center;
        font-family: "Noto Sans HK";
        font-size: 24px;
        font-style: normal;
        font-weight: 700;
        line-height: 120%;
        letter-spacing: 2.4px;
        padding-bottom: 20px;
      }

      &>div:first-child,
      &>div:last-child {
        color: #FDD3E3;
        text-align: center;
        font-family: "Noto Sans HK";
        font-size: 48px;
        font-style: normal;
        font-weight: 700;
        line-height: 100%;
        letter-spacing: 9.6px;
      }
    }
  }

  .tooth_tray_flow_share_bg {
    background: linear-gradient(184deg, var(--Pink-Pale, #FFE9EC) 13.58%, rgba(255, 255, 255, 0.00) 96.98%);
    box-sizing: border-box;
    padding: 85px 0 50px;
    width: 100%;
    position: relative;

    :deep(.swiper) {
      max-width: 960px;
      margin: 0 auto;
      overflow: initial;
    }

    .swiper_share_item {
      width: 300px;
      height: 275px;
      border-radius: 10px;
      border: 2px solid var(--Pink-Mid, #FFA5CF);
      background: linear-gradient(191deg, #FFF 3.08%, rgba(255, 255, 255, 0.00) 98.82%), var(--White, #FFF);
      position: relative;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      box-sizing: border-box;
      padding: 75px 20px 20px;
      position: relative;

      &>img {
        position: absolute;
        width: 135px;
        height: 135px;
        object-fit: cover;
        top: -65px;
      }

      h3 {
        color: var(--Grey-Dark, #333);
        text-align: center;
        font-family: "Noto Sans HK";
        font-size: 18px;
        font-style: normal;
        font-weight: 700;
        line-height: 200%;
        letter-spacing: 1.8px;
      }

      p:nth-child(3) {
        color: var(--Brand-Color, #F8298A);
        text-align: center;
        font-family: "Noto Sans HK";
        font-size: 18px;
        font-style: normal;
        font-weight: 400;
        line-height: 200%;
        letter-spacing: 1.8px;
      }

      p:nth-child(4) {
        color: var(--Grey-Dark, #333);
        text-align: justify;
        font-family: "Noto Sans HK";
        font-size: 18px;
        font-style: normal;
        font-weight: 400;
        line-height: 200%;
        letter-spacing: 1.8px;
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
      box-shadow: 0px 0px 2.665vw rgba(0, 0, 0, 0.3);
      opacity: 1;
      margin: 0;
    }

    .swiper-pagination {
      position: initial;
      display: flex;
      align-items: center;
      gap: 0 10px;
      margin: 0 10px;
    }

    .swiper-pagination-bullet {
      width: 18px;
      height: 18px;
      background: #fff;
      box-shadow: 0px 0px 2.665vw rgba(0, 0, 0, 0.3);
      opacity: 1;
      margin: 0;
      cursor: pointer;
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
      box-shadow: 0px 0px 2.665vw rgba(0, 0, 0, 0.3);
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

  .tooth_tray_flow_problem {
    box-sizing: border-box;
    padding: 30px 0;

    :deep(.problem) {
      margin: 0;
    }
  }

  .tooth_tray_new_steps {
    margin-bottom: 15px;

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

}

@keyframes identifier {
  0% {
    opacity: 0;
  }

  100% {
    opacity: 1;
  }
}

@media screen and (max-width: 991px) {
  .tooth_tray {
    margin-top: 30px;
  }

  .tooth_tray_comparison {
    margin: 30px 0;

    .tooth_tray_content {
      box-sizing: border-box;
      padding: 0 30px;
      margin-top: 20px;

      &>div {
        color: var(--Grey-Deep, #4D4D4D);

        /* 手機版/MB-14Pt字（粗） */
        font-family: "Noto Sans HK";
        font-size: 14px;
        font-style: normal;
        font-weight: 600;
        line-height: 150%;
        letter-spacing: 0.7px;

        span {
          color: var(--Brand-Color, #F8298A);
        }
      }
    }
  }

  .tooth_tray_new_technique {
    margin: 30px 0 0;

    .tooth_tray_table {
      box-sizing: border-box;
      padding: 0 15px;
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      box-sizing: border-box;


      &>div:nth-child(3n + 1) {
        width: 65px;
        border: 1px solid var(--Brand-Color, #F8298A);
        background: var(--Brand-Color, #F8298A);
        display: flex;
        align-items: center;
        justify-content: center;
        color: var(--White, #FFF);
        text-align: center;
        font-family: "Noto Sans HK";
        font-size: 12px;
        font-style: normal;
        font-weight: 500;
        line-height: 150%;
        box-sizing: border-box;
        padding: 6px 0;
        border-bottom: 3px solid var(--Brand-Color, #F8298A);
      }

      &>div:nth-child(3n + 2),
      &>div:nth-child(3n + 3) {
        width: 140px;
        background: var(--White, #fff);
        color: var(--Grey-Dark, #333);
        text-align: center;
        font-family: "Noto Sans HK";
        font-size: 12px;
        font-style: normal;
        font-weight: 400;
        line-height: 150%;
        display: flex;
        align-items: center;
        justify-content: center;
      }

      &>div:nth-child(1),
      &>div:nth-child(2),
      &>div:nth-child(3),
      &>div:nth-child(4),
      &>div:nth-child(7) {
        background: transparent;
        border: none;
      }

      &>div:nth-child(10) {
        border-radius: 10px 0px 0px 0px;
        border-top: 3px solid var(--Brand-Color, #F8298A);
      }

      &>div:nth-child(31) {
        border-radius: 0px 0px 0px 10px;
      }

      &>div:nth-child(2) {
        color: var(--Brand-Color, #F8298A);
        text-align: center;
        font-family: "Noto Sans HK";
        font-size: 14px;
        font-style: normal;
        font-weight: 700;
        line-height: normal;
        margin-bottom: 20px;
      }

      &>div:nth-child(5) {
        border-radius: 10px 10px 0px 0px;
        border-top: 4px solid var(--Brand-Color, #F8298A);
        background: var(--Brand-Color, #F8298A);
        color: var(--White, #FFF);
        text-align: center;
        font-family: "Noto Sans HK";
        font-size: 16px;
        font-style: normal;
        font-weight: 700;
        line-height: 150%;
        letter-spacing: 1.6px;
        display: flex;
        align-items: center;
        justify-content: center;
        box-sizing: border-box;
        padding: 5px 0;
        position: relative;
      }

      &>div:nth-child(5)::after {
        content: "";
        position: absolute;
        top: -24px;
        left: 50%;
        transform: translateX(-50%);
        width: 19.791px;
        height: 12.007px;
        background: url(/_nuxt/assets/images/group3910.svg) no-repeat;
        background-size: contain;
        z-index: 1;
      }

      &>div:nth-child(6) {
        border-radius: 20px 10px 0px 0px;
        background: var(--Blue-Deep, #00AEFF);
        color: var(--White, #FFF);
        text-align: center;
        font-family: "Noto Sans HK";
        font-size: 16px;
        font-style: normal;
        font-weight: 700;
        line-height: 150%;
        letter-spacing: 1.6px;
        display: flex;
        align-items: center;
        justify-content: center;
        box-sizing: border-box;
        padding: 5px 0;
      }

      &>div:nth-child(8),
      &>div:nth-child(9) {
        width: 100%;
        height: 100%;

        &>img {
          width: 100%;
          height: 100%;
          object-fit: cover;
        }
      }

      &>div:nth-child(11),
      &>div:nth-child(12),
      &>div:nth-child(14),
      &>div:nth-child(15),
      &>div:nth-child(17),
      &>div:nth-child(18),
      &>div:nth-child(20),
      &>div:nth-child(21),
      &>div:nth-child(23),
      &>div:nth-child(24),
      &>div:nth-child(26),
      &>div:nth-child(27),
      &>div:nth-child(32) {
        position: relative;
      }

      &>div:nth-child(12),
      &>div:nth-child(15),
      &>div:nth-child(18),
      &>div:nth-child(21),
      &>div:nth-child(24),
      &>div:nth-child(27),
      &>div:nth-child(30) {
        border-right: 3px solid var(--Grey-Lightest, #F2F2F2);
      }

      &>div:nth-child(11)::after,
      &>div:nth-child(12)::after,
      &>div:nth-child(14)::after,
      &>div:nth-child(15)::after,
      &>div:nth-child(17)::after,
      &>div:nth-child(18)::after,
      &>div:nth-child(20)::after,
      &>div:nth-child(21)::after,
      &>div:nth-child(23)::after,
      &>div:nth-child(24)::after,
      &>div:nth-child(26)::after,
      &>div:nth-child(27)::after,
      &>div:nth-child(32)::after {
        content: '';
        position: absolute;
        bottom: 0;
        left: 0;
        width: 100%;
        height: 3px;
        background: var(--Grey-Lightest, #F2F2F2);
      }

      &>div:nth-child(5),
      &>div:nth-child(8),
      &>div:nth-child(11),
      &>div:nth-child(14),
      &>div:nth-child(17),
      &>div:nth-child(20),
      &>div:nth-child(23),
      &>div:nth-child(26),
      &>div:nth-child(29) {
        border-left: 4px solid var(--Brand-Color, #F8298A);
        border-right: 4px solid var(--Brand-Color, #F8298A);
      }

      &>div:nth-child(29) {
        border-bottom: 4px solid var(--Brand-Color, #F8298A);
      }

      &>div:nth-child(33) {
        border: 4px solid var(--Blue-Deep, #00AEFF);
        border-radius: 0px 0px 10px 0px;

      }
    }
  }

  .tooth_tray_share_food {
    margin: 7px 0 30px;

    .tooth_tray_share_food_content {
      margin-top: 7px;
      box-sizing: border-box;
      padding: 0 30px;
      color: var(--Grey-Deep, #4D4D4D);
      text-align: justify;
      font-family: "Noto Sans HK";
      font-size: 12px;
      font-style: normal;
      font-weight: 400;
      line-height: 150%;
      letter-spacing: 0.6px;
    }
  }

  .tooth_tray_service {
    margin: 30px 0;

    .tooth_tray_step {
      margin-top: 20px;
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 7.2vw 4.8vw;
      box-sizing: border-box;
      padding: 0 20px;

      .fillings-step-item {
        position: relative;

        &>div:nth-child(1) {
          position: absolute;
          z-index: 3;
          top: -1.06vw;
          left: -1.06vw;
          color: var(--White, #fff);
          font-family: 'Noto Sans HK';
          font-size: 4.8vw;
          font-style: normal;
          font-weight: 700;
          line-height: normal;
          letter-spacing: 0.48vw;
          background: url(https://static.cmereye.com/imgs/2024/11/3b0a5e9326c68638.png) no-repeat;
          background-size: cover;
          width: 8vw;
          height: 8vw;
          display: flex;
          align-items: center;
          justify-content: center;
        }

        &>div:nth-child(2) {
          position: relative;
        }

        &>div:nth-child(2)::after {
          content: '';
          position: absolute;
          width: 2.93vw;
          height: 6.4vw;
          background: url(https://static.ckjhk.com/ckj-image/2025032009130001.png) no-repeat;
          background-size: cover;
          top: 50%;
          right: -2vw;
          z-index: -1;
          transform: translateY(-50%);
        }

        &>div:nth-child(3) {
          margin-top: 4px;
          display: flex;
          flex-direction: column;
          box-sizing: border-box;
          padding: 0 6px;

          &>span:nth-child(1) {
            color: var(--Brand-Color, #F8298A);
            text-align: center;
            font-family: "Noto Sans HK";
            font-size: 14px;
            font-style: normal;
            font-weight: 600;
            line-height: 150%;
            letter-spacing: 0.7px;
          }

          &>span:nth-child(2) {
            color: #000;
            font-family: "Noto Sans HK";
            font-size: 12px;
            font-style: normal;
            font-weight: 400;
            line-height: 150%;
            letter-spacing: 0.5px;
          }
        }
      }

      .fillings-step-item:last-child {
        &>div:nth-child(2)::after {
          content: none;
        }
      }

      .fillings-step-item-last {
        display: flex;
        align-items: center;
        justify-content: center;

        &>img {
          transform: scale(1.5);
        }
      }
    }

    .tooth_tray_btn {
      margin-top: 15px;
      display: flex;
      align-items: center;
      justify-content: center;
    }
  }

  .tooth_tray_compare_kind {
    margin: 30px 0;

    .tooth_tray_compare_kind_tab {
      display: flex;
      align-items: center;
      justify-content: center;
      margin: 20px 0 8px;

      &>div:nth-child(1) {
        border-radius: 5px 0px 0px 5px;
      }

      &>div:nth-child(2) {
        border-radius: 0px 5px 5px 0px;
        border-right: 1px solid var(--Grey-Light, #E6E6E6);
      }

      .tooth_tray_compare_kind_btn {
        border-left: 1px solid var(--Grey-Light, #E6E6E6);
        border-top: 1px solid var(--Grey-Light, #E6E6E6);
        border-bottom: 1px solid var(--Grey-Light, #E6E6E6);
        background: var(--White, #FFF);
        box-sizing: border-box;
        padding: 5px 40px;
      }

      .tooth_tray_compare_kind_btn_active {
        background: var(--Brand-Color, #F8298A);
        color: var(--White, #FFF);
        border: 1px solid var(--Brand-Color, #F8298A);
      }

    }

    .tooth_tray_compare_kind_table {
      box-sizing: border-box;
      padding: 0 15px;
      display: grid;
      grid-template-columns: repeat(3, 1fr);

      &>div {
        width: 140px;
        border-bottom: 0.2px solid var(--Grey-Light, #E6E6E6);
        border-right: 0.2px solid var(--Grey-Light, #E6E6E6);
        box-sizing: border-box;
        padding: 5px 3px;
        display: flex;
        align-items: center;
        justify-content: center;
        color: var(--Grey-Dark, #333);
        font-family: "Noto Sans HK";
        font-size: 12px;
        font-style: normal;
        font-weight: 400;
        line-height: 150%;
        letter-spacing: 0px;
        flex-direction: column;

        span {
          display: flex;
          align-items: center;
          justify-content: flex-start;
          color: var(--Grey-Dark, #333);
          font-family: "Noto Sans HK";
          font-size: 12px;
          font-style: normal;
          font-weight: 400;
          line-height: 150%;
          letter-spacing: 0px;
          width: 100%;
          padding-left: 12px;
          position: relative;
        }

        span::before {
          content: '·';
          position: absolute;
          left: 1px;
          top: 9px;
          transform: translateY(-50%);
          color: var(--Grey-Dark, #333);
          font-family: "Noto Sans HK";
          font-size: 12px;
          font-style: normal;
          font-weight: 400;
          line-height: 150%;
          letter-spacing: 0px;
        }
      }

      &>div:nth-child(1) {
        grid-row: span 2;
      }

      .table_two_col {
        grid-column: span 2;
        width: calc(140px * 2);
        display: flex;
        align-items: center;
        justify-content: center;

        &>span {
          width: fit-content;
          display: flex;
          justify-content: center;
        }
      }

      .table_img_box {
        padding: 0;
        width: 100%;
        height: 100%;
        overflow: hidden;

        &>img {
          width: 100%;
          height: 100%;
          object-fit: cover;
          transform: scale(1.01);
        }
      }

      .table_row_one {
        width: 65px;
        border: 1px solid var(--Pink-Mid, #F670AE);
        background: var(--Brand-Color, #F8298A);
        color: var(--White, #FFF);
        text-align: center;
        font-family: "Noto Sans HK";
        font-size: 12px;
        font-style: normal;
        font-weight: 400;
        line-height: 150%;
        letter-spacing: 0px;
        display: flex;
        align-items: center;
        justify-content: center;
      }

      &>div:nth-child(1) {
        border-radius: 20px 0px 0px 0px;
      }

      .table_pink_title_box {
        border: 1px solid var(--Grey-Light, #E6E6E6);
        background: var(--Pink-Mid, #F670AE);
        color: var(--White, #FFF);
        text-align: center;
        font-family: "Noto Sans HK";
        font-size: 12px;
        font-style: normal;
        font-weight: 400;
        line-height: 150%;
        letter-spacing: 0px;
      }

      .table_blue_title_box {
        border: 1px solid var(--Grey-Light, #E6E6E6);
        background: var(--Blue-Deep, #00AEFF);
        color: var(--White, #FFF);
        text-align: center;
        font-family: "Noto Sans HK";
        font-size: 12px;
        font-style: normal;
        font-weight: 400;
        line-height: 150%;
        letter-spacing: 0px;
      }

      &>div:nth-child(5) {
        border-radius: 0px 20px 0px 0px;
      }

      &>div:nth-child(30) {
        border-radius: 0px 0px 0px 20px;
      }

      &>div:nth-child(32) {
        border-radius: 0px 0px 20px 0px;
      }
    }
  }

  .tooth_tray_flow_custom_made_bg {
    background: linear-gradient(0deg, rgba(255, 241, 240, 0.00) 0%, rgba(255, 241, 240, 0.70) 12.5%, rgba(255, 241, 240, 0.70) 81.99%, rgba(255, 241, 240, 0.00) 100%);

    .tooth_tray_flow_custom_made {
      margin: 30px 0;

      .flow_custom_made_tab {
        margin: 20px auto;
        box-sizing: border-box;
        padding: 0 20px;
        display: flex;
        justify-content: center;
        align-items: center;

        .flow_custom_made_tab_text {
          color: var(--Grey-Mid, #666);
          text-align: center;

          /* 桌面版/PC-頂部目錄 */
          font-family: "Noto Sans TC";
          font-size: 16px;
          font-style: normal;
          font-weight: 700;
          line-height: 150%;
          /* 24px */
          letter-spacing: 1px;
          box-sizing: border-box;
          padding: 5.5px 40px;
          background: var(--White, #FFF);
        }

        .flow_custom_made_tab_active {
          transition: all 0.3s ease;
          color: var(--White, #FFF);
          text-align: center;
          font-family: "Noto Sans TC";
          font-size: 16px;
          font-style: normal;
          font-weight: 700;
          line-height: 150%;
          letter-spacing: 1px;
          background: var(--Brand-Color, #F8298A);
          border: 1px solid transparent;
          position: relative;
        }

        .flow_custom_made_tab_text:nth-child(1) {
          border-right: 1px solid var(--Grey-Light, #E6E6E6);
          border-radius: 5px 0 0 5px;
          border: 1px solid var(--Grey-Light, #E6E6E6);
          border-right: none;
        }

        .flow_custom_made_tab_text:nth-child(2) {
          border-left: 1px solid var(--Grey-Light, #E6E6E6);
          border-radius: 0 5px 5px 0;
          border: 1px solid var(--Grey-Light, #E6E6E6);
          border-left: none;
        }

      }

      .flow_custom_made_tab_collapse {
        box-sizing: border-box;
        padding: 0 20px;

        .wrapper {
          animation: identifier 0.5s ease forwards;
        }

        .flow_custom_made_tab_item {
          margin: 3px 0;
          display: flex;
          width: 100%;
          gap: 0 3px;
        }

        .flow_custom_made_tab_item:nth-child(1) {
          .color-block {
            opacity: 0.2;
            clip-path: polygon(50% 0%, 100% 0, 100% 85%, 50% 100%, 0 85%, 0 0);
          }
        }

        .flow_custom_made_tab_item:nth-child(2) {
          .color-block {
            opacity: 0.4;
          }
        }

        .flow_custom_made_tab_item:nth-child(3) {
          .color-block {
            opacity: 0.6;
          }
        }

        .flow_custom_made_tab_item:nth-child(4) {
          .color-block {
            opacity: 0.8;
          }
        }

        .flow_custom_made_tab_item:nth-child(5) {
          .color-block {
            opacity: 1;
          }
        }

        .flow_custom_made_tab_item-container {
          width: 100%;
          display: flex;
          flex-direction: column;
        }

        .flow_custom_made_tab_item-header {
          width: 100%;
          display: flex;
          align-items: center;
          cursor: pointer;
          border-radius: 0px 5px 5px 0px;
          background: var(--White, #FFF);
          height: 40px;
          box-sizing: border-box;
          padding: 9px 11px;
          display: flex;
          align-items: center;
          justify-content: flex-start;
          gap: 0 9px;
          position: relative;

          &>div:nth-child(1) {
            color: var(--Theme-Color, #FC1682);
            font-family: "Noto Sans HK";
            font-size: 14px;
            font-style: normal;
            font-weight: 600;
            line-height: 150%;
            letter-spacing: 0.7px;
          }

          &>div:nth-child(2) {
            color: var(--Grey-Dark, #333);
            text-align: justify;
            font-family: "Noto Sans HK";
            font-size: 14px;
            font-style: normal;
            font-weight: 600;
            line-height: 150%;
            letter-spacing: 0.7px;
          }

          &>div:nth-child(3) {
            position: absolute;
            right: 11px;
            top: 50%;
            transform: translateY(-50%);
            font-size: 18px;
            color: var(--Theme-Color, #FC1682);
            font-weight: 900;
            transition: all 0.3s ease;
          }
        }

        .color-block {
          width: 27px;
          height: 40px;
          background-color: #ff60a7;
          transition: all 0.3s ease;
          clip-path: polygon(50% 15%, 100% 0, 100% 85%, 50% 100%, 0 85%, 0 0);
        }

        .color-block-active {
          transition: all 0.3s ease;
          clip-path: polygon(50% 5%, 100% 0, 100% 90%, 50% 100%, 0 90%, 0 0);
        }

        .flow_custom_made_tab_item-header span {
          margin-left: 10px;
          font-size: 16px;
        }

        .flow_custom_made_tab_item-content {
          margin-top: 0;
          padding: 0px 30px 9px 30px;
          transition: all 0.3s ease;
          border-radius: 10px;
          background: var(--White, #FFF);

          &>div {
            strong {
              color: var(--Theme-Color, #FC1682);
              text-align: justify;
              font-family: "Noto Sans HK";
              font-size: 12px;
              font-style: normal;
              font-weight: 400;
              line-height: 150%;
              /* 18px */
              letter-spacing: 0.6px;
            }

            color: var(--Grey-Deep, #4D4D4D);
            font-family: "Noto Sans HK";
            font-size: 12px;
            font-style: normal;
            font-weight: 400;
            line-height: 150%;
            /* 18px */
            letter-spacing: 0.6px;
          }
        }
      }
    }
  }

  .tooth_tray_flow_advantage {
    margin: 30px 0 70px;

    .tooth_tray_flow_advantage_content {
      margin-top: 20px;
      margin-left: 20px;
      display: flex;
      gap: 0 14px;
      width: 720px;
      overflow-x: scroll;
      overflow-y: hidden;
      scrollbar-width: none;
      -ms-overflow-style: none;
      scroll-behavior: smooth;
      padding-right: 370px;

      &>div {
        width: 180px;
        min-width: 180px;
        height: 298px;
        border-radius: 10px;
        border: 2px solid var(--Pink-Mid, #FFA5CF);
        background: linear-gradient(194deg, #FEE6F1 3.13%, rgba(254, 230, 241, 0.00) 49.04%), var(--White, #FFF);
        box-sizing: border-box;
        padding: 14px 17px 18px 21px;
        display: flex;
        flex-direction: column;

        &>div:nth-child(1) {
          width: 120px;
          height: 120px;
          display: flex;
          align-items: center;
          justify-content: center;
          margin: 0 auto;

          &>img {
            width: 100%;
            height: 100%;
            object-fit: cover;
          }

        }

        &>div:nth-child(2) {
          margin: 8px 0 12px;
          color: var(--Theme-Color, #FC1682);
          text-align: center;
          font-family: "Noto Sans HK";
          font-size: 18px;
          font-style: normal;
          font-weight: 700;
          line-height: 120%;
          /* 21.6px */
          letter-spacing: 1.8px;

          span {
            font-size: 16px;
            letter-spacing: 1.6px;
          }
        }

        &>div:nth-child(3) {
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

      &>div:last-child {
        &>div:nth-child(2) {
          color: var(--GHV-Green, #01A853);
        }
      }
    }

    .tooth_tray_flow_advantage_scroll_button_wrapper {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 0 10px;
      position: absolute;
      margin: 20px auto;
      width: 100%;

      .scroll_button {
        width: 3.21vw;
        height: 3.2vw;
        overflow: hidden;
        border-radius: 50%;
        background: #fff;
        box-shadow: 0px 5.333px 5.333px rgba(77, 77, 77, 0.2);
      }

      .scroll_button_active {
        background: var(--Pink-Mid, #f670ae);
        filter: drop-shadow(0px 4px 4px rgba(77, 77, 77, 0.2));
        transition: all 0.3s ease-in-out;
      }

      &>div:first-child,
      &>div:last-child {
        width: 5.33vw;
        height: 5.33vw;
        overflow: hidden;
        border-radius: 50%;
        background: url('~/assets/images/2025040215172701.svg') no-repeat;
        background-size: cover;
        box-shadow: 0px 5.333px 5.333px rgba(77, 77, 77, 0.2);
      }

      &>div:last-child {
        transform: rotate(180deg);
        box-shadow: -5.333px -5.333px 5.333px rgba(77, 77, 77, 0.2);
      }
    }
  }

  .tooth_tray_flow_share {
    margin: 30px 0 0;

    .tooth_tray_flow_share_content {
      margin-top: 20px;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 0 0px;

      &>div:nth-child(2) {
        color: var(--Theme-Color, #FC1682);
        text-align: center;
        font-family: "Noto Sans HK";
        font-size: 18px;
        font-style: normal;
        font-weight: 700;
        line-height: 120%;
        /* 21.6px */
        letter-spacing: 1.8px;
        padding-bottom: 24px;
      }

      &>div:first-child,
      &>div:last-child {
        color: #FDD3E3;
        text-align: center;
        font-family: "Noto Sans HK";
        font-size: 48px;
        font-style: normal;
        font-weight: 700;
        line-height: 100%;
        letter-spacing: 9.6px;
      }
    }
  }

  .tooth_tray_flow_share_bg {
    background: linear-gradient(184deg, var(--Pink-Pale, #FFE9EC) 13.58%, rgba(255, 255, 255, 0.00) 96.98%);
    box-sizing: border-box;
    padding: 85px 0 50px;
    position: relative;
    // margin-left: 20px;

    :deep(.swiper) {
      max-width: 100%;
      margin: 0 auto 0 20px;
      overflow: initial;
    }

    .swiper_share_item {
      // width: 180px;
      // min-width: 180px;
      // height: 225px;
      border-radius: 10px;
      border: 2px solid var(--Pink-Mid, #FFA5CF);
      background: linear-gradient(191deg, #FFF 3.08%, rgba(255, 255, 255, 0.00) 98.82%), var(--White, #FFF);
      position: relative;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      box-sizing: border-box;
      padding: 75px 15px 15px;
      position: relative;

      &>img {
        position: absolute;
        width: 124px;
        height: 124px;
        object-fit: cover;
        top: -65px;
      }

      h3 {
        color: var(--Grey-Dark, #333);
        text-align: center;
        font-family: "Noto Sans HK";
        font-size: 14px;
        font-style: normal;
        font-weight: 600;
        line-height: 150%;
        /* 21px */
        letter-spacing: 0.7px;
      }

      p:nth-child(3) {
        color: var(--Brand-Color, #F8298A);
        text-align: center;
        font-family: "Noto Sans HK";
        font-size: 14px;
        font-style: normal;
        font-weight: 600;
        line-height: 150%;
        /* 21px */
        letter-spacing: 0.7px;
      }

      p:nth-child(4) {
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

    .swiper-button-prev:after,
    .swiper-button-next:after {
      display: none;
    }

    .swiper-pagination-bullet {
      width: 3.2vw;
      height: 3.2vw;
      background: #fff;
      box-shadow: 0px 0px 2.665vw rgba(0, 0, 0, 0.3);
      opacity: 1;
      margin: 0;
    }

    .swiper-pagination {
      position: initial;
      display: flex;
      align-items: center;
      gap: 0 10px;
      margin: 0 10px;
    }

    .swiper-pagination-bullet {
      width: 18px;
      height: 18px;
      background: #fff;
      box-shadow: 0px 0px 2.665vw rgba(0, 0, 0, 0.3);
      opacity: 1;
      margin: 0;
      cursor: pointer;
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
      box-shadow: 0px 0px 2.665vw rgba(0, 0, 0, 0.3);
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

  .tooth_tray_new_steps {
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
}
</style>

<style lang="scss" scoped>
.banner-in-box {
  position: absolute;
  top: 50%;
  left: 0;
  transform: translateY(-50%);
  height: 20.83vw;
  width: 100%;
  z-index: 10;
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

.mobile_orthodontics {
  :deep(.introduce) {
    .introduce-in-l {
      position: absolute;
      bottom: -20px;

      .content {
        width: 100%;
        padding: 0 8vw;
        font-weight: 400;
        color: var(--Grey-Deep, #4d4d4d);
        text-align: justify;
        font-family: 'Noto Sans HK';
        font-size: 16px;
      }
    }

    .mobile_new {
      margin: 6.65vw 8vw 12vw;
    }
  }
}

.reason {
  width: 100%;
  max-width: 894px;
  margin: 80px auto 0;

  &-in {
    margin-top: 40px;
    display: flex;
    align-items: center;

    &-l {
      width: 460px;
      margin-right: 48px;

      img {
        width: 100%;
      }
    }

    &-r {
      flex: 1;

      .item {
        font-size: 19px;
        font-style: normal;
        font-weight: 500;
        line-height: 160%;
        /* 30.4px */
        letter-spacing: 5.7px;
        color: var(--textColor);
        display: flex;

        &:not(:last-child) {
          margin-bottom: 20px;
        }

        &::before {
          content: none;
          font-size: 36px;
          display: inline-block;
          margin-right: 5px;
        }
      }
    }
  }
}

.contrast {
  margin-top: 100px;

  &-bg {
    padding: 76px 0 103px;
    background: linear-gradient(270deg,
        rgba(255, 241, 240, 0) 2.6%,
        rgba(255, 241, 240, 0.7) 23.89%,
        rgba(255, 241, 240, 0.7) 75.33%,
        rgba(255, 241, 240, 0) 97.4%);
  }

  &-context {
    text-align: center;
    font-style: normal;
    font-weight: 400;
    font-size: 20px;
    line-height: 160%;
    color: #666666;
    max-width: 820px;
    margin: 35px auto 0;
  }

  &-tableRemark {
    margin-top: 28px;
    font-style: normal;
    font-weight: 500;
    font-size: 20px;
    line-height: 160%;
    color: var(--indexColor1);
    text-align: center;
  }

  &-table {
    margin: 20px auto 0;
    max-width: 1452px;
    width: 100%;
    display: flex;

    &-in {
      display: flex;
      flex-direction: column;

      &>div {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;

        &.content {
          flex-direction: row;

          &>div {
            flex: 1;
            height: 100%;
            display: flex;
            flex-direction: column;
            justify-content: center;
            font-style: normal;
            font-weight: 400;
            font-size: 20px;
            line-height: 160%;
            color: #666666;
            padding: 0 18px;
            background: #ffffff;

            &>div {
              display: flex;

              span {
                &:first-child {
                  width: 20px;
                }

                &:last-child {
                  flex: 1;
                }
              }
            }
          }

          &:not(:last-child) {
            margin-bottom: 6px;
          }

          .content-l {
            margin-right: 4px;
          }

          .content-c {
            align-items: center;
          }
        }

        &:nth-of-type(1) {
          height: 271px;
          display: flex;
          margin-bottom: 6px;

          .th {
            background: var(--indexColor1);
            font-style: normal;
            font-weight: 500;
            font-size: 24px;
            line-height: 160%;
            color: #ffffff;
            margin-bottom: 6px;
            height: 69px;
            flex: initial;
          }

          &>div {
            flex: 1;
            display: flex;
            align-items: center;
            justify-content: center;
            width: 100%;

            .td {
              font-style: normal;
              font-weight: 500;
              font-size: 24px;
              line-height: 160%;
              color: var(--indexColor1);
              text-shadow: -1px -1px 0 #fff, 1px -1px 0 #fff, -1px 1px 0 #fff,
                1px 1px 0 #fff;
            }

            span {
              flex: 1;
              height: 100%;
              text-align: center;
              display: flex;
              justify-content: center;
              align-items: center;

              &:last-child {
                margin-left: 4px;
              }
            }
          }
        }

        &:nth-of-type(2) {
          height: 140px;
        }

        &:nth-of-type(3) {
          height: 125px;
        }

        &:nth-of-type(4) {
          height: 69px;
        }

        &:nth-of-type(5) {
          height: 140px;
        }

        &:nth-of-type(6) {
          height: 105px;
        }

        &:nth-of-type(7) {
          height: 87px;
        }
      }
    }

    .tableBox {
      width: 43.1%;
      margin-right: 4px;

      &.tableTab {
        width: 13.5%;
        border-radius: 60px 0 0 60px;
        overflow: hidden;

        .contrast-table-in {
          &>div {
            font-style: normal;
            font-weight: 500;
            font-size: 24px;
            line-height: 160%;
            background: var(--indexColor2);
            color: #505050;
            margin-bottom: 6px;

            &:last-child {
              margin-bottom: 0;
            }
          }
        }
      }

      &:last-child {
        border-radius: 0 60px 60px 0;
        overflow: hidden;
        margin-right: 0px;
      }

      &.tabletab-mb {
        display: none;
      }
    }
  }
}

.process {
  margin-top: 80px;

  &-in {
    width: 100%;
    max-width: 1091px;
    margin: 38px auto 0;
    overflow: hidden;
    border-radius: 65px;
  }

  .table {
    display: flex;

    &-in {
      background: var(--indexColor2);
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 0;
      flex: 1;
      min-height: 71px;

      .context {
        font-size: 19px;
        font-style: normal;
        font-weight: 400;
        line-height: 160%;
        color: var(--textColor);

        &:not(:last-child) {
          margin-bottom: 10px;
        }

        &>p {
          &::before {
            content: attr(data-name);
            color: var(--indexColor1);
          }
        }
      }

      h3 {
        color: #fff;
        text-align: center;
        font-size: 23px;
        font-style: normal;
        font-weight: 500;
        line-height: 160%;
        width: 100%;
      }

      &.text {
        padding: 30px 55px;
        align-items: flex-start;
      }

      &.h2 {
        background: var(--indexColor1);
      }

      &.h3 {
        background: #ffa8c6;
      }

      &:not(:last-child) {
        margin-right: 8px;
      }
    }

    &:not(:last-child) {
      margin-bottom: 8px;
    }
  }
}

.advantage {
  margin-top: 117px;

  &-title {
    margin-bottom: 54px;
  }

  &-lists {
    width: 100%;
    max-width: 1325px;
    margin: 0 auto;
    display: flex;

    &-in {
      flex: 1;
      margin: 0 calc((40 / 1325) * 100%);

      &-image {
        width: auto;
        margin: 0 calc((22 / 230) * 100%);
        border-radius: 10px;
        height: 0;
        padding-bottom: calc((186 / 230) * 100%);
        position: relative;

        img {
          position: absolute;
          left: 50%;
          top: 50%;
          transform: translate(-50%, -50%);
          max-width: 90%;
          max-height: 75%;
        }
      }

      &-name {
        color: var(--indexColor1);
        text-align: center;
        font-size: 22px;
        font-style: normal;
        font-weight: 500;
        line-height: 160%;
        margin: 10px 0;
      }

      &-text {
        color: var(--textColor);
        text-align: justify;
        font-size: 18px;
        font-style: normal;
        font-weight: 400;
        line-height: 160%;
        padding: 0 10px;
        letter-spacing: 3.8px;
      }
    }
  }
}

.case {
  width: 100%;
  margin-top: 97px;

  &-title {
    display: flex;
    justify-content: center;

    &-in {
      font-style: normal;
      position: relative;
      font-weight: 600;
      font-size: 30px;
      line-height: 150%;
      text-indent: 65px;
      color: #666666;
      background: url(@/assets/images/indexTitle_bg_2.png) no-repeat;
      background-size: auto 100%;
      padding-bottom: 5px;
      padding-right: 7px;
    }
  }

  &-context {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-top: 21px;

    span {
      color: #fc1682;
      text-align: center;
      font-size: 35px;
      font-style: normal;
      font-weight: 600;
      line-height: 160%;
    }
  }

  &-content {
    display: flex;
    justify-content: center;
    margin-top: 46px;
    padding: 58px 0 62px;
    background: linear-gradient(279deg,
        rgba(252, 22, 130, 0.4) -0.55%,
        rgba(252, 22, 130, 0.28) -0.54%,
        rgba(255, 168, 198, 0) 99.3%);

    &-in {
      width: 100%;
      max-width: 1560px;
      margin: 0 auto;
      display: flex;
      justify-content: center;

      &>div {
        display: flex;
        width: calc(100% / 3);
        flex-direction: column;
        background: #fff;
        padding: 14px 29px 25px;
        box-sizing: border-box;

        &:not(:first-child) {
          margin-left: 16px;
        }
      }

      &-l {
        display: flex;

        img {
          border-radius: 50%;
          margin-top: -36%;
          border: 8px solid #fff;
        }

        span {
          display: block;
          margin-left: 18px;

          &:nth-of-type(1) {
            color: #4d4d4d;
            font-size: 28px;
            font-style: normal;
            font-weight: 600;
            line-height: 160%;
          }

          &:nth-of-type(2) {
            color: #fc1682;
            font-size: 21px;
            font-style: normal;
            font-weight: 500;
            line-height: 160%;
          }
        }
      }

      &-r {
        margin-top: 15px;
        color: #4d4d4d;
        text-align: justify;
        font-size: 20px;
        font-style: normal;
        font-weight: 500;
        line-height: 160%;
      }
    }
  }
}

@media (min-width: 768px) and (max-width: 1920px) {
  .mobile_orthodontics {
    :deep(.introduce) {
      .introduce-in-l {
        position: absolute;
        bottom: -20px;

        .content {
          width: 100%;
          padding: 0 8vw;
          font-weight: 400;
          color: var(--Grey-Deep, #4d4d4d);
          text-align: justify;
          font-family: 'Noto Sans HK';
          font-size: 16px;
        }
      }

      .mobile_new {
        margin: 6.65vw 8vw 12vw;
      }
    }
  }

  .reason {
    max-width: 46.5625vw;
    margin: 4.1667vw auto 0;

    &-in {
      margin-top: 2.0833vw;

      &-l {
        width: 23.9583vw;
        margin-right: 2.5vw;
      }

      &-r {
        .item {
          font-size: 0.9896vw;
          letter-spacing: 0.2969vw;

          &:not(:last-child) {
            margin-bottom: 1.0417vw;
          }

          &::before {
            font-size: 1.875vw;
            margin-right: 0.2604vw;
          }
        }
      }
    }
  }

  .contrast {
    margin-top: 5.2083vw;

    &-bg {
      padding: 3.9583vw 0 5.3646vw;
    }

    &-context {
      font-size: 1.0417vw;
      max-width: 42.7083vw;
      margin: 1.8229vw auto 0;
    }

    &-tableRemark {
      margin-top: 1.4583vw;
      font-size: 1.0417vw;
    }

    &-table {
      margin: 1.0417vw auto 0;
      max-width: 75.625vw;

      &-in {
        &>div {
          &.content {
            &>div {
              font-size: 1.0417vw;
              padding: 0 0.9375vw;

              &>div {
                span {
                  &:first-child {
                    width: 1.0417vw;
                  }
                }
              }
            }

            &:not(:last-child) {
              margin-bottom: 0.3125vw;
            }

            .content-l {
              margin-right: 0.2083vw;
            }
          }

          &:nth-of-type(1) {
            height: 14.1146vw;
            margin-bottom: 0.3125vw;

            .th {
              font-size: 1.25vw;
              margin-bottom: 0.3125vw;
              height: 3.5938vw;
            }

            &>div {
              .td {
                font-size: 1.25vw;
              }

              span {
                &:last-child {
                  margin-left: 0.2083vw;
                }
              }
            }
          }

          &:nth-of-type(2) {
            height: 7.2917vw;
          }

          &:nth-of-type(3) {
            height: 6.5104vw;
          }

          &:nth-of-type(4) {
            height: 3.5938vw;
          }

          &:nth-of-type(5) {
            height: 7.2917vw;
          }

          &:nth-of-type(6) {
            height: 5.4688vw;
          }

          &:nth-of-type(7) {
            height: 4.5313vw;
          }
        }
      }

      .tableBox {
        margin-right: 0.2083vw;

        &.tableTab {
          border-radius: 3.125vw 0 0 3.125vw;

          .contrast-table-in {
            &>div {
              font-size: 1.25vw;
              margin-bottom: 0.3125vw;
            }
          }
        }

        &:last-child {
          border-radius: 0 3.125vw 3.125vw 0;
          margin-right: 0px;
        }
      }
    }
  }

  .process {
    margin-top: 4.1667vw;

    &-in {
      max-width: 56.8229vw;
      margin: 1.9792vw auto 0;
      border-radius: 3.3854vw;
    }

    .table {
      &-in {
        min-height: 3.6979vw;

        .context {
          font-size: 0.9896vw;

          &:not(:last-child) {
            margin-bottom: 0.5208vw;
          }
        }

        h3 {
          font-size: 1.1979vw;
        }

        &.text {
          padding: 1.5625vw 2.8646vw;
        }

        &:not(:last-child) {
          margin-right: 0.4167vw;
        }
      }

      &:not(:last-child) {
        margin-bottom: 0.4167vw;
      }
    }
  }

  .advantage {
    margin-top: 6.0938vw;

    &-title {
      margin-bottom: 2.8125vw;
    }

    &-lists {
      max-width: 69.0104vw;

      &-in {
        &-image {
          border-radius: 0.5208vw;
        }

        &-name {
          font-size: 1.1458vw;
          margin: 0.5208vw 0;
        }

        &-text {
          font-size: 0.9375vw;
          padding: 0 0.5208vw;
          letter-spacing: 0.1979vw;
        }
      }
    }
  }

  .case {
    margin-top: 5.0521vw;

    &-title {
      &-in {
        font-size: 1.5625vw;
        text-indent: 3.3854vw;
        padding-bottom: 0.2604vw;
        padding-right: 0.3646vw;
      }
    }

    &-context {
      margin-top: 1.0938vw;

      span {
        font-size: 1.8229vw;
      }
    }

    &-content {
      margin-top: 2.3958vw;
      padding: 3.0208vw 0 3.2292vw;

      &-in {
        max-width: 81.25vw;

        &>div {
          padding: 0.7292vw 1.5104vw 1.3021vw;

          &:not(:first-child) {
            margin-left: 0.8333vw;
          }
        }

        &-l {
          img {
            width: 9.1146vw;
            border: 0.4167vw solid #fff;
          }

          span {
            margin-left: 0.9375vw;

            &:nth-of-type(1) {
              font-size: 1.4583vw;
            }

            &:nth-of-type(2) {
              font-size: 1.0938vw;
            }
          }
        }

        &-r {
          margin-top: 0.7813vw;
          font-size: 1.0417vw;
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

  .mobile_orthodontics {
    :deep(.introduce) {
      .introduce-in-l {
        position: absolute;
        bottom: -20px;

        .content {
          width: 100%;
          padding: 0 8vw;
          font-weight: 400;
          color: var(--Grey-Deep, #4d4d4d);
          text-align: justify;
          font-family: 'Noto Sans HK';
          font-size: 16px;
        }
      }

      .mobile_new {
        margin: 6.65vw 8vw 12vw;
      }
    }
  }

  :deep(.tabNav) {
    padding: 0;
  }

  .reason {
    padding: 0 8vw;
    width: 100%;
    overflow: hidden;

    &-in {
      flex-direction: column;
      margin-top: 0;

      &-l {
        width: 100%;
        margin-right: 0;
      }

      &-r {
        margin-top: 5.33vw;

        .item {
          font-size: 4vw;
          letter-spacing: 4.5px;

          .item-r h3 {
            color: #fc1682;
            font-family: 'Noto Sans HK';
            font-size: 4.2665vw;
            font-style: normal;
            font-weight: 400;
            line-height: 200%;
            /* 32px */
            letter-spacing: 1.6px;
          }

          .item-r p {
            color: var(--Black, #4d4d4d);
            font-family: 'Noto Sans HK';
            font-size: 4.265vw;
            font-style: normal;
            font-weight: 400;
            line-height: 200%;
            letter-spacing: 1.6px;
          }
        }
      }
    }

    .mobile_title {
      display: flex;
      align-items: flex-end;
      flex-direction: row;

      &>div:nth-child(1) {
        &>img {
          position: relative;
          z-index: 4;
        }
      }

      &>div:nth-child(2) {
        color: var(--Grey-Deep, #4d4d4d);
        font-family: 'FakePearl-Regular';
        font-size: 5.33vw;
        font-style: normal;
        font-weight: 400;
        line-height: 160%;
        /* 32px */
        padding-bottom: 2.8vw;
        position: relative;
        margin-left: 2.665vw;
      }

      &>div:nth-child(2)::after {
        content: '';
        display: inline-block;
        width: 300%;
        height: 1px;
        background: #fc1682;
        margin-left: 10px;
        position: absolute;
        left: -35px;
        bottom: 15px;
      }
    }
  }

  .contrast {
    margin-top: 30px;

    &-bg {
      padding: 44px 0 10px;
      background: linear-gradient(360deg,
          rgba(255, 241, 240, 0) 0%,
          rgba(255, 241, 240, 0.7) 12.5%,
          rgba(255, 241, 240, 0.7) 81.99%,
          rgba(255, 241, 240, 0) 100%);
    }

    &-context {
      margin: 15px 30px 0;
      font-weight: 500;
      font-size: 16px;
      text-align: left;
    }

    &-tableRemark {
      // font-weight: 500;
      // font-size: 14px;
      margin-top: 8px;
      margin: 0 10.65vw;
      color: var(--Theme-Color, #fc1682);
      text-align: center;
      font-family: 'FakePearl-Regular';
      font-size: 15px;
      font-style: normal;
      font-weight: 500;
      line-height: 160%;
      /* 24px */
    }

    &-table {
      padding: 0 30px;
      margin: 35px auto 0;
      flex-wrap: wrap;

      &-in {
        &>div {
          &.content {
            &>div {
              font-size: 12px;
              padding: 0 11px;

              &>div {
                span {
                  &:first-child {
                    width: 10px;
                    font-size: 20px;
                  }
                }
              }
            }

            .content-l {
              margin-right: 2px;
            }

            &:not(:last-child) {
              margin-bottom: 2px;
            }
          }

          &:nth-of-type(1) {
            height: 120px;
            margin-bottom: 2px;

            .th {
              font-size: 15px;
              margin-bottom: 2px;
              height: 40px;
            }

            &>div {
              .td {
                font-size: 15px;
              }

              span {
                &:last-child {
                  margin-left: 2.5px;
                }
              }
            }
          }

          &:nth-of-type(2) {
            height: 115.07px;
          }

          &:nth-of-type(3) {
            height: 78px;
          }

          &:nth-of-type(4) {
            height: 78px;
          }

          &:nth-of-type(5) {
            height: 135px;
          }

          &:nth-of-type(6) {
            height: 88px;
          }

          &:nth-of-type(7) {
            height: 64px;
          }
        }
      }

      .tableBox {
        width: calc(100% - 64px);
        margin-right: 0;
        border-radius: 0 20px 0 0;
        overflow: hidden;
        margin-bottom: 30px;

        &.tableTab {
          width: 60px;
          margin-right: 2px;
          border-radius: 20px 0 0 20px;

          .contrast-table-in {
            &>div {
              font-size: 15px;
              margin-bottom: 2px;
            }
          }
        }

        &:last-child {
          border-radius: 0 20px 0px 0;
        }

        &.tabletab-mb {
          display: block;
        }
      }
    }
  }

  .process {
    margin-top: 50px;
    padding: 0 30px;

    &-in {
      margin-top: 30px;
      border-radius: 20px;
    }

    .table {
      &-in {
        min-height: 34px;

        .context {
          font-size: 12px;
        }

        &.text {
          padding: 20px 12px;
        }

        &.h2 {
          // border-radius: 25px 25px 0 0;
        }

        h3 {
          font-size: 16px;
        }

        &:not(:last-child) {
          margin-right: 4px;
        }
      }

      &:not(:last-child) {
        margin-bottom: 4px;
      }
    }
  }

  .advantage {
    margin-top: 60px;
    overflow: hidden;

    &-title {
      margin-bottom: 0;
    }

    &-lists {
      // max-width: 390px;
      margin-left: 30px;
      margin-top: 20px;
      margin-bottom: 20px;
      padding-right: 50px;
      padding-bottom: 20px;
      box-sizing: border-box;
      flex-wrap: nowrap;
      gap: 0 15px;
      overflow-x: scroll;

      &-in {
        // width: 50%;
        // flex: initial;
        border-radius: 10px;
        border: 1px solid var(--Pink-Dark, #ffa8c6);
        background: linear-gradient(194deg,
            #fee6f1 3.13%,
            rgba(254, 230, 241, 0) 49.04%);
        min-width: 180px;
        margin: 0;

        &-image {
          margin: 0 10px;
          padding-bottom: calc(100% - 20px);

          span {
            top: 14px;
            left: 18px;
          }

          img {
            // width: 100%;
            width: 100px;
          }
        }

        &-name {
          margin: 0 0 10px;
          font-size: 20px;
          white-space: pre-wrap;
        }

        &-text {
          font-size: 15px;
          padding: 0;
          letter-spacing: 3px;
          box-sizing: border-box;
          padding: 15px;
        }

        &:nth-child(n + 3) {
          .advantage-lists-in-name {
            min-height: 64px;
            display: flex;
            align-items: flex-end;
            justify-content: center;
          }
        }
      }
    }

    &-lists::-webkit-scrollbar {
      height: 12px;
      width: 0;
      cursor: pointer;
    }

    &-lists::-webkit-scrollbar-thumb {
      height: 12px;
      background: #fc1682;
      border: none;
      cursor: pointer;
    }

    &-lists::-webkit-scrollbar-track {
      background: #fee6f1;
    }
  }

  .case {
    margin-top: 60px;
    padding: 44px 0 0;

    &-title {
      &-in {
        font-size: 20px;
        text-indent: 45px;
      }
    }

    &-context {
      display: flex;
      flex-direction: row;
      justify-content: center;
      margin: 30px auto;

      span {
        font-size: 16px;
      }

      position: relative;
      width: fit-content;
    }

    &-context::before {
      content: '';
      position: absolute;
      background: url('https://static.cmereye.com/imgs/2024/09/b8d7b49444c440db.png') no-repeat;
      width: 16px;
      height: 15px;
      background-size: cover;
      display: inline-block;
      left: -22px;
      top: 0px;
    }

    &-context::after {
      content: '';
      position: absolute;
      background: url('https://static.cmereye.com/imgs/2024/09/1e3be61edaf5a06f.png') no-repeat;
      width: 16px;
      height: 15px;
      background-size: cover;
      display: inline-block;
      right: -22px;
      bottom: 0px;
    }

    &-content {
      background: linear-gradient(180deg,
          #fee6f1 0%,
          rgba(254, 230, 241, 0) 100%);
      // background: none;
      margin-top: 0;
      padding: 0 8vw;
      margin-right: 0;

      &-in {
        // flex-direction: column;
        flex-direction: row;
        overflow-x: scroll;
        gap: 0 15px;
        padding: 50px 0px 20px 0px;
        margin: 30px 0;
        justify-content: flex-start;

        &>div {
          width: 100%;
          padding: 4vw 7.465vw;
          min-width: 180px;

          &:not(:first-child) {
            margin-left: 0px;
            margin-top: 0;
          }
        }

        &-l {
          // align-items: flex-end;
          flex-direction: column;
          align-items: center;
          margin-top: -70px;

          &>div:nth-child(2) {
            display: flex;
            flex-direction: column;
            // justify-content: center;
            align-items: center;
          }

          img {
            width: 125px;
            height: 125px;
            margin-top: 5px;
            border: 4px solid #fff;
          }

          span {
            margin-left: 0;

            &:nth-of-type(1) {
              font-size: 20px;
            }

            &:nth-of-type(2) {
              font-size: 18px;
            }
          }
        }

        &-r {
          margin-top: 10px;
          font-size: 16px;
        }
      }

      &-in::-webkit-scrollbar {
        height: 8px;
        width: 0;
        cursor: pointer;
      }

      &-in::-webkit-scrollbar-thumb {
        height: 12px;
        background: #fc1682;
        border: none;
        cursor: pointer;
      }

      &-in::-webkit-scrollbar-track {
        background: #fee6f1;
      }
    }
  }

  :deep(.problem-title-in),
  :deep(.bb) {
    font-size: 5.3334vw;
  }

  .banner-in-box {
    position: absolute;
    bottom: 0;
    left: 0;
    height: 100vw;
    width: 100%;
    z-index: 22;
    box-sizing: border-box;
    // padding-left: 20px;
    padding-bottom: 35px;
    // display: flex;
    // align-items: flex-start;
    // justify-content: flex-start;
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
      min-height: 22.665vw;
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
