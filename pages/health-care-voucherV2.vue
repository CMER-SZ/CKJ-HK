<script lang="ts" setup>
import { Swiper, SwiperSlide } from 'swiper/vue'
import { Autoplay, Navigation, Pagination } from 'swiper'
import { phoneNum } from '~/assets/js/common'
const locale = useState<string>('locale.setting')
const { width, height } = useWindowSize()
const { x, y } = useWindowScroll()
const router = useRouter()
useHead({
  title: '長者醫療券',
})


const headerConfig = ref({
  bg: '',
  img: 'https://static.ckjhk.com/ckj-image/d25c5ec24fe5.webp',
  mbImg: 'https://static.ckjhk.com/ckj-image/008e38b39a5d.webp',
  pageName: 'health-care-voucher',
  pcText: [],
  mbText: [],
})


const pageDetail: any = {
  title: '',
  img: '',
  content: [
    {
      type: 'p',
      list: [
        {
          type: 'defule',
          text: 'health-care-voucher.pageDetail.content_1.list_1.text_1',
        },
        {
          type: 'indexColor',
          text: 'health-care-voucher.pageDetail.content_1.list_1.text_2',
        },
      ],
    },
    {
      type: 'h2',
      text: 'health-care-voucher.pageDetail.content_1.list_2.text',
      className: 'nob',
    },
    {
      type: 'p',
      list: [
        {
          type: 'defule',
          text: 'health-care-voucher.pageDetail.content_1.list_3.text',
        },
      ],
    },
    {
      type: 'p',
      list: [
        {
          type: 'defule',
          text: 'health-care-voucher.pageDetail.content_1.list_4.text',
        },
      ],
    },
    {
      type: 'p',
      list: [
        {
          type: 'defule',
          text: 'health-care-voucher.pageDetail.content_1.list_5.text',
        },
      ],
    },
    {
      type: 'h2',
      text: 'health-care-voucher.pageDetail.content_1.list_6.text',
      className: 'nob',
    },
    {
      type: 'img',
      list: [
        'https://static.cmereye.com/imgs/2024/07/40092437294c9e2b.webp',
        'https://static.cmereye.com/imgs/2024/02/8b093aa825acf2bf.webp',
      ],
      className: 'imgLists nob twoImg',
    },
    {
      type: 'p',
      list: [
        {
          type: 'defule',
          text: 'health-care-voucher.pageDetail.content_1.list_7.text',
        },
      ],
    },
    {
      type: 'h2',
      text: 'health-care-voucher.pageDetail.content_1.list_8.text',
      className: 'nob',
    },
    {
      type: 'img',
      list: ['https://static.cmereye.com/imgs/2024/02/b4e5c4e78e6d820e.webp'],
      className: 'imgone nob',
    },
    {
      type: 'p',
      list: [
        {
          type: 'defule',
          text: 'health-care-voucher.pageDetail.content_1.list_9.text',
        },
      ],
    },
    {
      type: 'p',
      list: [
        {
          type: 'defule',
          text: 'health-care-voucher.pageDetail.content_1.list_9.text1',
        },
      ],
    },
    {
      type: 'p',
      list: [
        {
          type: 'defule',
          text: 'health-care-voucher.pageDetail.content_1.list_9.text2',
        },
      ],
    },
    {
      type: 'h2',
      text: 'health-care-voucher.pageDetail.content_1.list_13.text',
      className: 'nob',
    },
    {
      type: 'p',
      list: [
        {
          type: 'defule',
          text: 'health-care-voucher.pageDetail.content_1.list_14.text',
        },
      ],
      className: 'nob',
    },
    {
      type: 'img',
      list: [
        'https://static.cmereye.com/imgs/2024/07/af47792c9813ef40.webp',
      ],
      className: 'imgLists nob imgStyle',
    },
    {
      type: 'p',
      list: [
        {
          type: 'defule',
          text: 'health-care-voucher.pageDetail.content_1.list_17.text',
        },
      ],
    },
    {
      type: 'p',
      list: [
        {
          type: 'defule',
          text: 'health-care-voucher.pageDetail.content_1.list_18.text',
        },
        {
          type: 'indexColor a',
          text: 'https://bit.ly/愛康健長者醫療券預約',
          link: 'https://bit.ly/愛康健長者醫療券預約',
        },
      ],
      className: 'nob',
    },
    {
      type: 'p',
      list: [
        {
          type: 'defule',
          text: 'health-care-voucher.pageDetail.content_1.list_19.text',
        },
        {
          type: 'indexColor a',
          text: '+852 69338128',
          link: 'tel: +852 69338128',
        },
      ],
      className: 'nob',
    },
    {
      type: 'p',
      list: [
        {
          type: 'defule',
          text: 'health-care-voucher.pageDetail.content_1.list_20.text',
        },
        {
          type: 'indexColor a',
          text: 'https://ckjhk.com/health-care-voucher',
          link: 'https://ckjhk.com/health-care-voucher',
        },
      ],
      className: 'nob',
    },
    {
      type: 'p',
      list: [
        {
          type: 'defule',
          text: 'health-care-voucher.pageDetail.content_1.list_21.text',
        },
        {
          type: 'indexColor a',
          text: 'https://www.hcv.gov.hk/tc/index.html',
          link: 'https://www.hcv.gov.hk/tc/index.html',
        },
      ],
    },
    {
      type: 'p',
      list: [
        {
          type: 'defule',
          text: 'health-care-voucher.pageDetail.content_1.list_22.text_1',
        },
        {
          type: 'defule',
          text: 'health-care-voucher.pageDetail.content_1.list_22.text_2',
        },
        {
          type: 'a',
          text: 'https://www.info.gov.hk/gia/general/202305/10/P2023051000264.html',
          link: 'https://www.info.gov.hk/gia/general/202305/10/P2023051000264.html',
        },
      ],
      className: 'lastpa pa nob',
    },
  ],
  tags: [
    'health-care-voucher.pageDetail.content_1.list_23.text_1',
    'health-care-voucher.pageDetail.content_1.list_23.text_2',
    'health-care-voucher.pageDetail.content_1.list_23.text_3',
  ],
}

const docHeight = ref('')
const changeConfig = () => {
  if (width.value > 768) {
    if (y.value > 4400) {
      docHeight.value = 'pc'
    }
  } else {
    if (y.value > 3300) {
      docHeight.value = 'mb'
    }
  }
}
watch(y, (n, o) => {
  if (width.value > 768) {
    changeConfig()
  } else {
    changeConfig()
  }
})
let windowWidth = ref(390)

const getWindowWidth = () => {
  windowWidth.value = window.innerWidth
}
onMounted(() => {
  getWindowWidth()
  window.addEventListener('resize', getWindowWidth)

  if (width.value > 768) {
    changeConfig()
  } else {
    changeConfig()
  }
  window.addEventListener('scroll', () => {
    if (width.value > 768) {
      changeConfig()
    } else {
      changeConfig()
    }
  })
})
const newsmoduleLists = ref([
  {
    id: '192',
    img: 'https://static.cmereye.com/imgs/2024/06/247bc49f8a117cf8.jpg',
    name: '【#長者醫療券使用指南】配偶共用醫療券方法',
    desc: '為了更好地照顧家庭健康，長者醫療券計劃允許配偶之間共享使用醫療券餘額。這意味著，如果其中一方醫療券戶口內的餘額耗盡後，便可以使用配偶戶口內的醫療券餘額。',
    link: '/news/news-information/192',
  },
  {
    id: '164',
    img: 'https://static.cmereye.com/imgs/2024/08/32c328667af0ce46.png',
    name: '【#長者醫療券使用指南】提早下載醫健通 用醫療券好輕鬆 📱👍',
    desc: '親愛嘅長者們！使用醫療劵前，可以先下載 📱「醫健通eHealth」App 同進行登記啊！利用呢個App，您可以更方便地管理您嘅醫療劵，包括：✅ 查閱醫療劵戶口餘額 - 隨時了解剩餘金額，合理規劃使用。✅ 查閱過去使用醫療劵紀錄 - 明白每一筆交易，清楚消費。✅ 查閱提供服務嘅醫療機構 - 揾到最適合您嘅醫療服務地點。✅ 獲取最新醫療劵消息 - 不錯過任何重要更新同資訊。',
    link: '/news/news-information/164',
  },
  {
    id: '152',
    img: 'https://static.cmereye.com/imgs/2024/08/cab2e7dea18bbfe2.png',
    name: '【#長者醫療券使用指南】首次使用醫療券要登記',
    desc: '長者朋友們，首次使用醫療券需要前往已註冊的醫療券服務提供的醫院或診所進行戶口登記。不過唔使擔心，登記過程非常簡單，而且完全免費。如果您覺得有需要，可以帶埋照顧者一齊前往進行登記手續。',
    link: '/news/news-information/152',
  },
])

const problemData = {
  title: "<span style='color: var(--GHV-Green, #01A853);'>醫療券</span><span>常見問題</span>",
  lists: [
    {
      Q: '什為是長者醫療券？',
      A: '指由香港政府資助<i>年滿65歲</i>及持有效<i>香港身份證</i>或入境事務處發出的<i>《豁免登記證明書》</i>的長者，選擇私營基層醫療服務。',
    },
    {
      Q: '如何參加長者醫療券計劃？',
      A: '凡年滿 65歲並持有有效香港身份證或入境事務處發出的《豁免登記證明書》的長者，即符合資格領取及使用醫療券支付私營基層醫療服務的費用。每名合資格長者每年可獲發的醫療券金額為2,000港元，醫療券的累積金額上限為 8,000港元。',
    },
    {
      Q: '長者如何獲得醫療券？',
      A: '長者自踏入65歲的年度起，便於每年1月1日自動存入「醫健通」戶口。現時政府每年派<i>2,000港元</i>，累積金額上限為<i>8,000港元</i>。在牙科醫療服務上，<i>不設金額使用上限</i>。首次使用醫療券長者，可向深圳愛康健口腔醫院提出開設醫療券戶口。',
    },
    {
      Q: '醫療券必須本人使用療程嗎?',
      A: '是的，必須<i>親身接受醫療服務</i>後才可使用，也不接受由委托人士代為到醫院配藥。',
    },
    {
      Q: '醫療券可以購買抗敏牙膏、電動牙刷、水牙線機、家用牙齒美白儀等產品嗎?',
      A: '不可以，醫療券不可用以購買物品，如藥物、個人護理用品、食品或其他醫療用品。',
    },
    {
      Q: '什為是配偶共用醫療券？',
      A: '兩名乎合醫療券資格及有配偶關係的長者，雙方同意下申請<i>雙方戶口連結</i>。當其中一方醫療券戶口內的餘額耗盡後，便可以使用配偶戶口內的醫療券餘額。使用時必須出示<i>配偶最新的香港身份證副本</i>或《豁免登記證明書》副本。首次申請雙方戶口連結時，二人需<i>親身</i>帶同證件到深圳愛康健口腔醫院辦理。',
    },
    {
      Q: '什為是長者醫療券獎賞先導計劃？',
      A: '獎賞先導計劃是為期3年的短期計劃，至2026年12月31日止。長者在同一年度累計使用至少1,000港元醫療券於特定基層醫療服務，包括<i>牙齒檢查、洗牙、脫牙、補牙</i>等，醫健通會自動發放獎賞<i>500港元</i>一次。3年最多可獲<i>1500港元</i>獎賞。獎賞只可支付特定基層醫療服務費用，包括牙齒檢查、洗牙、脫牙、補牙等。',
    },
    {
      Q: '醫療券涵蓋的牙科服務？',
      A: '洗牙、補牙、拔牙、杜牙根、牙冠、牙橋、種植牙、活動假牙、牙周病治療等。',
    },
    {
      Q: '牙科服務如何計算匯率？',
      A: '醫療券是以港幣為單位，而深圳愛康健口腔醫院是以人民幣結算。香港銀行公會每月會定立固定匯率，最後要以四捨五入方式計算最接近整數的港幣金額。<br />例子：人民幣¥200 x 匯率1.127 = 港幣$225.4，四捨五入後金額為$225。',
    },
    {
      Q: '如何查閱醫療券戶口餘額？',
      A: "· 醫院會為長者申報使用醫療券，有關戶口内的醫療券使用記錄亦會即時更新 <br />· 在完成申報後醫院會給長者一份《醫療券使用記錄》，列明扣取前、已扣取及剩餘的醫療券金額，以供保存 <br />· 醫健通系統亦會即時以電話短訊通知有關長者或其指定的家人或照顧者 <br /> <br />亦可用以下3個途徑查詢醫療券戶口餘額<br /> <br />· 登入網頁 <a href = 'https://www.hcv.gov.hk' target ='_blank'> www.hcv.gov.hk </a> <br / >· 致電醫療券結存查詢熱線 <a href = 'tel: 852 850 28380511' target='_blank' > (852) 2838 0511 </a> <br / >· <a target='_blank' href='https://app.ehealth.gov.hk/cross-boundary-health-record' >安裝「醫健通eHealth」手機應用程式</a>",
    },
    {
      Q: '發現醫療券申報金額錯誤怎麼辦？',
      A: '長者請<i>盡快親身回到深圳愛康健口腔醫院</i>，重新簽署「醫療券使用者使用醫療券同意書」。詳情可致電 (+852) 6933 8128。<br />注意：任何情況下醫療券都不可以兌換成現金作退款。',
    },
  ],
}

const showMoreInfo = ref(false)
const infoShow = () => {
  showMoreInfo.value = !showMoreInfo.value
}

const showNewsContent = ref(false)



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
  if (swiperRef.activeIndex >= newsmoduleLists.value.length - 1) {
    swiperRef.slideTo(0)
  }
  swiperRef.slideNext()
  handleProcessBtnClick()
}
const subNum = () => {
  if (swiperRef.activeIndex <= 0) {
    swiperRef.slideTo(newsmoduleLists.value.length - 1)
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
    <PageHeaderV2 v-if="windowWidth > 768" :headerConfig="headerConfig" />
    <MobileHeaderV2 v-if="windowWidth < 768" :headerConfig="headerConfig" />
    <PagePcBannerNoHome v-if="windowWidth > 768" :headerConfig="headerConfig" />
    <div class="new-health-care-voucher">
      <section class="senior_citizen_discount_bg">
        <section class="ckj-container senior_citizen_discount">
          <div class="d-flex flex-row  d-none d-lg-flex align-items-end subheading">
            <span>65歲及以上</span><span>香港長者睇牙優惠</span>
          </div>
          <div class="d-flex flex-row  d-lg-none align-items-end subheading">
            <span style="color: var(--Brand-Color, #F8298A);font-size: 18px;line-height: 150%;">65歲及以上</span>
            <span style="font-size: 16px;color: var(--Grey-Dark, #333);">香港長者睇牙優惠</span>
          </div>
          <div class="senior_citizen_discount_content">
            <div class="senior_items">
              <div class="senior_items_title">首次到診</div>
              <div class="senior_items_content senior_items_one">
                <div class="senior_items_text_red">免費</div>
                <div class="senior_items_text">掛號及CT拍片檢查</div>
              </div>
            </div>
            <div class="senior_items">
              <div class="senior_items_title">全科治療</div>
              <div class="senior_items_content senior_items_two">
                <div class="senior_items_text">原價<span class="senior_items_num">9</span><span
                    class="senior_items_text_red">折</span></div>
                <div class="senior_items_text">(或使用網上優惠)</div>
              </div>
            </div>
            <div class="senior_items">
              <div class="senior_items_title">義齒修復</div>
              <div class="senior_items_content senior_items_three">
                <div class="senior_items_text"><span class="senior_items_text_red">免費</span>拔牙1顆</div>
                <div class="senior_items_text">（智慧齒除外）</div>
              </div>
            </div>
            <div class="senior_items">
              <div class="senior_items_title">洗牙</div>
              <div class="senior_items_content senior_items_four">
                <div class="senior_items_bg_red">超聲波洗牙</div>
                <div class="senior_items_text senior_items_bottom_line">
                  <span class="senior_items_text_red">￥</span><span class="senior_items_num">58</span><span
                    class="senior_items_text_slow">(原價¥180/次)</span>
                </div>
                <div class="senior_items_bg_red">無鹽噴砂洗牙</div>
                <div class="senior_items_text">
                  <span class="senior_items_text_red">￥</span><span class="senior_items_num">168</span><span
                    class="senior_items_text_slow">(原價¥550/次)</span>
                </div>
              </div>
            </div>
            <div class="senior_items">
              <div class="senior_items_title">種植牙</div>
              <div class="senior_items_content senior_items_five">
                <div class="senior_items_bg_red">政府補助種植牙</div>
                <div class="senior_items_text">（集採種植牙）</div>
                <div class="senior_items_text_red senior_items_bottom_line">延長1年保修期</div>
                <div class="senior_items_bg_red">歐美種植牙</div>
                <div class="senior_items_text">享有網上優惠</div>
                <div class="senior_items_text_red">再<span class="senior_items_num">9</span>折</div>
                <div class="senior_items_text_slow">(特價產品除外)</div>
              </div>
            </div>
            <div class="senior_items">
              <div class="senior_items_title">牙周治療套餐</div>
              <div class="senior_items_content senior_items_six">
                <div class="senior_items_text senior_items_bottom_line">原價<span class="senior_items_num">9</span><span
                    class="senior_items_text_red">折</span></div>
                <div class="senior_items_bg_red">牙周專科檢查記錄表</div>
                <div class="senior_items_text_slow senior_items_bottom_line"><span
                    class="senior_items_text_red">￥</span><span class="senior_items_num">240</span>(原價¥300)</div>
                <div class="senior_items_text_red">贈送2次</div>
                <div class="senior_items_bg_red">牙周治療後維護</div>
                <div class="senior_items_text_slow">（價值¥800/次）</div>
              </div>
            </div>
          </div>
          <div class="senior_citizen_discount_btn">
            <PageAnimBtnTypeTwo :str="'WhatsApp查詢長者醫療券'" />
          </div>
        </section>
      </section>
      <section class="ckj-container medical_voucher">
        <div class="d-flex flex-row  d-none d-lg-flex align-items-end subheading">
          <span style="color: var(--GHV-Green, #01A853);">醫療券</span><span>牙科項目</span>
        </div>
        <div class="d-flex flex-row  d-lg-none align-items-end subheading">
          <span style="color: var(--GHV-Green, #01A853);font-size: 18px;line-height: 150%;">醫療券</span>
          <span style="font-size: 16px;color: var(--Grey-Dark, #333);">牙科項目</span>
        </div>
        <div class="medical_voucher_content">
          <div>
            <div class="medical_voucher_items">
              <div class="medical_voucher_items_title">預防性牙科項目*</div>
              <div class="medical_voucher_items_list">
                <div>1.牙齒檢查</div>
                <div>2.牙科放射照（CT拍片/Ｘ光）</div>
                <div>3.口腔衞生指導/口腔健康教育</div>
                <div>4.洗牙/打磨</div>
                <div>5.塗搽高濃度氟化物劑</div>
              </div>
            </div>
            <div class="medical_voucher_items">
              <div class="medical_voucher_items_title">跟進/監察慢性病症牙科項目**</div>
              <div class="medical_voucher_items_list">
                <div>1.覆檢假牙托/牙橋/種植體</div>
                <div>2.治理顳下頷關節（牙骹）病症/痛症</div>
                <div>3.治理蛀牙，包括補牙、脫牙、杜牙根（牙髓治療）</div>
                <div>4.治理牙周病，包括進階牙周治療</div>
              </div>
            </div>
            <div>*可參與長者醫療券獎賞先導計劃，累計使用至少1,000元醫療券可發放500元獎賞</div>
          </div>
          <div>
            <div class="medical_voucher_items">
              <div class="medical_voucher_items_title">治理急性病症牙科項目</div>
              <div class="medical_voucher_items_list">
                <div>1.牙根刮治/清創</div>
                <div>2.牙髓摘除</div>
                <div>3.小型口腔手術</div>
                <div>4.處方藥物</div>
              </div>
            </div>
            <div class="medical_voucher_items">
              <div class="medical_voucher_items_title">復康性牙科項目</div>
              <div class="medical_voucher_items_list">
                <div>1.洞內嵌體/高嵌體</div>
                <div>2.鑲配人造牙冠/牙橋</div>
                <div>3.鑲配假牙托</div>
                <div>4.種植牙</div>
              </div>
            </div>
          </div>
        </div>
      </section>
      <section class="ckj-container brief_introduction">
        <div class="d-flex flex-row  d-none d-lg-flex align-items-end subheading">
          <span class="span_colours">深圳愛康健口腔醫院</span><span>簡介</span>
        </div>
        <div class="d-flex flex-row  d-lg-none align-items-end subheading">
          <span style="color: var(--Brand-Color, #F8298A);font-size: 18px;line-height: 150%;">深圳愛康健口腔醫院</span>
          <span style="font-size: 16px;color: var(--Grey-Dark, #333);">簡介</span>
        </div>
        <div class="brief_introduction_content">
          <div class="brief_introduction_content_box1">
            <div><img src="https://static.ckjhk.com/ckj-image/2025042516421801.webp" alt="往羅湖口岸"></div>
            <div class="brief_introduction_content_info">
              <div><span>醫院地址：</span><span>深圳市羅湖區羅湖火車站大廈C區1樓大堂（出關後步行4分鐘）</span></div>
              <div><span>醫院營業時間：</span><span>上午9:00-下午6:00（假日照常）</span></div>
              <div><span>查詢及預約電話：</span><a href="tel: 852 69338128">(852) 6933 8128</a></div>
            </div>
          </div>
          <div class="brief_introduction_content_btn" @click="showMoreInfo = !showMoreInfo" v-if="!showMoreInfo">
            <div class="animbtntypetwo">
              <div class="animbtntypetwo-in">
                <span>點撃閱讀詳情</span>
              </div>
            </div>
          </div>
          <div class="brief_introduction_content_text" v-if="showMoreInfo">
            深圳愛康健口腔醫院是深圳市政府批准成立的二級口腔專科醫院，位於羅湖口岸旁火車站大樓C區1-8樓，建築面積約9,600平方米，設置牙椅84張，床位20個。醫院內有數十位來自華西、北大、港大等高校畢業的醫生，設置六大專科，提供全面性牙科醫療服務。以及提供優質醫療服務，包括無假日齒科、可自選預約醫生、一醫一患一診室、全程陪護、廣東話服務等。
          </div>
        </div>
      </section>
      <section class="ckj-container method_step">
        <div class="d-flex flex-row  d-none d-lg-flex align-items-end subheading">
          <span style="font-size: 24px;color: var(--Grey-Dark, #333);">使用醫療券預約</span><span
            style="color: var(--GHV-Green, #01A853);font-size: 30px;">方法及就醫流程</span>
        </div>
        <div class="d-flex flex-row  d-lg-none align-items-end subheading">
          <span style="font-size: 16px;color: var(--Grey-Dark, #333);">使用醫療券預約</span><span
            style="color: var(--GHV-Green, #01A853);font-size: 18px;line-height: 150%;">方法及就醫流程</span>
        </div>
        <div class="method_step_content">
          <div>
            <span>長者可透過深圳愛康健口腔醫院香港官方網站進行</span><a
              href="https://bit.ly/%E6%84%9B%E5%BA%B7%E5%81%A5%E9%95%B7%E8%80%85%E9%86%AB%E7%99%82%E5%88%B8%E9%A0%90%E7%B4%84"
              target="_blank">
              網上查詢</a>
            <span>或致電</span><a href="tel: 852 69338128" target="_blank">69338128 </a><span>進行登記預約。</span><br /><br />
          </div>
          <div>
            長者亦可親身前往該院一樓大堂接待處，待醫院職員安排分診。完成分診後，長者可前往五樓、六樓或七樓出示有效香港身份證或由入境事務處發出的《豁免登記證明書》進行身份認證及掛號。在接受牙科治療後，長者可按醫院指示到收費專窗使用醫療券支付服務費用。
          </div>
        </div>
      </section>
      <section class="ckj-container see_a_doctor_flow">
        <div class="bg_text bg_red_text">長者到診</div>
        <div class="flex">
          <div class="bg_text bg_ghv_green_text">有預約</div>
          <div class="bg_text bg_grey_deep_text">未有預約</div>
        </div>
        <div class="flex">
          <div class=" bg_text bg_ghv_green_text">
            <span>登記掛號</span><span>(安排科室樓層)</span>
          </div>
          <div class="bg_text bg_grey_deep_text">到一樓大堂分診</div>
        </div>
        <div class="bg_text bg_red_text">檢查/就診</div>
        <div class="flex">
          <div class="bg_text bg_ghv_green_text">需轉診</div>
          <div class="bg_text bg_grey_deep_text">不需轉診</div>
        </div>
        <div class="flex">
          <div class="bg_text bg_ghv_green_text">到轉診室候診</div>
          <div></div>
        </div>
        <div class="bg_text bg_red_text">治療/取藥</div>
        <div class="bg_text bg_red_text">繳費/預約覆診</div>
        <div class="bg_text bg_red_text">完成就診</div>
      </section>
      <section class="ckj-container apply_for_path">
        <div class="d-flex flex-row  d-none d-lg-flex  align-items-end subheading">
          <span style="color: var(--GHV-Green, #01A853);font-size: 30px;">醫健通「跨境健康紀錄」</span><span
            style="font-size: 24px;color: var(--Grey-Dark, #333);">申請方法</span>
        </div>
        <div class="d-flex flex-row  d-lg-none align-items-end subheading">
          <span style="font-size: 18px;color: var(--GHV-Green, #01A853);">使用醫療券預約</span><span
            style="color: var(--Grey-Dark, #333);font-size: 16px;line-height: 150%;">方法及就醫流程</span>
        </div>
        <div class="apply_for_path_iframe">
          <iframe class="iframe" src="https://www.youtube.com/embed/dwNohpI4eNM?si=IfOfJBy7IRgTnDU5" width="100%"
            height="100%" frameborder="0"></iframe>
        </div>
        <div class="apply_for_path_content">
          <div>「醫健通eHealth」流動應用程式，讓長者輕鬆獲取過去3年的醫療紀錄到深圳愛康健口腔醫院使用。 </div>
          <a target="_blank" href="https://app.ehealth.gov.hk/cross-boundary-health-record">安裝「醫健通eHealth」手機應用程式</a>
          <div>*長者在香港以外地方使用醫療券時，需要先同意加入電子健康紀錄互通系統（「醫健通」）（如未曾加入）。</div>
        </div>
      </section>
      <section class="ckj-container about_link">
        <div class="d-flex flex-row  d-none d-lg-flex  align-items-end subheading">
          <span style="font-size: 24px;color: var(--Grey-Dark, #333);">長者醫療券</span><span
            style="color: var(--GHV-Green, #01A853);font-size: 30px;">相關連結</span>
        </div>
        <div class="d-flex flex-row  d-lg-none align-items-end subheading">
          <span style="font-size: 18px;color: var(--GHV-Green, #01A853);">長者醫療券</span><span
            style="color: var(--Grey-Dark, #333);font-size: 16px;line-height: 150%;">相關連結</span>
        </div>
        <ul>
          <li><a target="_blank" href="https://www.hcv.gov.hk/tc/index.html">醫療券官方網頁</a></li>
          <li><a target="_blank" href="https://www.ehealth.gov.hk/tc/">醫健通官方網頁</a></li>
          <li><a target="_blank" href="https://www.hcv.gov.hk/tc/hcv_gba_pilot_scheme/szckjsh.html">深圳愛康健口腔醫院醫療券官方頁面</a>
          </li>
        </ul>
      </section>
      <section class="ckj-container news_content_list">
        <div class="d-flex flex-row  d-none d-lg-flex align-items-end subheading">
          <span style="color: var(--GHV-Green, #01A853);font-size: 18px;">「長者醫療券大灣區試點計劃」</span><span>新聞</span>
        </div>
        <div class="d-flex flex-row  d-lg-none align-items-end subheading">
          <span style="font-size: 18px;color: var(--GHV-Green, #01A853);">「長者醫療券大灣區試點計劃」</span><span
            style="color: var(--Grey-Dark, #333);font-size: 16px;line-height: 150%;">新聞</span>
        </div>
        <div>
          <div class="news_content_list_item">
            <div class="news_content_list_item_img">
              <img loading="lazy" src="https://static.cmereye.com/imgs/2024/02/74d44b6145445bfd.webp" title="灣區長者醫療券"
                alt="灣區長者醫療券" />
            </div>
            <div class="news_content_list_item_text"
              :class="[showNewsContent == false ? 'news_content_list_item_text_one' : '']">
              2024年2月19日，政府公布深圳愛康健齒科已經正式成為「長者醫療券大灣區試點計劃」的參與機構。這個計劃旨在資助符合條件的長者跨境到愛康健齒科口腔醫院使用長者醫療券支付治療費用。政府預計約有170萬名合資格的長者將從中受益。
            </div>
          </div>
          <div class="brief_introduction_content_btn" @click="showNewsContent = !showNewsContent"
            v-if="!showNewsContent">
            <div class="animbtntypetwo">
              <div class="animbtntypetwo-in">
                <span>點撃閱讀詳情</span>
              </div>
            </div>
          </div>
          <div class="news_content_list_item" v-if="showNewsContent">
            <div class="news_content_list_item_text">
              2024年8月5日，香港衛生署正式與深圳愛康健口腔醫院簽署服務協議，並公布相關使用細節。「長者醫療券大灣區試點計劃」首次有牙科專業醫療機構參與，為醫療券計劃在內地推行帶來一大突破，讓合資格香港長者可在深圳使用醫療券接受牙科服務的選擇更多，以回應香港長者對牙科服務的殷切需求。
            </div>
            <div class="news_content_list_item_img">
              <img loading="lazy" src="https://static.cmereye.com/imgs/2024/08/4831c2a8a353d328.png" title="灣區長者醫療券"
                alt="灣區長者醫療券" />
            </div>
            <div class="news_content_list_item_text">
              2024年8月14日起，合資格申領醫療券的香港長者將可在深圳愛康健口腔醫院使用醫療券支付門診醫療護理費用，為居住在大灣區內地城市的合資格香港長者提供更大的便利和靈活性。
            </div>
            <div class="news_content_list_item_iframe">
              <iframe class="iframe" src="https://www.youtube.com/embed/XzxwTy9Iheg?si=3BXyyQXpUmhlSRkb" width="100%"
                height="100%" frameborder="0"></iframe>
            </div>
          </div>
        </div>
      </section>
    </div>
    <div class="v2-service-problem">
      <V2ServiceProblem :problem-data="problemData" :v2-versions="true" />
      <div class="brief_introduction_content_btn">
        <a class="animbtntypetwo" href="https://static.ckjhk.com/ckj-pdf/CKJ愛康健-長者醫療券小冊子2025.pdf" target="_blank">
          <div class="animbtntypetwo-in">
            <span><svg xmlns="http://www.w3.org/2000/svg" width="24" height="26" viewBox="0 0 24 26" fill="none">
                <path d="M16.9379 25.2583H3.56445V1H22.8155V19.3807L16.9379 25.2583Z" fill="white" stroke="#F8298A"
                  stroke-linecap="round" stroke-linejoin="round" />
                <path d="M19.0881 5.59875H1.17773V14.0852H19.0881V5.59875Z" fill="#F8298A" stroke="#F8298A"
                  stroke-linecap="round" stroke-linejoin="round" />
                <path d="M16.9277 19.3646L16.9364 25.2585L22.8216 19.3722L16.9277 19.3646Z" fill="white"
                  stroke="#F8298A" stroke-linecap="round" stroke-linejoin="round" />
                <path
                  d="M4.66385 7.00645C5.12448 7.00645 5.50924 7.04439 5.81922 7.12026C6.12811 7.19613 6.37739 7.31643 6.56489 7.48226C6.75348 7.64808 6.88679 7.86268 6.96483 8.12714C7.04395 8.39159 7.08297 8.71132 7.08297 9.0885C7.08297 9.49927 7.03961 9.84285 6.95182 10.1214C6.86403 10.3999 6.72422 10.6232 6.53021 10.7912C6.33621 10.9603 6.08584 11.0806 5.7802 11.1532C5.47347 11.2258 5.10172 11.2627 4.66277 11.2627H4.06449V12.8559H2.38672V7.00537H4.66277L4.66385 7.00645ZM5.157 9.76264C5.30006 9.64992 5.37159 9.43966 5.37159 9.13077C5.37159 8.80453 5.29898 8.58452 5.15266 8.46855C5.00634 8.35258 4.76248 8.29622 4.41891 8.29622H4.06449V9.93172H4.41891C4.76682 9.93172 5.01285 9.87536 5.157 9.76264Z"
                  fill="white" />
                <path
                  d="M11.3924 7.12026C11.7468 7.19613 12.0481 7.34136 12.2984 7.55487C12.5488 7.76839 12.7406 8.06644 12.8761 8.44795C13.0105 8.83055 13.0788 9.32477 13.0788 9.93172C13.0788 10.4996 13.0116 10.97 12.8761 11.344C12.7417 11.7179 12.5488 12.017 12.2984 12.2414C12.0481 12.4657 11.7468 12.625 11.3924 12.7172C11.0379 12.8093 10.6423 12.8559 10.2034 12.8559H7.96094V7.00537H10.2034C10.6413 7.00537 11.0379 7.04331 11.3924 7.11917V7.12026ZM10.7052 11.3559C10.8656 11.3104 10.9913 11.2312 11.0845 11.1153C11.1778 11.0004 11.2417 10.8465 11.2785 10.6557C11.3154 10.465 11.3338 10.2233 11.3338 9.93064C11.3338 9.638 11.3143 9.37571 11.2753 9.17629C11.2363 8.97686 11.1691 8.82079 11.0726 8.70807C10.9772 8.59535 10.8504 8.51732 10.6933 8.4718C10.5361 8.42628 10.3389 8.4046 10.1037 8.4046H9.63979V11.422H10.1037C10.3454 11.422 10.5459 11.3992 10.7063 11.3548L10.7052 11.3559Z"
                  fill="white" />
                <path
                  d="M15.7403 9.39956H17.7042V10.8324H15.7403V12.8559H14.0625V7.00537H17.8808V8.45554H15.7403V9.39956Z"
                  fill="white" />
              </svg>下載醫療券小冊子</span>
          </div>
        </a>
      </div>
    </div>
    <div class="health-care-voucher pageIn whitebgColor">
      <div class="newsmodule smallPageCon">
        <div class="d-flex flex-row  d-none d-lg-flex align-items-end subheading">
          <span style="color: var(--GHV-Green, #01A853);font-size: 30px;">醫療券</span><span
            style="font-size: 24px;">資訊</span>
        </div>
        <div class="d-flex flex-row  d-lg-none align-items-end subheading">
          <span style="color: var(--GHV-Green, #01A853);font-size: 18px;">醫療券</span><span
            style="font-size: 16px;">資訊</span>
        </div>

        <div class="newsmodule-lists d-grid flex-row  d-none d-lg-grid">
          <div @click="router.push(item.link)" class="list-in" v-for="item in newsmoduleLists" :key="item.id">
            <div class="image">
              <img :title="item.name" :src="item.img" alt="" />
            </div>
            <h2 :title="item.name">{{ item.name }}</h2>
            <p :title="item.desc">{{ item.desc }}</p>
            <div class="btn">
              <PageAnimBtnTypeTwo str="查看全文" :link="item.link" :key="item.id" />
            </div>
          </div>
        </div>
        <div class="newsmodule-lists-mobile d-grid flex-row  d-lg-none">
          <Swiper class="mySwiper" @swiper="setSwiperRef" :modules="[Autoplay, Navigation, Pagination]"
            :slides-per-view="1" :loop="true" :speed="800" :autoplay="{
              delay: 6000,
              disableOnInteraction: false
            }">
            <SwiperSlide @click="router.push(item.link)" class="list-in" v-for="item in newsmoduleLists" :key="item.id">
              <div class="image">
                <img :title="item.name" :src="item.img" alt="" />
              </div>
              <h2 :title="item.name">{{ item.name }}</h2>
              <div :title="item.desc">{{ item.desc }}</div>
              <div class="btn">
                <PageAnimBtnTypeTwo str="查看全文" :link="item.link" :key="item.id" />
              </div>
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
                  <div v-for="(item, index) in newsmoduleLists" :key="index" @click="handleLineCurStrength(index + 1)"
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
      </div>
      <BranchAddress />
      <AppointmentFormV2 />
    </div>
    <FooterV2 />
    <AsideV2 />
  </div>
</template>

<style lang="scss" scoped>
.animbtntypetwo {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 30px auto;

  &-in {
    position: relative;
    display: inline-block;

    &>span {
      padding: 14px 50px;
      background: #00aeff;
      position: relative;
      z-index: 1;
      border-radius: 50px;
      display: inline-block;
      animation: btntestAnima 5.6s infinite;
      box-shadow: 10px 10px 20px rgba(103, 214, 239, 0.75);
      cursor: pointer;
      transition: all 0.5s;

      color: var(--White, #fff);
      text-align: center;
      font-family: 'Noto Sans HK';
      font-size: 30px;
      font-style: normal;
      font-weight: 700;
      line-height: normal;
      letter-spacing: 3px;

      display: flex;
      align-items: center;
      gap: 0 20px;
    }

    &::after {
      content: '';
      position: absolute;
      display: inline-block;
      left: 50%;
      top: 50%;
      transform: translate(-50%, -50%);
      -webkit-transform: translate(-50%, -50%);
      width: 90%;
      height: 90%;
      border: 10px solid #b9d9fc;
      z-index: 0;
      border-radius: 70px;
      animation: btntestafterAnima 5.6s infinite;
      transition: all 0.5s;
    }

    &:hover {
      &>span {
        background: #ff9900;
        box-shadow: 10px 10px 20px rgba(239, 176, 103, 0.75);
        animation: btntesthoverAnima 5.6s infinite;
      }

      &::after {
        border: 10px solid #fcd1b9;
        animation: btntestafterhoverAnima 5.6s infinite;
      }
    }
  }
}

@keyframes btntestAnima {
  5% {
    transform: scale(0.95);
    -webkit-transform: scale(0.95);
  }

  8% {
    transform: scale(1);
    -webkit-transform: scale(1);
  }
}

@keyframes btntesthoverAnima {
  5% {
    transform: scale(0.95);
    -webkit-transform: scale(0.95);
  }

  8% {
    transform: scale(1);
    -webkit-transform: scale(1);
  }
}

@keyframes btntestafterAnima {
  0% {
    width: 90%;
    height: 90%;
    border: 10px solid #b9d9fc;
  }

  19% {
    border: 10px solid rgba(185, 217, 252, 0.5);
    width: calc(100% + 40px);
    height: calc(100% + 40px);
  }

  24% {
    width: calc(100% + 40px);
    height: calc(100% + 40px);
  }

  29% {
    border: 0 solid rgba(185, 217, 252, 0);
    width: calc(100% + 40px);
    height: calc(100% + 40px);
  }

  100% {
    border: 0 solid rgba(185, 217, 252, 0);
    width: calc(100% + 40px);
    height: calc(100% + 40px);
  }
}

@keyframes btntestafterhoverAnima {
  0% {
    width: 90%;
    height: 90%;
    border: 10px solid #fcd1b9;
  }

  19% {
    border: 10px solid rgba(252, 209, 185, 0.5);
    width: calc(100% + 40px);
    height: calc(100% + 40px);
  }

  24% {
    width: calc(100% + 40px);
    height: calc(100% + 40px);
  }

  29% {
    border: 0 solid rgba(252, 209, 185, 0);
    width: calc(100% + 40px);
    height: calc(100% + 40px);
  }

  100% {
    border: 0 solid rgba(252, 209, 185, 0);
    width: calc(100% + 40px);
    height: calc(100% + 40px);
  }
}

@media screen and (min-width:991px) {
  .senior_citizen_discount_bg {
    background: var(--Pale-Pink-Grad, linear-gradient(184deg, rgba(255, 255, 255, 0.00) 13.58%, var(--Pink-Pale, #FFE9EC) 96.98%));

    .senior_citizen_discount {
      box-sizing: border-box;
      padding: 30px 0;
    }

    .senior_citizen_discount_content {
      box-sizing: border-box;
      padding: 30px 0;
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 30px;
      justify-content: center;

      .senior_items {
        border-radius: 10px;
        border: 2px solid var(--Pink-Mid, #FFA5CF);
        background: linear-gradient(90deg, var(--White, #FFF) 0%, rgba(255, 250, 250, 0.50) 26.5%, rgba(255, 250, 250, 0.50) 70.33%, var(--White, #FFF) 96.35%), var(--White, #FFF);
        box-sizing: border-box;
        padding: 15px;
        height: fit-content;
        min-height: 148px;

        .senior_items_title {
          color: var(--Grey-Deep, #4D4D4D);
          text-align: center;
          font-family: "Noto Sans HK";
          font-size: 24px;
          font-style: normal;
          font-weight: 700;
          line-height: 120%;
          letter-spacing: 2.4px;
          position: relative;
          margin-bottom: 15px;
        }

        .senior_items_title::after {
          position: absolute;
          content: '';
          display: inline-block;
          width: 142px;
          bottom: -5px;
          z-index: 3;
          left: 50%;
          transform: translateX(-50%);
          height: 2px;
          background: #FFE9EC;
        }

        .senior_items_title::before {
          position: absolute;
          content: '';
          display: inline-block;
          width: 20%;
          bottom: -5px;
          z-index: 4;
          left: 50%;
          transform: translateX(-50%);
          height: 2px;
          background: #F8298A;
        }

        .senior_items_content {
          display: flex;
          align-items: center;
          justify-content: center;
          flex-direction: column;
        }

        .senior_items_num {
          color: var(--Brand-Color, #F8298A);
          font-family: "Noto Sans HK";
          font-size: 30px;
          font-style: normal;
          font-weight: 900;
          line-height: 120%;
          letter-spacing: 3px;
        }

        .senior_items_text_red {
          color: var(--Brand-Color, #F8298A);
          font-family: "Noto Sans HK";
          font-size: 24px;
          font-style: normal;
          font-weight: 700;
          line-height: 120%;
          letter-spacing: 2.4px;
        }

        .senior_items_text {
          color: var(--Grey-Deep, #4D4D4D);
          font-family: "Noto Sans HK";
          font-size: 20px;
          font-style: normal;
          font-weight: 500;
          line-height: normal;
          letter-spacing: 2px;
        }

        .senior_items_text_slow {
          color: var(--Grey-Dark, #333);
          font-family: "Noto Sans HK";
          font-size: 16px;
          font-style: normal;
          font-weight: 400;
          line-height: 150%;
          letter-spacing: 1.6px;
        }

        .senior_items_bottom_line {
          padding-bottom: 8px;
          border-bottom: 1.28px dashed var(--Brand-Color, #F8298A);
          margin-bottom: 10px;
        }


        .senior_items_bg_red {
          border-radius: 5px;
          background: var(--Brand-Color, #F8298A);
          box-sizing: border-box;
          padding: 5px 10px;
          margin-bottom: 5px;
          color: var(--White, #FFF);
          font-family: "Noto Sans HK";
          font-size: 20px;
          font-style: normal;
          font-weight: 500;
          line-height: normal;
          letter-spacing: 2px;
        }
      }
    }

    .senior_citizen_discount_btn {
      display: flex;
      justify-content: center;
    }

  }


  .medical_voucher {
    box-sizing: border-box;
    padding: 30px 0;

    .medical_voucher_content {
      margin-top: 30px;
      display: flex;
      gap: 0 40px;

      &>div:nth-child(1) {
        border-radius: 10px;
        border: 1px solid var(---Green, #00A752);
        background: rgba(1, 168, 83, 0.07);
        box-sizing: border-box;
        padding: 15px 20PX;
        display: flex;
        flex-direction: column;
        gap: 15px 0;
        max-width: 600px;

        &>div:last-child {
          color: var(--GHV-Green, #01A853);
          font-family: "Noto Sans TC";
          font-size: 20px;
          font-style: normal;
          font-weight: 700;
          line-height: 160%;
          letter-spacing: 1.6px;
        }
      }

      &>div:nth-child(2) {
        display: flex;
        flex-direction: column;
        gap: 15px 0;
        padding: 15px 0;
      }

      .medical_voucher_items {
        display: flex;
        flex-direction: column;

        .medical_voucher_items_title {
          box-sizing: border-box;
          padding: 0 15px;
          color: var(--White, #FFF);
          font-family: "Noto Sans TC";
          font-size: 20px;
          font-style: normal;
          font-weight: 700;
          line-height: 160%;
          letter-spacing: 2px;
          width: fit-content;
          border-radius: 30px;
          background: var(--GHV-Green, #01A853);
        }

        .medical_voucher_items_list {
          padding-left: 10px;

          &>div {
            color: var(--Grey-Dark, #333);
            font-family: "Noto Sans HK";
            font-size: 20px;
            font-style: normal;
            font-weight: 400;
            line-height: 160%;
            letter-spacing: 3.5px;
          }
        }
      }
    }
  }

  .brief_introduction {
    box-sizing: border-box;
    padding: 30px 0;

    .brief_introduction_content_box1 {
      max-width: 960px;
      margin: 30px auto;

      .brief_introduction_content_info {
        display: flex;
        flex-direction: column;
        margin-top: 30px;

        &>div {
          &>span:nth-child(1) {
            color: var(--Grey-Deep, #4D4D4D);
            text-align: justify;
            font-family: "Noto Sans HK";
            font-size: 18px;
            font-style: normal;
            font-weight: 400;
            line-height: 200%;
            letter-spacing: 1.8px;
          }

          &>span:nth-child(2),
          &>a {
            color: var(--Theme-Color, #FC1682);
            font-family: "Noto Sans HK";
            font-size: 18px;
            font-style: normal;
            font-weight: 400;
            line-height: 200%;
            letter-spacing: 1.8px;
          }
        }
      }
    }

    .brief_introduction_content_text {
      color: var(--Grey-Deep, #4D4D4D);
      text-align: justify;
      font-family: "Noto Sans HK";
      font-size: 18px;
      font-style: normal;
      font-weight: 400;
      line-height: 200%;
      letter-spacing: 1.8px;
    }

    .brief_introduction_content_btn {
      display: flex;
      justify-content: center;
      margin-top: 30px;
    }
  }

  .method_step {
    .method_step_content {
      margin: 30px 0;
      color: var(--Grey-Deep, #4D4D4D);
      text-align: justify;
      font-family: "Noto Sans HK";
      font-size: 18px;
      font-style: normal;
      font-weight: 400;
      line-height: 200%;
      letter-spacing: 1.8px;

      &>div {
        a {
          color: var(--Brand-Color, #F8298A);
        }
      }
    }
  }

  .see_a_doctor_flow {
    margin: 30px auto;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 32px 0;
    box-sizing: border-box;
    padding: 30px 0;

    .bg_text {
      color: var(--White, #FFF);
      text-align: center;
      font-family: "Noto Sans TC";
      font-size: 28.571px;
      font-style: normal;
      font-weight: 700;
      line-height: 160%;
      letter-spacing: 2.857px;
      border-radius: 7.143px;
      padding: 5px 30px;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: fit-content;
    }

    .bg_red_text {
      background: var(--Brand-Color, #F8298A);
    }

    .bg_grey_deep_text {
      background: var(--Grey-Deep, #4D4D4D);
    }

    .bg_ghv_green_text {
      background: var(--GHV-Green, #01A853);
    }

    &>div:nth-child(2) {
      gap: 0 145px;
    }

    &>div:nth-child(3) {
      gap: 0 42px;
    }

    &>div:nth-child(5) {
      gap: 0 85px;
    }

    &>div:nth-child(6) {
      gap: 0 270px;
    }

    &>div {
      position: relative;
    }

    &>div:nth-child(1)::after,
    &>div:nth-child(4)::after {
      content: '';
      position: absolute;
      display: inline-block;
      width: 248px;
      height: 25px;
      background: url('https://static.ckjhk.com/ckj-image/3ba4d18c6ac3.svg') no-repeat;
      background-size: cover;
      bottom: -50%;
      left: 50%;
      transform: translateX(-50%);
    }

    &>div:nth-child(2) {
      &>div {
        position: relative;
      }

      &>div::after {
        content: '';
        position: absolute;
        display: inline-block;
        width: 11px;
        height: 25px;
        background: url('https://static.ckjhk.com/ckj-image/ceba626974a3.svg') no-repeat;
        background-size: cover;
        bottom: -50%;
        left: 50%;
        transform: translateX(-50%);
      }
    }

    &>div:nth-child(3) {
      &>div {
        position: relative;
      }

      &>div:nth-child(1)::after {
        content: '';
        position: absolute;
        display: inline-block;
        width: 43px;
        height: 56px;
        background: url('https://static.ckjhk.com/ckj-image/da511156228a.svg') no-repeat;
        background-size: cover;
        bottom: -55%;
        left: 70%;
        transform: translateX(-50%);
      }

      &>div:nth-child(2)::after {
        content: '';
        position: absolute;
        display: inline-block;
        width: 11px;
        height: 25px;
        background: url('https://static.ckjhk.com/ckj-image/ceba626974a3.svg') no-repeat;
        background-size: cover;
        bottom: 20%;
        left: -8%;
        transform: translateX(-50%) rotate(90deg);
      }
    }

    &>div:nth-child(6) {
      &>div:nth-child(1) {
        position: relative;
      }

      &>div:nth-child(1)::after {
        content: '';
        position: absolute;
        display: inline-block;
        width: 43px;
        height: 56px;
        background: url('https://static.ckjhk.com/ckj-image/da511156228a.svg') no-repeat;
        background-size: cover;
        bottom: -105%;
        left: 60%;
        transform: translateX(-50%);
      }
    }

    &>div:nth-child(5) {
      &>div {
        position: relative;
      }

      &>div:nth-child(1)::after {
        content: '';
        position: absolute;
        display: inline-block;
        width: 11px;
        height: 25px;
        background: url('https://static.ckjhk.com/ckj-image/ceba626974a3.svg') no-repeat;
        background-size: cover;
        bottom: -50%;
        left: 50%;
        transform: translateX(-50%);
      }

      &>div:nth-child(2)::after {
        content: '';
        position: absolute;
        display: inline-block;
        width: 42px;
        height: 132px;
        background: url('https://static.ckjhk.com/ckj-image/311219214d38.svg') no-repeat;
        background-size: cover;
        bottom: -240%;
        left: 40%;
        transform: translateX(-50%);
      }
    }

    &>div:nth-child(7)::after,
    &>div:nth-child(8)::after {
      content: '';
      position: absolute;
      display: inline-block;
      width: 11px;
      height: 25px;
      background: url('https://static.ckjhk.com/ckj-image/ceba626974a3.svg') no-repeat;
      background-size: cover;
      bottom: -50%;
      left: 50%;
      transform: translateX(-50%);
    }
  }

  .apply_for_path {
    box-sizing: border-box;
    padding: 30px 0;

    .apply_for_path_iframe {
      width: 672px;
      height: 378px;
      margin: 30px auto;

      &>iframe {
        width: 100%;
        height: 100%;
      }
    }

    .apply_for_path_content {
      display: flex;
      flex-direction: column;
      align-items: center;

      &>a {
        color: var(--GHV-Green, #01A853);
        font-family: "Noto Sans HK";
        font-size: 18px;
        font-style: normal;
        font-weight: 700;
        line-height: 200%;
        letter-spacing: 1.8px;
        text-decoration-line: underline;
        text-decoration-style: solid;
        text-decoration-skip-ink: auto;
        text-decoration-thickness: auto;
        text-underline-offset: auto;
        text-underline-position: from-font;
      }

      &>div {
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
  }

  .about_link {
    box-sizing: border-box;
    padding: 30px 0;

    ul {
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 0 50px;
      margin-top: 30px;

      li {
        list-style: disc;
        color: var(--Brand-Color, #F8298A);

        a {
          color: var(--Brand-Color, #F8298A);
          text-align: center;
          font-family: "Noto Sans HK";
          font-size: 18px;
          font-style: normal;
          font-weight: 400;
          line-height: 200%;
          /* 36px */
          letter-spacing: 1.8px;
          text-decoration-line: underline;
          text-decoration-style: solid;
          text-decoration-skip-ink: auto;
          text-decoration-thickness: auto;
          text-underline-offset: auto;
          text-underline-position: from-font;
        }
      }
    }
  }

  .news_content_list {
    box-sizing: border-box;
    padding: 30px 0;

    &>div:nth-child(3) {

      .news_content_list_item {
        margin-top: 30px;
        margin-bottom: 30px;
        display: flex;
        flex-direction: column;
        gap: 30px 0;
      }

      .news_content_list_item_img {
        max-width: 960px;
        margin: 0 auto;
      }

      .news_content_list_item_text {
        color: var(--Grey-Deep, #4D4D4D);
        text-align: justify;
        font-family: "Noto Sans HK";
        font-size: 18px;
        font-style: normal;
        font-weight: 400;
        line-height: 200%;
        letter-spacing: 1.8px;
      }

      .news_content_list_item_iframe {
        width: 672px;
        height: 378px;
        margin: 0 auto;

        &>iframe {
          width: 100%;
          height: 100%;
        }
      }

      .brief_introduction_content_btn {
        display: flex;
        justify-content: center;
        align-items: center;
      }
    }

  }

  .v2-service-problem {
    box-sizing: border-box;
    padding: 30px 0;

    :deep(.problem) {
      margin: 0;
    }

    :deep(.problem-in) {
      margin-top: 30px;
    }
  }

  .health-care-voucher {
    margin-top: 0;
    box-sizing: border-box;
    padding: 0 0 30px;

    .newsmodule {
      &-title {
        display: flex;
        justify-content: space-between;

        .mewsmodule-btn {
          &>a {
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

      &-lists {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        justify-content: center;
        max-width: 1187px;
        margin: 30px auto;
        gap: 31px;

        .list-in {
          width: 100%;
          display: flex;
          flex-direction: column;
          display: block;

          .image {
            width: 100%;
            height: 0;
            padding-bottom: 100%;
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
            -webkit-line-clamp: 1;
            line-clamp: 1;
            -webkit-box-orient: vertical;
            overflow: hidden;
            text-overflow: ellipsis;
            padding: 0 20px;
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
            -webkit-line-clamp: 2;
            line-clamp: 2;
            -webkit-box-orient: vertical;
            overflow: hidden;
            text-overflow: ellipsis;
            padding: 0 20px;
            flex: 1;
          }

          .btn {
            display: flex;
            justify-content: center;
            margin-top: 20px;
          }
        }
      }
    }
  }
}

@media screen and (max-width:992px) {
  .senior_citizen_discount_bg {
    background: var(--Pale-Pink-Grad, linear-gradient(184deg, rgba(255, 255, 255, 0.00) 13.58%, var(--Pink-Pale, #FFE9EC) 96.98%));

    .senior_citizen_discount {
      margin: 8vw 0;

      .senior_citizen_discount_content {
        margin: 4vw 5.33vw 21.865vw;
        height: 133.33vw;
        display: flex;
        gap: 4vw;
        position: relative;
        flex-direction: column;
        justify-content: space-between;

        .senior_items {
          width: 42.65vw;
          height: fit-content;
          border-radius: 10px;
          padding: 2.65vw 0;
          border: 2px solid var(--Pink-Mid, #FFA5CF);
          background: linear-gradient(90deg, var(--White, #FFF) 0%, rgba(255, 250, 250, 0.50) 26.5%, rgba(255, 250, 250, 0.50) 70.33%, var(--White, #FFF) 96.35%), var(--White, #FFF);

          .senior_items_title {
            color: var(--Grey-Deep, #4D4D4D);
            text-align: center;
            font-family: "Noto Sans HK";
            font-size: 4.8vw;
            font-style: normal;
            font-weight: 700;
            line-height: 120%;
            letter-spacing: 0.48vw;
            position: relative;
            margin-bottom: 2.65vw;
          }

          .senior_items_title::after {
            position: absolute;
            content: '';
            display: inline-block;
            width: 37.865vw;
            bottom: -1.33vw;
            z-index: 3;
            left: 50%;
            transform: translateX(-50%);
            height: 2px;
            background: #FFE9EC;
          }

          .senior_items_title::before {
            position: absolute;
            content: '';
            display: inline-block;
            width: 20%;
            bottom: -1.33vw;
            z-index: 4;
            left: 50%;
            transform: translateX(-50%);
            height: 2px;
            background: #F8298A;
          }

          .senior_items_content {
            display: flex;
            align-items: center;
            justify-content: center;
            flex-direction: column;
          }

          .senior_items_num {
            color: var(--Brand-Color, #F8298A);
            font-family: "Noto Sans HK";
            font-size: 6.4vw;
            font-style: normal;
            font-weight: 700;
            line-height: normal;
            letter-spacing: 0.64vw;
          }

          .senior_items_text_red {
            color: var(--Brand-Color, #F8298A);
            font-family: "Noto Sans HK";
            font-size: 4.8vw;
            font-style: normal;
            font-weight: 700;
            line-height: 120%;
            letter-spacing: 0.48vw;
          }

          .senior_items_text {
            color: var(--Grey-Deep, #4D4D4D);
            font-family: "Noto Sans HK";
            font-size: 3.733vw;
            font-style: normal;
            font-weight: 600;
            line-height: 150%;
            letter-spacing: 0.186vw;
          }

          .senior_items_text_slow {
            color: var(--Grey-Deep, #4D4D4D);
            text-align: center;
            font-family: "Noto Sans HK";
            font-size: 3.2vw;
            font-style: normal;
            font-weight: 500;
            line-height: 150%;
            letter-spacing: 0.16vw;
          }

          .senior_items_bottom_line {
            padding-bottom: 2.13vw;
            border-bottom: 1.28px dashed var(--Brand-Color, #F8298A);
            margin-bottom: 3.73vw;
          }


          .senior_items_bg_red {
            border-radius: 5px;
            background: var(--Brand-Color, #F8298A);
            box-sizing: border-box;
            padding: 0.8vw 3.733vw;
            margin-bottom: 1.33vw;
            color: var(--White, #FFF);
            font-family: "Noto Sans HK";
            font-size: 3.73vw;
            font-style: normal;
            font-weight: 600;
            line-height: 150%;
            letter-spacing: 0.1865vw;
          }
        }

        .senior_items:nth-child(5),
        .senior_items:nth-child(6) {
          position: absolute;
          right: 0;
          top: 0;
        }

        .senior_items:nth-child(5) {
          top: auto;
          bottom: -17.5vw;
        }
      }

      .senior_citizen_discount_btn {
        margin: 5px auto 20px;
        padding-bottom: 20px;

        :deep(.animbtntypetwo) {
          margin: 0;
        }
      }
    }
  }

  .medical_voucher {
    padding: 0;
    margin: 8vw auto;

    .medical_voucher_content {
      margin-top: 8vw;
      display: flex;
      flex-direction: column;
      gap: 2.665vw 0;

      &>div:nth-child(1) {
        border-radius: 10px;
        border: 1px solid var(---Green, #00A752);
        background: rgba(1, 168, 83, 0.07);
        box-sizing: border-box;
        padding: 2.665vw;
        margin: 0 2.665vw;
        display: flex;
        flex-direction: column;
        gap: 4vw 0;
        max-width: 100%;

        &>div:last-child {
          color: var(--GHV-Green, #01A853);
          text-align: justify;
          font-family: "Noto Sans HK";
          font-size: 3.2vw;
          font-style: normal;
          font-weight: 500;
          line-height: 150%;
          letter-spacing: 0.16vw;
        }
      }

      &>div:nth-child(2) {
        margin: 0 2.66vw;
        box-sizing: border-box;
        padding: 0 2.66vw;
        display: flex;
        flex-direction: column;
        gap: 2.66vw 0;
      }

      .medical_voucher_items {
        display: flex;
        flex-direction: column;

        .medical_voucher_items_title {
          box-sizing: border-box;
          padding: 0 4vw;
          color: var(--White, #FFF);
          font-family: "Noto Sans HK";
          font-size: 3.733vw;
          font-style: normal;
          font-weight: 600;
          line-height: 150%;
          letter-spacing: 0.1865vw;
          width: fit-content;
          border-radius: 8vw;
          background: var(--GHV-Green, #01A853);
        }

        .medical_voucher_items_list {
          padding-left: 2.665vw;

          &>div {
            color: var(--Grey-Dark, #333);
            font-family: "Noto Sans HK";
            font-size: 3.2vw;
            font-style: normal;
            font-weight: 400;
            line-height: 150%;
            letter-spacing: 0.16vw;
          }
        }
      }
    }
  }

  .brief_introduction {
    margin: 8vw 0;

    .brief_introduction_content {
      margin: 0 8vw;
    }

    .brief_introduction_content_box1 {
      margin: 8vw auto;

      .brief_introduction_content_info {
        display: flex;
        flex-direction: column;
        margin-top: 8vw;

        &>div {
          &>span:nth-child(1) {
            color: var(--Grey-Deep, #4D4D4D);
            text-align: justify;
            font-family: "Noto Sans HK";
            font-size: 3.733vw;
            font-style: normal;
            font-weight: 400;
            line-height: 150%;
            /* 21px */
            letter-spacing: 0.13vw;
          }

          &>span:nth-child(2),
          &>a {
            color: var(--Theme-Color, #FC1682);
            font-family: "Noto Sans HK";
            font-size: 3.733vw;
            font-style: normal;
            font-weight: 400;
            line-height: 150%;
            /* 21px */
            letter-spacing: 0.133vw;
          }
        }
      }
    }

    .brief_introduction_content_text {
      color: var(--Grey-Deep, #4D4D4D);
      text-align: justify;
      font-family: "Noto Sans HK";
      font-size: 3.733vw;
      font-style: normal;
      font-weight: 400;
      line-height: 150%;
      letter-spacing: 0.1865vw;
    }

    .brief_introduction_content_btn {
      display: flex;
      justify-content: center;
      margin-top: 8vw;
    }
  }

  .method_step {
    .method_step_content {
      margin: 4vw 8vw 0;
      color: var(--Grey-Deep, #4D4D4D);
      text-align: justify;
      font-family: "Noto Sans HK";
      font-size: 3.733vw;
      font-style: normal;
      font-weight: 400;
      line-height: 150%;
      /* 21px */
      letter-spacing: 0.1865vw;

      &>div {
        a {
          color: var(--Brand-Color, #F8298A);
        }
      }
    }
  }

  .see_a_doctor_flow {
    margin: 8vw auto;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 6.667vw 0;
    box-sizing: border-box;
    padding: 0 8vw;

    .bg_text {
      color: var(--White, #FFF);
      text-align: center;
      font-family: "Noto Sans TC";
      font-size: 3.733vw;
      font-style: normal;
      font-weight: 600;
      line-height: 150%;
      /* 21px */
      letter-spacing: 0.1865vw;

      border-radius: 5px;
      padding: 1.065vw 5.33vw;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: fit-content;
    }

    .bg_red_text {
      background: var(--Brand-Color, #F8298A);
    }

    .bg_grey_deep_text {
      background: var(--Grey-Deep, #4D4D4D);
    }

    .bg_ghv_green_text {
      background: var(--GHV-Green, #01A853);
    }

    &>div:nth-child(2) {
      gap: 0 21.2vw;
    }

    &>div:nth-child(3) {
      gap: 0 7.865vw;
    }

    &>div:nth-child(5) {
      gap: 0 21.2vw;
    }

    &>div:nth-child(6) {
      gap: 0 45.33vw;
    }

    &>div {
      position: relative;
    }

    &>div:nth-child(1)::after,
    &>div:nth-child(4)::after {
      content: '';
      position: absolute;
      display: inline-block;
      width: 45.6vw;
      height: 4.53vw;
      background: url('https://static.ckjhk.com/ckj-image/3ba4d18c6ac3.svg') no-repeat;
      background-size: cover;
      bottom: -68%;
      left: 50%;
      transform: translateX(-50%);
    }

    &>div:nth-child(2) {
      &>div {
        position: relative;
      }

      &>div::after {
        content: '';
        position: absolute;
        display: inline-block;
        width: 1.865vw;
        height: 4.53vw;
        background: url('https://static.ckjhk.com/ckj-image/ceba626974a3.svg') no-repeat;
        background-size: cover;
        bottom: -65%;
        left: 50%;
        transform: translateX(-50%);
      }
    }

    &>div:nth-child(3) {
      &>div {
        position: relative;
      }

      &>div:nth-child(1)::after {
        content: '';
        position: absolute;
        display: inline-block;
        width: 7.5453vw;
        height: 10.265vw;
        background: url('https://static.ckjhk.com/ckj-image/da511156228a.svg') no-repeat;
        background-size: cover;
        bottom: -80%;
        left: 57%;
        transform: translateX(-50%);
      }

      &>div:nth-child(2)::after {
        content: '';
        position: absolute;
        display: inline-block;
        width: 1.865vw;
        height: 4.53vw;
        background: url('https://static.ckjhk.com/ckj-image/ceba626974a3.svg') no-repeat;
        background-size: cover;
        bottom: 20%;
        left: -10%;
        transform: translateX(-50%) rotate(90deg);
      }
    }

    &>div:nth-child(6) {
      &>div:nth-child(1) {
        position: relative;
      }

      &>div:nth-child(1)::after {
        content: '';
        position: absolute;
        display: inline-block;
        width: 7.5453vw;
        height: 10.265vw;
        background: url('https://static.ckjhk.com/ckj-image/da511156228a.svg') no-repeat;
        background-size: cover;
        bottom: -141%;
        left: 57%;
        transform: translateX(-50%);
      }
    }

    &>div:nth-child(5) {
      &>div {
        position: relative;
      }

      &>div:nth-child(1)::after {
        content: '';
        position: absolute;
        display: inline-block;
        width: 1.865vw;
        height: 4.53vw;
        background: url('https://static.ckjhk.com/ckj-image/ceba626974a3.svg') no-repeat;
        background-size: cover;
        bottom: -68%;
        left: 50%;
        transform: translateX(-50%);
      }

      &>div:nth-child(2)::after {
        content: '';
        position: absolute;
        display: inline-block;
        width: 7.5453vw;
        height: 24.416vw;
        background: url('https://static.ckjhk.com/ckj-image/311219214d38.svg') no-repeat;
        background-size: cover;
        bottom: -330%;
        left: 40%;
        transform: translateX(-50%);
      }
    }

    &>div:nth-child(7)::after,
    &>div:nth-child(8)::after {
      content: '';
      position: absolute;
      display: inline-block;
      width: 1.865vw;
      height: 4.53vw;
      background: url('https://static.ckjhk.com/ckj-image/ceba626974a3.svg') no-repeat;
      background-size: cover;
      bottom: -68%;
      left: 50%;
      transform: translateX(-50%);
    }
  }

  .apply_for_path {
    margin: 8vw auto;

    .apply_for_path_iframe {
      width: 72.533vw;
      height: 40.8vw;
      margin: 4vw auto;
      box-sizing: border-box;

      &>iframe {
        width: 100%;
        height: 100%;
      }
    }

    .apply_for_path_content {
      box-sizing: border-box;
      padding: 0 8vw;
      display: flex;
      flex-direction: column;
      align-items: flex-start;
      gap: 4vw 0;

      &>a {
        color: var(--GHV-Green, #01A853);
        font-family: "Noto Sans HK";
        font-size: 3.733vw;
        font-style: normal;
        font-weight: 400;
        line-height: 150%;
        /* 21px */
        letter-spacing: 0.1865vw;
        text-decoration-line: underline;
        text-decoration-style: solid;
        text-decoration-skip-ink: auto;
        text-decoration-thickness: auto;
        text-underline-offset: auto;
        text-underline-position: from-font;
      }

      &>div {
        color: var(--Grey-Deep, #4D4D4D);
        font-family: "Noto Sans HK";
        font-size: 3.733vw;
        font-style: normal;
        font-weight: 400;
        line-height: 150%;
        /* 21px */
        letter-spacing: 0.1865vw;
      }
    }
  }

  .about_link {
    margin: 8vw auto;

    ul {
      display: flex;
      justify-content: center;
      flex-direction: column;
      align-items: flex-start;
      gap: 0;
      margin-top: 0;
      padding-left: 8vw;

      li {
        margin-left: 5.33vw;
        box-sizing: border-box;
        padding: 0;
        list-style: disc;
        color: var(--Brand-Color, #F8298A);

        a {
          color: var(--Brand-Color, #F8298A);
          text-align: center;
          font-family: "Noto Sans HK";
          font-size: 3.733vw;
          font-style: normal;
          font-weight: 400;
          line-height: 150%;
          letter-spacing: 0.1865vw;
          text-decoration-line: underline;
          text-decoration-style: solid;
          text-decoration-skip-ink: auto;
          text-decoration-thickness: auto;
          text-underline-offset: auto;
          text-underline-position: from-font;
        }
      }
    }
  }

  .news_content_list {
    margin: 8vw auto;

    &>div:nth-child(3) {

      .news_content_list_item {
        margin-top: 4vw;
        margin-bottom: 4vw;
        display: flex;
        flex-direction: column;
        gap: 4vw 0;
      }

      .news_content_list_item_img {
        max-width: 100%;
        margin: 0 auto;
      }

      .news_content_list_item_text {
        box-sizing: border-box;
        padding: 0 8vw;
        color: var(--Grey-Deep, #4D4D4D);
        text-align: justify;
        font-family: "Noto Sans HK";
        font-size: 3.733vw;
        font-style: normal;
        font-weight: 400;
        line-height: 150%;
        letter-spacing: 0.1865vw;
      }

      .news_content_list_item_text_one {
        // 显示三行 多余 ...
        overflow: hidden;
        text-overflow: ellipsis;
        display: -webkit-box;
        -webkit-line-clamp: 3;
        -webkit-box-orient: vertical;
        word-break: break-all;
      }

      .news_content_list_item_iframe {
        width: 72.533vw;
        height: 40.618vw;
        margin: 0 auto;

        &>iframe {
          width: 100%;
          height: 100%;
        }
      }

      .brief_introduction_content_btn {
        display: flex;
        justify-content: center;
        align-items: center;
      }
    }

  }

  .animbtntypetwo {
    &-in {
      &>span {
        font-size: 5.33vw;
        padding: 2.133vw 8vw;
      }

      &::after {
        border: 7px solid #b9d9fc;
      }

      &.smallmb {
        &>span {
          font-size: 4.265vw;
          padding: 1.33vw 5.33vw;
        }
      }
    }
  }

  @keyframes btntestafterAnima {
    0% {
      width: 90%;
      height: 90%;
      border: 7px solid #b9d9fc;
    }

    19% {
      border: 7px solid rgba(185, 217, 252, 0.5);
      width: calc(100% + 28px);
      height: calc(100% + 28px);
    }

    24% {
      width: calc(100% + 28px);
      height: calc(100% + 28px);
    }

    29% {
      border: 0 solid rgba(185, 217, 252, 0);
      width: calc(100% + 28px);
      height: calc(100% + 28px);
    }

    100% {
      border: 0 solid rgba(185, 217, 252, 0);
      width: calc(100% + 28px);
      height: calc(100% + 28px);
    }
  }

  @keyframes btntestafterhoverAnima {
    0% {
      width: 90%;
      height: 90%;
      border: 7px solid #fcd1b9;
    }

    19% {
      border: 7px solid rgba(252, 209, 185, 0.5);
      width: calc(100% + 28px);
      height: calc(100% + 28px);
    }

    24% {
      width: calc(100% + 28px);
      height: calc(100% + 28px);
    }

    29% {
      border: 0 solid rgba(252, 209, 185, 0);
      width: calc(100% + 28px);
      height: calc(100% + 28px);
    }

    100% {
      border: 0 solid rgba(252, 209, 185, 0);
      width: calc(100% + 28px);
      height: calc(100% + 28px);
    }
  }
}
</style>

<style lang="scss" scoped>
.new_info_health {
  position: relative;
  margin-top: 230px;
  margin-bottom: 0;
}

:deep(.problem) {
  i {
    font-style: normal !important;
    color: #43be7f !important;
  }
}

:deep(.header-content .explain_box_mobile) {
  display: none !important;
}

.new_info_header {
  display: flex;
  justify-content: center;
  position: relative;

  &>div:nth-child(1) {
    position: absolute;
    z-index: 1;
    bottom: -150%;
    left: 17%;
  }

  color: var(--Theme-Color, #fc1682);
  text-align: justify;
  font-family: FakePearl;
  font-size: 48px;
  font-style: normal;
  font-weight: 400;
  line-height: 130%;
  /* 62.4px */
}

.new_info_content_bg {
  position: relative;
  z-index: 5;
  border-radius: 60px 60px var(--Count, 0px) var(--Count, 0px);
  background: linear-gradient(180deg, #fee6f1 -15.1%, #fff 68.08%);
}

.new_info_content_bg::before {
  position: absolute;
  content: '';
  display: inline-block;
  width: 70px;
  height: 85px;
  background: url('https://static.cmereye.com/imgs/2024/08/843c8466fed81592.png') no-repeat;
  background-size: 100% 100%;
  top: -40px;
  left: 19%;
}

.new_info_content {
  position: relative;
  z-index: 10;
  box-sizing: border-box;
  padding: 120px 0 0;
  max-width: 1450px;
  margin: 0 auto;
  margin-top: 30px;

  &>div:nth-child(1) {
    color: var(--Grey-Deep, #4d4d4d);
    text-align: justify;
    font-family: 'Noto Sans HK';
    font-size: 20px;
    font-style: normal;
    font-weight: 400;
    line-height: 160%;
    /* 32px */
    letter-spacing: 4px;
  }

  &>div:nth-child(2) {
    margin-top: 60px;

    &>div:nth-child(1) {
      margin-bottom: 60px;
      color: var(--Theme-Color, #fc1682);
      text-align: center;
      font-family: 'FakePearl-Regular';
      font-size: 30px;
      font-style: normal;
      font-weight: 400;
      line-height: 160%;
      /* 48px */
      letter-spacing: 3px;
    }
  }

  &>div:nth-child(3) {
    margin-top: 0px;
    color: var(--Grey-Deep, #4d4d4d);
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

.explain {
  color: var(--Grey-Deep, #4d4d4d);
  text-align: right;
  font-family: 'Noto Sans HK';
  font-size: 20px;
  font-style: normal;
  font-weight: 400;
  line-height: 160%;
  letter-spacing: 4px;
  position: relative;
  top: -30px;
}

.new_info_content_items {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 64px clamp(10px, 3vw, 125px);

  &>div {
    width: clamp(340px, 20.9vw, 402px);
    position: relative;
    z-index: 5;

    &>div:nth-child(1) {
      border-radius: 30px;
      border: 2px solid #fc1682;
      background: #fff;
      box-shadow: 6px 6px 0px 0px rgba(252, 22, 130, 0.3);

      &>div:nth-child(1) {
        padding: clamp(10px, 0.05vw, 30px) 0 15px;
        color: #14a033;
        text-align: center;
        font-family: 'FakePearl-Regular';
        font-size: 30px;
        font-style: normal;
        font-weight: 500;
        line-height: 160%;
        /* 48px */
        letter-spacing: 3px;
      }

      &>div:nth-child(2) {
        box-sizing: border-box;
        padding: 20px clamp(10px, 0.05vw, 30px);
        border-radius: var(--Count, 0px) var(--Count, 0px) 30px 30px;
        background: var(--Pink-Pale, #fee6f1);
      }
    }

    &>div:nth-child(1) {
      &>div:nth-child(2) {
        display: flex;
        flex-direction: column;
        color: var(--Theme-Color, #fc1682);
        text-align: center;
        text-shadow: 0px 2px 0px var(--White, #fff);
        -webkit-text-stroke-width: 2;
        -webkit-text-stroke-color: #fff;
        font-family: 'Noto Sans HK';
        font-size: 35px;
        font-style: normal;
        font-weight: 700;
        line-height: 160%;
        /* 56px */
        letter-spacing: 5.6px;

        i {
          color: var(--Grey-Deep, #4d4d4d);
          font-family: 'Noto Sans HK';
          font-size: 30px;
          font-style: normal;
          font-weight: 500;
          line-height: 160%;
          letter-spacing: 4.8px;
        }
      }
    }
  }

  &>div:nth-child(2) {
    &>div:nth-child(1) {
      display: flex;
      flex-direction: column;
      color: var(--Theme-Color, #fc1682);
      text-align: center;
      text-shadow: 0px 2px 0px var(--White, #fff);
      -webkit-text-stroke-width: 2;
      -webkit-text-stroke-color: #fff;
      font-family: 'Noto Sans HK';
      font-size: 35px;
      font-style: normal;
      font-weight: 700;
      line-height: 160%;
      /* 56px */
      letter-spacing: 5.6px;

      &>div:nth-child(2) {
        &>span:nth-child(2) {
          color: var(--Grey-Deep, #4d4d4d);
          font-family: 'Noto Sans HK';
          font-size: 20px;
          font-style: normal;
          font-weight: 500;
          line-height: 160%;
          letter-spacing: 3.2px;
        }
      }
    }
  }

  &>div:nth-child(3) {
    &>div:nth-child(1) {
      display: flex;
      flex-direction: column;
      color: var(--Theme-Color, #fc1682);
      text-align: center;
      text-shadow: 0px 2px 0px var(--White, #fff);
      -webkit-text-stroke-width: 2;
      -webkit-text-stroke-color: #fff;
      font-family: 'Noto Sans HK';
      font-size: 35px;
      font-style: normal;
      font-weight: 700;
      line-height: 160%;
      /* 56px */
      letter-spacing: 5.6px;

      &>div:nth-child(2) {
        display: flex;
        flex-direction: row;
        align-items: flex-end;
        justify-content: center;

        &>span:nth-child(1) {
          color: var(--Theme-Color, #fc1682);
          font-family: 'Noto Sans HK';
          font-size: 60px;
          font-style: normal;
          font-weight: 900;
          line-height: 100%;
          letter-spacing: 9.6px;

          &>i {
            color: var(--Theme-Color, #fc1682);
            text-align: center;
            text-shadow: 0px 2px 0px var(--White, #fff);
            -webkit-text-stroke-width: 2;
            -webkit-text-stroke-color: #fff;
            font-family: 'Noto Sans HK';
            font-size: 30px;
            font-style: normal;
            font-weight: 700;
            line-height: 160%;
            /* 48px */
            letter-spacing: 4.8px;
          }
        }

        &>span:nth-child(2) {
          color: var(--Grey-Deep, #4d4d4d);
          font-family: 'Noto Sans HK';
          font-size: 20px;
          font-style: normal;
          font-weight: 500;
          line-height: 200%;
          letter-spacing: 3.2px;
          position: relative;
        }

        &>span:nth-child(2)::after {
          content: '';
          width: 100%;
          height: 2px;
          background: #4d4d4d;
          display: inline-block;
          position: absolute;
          left: 0;
          top: 50%;
          transform: rotate(-5deg);
        }
      }
    }
  }

  &>div:nth-child(4) {
    &>div:nth-child(1) {
      display: flex;
      flex-direction: column;
      color: var(--Theme-Color, #fc1682);
      text-align: center;
      text-shadow: 0px 2px 0px var(--White, #fff);
      -webkit-text-stroke-width: 2;
      -webkit-text-stroke-color: #fff;
      font-family: 'Noto Sans HK';
      font-size: 35px;
      font-style: normal;
      font-weight: 700;
      line-height: 160%;
      /* 56px */
      letter-spacing: 5.6px;

      &>div:nth-child(2) {
        display: flex;
        flex-direction: row;
        align-items: flex-end;
        justify-content: center;

        &>span:nth-child(1) {
          color: var(--Theme-Color, #fc1682);
          font-family: 'Noto Sans HK';
          font-size: 60px;
          font-style: normal;
          font-weight: 900;
          line-height: 100%;
          letter-spacing: 9.6px;

          &>i {
            color: var(--Theme-Color, #fc1682);
            text-align: center;
            text-shadow: 0px 2px 0px var(--White, #fff);
            -webkit-text-stroke-width: 2;
            -webkit-text-stroke-color: #fff;
            font-family: 'Noto Sans HK';
            font-size: 30px;
            font-style: normal;
            font-weight: 700;
            line-height: 160%;
            /* 48px */
            letter-spacing: 4.8px;
          }
        }

        &>span:nth-child(2) {
          color: var(--Grey-Deep, #4d4d4d);
          font-family: 'Noto Sans HK';
          font-size: 20px;
          font-style: normal;
          font-weight: 500;
          line-height: 200%;
          letter-spacing: 3.2px;
          position: relative;
        }

        &>span:nth-child(2)::after {
          content: '';
          width: 100%;
          height: 2px;
          background: #4d4d4d;
          display: inline-block;
          position: absolute;
          left: 0;
          top: 50%;
          transform: rotate(-5deg);
        }
      }
    }
  }

  &>div:nth-child(5) {
    &>div:nth-child(1) {
      &>div:nth-child(2) {
        display: flex;
        flex-direction: row;
        align-items: flex-end;
        white-space: nowrap;

        &>span:nth-child(1) {
          text-align: center;
          text-shadow: 0px 2px 0px var(--White, #fff);
          -webkit-text-stroke-width: 2;
          -webkit-text-stroke-color: #fff;
          font-family: 'Noto Sans HK';
          font-size: 45px;

          i {
            font-size: 30px;
            font-style: normal;
            font-weight: 500;
            line-height: 160%;
            /* 48px */
            letter-spacing: 4.8px;
          }
        }

        &>span:nth-child(2) {
          color: var(--Grey-Deep, #4d4d4d);
          font-family: 'Noto Sans HK';
          font-size: 20px;
          font-style: normal;
          font-weight: 500;
          line-height: 160%;
          letter-spacing: 3.2px;
        }
      }
    }
  }

  &>div:nth-child(6) {
    &>div:nth-child(1) {
      &>div:nth-child(2) {
        padding-bottom: 48px;
        padding-top: 38px;

        &>div:nth-child(1) {
          display: flex;
          flex-direction: column;

          &>span:nth-child(1) {
            text-align: center;
            text-shadow: 0px 2px 0px var(--White, #fff);
            -webkit-text-stroke-width: 2;
            -webkit-text-stroke-color: #fff;
            font-size: 60px;
            font-style: normal;
            font-weight: 700;
            line-height: 160%;
            letter-spacing: 9.6px;
            font-family: 'Noto Sans HK';

            &>i {
              color: var(--Grey-Deep, #4d4d4d);
              font-size: 30px;
              font-style: normal;
              font-weight: 500;
              line-height: 160%;
              /* 48px */
              letter-spacing: 4.8px;
            }
          }

          &>span:nth-child(2) {
            color: var(--Grey-Deep, #4d4d4d);
            text-align: center;
            text-shadow: 0px 2px 0px var(--White, #fff);
            -webkit-text-stroke-width: 2;
            -webkit-text-stroke-color: #fff;
            font-family: 'Noto Sans HK';
            font-size: 30px;
            font-style: normal;
            font-weight: 500;
            line-height: 160%;
            /* 48px */
            letter-spacing: 4.8px;
          }
        }

        &>div:nth-child(2) {
          display: flex;
          flex-direction: row;
          align-items: flex-end;
          justify-content: center;
          margin-top: 10px;

          &>span:nth-child(1) {
            color: var(--Theme-Color, #fc1682);
            font-family: 'Noto Sans HK';
            font-size: 60px;
            font-style: normal;
            font-weight: 900;
            line-height: 100%;
            letter-spacing: 9.6px;

            &>i {
              color: var(--Theme-Color, #fc1682);
              text-align: center;
              text-shadow: 0px 2px 0px var(--White, #fff);
              -webkit-text-stroke-width: 2;
              -webkit-text-stroke-color: #fff;
              font-family: 'Noto Sans HK';
              font-size: 30px;
              font-style: normal;
              font-weight: 700;
              line-height: 160%;
              /* 48px */
              letter-spacing: 4.8px;
            }
          }

          &>span:nth-child(2) {
            color: var(--Grey-Deep, #4d4d4d);
            font-family: 'Noto Sans HK';
            font-size: 20px;
            font-style: normal;
            font-weight: 500;
            line-height: 200%;
            letter-spacing: 3.2px;
            position: relative;
          }

          &>span:nth-child(2)::after {
            content: '';
            width: 100%;
            height: 2px;
            background: #4d4d4d;
            display: inline-block;
            position: absolute;
            left: 0;
            top: 50%;
            transform: rotate(-5deg);
          }
        }

        &>div:nth-child(3) {
          &>span:nth-child(1) {
            color: var(--Grey-Deep, #4d4d4d);
            text-align: center;
            text-shadow: 0px 2px 0px var(--White, #fff);
            -webkit-text-stroke-width: 2;
            -webkit-text-stroke-color: #fff;
            font-family: 'Noto Sans HK';
            font-size: 30px;
            font-style: normal;
            font-weight: 500;
            line-height: 160%;
            /* 48px */
            letter-spacing: 4.8px;

            &>i {
              color: var(--Theme-Color, #fc1682);
              font-family: 'Noto Sans HK';
              font-size: 60px;
              font-style: normal;
              font-weight: 900;
              line-height: 160%;
              letter-spacing: 9.6px;

              &>i {
                font-size: 30px;
                letter-spacing: 4.8px;
              }
            }
          }

          &>span:nth-child(2) {
            color: var(--Grey-Deep, #4d4d4d);
            text-align: center;
            text-shadow: 0px 2px 0px var(--White, #fff);
            -webkit-text-stroke-width: 2;
            -webkit-text-stroke-color: #fff;
            font-family: 'Noto Sans HK';
            font-size: 30px;
            font-style: normal;
            font-weight: 500;
            line-height: 160%;
            /* 48px */
            letter-spacing: 4.8px;

            &>i {
              color: var(--Grey-Deep, #4d4d4d);
              font-family: 'Noto Sans HK';
              font-size: 20px;
              font-style: normal;
              font-weight: 500;
              line-height: 160%;
              letter-spacing: 3.2px;
            }
          }
        }
      }
    }
  }

  &>div:nth-child(7) {
    margin-top: 10px;

    &>div:nth-child(1) {
      &>div:nth-child(1) {
        display: flex;
        flex-direction: column;

        span {
          font-family: 'FakePearl-Regular';
        }
      }

      &>div:nth-child(2) {
        display: flex;
        flex-direction: row;
        align-items: flex-end;
        justify-content: center;

        &>span:nth-child(1) {
          color: var(--Grey-Deep, #4d4d4d);
          text-align: center;
          text-shadow: 0px 2px 0px var(--White, #fff);
          -webkit-text-stroke-width: 2;
          -webkit-text-stroke-color: #fff;
          font-family: 'Noto Sans HK';
          font-size: 30px;
          font-style: normal;
          font-weight: 500;
          line-height: 160%;
          /* 48px */
          letter-spacing: 4.8px;

          &>i {
            color: var(--Theme-Color, #fc1682);
            font-family: 'Noto Sans HK';
            font-size: 45px;
            font-style: normal;
            font-weight: 700;
            line-height: 130%;
            letter-spacing: 7.2px;
          }
        }

        &>span:nth-child(2) {
          color: var(--Grey-Deep, #4d4d4d);
          text-align: center;
          text-shadow: 0px 2px 0px var(--White, #fff);
          -webkit-text-stroke-width: 2;
          -webkit-text-stroke-color: #fff;
          font-family: 'Noto Sans HK';
          font-size: 30px;
          font-style: normal;
          font-weight: 500;
          line-height: 160%;
          /* 48px */
          letter-spacing: 4.8px;

          &>i {
            color: var(--Theme-Color, #fc1682);
          }
        }
      }
    }
  }

  &>div:nth-child(8) {
    margin-top: 10px;

    &>div:nth-child(1) {
      &>div:nth-child(1) {
        display: flex;
        flex-direction: column;

        span {
          font-family: 'FakePearl-Regular';
        }
      }

      &>div:nth-child(2) {
        display: flex;
        flex-direction: column;

        // align-items: flex-end;
        // justify-content: center;
        &>span:nth-child(1) {
          color: var(--Grey-Deep, #4d4d4d);
          text-align: center;
          text-shadow: 0px 2px 0px var(--White, #fff);
          -webkit-text-stroke-width: 2;
          -webkit-text-stroke-color: #fff;
          font-family: 'Noto Sans HK';
          font-size: 30px;
          font-style: normal;
          font-weight: 500;
          line-height: 160%;
          /* 48px */
          letter-spacing: 4.8px;

          &>i {
            color: var(--Theme-Color, #fc1682);
            font-family: 'Noto Sans HK';
            font-size: 45px;
            font-style: normal;
            font-weight: 700;
            line-height: 130%;
            letter-spacing: 7.2px;
          }

          &>i:nth-child(2) {
            font-size: 30px;
            letter-spacing: 4.8px;
          }
        }

        &>span:nth-child(2) {
          color: var(--Grey-Deep, #4d4d4d);
          font-size: 20px;
          font-style: normal;
          font-weight: 500;
          line-height: 160%;
          letter-spacing: 3.2px;
          font-family: 'FakePearl-Regular';
        }
      }
    }
  }

  .abs_box {
    position: absolute;
    top: -16px;
    left: -16px;
    z-index: 2;
    background: url('https://static.cmereye.com/imgs/2024/08/804246100e3ed97f.png') no-repeat;
    width: 86px;
    height: 86px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    color: #fff;
    text-align: center;
    font-family: 'FakePearl-Regular';
    font-size: 20px;
    font-style: normal;
    font-weight: 500;
    line-height: 160%;
    /* 32px */
  }
}

.new_info_content_items>div:nth-child(6) {
  grid-row: 2 / span 3;
  grid-column: 3 / span 1;
}

.health-care-voucher-top {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;

  .lang {
    display: flex;

    span {
      cursor: pointer;
      color: var(--textColor);

      &:hover {
        color: var(--indexColor1);
      }

      &:not(:last-child) {
        &::after {
          content: '|';
          display: inline-block;
          color: var(--textColor);
          margin: 0 10px;
        }
      }
    }
  }
}

.new_defule {
  color: #4d4d4d;
  text-align: justify;
  font-family: 'Noto Sans HK';
  font-size: 20px;
  font-style: normal;
  font-weight: 400;
  line-height: 160%;
  /* 32px */
  letter-spacing: 4px;
}

.new_step {
  background: linear-gradient(180deg,
      rgba(252, 22, 130, 0.4) -68.47%,
      rgba(252, 22, 130, 0.28) -68.46%,
      rgba(255, 168, 198, 0) 63.88%);

  .resolve_step {
    max-width: 960px;
    margin: 0 auto;
    padding: 42px 195.91px;
    position: relative;

    &>div {
      &>div:nth-child(1) {
        color: #fc1682;
        text-align: center;
        font-family: 'FakePearl-Regular';
        font-size: 36.075px;
        font-style: normal;
        font-weight: 400;
        line-height: 160%;
        /* 57.72px */
        margin-bottom: 35px;
      }

      box-sizing: border-box;
      padding: 36px 25px;
      border-radius: 18.037px;
      background: #fff;
      box-shadow: 3.607px 3.607px 7.215px 0px rgba(252, 22, 130, 0.2);
    }
  }

  .resolve_step::after {
    content: '';
    position: absolute;
    left: 15%;
    bottom: 20px;
    width: 167.765px;
    height: 212.842px;
    background: url('https://static.cmereye.com/imgs/2024/08/b952133d20d8754c.png') no-repeat;
    z-index: 99;
  }

  .step_shade {
    position: absolute;
    width: 519.085px;
    height: 1004.393px;
    border-radius: 7.21px;
    background: #fff;
    top: 170px;
  }

  .step_active {
    animation-fill-mode: forwards;
    animation-duration: 3s;
    animation-iteration-count: 1;
    animation-name: mask;
  }

  .step_pink {
    color: var(--indexColor1);
    text-align: justify;
    font-family: 'Noto Sans HK';
    font-size: 20px;
    font-style: normal;
    font-weight: 400;
    line-height: 160%;
    /* 32px */
    letter-spacing: 4px;
    max-width: 960px;
    margin: 20px auto;
  }
}

@keyframes mask {

  // 从上到下 失去高度
  0% {
    top: auto;
    bottom: 75px;
    height: 1004.393px;
  }

  98% {
    height: 0;
    top: auto;
    bottom: 75px;
  }

  100% {
    display: none;
  }
}

.new_address_pink {
  color: var(--indexColor1);
  font-family: 'Noto Sans HK';
  font-size: 20px;
  font-style: normal;
  font-weight: 400;
  line-height: 160%;
  letter-spacing: 4px;
  word-break: break-word;
}

.new_address_gray {
  color: #4d4d4d;
  text-align: justify;
  font-family: 'Noto Sans HK';
  font-size: 20px;
  font-style: normal;
  font-weight: 400;
  line-height: 160%;
  /* 32px */
  letter-spacing: 4px;
}

.new_address>div {
  span:nth-child(1) {
    color: #4d4d4d;
    text-align: justify;
    font-family: 'Noto Sans HK';
    font-size: 20px;
    font-style: normal;
    font-weight: 400;
    line-height: 160%;
    /* 32px */
    letter-spacing: 4px;
  }

  span:nth-child(2) {
    color: var(--indexColor1);
    font-family: 'Noto Sans HK';
    font-size: 20px;
    font-style: normal;
    font-weight: 400;
    line-height: 160%;
    letter-spacing: 4px;
  }
}

.new_two_img {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 20px 0;
  box-sizing: border-box;
  padding: 0 50px;
}

.new_table {
  margin: 98px auto 100px;
  max-width: 1100px;
}

.new_table_title {
  h1 {
    color: #fc1682;
    text-align: center;
    font-family: 'FakePearl-Regular';
    font-size: 30px;
    font-style: normal;
    font-weight: 400;
    line-height: 160%;
    /* 48px */
    letter-spacing: 3px;
  }
}

.new_table_tbody {
  display: flex;
  flex-direction: column;
  background: var(--Pink-Mid, #fee6f1);
  border-radius: 20px;
  overflow: hidden;
  width: 1100px;
  margin-left: -70px;

  &>div {
    display: flex;
    gap: 0 4px;
    border-bottom: 4px solid #fff;

    &>div:nth-child(1) {
      width: 315px;
      border-right: 4px solid #fff;
      display: flex;
      justify-content: center;
      flex-direction: column;
      align-items: center;
      font-family: 'FakePearl-Regular';
      font-size: 24px;
      font-style: normal;
      font-weight: 500;
      line-height: 160%;
      /* 38.4px */
      background: var(--Pink-Mid, #fdd3e3);

      &>span {
        font-family: 'Noto Sans HK';
        color: var(--Theme-Color, #fc1682);
        text-align: center;
        text-shadow: 0px 2px 0px var(--White, #fff);
        -webkit-text-stroke-width: 2;
        -webkit-text-stroke-color: #fff;
      }
    }

    &>div:nth-child(2) {
      flex: 6;
      display: flex;
      flex-direction: column;
      padding: 30px 25px;

      &>span {
        display: flex;
        color: #4d4d4d;
        font-family: 'FakePearl-Regular';
        font-size: 19px;
        font-style: normal;
        font-weight: 400;
        line-height: 160%;
        /* 30.4px */
        letter-spacing: 1px;

        &>i {
          margin-right: 5px;
          width: 24px;
          height: 24px;
          border-radius: 50%;
          background: var(--Theme-Color, #fc1682);
          color: #fff;
          font-family: 'FakePearl-Regular';
          font-size: 24px;
          font-style: normal;
          font-weight: 500;
          line-height: 100%;
          /* 38.4px */
          display: flex;
          justify-content: center;
          align-items: center;
          box-sizing: border-box;
        }

        margin-bottom: 12px;
      }

      &>p {
        color: #808080;
        font-family: 'FakePearl-Regular';
        font-size: 19px;
        font-style: normal;
        font-weight: 400;
        line-height: 160%;
        /* 30.4px */
        letter-spacing: 1px;
        color: var(--Theme-Color, #fc1682);
      }
    }
  }

  &>div:nth-of-type(4) {
    border-bottom: none;
  }
}



.tabNav {
  font-weight: 400;
  font-size: 1.25rem;
  line-height: 160%;
  color: #cbcbcb;
  margin-top: 44px;

  a {
    &:not(:last-child)::after {
      content: '';
      width: 20px;
      height: 2px;
      margin: 0 10px;
      background: #cbcbcb;
      display: inline-block;
      vertical-align: middle;
      margin-top: -4px;
    }
  }

  &>span {
    cursor: pointer;
    color: var(--indexColor1);
  }
}

@keyframes btnAnim {
  0% {
    opacity: 0;
  }

  15% {
    opacity: 1;
    width: calc(100% + 35px);
    height: calc(100% + 35px);
    border: 10px solid #b9d9fc;
  }

  20% {
    border: 0px solid #b9d9fc;
    opacity: 0;
    width: calc(100% + 35px);
    height: calc(100% + 35px);
  }

  100% {
    opacity: 0;
    width: 100%;
    height: 100%;
  }
}

@keyframes btnAnimHover {
  0% {
    opacity: 0;
  }

  15% {
    opacity: 1;
    width: calc(100% + 35px);
    height: calc(100% + 35px);
    border: 10px solid #fcd1b9;
  }

  20% {
    border: 0px solid #fcd1b9;
    opacity: 0;
    width: calc(100% + 35px);
    height: calc(100% + 35px);
  }

  100% {
    opacity: 0;
    width: 100%;
    height: 100%;
  }
}

.content {
  width: 100%;
  max-width: 960px;
  margin: 60px auto;

  &>div {
    margin-bottom: 35px;

    &.nob {
      margin-bottom: 0;
    }

    &.imgLists {
      margin: 5px 0;

      section {
        display: flex;
        flex: 1;

        img {
          width: 100%;
        }
      }

      .imgItem:not(:last-child) {
        margin-right: 10px;
      }
    }

    &.imgStyle {
      section {
        width: 100%;

        img {
          width: 100%;
        }
      }
    }

    &.imgone {
      margin: 5px 0;
    }

    &.lastpa {
      p {
        font-size: 14px;
        letter-spacing: 1.5px;
      }
    }

    &.btn {
      display: flex;
      justify-content: center;
      margin: 80px auto 0;
      max-width: calc(100% - 30px);

      a {
        font-size: 35px;
        line-height: 160%;
        background: #00aeff;
        padding: 10px 35px;
        border-radius: 50px;
        color: #fff;
        transition: all 0.3s;
        position: relative;
        box-shadow: 3px 3px 12.4px 0px rgba(0, 174, 255, 0.5);
        text-align: center;

        &:hover {
          background: #ff9900;
          box-shadow: 3px 3px 12.4px 0px rgba(255, 153, 0, 0.5);

          &::before {
            animation: btnAnimHover 5s linear infinite;
          }
        }

        &::after {
          content: '';
          position: absolute;
          right: -15px;
          top: 30%;
          background: url(https://static.cmereye.com/imgs/2024/02/e750f6e517ea0dee.png);
          background-size: 100% 100%;
          width: 50px;
          height: 60px;
        }

        &::before {
          content: '';
          position: absolute;
          width: 100%;
          height: 100%;
          left: 50%;
          top: 50%;
          transform: translate(-50%, -50%);
          border: 10px solid var(--Blue-Light, #b9d9fc);
          animation: btnAnim 5s linear infinite;
          border-radius: 100px;
          z-index: -1;
        }
      }
    }

    &.tags {
      margin-top: 60px;

      span {
        font-size: 20px;
        line-height: 160%;
        margin-right: 20px;
        color: var(--textColor);
        border-bottom: 1px solid var(--textColor);
      }
    }
  }

  h1 {
    line-height: 130%;
    color: var(--indexColor1);
    text-align: center;
    color: var(--Theme-Color, #fc1682);
    font-size: 30px;
    font-weight: 400;
    letter-spacing: 3px;
  }

  h2 {
    font-size: 30px;
    line-height: 160%;
    color: var(--indexColor1);
  }

  h3 {
    font-size: 28px;
    line-height: 160%;
    color: var(--textColor);
  }

  ul {
    margin: 10px 0;

    li {
      font-size: 20px;
      line-height: 160%;
      color: var(--textColor);

      &::before {
        content: '·';
        margin-right: 10px;
      }
    }
  }

  p {
    font-size: 20px;
    line-height: 160%;
    color: var(--textColor);
    text-align: justify;
    letter-spacing: 2px;

    &.english {
      text-align: initial;
    }

    section {
      display: initial;
    }

    span {
      &.indexColor {
        color: var(--indexColor1);
      }
    }

    a {
      word-break: break-all;
      /* 允许在单词内换行 */
      white-space: normal;

      &.indexColor {
        color: var(--indexColor1);
      }
    }

    &.time {
      font-size: 28px;
      line-height: 160%;
    }
  }
}



.iframe {
  width: 100%;
  height: 540px;
}

@media (min-width: 768px) and (max-width: 1920px) {
  .newsmodule {
    &-title {
      .mewsmodule-btn {
        &>a {
          font-size: 1.5625vw;

          &::after {
            font-size: 1.4583vw;
          }
        }
      }
    }
  }

  .new_info_header {
    &>div:nth-child(2) {
      transform: translateX(30%);
    }
  }
}

@media screen and (min-width: 769px) {
  .explain_box_mobile {
    display: none !important;
  }
}

@media screen and (max-width: 768px) {
  .new_two_img {
    .nob {
      h2 {
        white-space: nowrap;
      }
    }
  }

  .explain {
    color: var(--Grey-Deep, #4d4d4d);
    text-align: right;
    font-family: 'Noto Sans HK';
    font-size: 14px;
    font-style: normal;
    font-weight: 400;
    line-height: 160%;
    letter-spacing: 2px;
    position: relative;
    top: 20px;
  }

  .iframe {
    width: 100%;
    height: 56vw;
  }

  .new_info_health {
    position: relative;
    margin-top: 20px;
    margin-bottom: 0;
  }

  .new_info_header {
    display: flex;
    justify-content: center;
    position: relative;

    &>div:nth-child(1) {
      position: absolute;
      z-index: 1;
      bottom: -40%;
      left: -10%;
      width: 64.001px;
      height: 81.128px;

      &>svg {
        width: 100%;
        height: 100%;
      }
    }

    &>div:nth-child(2) {
      transform: translateX(30%);
    }

    color: var(--Theme-Color, #fc1682);
    text-align: justify;
    font-family: 'FakePearl-Regular';
    font-size: 5.33vw;
    font-style: normal;
    font-weight: 400;
    line-height: 130%;
    /* 26px */
    max-width: 57.33vw;
    margin-left: 21.33vw;
  }

  .new_info_content_bg::before {
    position: absolute;
    content: '';
    display: inline-block;
    width: 4.8vw;
    height: 5.865vw;
    background: url('https://static.cmereye.com/imgs/2024/08/843c8466fed81592.png') no-repeat;
    background-size: 100% 100%;
    top: -4.265vw;
    left: 20%;
  }

  .new_info_content {
    position: relative;
    z-index: 10;
    box-sizing: border-box;
    padding: 2vw 8vw;
    max-width: 100%;
    margin: 0 auto;
    margin-top: 2.65vw;

    &>div:nth-child(1) {
      color: var(--Grey-Deep, #4d4d4d);
      font-family: 'Noto Sans HK';
      font-size: 4.265vw;
      font-style: normal;
      font-weight: 400;
      line-height: 200%;
      /* 32px */
      letter-spacing: 1.6px;
    }

    &>div:nth-child(2) {
      margin-top: 8vw;

      &>div:nth-child(1) {
        margin-bottom: 5.3vw;
        color: var(--Theme-Color, #fc1682);
        text-align: center;
        font-family: 'Noto Sans HK';
        font-size: 4.265vw;
        font-style: normal;
        font-weight: 700;
        line-height: 200%;
        /* 32px */
        letter-spacing: 1.6px;
      }
    }

    &>div:nth-child(3) {
      margin-top: 8vw;
      color: var(--Grey-Deep, #4d4d4d);
      font-family: 'Noto Sans HK';
      font-size: 4.265vw;
      font-style: normal;
      font-weight: 400;
      line-height: 200%;
      /* 32px */
      letter-spacing: 1.6px;
      text-align: left;
    }
  }

  .new_info_content_bg {
    border-radius: 5.3vw 5.3vw var(--Count, 0px) var(--Count, 0px);
    background: linear-gradient(180deg, #fee6f1 -23.02%, #fff 58.97%);
    position: relative;
    z-index: 5;
  }

  .new_info_content_items {
    display: flex;
    flex-direction: column;
    gap: 8vw 0;
    margin-left: 2.65vw;
    align-items: center;

    &>div {
      margin: 0;
      width: 84vw;
      position: relative;
      z-index: 5;

      &>div:nth-child(1) {
        border-radius: 8vw;
        border: 2px solid #fc1682;
        background: #fff;
        box-shadow: 6px 6px 0px 0px rgba(252, 22, 130, 0.3);

        &>div:nth-child(1) {
          padding: 5.3vw 0 2.65vw;
          color: #14a033;
          text-align: center;
          font-family: 'FakePearl-Regular';
          font-size: 5.3vw;
          font-style: normal;
          font-weight: 500;
          line-height: 160%;
          /* 32px */
        }

        &>div:nth-child(2) {
          box-sizing: border-box;
          padding: 5.3vw 8vw;
          border-radius: var(--Count, 0px) var(--Count, 0px) 30px 30px;
          background: var(--Pink-Pale, #fee6f1);
        }
      }

      &>div:nth-child(1) {
        &>div:nth-child(2) {
          display: flex;
          flex-direction: column;
          color: var(--Theme-Color, #fc1682);
          text-align: center;
          text-shadow: 0px 2px 0px var(--White, #fff);
          -webkit-text-stroke-width: 2;
          -webkit-text-stroke-color: #fff;
          font-family: 'Noto Sans HK';
          font-size: 6.4vw;
          font-style: normal;
          font-weight: 700;
          line-height: 160%;
          /* 38.4px */
          letter-spacing: 3.84px;

          i {
            color: var(--Grey-Deep, #4d4d4d);
            font-family: 'Noto Sans HK';
            font-size: 5.3vw;
            font-style: normal;
            font-weight: 500;
            line-height: 160%;
            letter-spacing: 3.2px;
          }
        }
      }
    }

    &>div:nth-child(2) {
      &>div:nth-child(1) {
        display: flex;
        flex-direction: column;
        color: var(--Theme-Color, #fc1682);
        text-align: center;
        text-shadow: 0px 2px 0px var(--White, #fff);
        -webkit-text-stroke-width: 2;
        -webkit-text-stroke-color: #fff;
        font-family: 'Noto Sans HK';
        font-size: 35px;
        font-style: normal;
        font-weight: 700;
        line-height: 160%;
        /* 56px */
        letter-spacing: 5.6px;

        &>div:nth-child(2) {
          &>span:nth-child(2) {
            color: var(--Grey-Deep, #4d4d4d);
            font-family: 'Noto Sans HK';
            font-size: 20px;
            font-style: normal;
            font-weight: 500;
            line-height: 160%;
            letter-spacing: 3.2px;
          }
        }
      }
    }

    &>div:nth-child(3) {
      &>div:nth-child(1) {
        display: flex;
        flex-direction: column;
        color: var(--Theme-Color, #fc1682);
        text-align: center;
        text-shadow: 0px 2px 0px var(--White, #fff);
        -webkit-text-stroke-width: 2;
        -webkit-text-stroke-color: #fff;
        font-family: 'Noto Sans HK';
        font-size: 35px;
        font-style: normal;
        font-weight: 700;
        line-height: 160%;
        /* 56px */
        letter-spacing: 5.6px;

        &>div:nth-child(2) {
          display: flex;
          flex-direction: row;
          align-items: flex-end;
          justify-content: center;

          &>span:nth-child(1) {
            color: var(--Theme-Color, #fc1682);
            font-family: 'Noto Sans HK';
            font-size: 35px;
            font-style: normal;
            font-weight: 700;
            line-height: 130%;
            letter-spacing: 5.6px;

            &>i {
              color: var(--Theme-Color, #fc1682);
              text-align: center;
              text-shadow: 0px 2px 0px var(--White, #fff);
              -webkit-text-stroke-width: 2;
              -webkit-text-stroke-color: #fff;
              font-family: 'Noto Sans HK';
              font-size: 24px;
              font-style: normal;
              font-weight: 700;
              line-height: 100%;
              /* 38.4px */
              letter-spacing: 3.84px;
            }
          }

          &>span:nth-child(2) {
            color: var(--Grey-Deep, #4d4d4d);
            font-family: 'Noto Sans HK';
            font-size: 15px;
            font-style: normal;
            font-weight: 500;
            line-height: 160%;
            letter-spacing: 2.4px;
            position: relative;
          }

          &>span:nth-child(2)::after {
            content: '';
            width: 100%;
            height: 2px;
            background: #4d4d4d;
            display: inline-block;
            position: absolute;
            left: 0;
            top: 50%;
            transform: rotate(-5deg);
          }
        }
      }
    }

    &>div:nth-child(4) {
      &>div:nth-child(1) {
        display: flex;
        flex-direction: column;
        color: var(--Theme-Color, #fc1682);
        text-align: center;
        text-shadow: 0px 2px 0px var(--White, #fff);
        -webkit-text-stroke-width: 2;
        -webkit-text-stroke-color: #fff;
        font-family: 'Noto Sans HK';
        font-size: 35px;
        font-style: normal;
        font-weight: 700;
        line-height: 160%;
        /* 56px */
        letter-spacing: 5.6px;

        &>div:nth-child(2) {
          display: flex;
          flex-direction: row;
          align-items: flex-end;
          justify-content: center;

          &>span:nth-child(1) {
            color: var(--Theme-Color, #fc1682);
            font-family: 'Noto Sans HK';
            font-size: 35px;
            font-style: normal;
            font-weight: 700;
            line-height: 130%;
            letter-spacing: 5.6px;

            &>i {
              color: var(--Theme-Color, #fc1682);
              text-align: center;
              text-shadow: 0px 2px 0px var(--White, #fff);
              -webkit-text-stroke-width: 2;
              -webkit-text-stroke-color: #fff;
              font-family: 'Noto Sans HK';
              font-size: 24px;
              font-style: normal;
              font-weight: 700;
              line-height: 100%;
              /* 38.4px */
              letter-spacing: 3.84px;
            }
          }

          &>span:nth-child(2) {
            color: var(--Grey-Deep, #4d4d4d);
            font-family: 'Noto Sans HK';
            font-size: 15px;
            font-style: normal;
            font-weight: 500;
            line-height: 160%;
            letter-spacing: 2.4px;
            position: relative;
          }

          &>span:nth-child(2)::after {
            content: '';
            width: 100%;
            height: 2px;
            background: #4d4d4d;
            display: inline-block;
            position: absolute;
            left: 0;
            top: 50%;
            transform: rotate(-5deg);
          }
        }
      }
    }

    &>div:nth-child(5) {
      &>div:nth-child(1) {
        &>div:nth-child(2) {
          display: flex;
          flex-direction: row;
          align-items: flex-end;
          white-space: nowrap;

          &>span:nth-child(1) {
            text-align: center;
            text-shadow: 0px 2px 0px var(--White, #fff);
            -webkit-text-stroke-width: 2;
            -webkit-text-stroke-color: #fff;
            font-family: 'Noto Sans HK';
            font-size: 35px;
            font-style: normal;
            font-weight: 700;
            line-height: 130%;
            letter-spacing: 5.6px;

            i {
              font-size: 20px;
              font-style: normal;
              font-weight: 700;
              line-height: 100%;
              letter-spacing: 3.2px;
            }
          }

          &>span:nth-child(2) {
            color: var(--Grey-Deep, #4d4d4d);
            font-family: 'Noto Sans HK';
            font-size: 15px;
            font-style: normal;
            font-weight: 500;
            line-height: 160%;
            letter-spacing: 2.4px;
          }
        }
      }
    }

    &>div:nth-child(6) {
      &>div:nth-child(1) {
        &>div:nth-child(2) {
          padding-top: 48px;
          padding-bottom: 68px;

          &>div:nth-child(1) {
            display: flex;
            flex-direction: column;

            &>span:nth-child(1) {
              text-align: center;
              text-shadow: 0px 2px 0px var(--White, #fff);
              -webkit-text-stroke-width: 2;
              -webkit-text-stroke-color: #fff;
              font-size: 35px;
              font-style: normal;
              font-weight: 700;
              line-height: 160%;
              letter-spacing: 5.6px;

              &>i {
                color: var(--Grey-Deep, #4d4d4d);
                font-family: 'Noto Sans HK';
                font-size: 20px;
                font-style: normal;
                font-weight: 700;
                line-height: 160%;
                letter-spacing: 3.2px;
              }
            }

            &>span:nth-child(2) {
              color: var(--Grey-Deep, #4d4d4d);
              text-align: center;
              text-shadow: 0px 1.414px 0px var(--White, #fff);
              -webkit-text-stroke-width: 1.4140625;
              -webkit-text-stroke-color: #fff;
              font-family: 'Noto Sans HK';
              font-size: 20px;
              font-style: normal;
              font-weight: 500;
              line-height: 160%;
              /* 32px */
              letter-spacing: 3.2px;
            }
          }

          &>div:nth-child(2) {
            display: flex;
            flex-direction: row;
            align-items: flex-end;
            justify-content: center;
            margin-top: 10px;

            &>span:nth-child(1) {
              color: var(--Theme-Color, #fc1682);
              font-family: 'Noto Sans HK';
              font-size: 35px;
              font-style: normal;
              font-weight: 700;
              line-height: 100%;
              letter-spacing: 5.6px;

              &>i {
                color: var(--Theme-Color, #fc1682);
                text-align: center;
                text-shadow: 0px 2px 0px var(--White, #fff);
                -webkit-text-stroke-width: 2;
                -webkit-text-stroke-color: #fff;
                font-family: 'Noto Sans HK';
                font-size: 20px;
                font-style: normal;
                font-weight: 700;
                line-height: 130%;
                /* 32px */
                letter-spacing: 3.2px;
              }
            }

            &>span:nth-child(2) {
              color: var(--Grey-Deep, #4d4d4d);
              font-family: 'Noto Sans HK';
              font-size: 15px;
              font-style: normal;
              font-weight: 500;
              line-height: 160%;
              letter-spacing: 2.4px;
              position: relative;
            }

            &>span:nth-child(2)::after {
              content: '';
              width: 100%;
              height: 2px;
              background: #4d4d4d;
              display: inline-block;
              position: absolute;
              left: 0;
              top: 50%;
              transform: rotate(-5deg);
            }
          }

          &>div:nth-child(3) {
            &>span:nth-child(1) {
              color: var(--Grey-Deep, #4d4d4d);
              text-align: center;
              text-shadow: 0px 2px 0px var(--White, #fff);
              -webkit-text-stroke-width: 2;
              -webkit-text-stroke-color: #fff;
              font-family: 'Noto Sans HK';
              font-size: 20px;
              font-style: normal;
              font-weight: 500;
              line-height: 160%;
              /* 32px */
              letter-spacing: 3.2px;

              &>i {
                color: var(--Theme-Color, #fc1682);
                font-family: 'Noto Sans HK';
                font-size: 35px;
                font-style: normal;
                font-weight: 700;
                line-height: 160%;
                letter-spacing: 5.6px;

                &>i {
                  font-size: 20px;
                  letter-spacing: 3.2px;
                }
              }
            }

            &>span:nth-child(2) {
              color: var(--Grey-Deep, #4d4d4d);
              text-align: center;
              text-shadow: 0px 2px 0px var(--White, #fff);
              -webkit-text-stroke-width: 2;
              -webkit-text-stroke-color: #fff;
              font-family: 'Noto Sans HK';
              font-size: 20px;
              font-style: normal;
              font-weight: 500;
              line-height: 160%;
              /* 32px */
              letter-spacing: 3.2px;

              &>i {
                color: var(--Grey-Deep, #4d4d4d);
                font-family: 'Noto Sans HK';
                font-size: 15px;
                font-style: normal;
                font-weight: 500;
                line-height: 160%;
                letter-spacing: 2.4px;
              }
            }
          }
        }
      }
    }

    &>div:nth-child(7) {
      &>div:nth-child(1) {
        &>div:nth-child(2) {
          display: flex;
          flex-direction: row;
          align-items: flex-end;
          justify-content: center;

          &>span:nth-child(1) {
            color: var(--Grey-Deep, #4d4d4d);
            text-align: center;
            text-shadow: 0px 2px 0px var(--White, #fff);
            -webkit-text-stroke-width: 2;
            -webkit-text-stroke-color: #fff;
            font-family: 'Noto Sans HK';
            font-size: 14.141px;
            font-style: normal;
            font-weight: 500;
            line-height: 160%;
            /* 22.625px */
            letter-spacing: 2.263px;

            &>i {
              color: var(--Theme-Color, #fc1682);
              font-family: 'Noto Sans HK';
              font-size: 35px;
              font-style: normal;
              font-weight: 700;
              line-height: 100%;
              letter-spacing: 5.6px;
            }
          }

          &>span:nth-child(2) {
            color: var(--Grey-Deep, #4d4d4d);
            text-align: center;
            text-shadow: 0px 2px 0px var(--White, #fff);
            -webkit-text-stroke-width: 2;
            -webkit-text-stroke-color: #fff;
            font-family: 'Noto Sans HK';
            font-size: 14.141px;
            font-style: normal;
            font-weight: 500;
            line-height: 160%;
            /* 22.625px */
            letter-spacing: 2.263px;

            &>i {
              color: var(--Theme-Color, #fc1682);
            }
          }
        }
      }
    }

    &>div:nth-child(8) {
      &>div:nth-child(1) {
        &>div:nth-child(2) {
          display: flex;
          flex-direction: column;

          // align-items: flex-end;
          // justify-content: center;
          &>span:nth-child(1) {
            color: var(--Grey-Deep, #4d4d4d);
            text-align: center;
            text-shadow: 0px 2px 0px var(--White, #fff);
            -webkit-text-stroke-width: 2;
            -webkit-text-stroke-color: #fff;
            font-family: 'Noto Sans HK';
            font-size: 14.141px;
            font-style: normal;
            font-weight: 500;
            line-height: 160%;
            /* 22.625px */
            letter-spacing: 2.263px;

            &>i {
              color: var(--Theme-Color, #fc1682);
              font-family: 'Noto Sans HK';
              font-size: 35px;
              font-style: normal;
              font-weight: 700;
              line-height: 160%;
              letter-spacing: 5.6px;
            }

            &>i:nth-child(2) {
              font-size: 20px;
              letter-spacing: 3.2px;
            }
          }

          &>span:nth-child(2) {
            color: var(--Grey-Deep, #4d4d4d);
            font-family: 'Noto Sans HK';
            font-size: 14.141px;
            font-style: normal;
            font-weight: 500;
            line-height: 160%;
            /* 22.625px */
            letter-spacing: 2.263px;
          }
        }
      }
    }

    .abs_box {
      position: absolute;
      top: -10px;
      left: -10px;
      z-index: 2;
      background: url('https://static.cmereye.com/imgs/2024/08/804246100e3ed97f.png') no-repeat;
      background-size: 100% 100%;
      width: 60px;
      height: 60px;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      color: #fff;
      text-align: center;
      font-family: 'FakePearl-Regular';
      font-size: 14px;
      font-style: normal;
      font-weight: 500;
      line-height: 130%;
      /* 22.4px */
    }
  }

  .new_info_content_items>div:nth-child(6) {
    grid-row: 3 / span 3;
    grid-column: 3 / span 3;
  }

  @keyframes mask {

    // 从上到下 失去高度
    0% {
      top: auto;
      bottom: 75px;
      height: 1004.393px;
    }

    98% {
      height: 0;
      top: auto;
      bottom: 75px;
    }

    100% {
      display: none;
    }
  }

  .new_step {
    background: linear-gradient(180deg,
        rgba(252, 22, 130, 0.4) -68.47%,
        rgba(252, 22, 130, 0.28) -68.46%,
        rgba(255, 168, 198, 0) 43.88%);

    .resolve_step {
      max-width: 960px;
      margin: 0 auto;
      box-sizing: border-box;
      padding: 40px 30px;
      position: relative;

      &>div {
        &>div:nth-child(1) {
          color: #fc1682;
          text-align: center;
          font-family: 'FakePearl-Regular';
          font-size: 36.075px;
          font-style: normal;
          font-weight: 400;
          line-height: 160%;
          /* 57.72px */
          margin-bottom: 35px;
        }

        box-sizing: border-box;
        padding: 36px 25px;
        border-radius: 18.037px;
        background: #fff;
        box-shadow: 3.607px 3.607px 7.215px 0px rgba(252, 22, 130, 0.2);
      }
    }

    .resolve_step::after {
      content: '';
      position: absolute;
      left: 10px;
      bottom: 20px;
      width: 95px;
      height: 118px;
      background: url('https://static.cmereye.com/imgs/2024/08/b952133d20d8754c.png') no-repeat;
      background-size: cover;
      z-index: 99;
    }

    .step_shade_mb {
      display: none !important;
      position: absolute;
      width: 76.5vw;
      height: 148.53vw;
      border-radius: 10px;
      background: #fff;
      top: 36vw;
    }

    .step_active_mb {
      // 播放一次 消失
      animation-fill-mode: forwards;
      animation-duration: 3s;
      animation-iteration-count: 1;
      animation-name: mask;
    }

    .step_pink {
      color: var(--indexColor1);
      text-align: justify;
      font-family: 'Noto Sans HK';
      font-size: 20px;
      font-style: normal;
      font-weight: 400;
      line-height: 160%;
      /* 32px */
      letter-spacing: 4px;
      max-width: 960px;
      margin: 50px auto;
      box-sizing: border-box;
      padding: 0 30px;
    }
  }

  .new_defule {
    color: var(--Grey-Deep, #4d4d4d);
    text-align: justify;
    font-family: 'Noto Sans HK';
    font-size: 16px;
    font-style: normal;
    font-weight: 400;
    line-height: 200%;
    /* 32px */
    letter-spacing: 1.6px;
    box-sizing: border-box;
    padding: 0 30px;
  }

  .new_address {
    padding: 0 30px;

    &>div {
      span:nth-child(1) {
        color: var(--Grey-Deep, #4d4d4d);
        text-align: justify;
        font-family: 'Noto Sans HK';
        font-size: 16px;
        font-style: normal;
        font-weight: 400;
        line-height: 200%;
        /* 32px */
        letter-spacing: 1.6px;
      }

      span:nth-child(2) {
        color: var(--Theme-Color, #fc1682);
        font-family: 'Noto Sans HK';
        font-size: 16px;
        font-style: normal;
        font-weight: 400;
        line-height: 200%;
        letter-spacing: 1.6px;
      }
    }
  }

  .new_address_pink {
    color: var(--indexColor1);
    font-family: 'Noto Sans HK';
    font-size: 16px;
    font-style: normal;
    font-weight: 400;
    line-height: 200%;
    letter-spacing: 1.6px;
    word-break: break-all;
  }

  .new_address_gray {
    color: var(--Grey-Deep, #4d4d4d);
    font-family: 'Noto Sans HK';
    font-size: 16px;
    font-style: normal;
    font-weight: 400;
    line-height: 200%;
    /* 32px */
    letter-spacing: 1.6px;
  }

  .health-care-voucher-top {
    flex-direction: column-reverse;
    flex-wrap: wrap;

    .lang {
      width: calc(100% - 30px);
      // margin-right: 30px;
      margin-left: 30px;
      // margin-top: 20px;
      margin-bottom: 20px;
    }
  }

  .health-care-voucher {
    position: relative;
    z-index: 1;
    padding-top: 0px;
  }

  .tabNav {
    padding: 23px 30px 0;
    font-size: 1rem;
    margin-top: 0px;
  }

  .content {
    margin: 30px auto 0;

    &>div {
      margin-bottom: 35px;

      &.imgLists {
        margin: 10px 0;
      }

      &.imgListsMB {
        // display: flex;
        padding: 0 30px;

        section {
          flex-direction: column;

          .imgItem {
            width: 100%;

            img {
              width: 100%;
            }
          }

          .imgItem:not(:last-child) {
            margin-right: 0px;
            margin-bottom: 8px;
          }
        }
      }

      &.imgone {
        margin: 10px 0;
      }

      &.pa {
        span {
          display: block;
          letter-spacing: 1.5px;
        }
      }

      &.lastpa {
        p {
          font-size: 12px;
        }
      }

      &.btn {
        max-width: 100%;
        margin-top: 8vw;
        padding: 8vw 0;
        overflow: hidden;

        a {
          font-size: 6.43vw;
          padding: 1.3vw 5.3vw;

          &::after {
            right: -10px;
            top: 45%;
            width: 7.465vw;
            height: 8.8vw;
          }
        }
      }

      &.tags {
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
        margin-top: 10.65vw;
        margin-bottom: 0;

        span {
          font-size: 4.265vw;
          border-bottom: 0;
          text-decoration-line: underline;

          &:last-child {
            margin-right: 0;
          }
        }
      }
    }

    h1 {
      font-size: 5vw;
      color: var(--indexColor1);
      padding: 0 8vw;
      white-space: nowrap;
      box-sizing: border-box;
    }

    h2 {
      font-size: 5.3vw;
      line-height: 200%;
      padding: 0 8vw;
    }

    h3 {
      font-size: 5.3vw;
      padding: 0 8vw;
    }

    ul {
      padding: 0 8vw;

      li {
        font-size: 4.265vw;
        line-height: 200%;
      }
    }

    p {
      padding: 0 8vw;
      font-size: 4.265vw;
      line-height: 200%;
      letter-spacing: 3px;
      text-align: justify;

      &.time {
        font-size: 4.265vw;
        margin-top: 5.3vw;
      }

      a {
        text-align: initial;
        display: block;
        letter-spacing: 1px;
      }
    }
  }

  .health-care-voucher {
    margin: 30px auto;
  }

  .newsmodule {
    position: relative;
    margin-top: 0;

    &-title {
      .mewsmodule-btn {
        position: absolute;
        bottom: 0;
        left: 50%;
        transform: translate(-50%, 200%);

        &>a {
          float: initial;
          font-size: 5.3vw;
          margin-left: 2.65vw;

          &::before {
            border-bottom: 1px solid var(--indexColor1);
          }

          &::after {
            font-size: 4.8vw;
          }
        }
      }
    }

    .newsmodule-lists-mobile {
      box-sizing: border-box;
      margin: 15px 30px;
      max-width: 100%;
      position: relative;
      padding-bottom: 60px;

      :deep(.swiper) {
        width: 100%;
        margin: 0 auto;

      }

      :deep(.swiper-wrapper) {
        max-width: 100%;
        margin: 0 auto;
        box-sizing: border-box;
      }

      :deep(.swiper-slide) {
        .image {
          width: 84vw;
          height: 84vw;
          margin: 0 auto;

          img {
            object-fit: contain;
            width: 100%;
            height: 100%;
          }
        }

        h2 {
          margin: 2.665vw 0;
          overflow: hidden;
          color: var(--Brand-Color, #F8298A);
          text-align: justify;
          text-overflow: ellipsis;
          white-space: nowrap;
          font-family: "Noto Sans HK";
          font-size: 4.265vw;
          font-style: normal;
          font-weight: 700;
          line-height: 150%;
          /* 24px */
          letter-spacing: 0.265vw;
        }

        div:nth-child(3) {
          overflow: hidden;
          color: var(--Grey-Mid, #666);
          text-align: justify;
          text-overflow: ellipsis;
          font-family: "Noto Sans HK";
          font-size: 3.733vw;
          font-style: normal;
          font-weight: 400;
          line-height: 150%;
          overflow: hidden;
          text-overflow: ellipsis;
          display: -webkit-box;
          -webkit-line-clamp: 3;
          -webkit-box-orient: vertical;
          word-break: break-all;
        }
      }

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
        box-shadow: rgba(0, 0, 0, 0.3) 0px 0px 2.665vw;
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
        box-shadow: rgba(0, 0, 0, 0.3) 0px 0px 2.665vw;
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
    }

    .btn {
      width: 100%;
      margin-top: 0;
      display: flex;
      justify-content: space-between;

      :deep(.animbtntypetwo) {
        margin: 15px auto;
      }
    }
  }

  .new_table_title h1 {
    color: #fc1682;
    text-align: center;
    font-family: 'FakePearl-Regular';
    font-size: 5.33vw;
    font-style: normal;
    font-weight: 400;
    line-height: 160%;
    /* 32px */
    letter-spacing: 1px;
    padding: 0;
  }

  .new_table {
    box-sizing: border-box;
    padding: 0 15px;
    width: 100%;
    max-width: 100%;
    margin-top: 0;

    .btn {
      margin-top: 0 !important;
    }
  }

  .new_table_tbody {
    width: 100%;
    margin-left: 0;

    &>div {
      display: flex;
      gap: 0 2px;
      border-bottom: 2px solid #fff;

      &>div:nth-child(1) {
        flex: 1;
        width: 110px;
        min-width: 110px;
        box-sizing: border-box;
        padding: 0 20px;
        border-right: 2px solid #fff;
        display: flex;
        justify-content: center;
        flex-direction: column;
        max-width: 65px;
        text-align: center;
        -webkit-text-stroke-width: 2;
        -webkit-text-stroke-color: #fff;
        font-family: 'FakePearl-Regular';
        font-size: 15px;
        font-style: normal;
        font-weight: 500;
        line-height: 160%;

        /* 24px */
        &>span {
          color: #fc1682;
          text-shadow: -1px -1px 0 #fff, 1px -1px 0 #fff, -1px 1px 0 #fff,
            1px 1px 0 #fff;
        }
      }

      &>div:nth-child(2) {
        display: flex;
        flex-direction: column;
        padding: 20px 0 20px 20px;
        flex: 1;
        max-width: 235px;

        &>span {
          display: flex;
          color: #4d4d4d;
          font-family: 'FakePearl-Regular';
          font-size: 12px;
          font-style: normal;
          font-weight: 400;
          line-height: 160%;
          /* 19.2px */
          letter-spacing: 1.2px;
          letter-spacing: 1px;

          &>i {
            margin-right: 2px;
            width: 18px;
            height: 18px;
            min-width: 18px;
            border-radius: 50%;
            background: var(--Theme-Color, #fc1682);
            color: #fff;
            font-family: 'FakePearl-Regular';
            font-size: 16px;
            font-style: normal;
            font-weight: 500;
            line-height: 130%;
            /* 20.8px */

            display: flex;
            justify-content: center;
            align-items: center;
            box-sizing: border-box;
          }

          margin-bottom: 10px;
        }

        &>p {
          color: #808080;
          font-family: 'FakePearl-Regular';
          font-size: 12px;
          font-style: normal;
          font-weight: 400;
          line-height: 160%;
          /* 19.2px */
          letter-spacing: 1.2px;
          padding: 0;
          color: var(--Theme-Color, #fc1682);
        }
      }
    }

    &>div:nth-of-type(4) {
      border-bottom: none;
    }
  }

  .mb_new_defule {
    &>span {
      margin-left: 30px;
    }
  }
}
</style>
