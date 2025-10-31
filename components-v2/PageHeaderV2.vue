<script lang="ts" setup>
import { zh_tran, zh_getLang, getCookie } from '~/assets/js/uselang'
import serviceLists from '~/assets/js/service'
import { useAppState } from '~/stores/appState'

defineProps({
  headerConfig: {
    type: Object,
    default() {
      return {
        img: 'https://static.cmereye.com/imgs/2024/06/d1a92001b420ca10.jpg',
        bg: '',
        mbImg: 'https://static.cmereye.com/imgs/2024/01/a59e0a87dfb394f1.jpg',
        pageName: 'index',
        pcText: [],
        mbText: [],
      }
    },
  },
  btnText: {
    type: String,
    default: '',
  },
  isPageNoBanner: {
    type: Boolean,
    default: false,
  },
})
const menuBoxBool = ref(false)
const windowWidth = ref(1920)

onMounted(() => {
  getWindowWidth()
  console.log(window.innerWidth, 'window.innerWidth')

  windowWidth.value = window.innerWidth
  window.addEventListener('resize', () => {
    getWindowWidth()
    windowWidth.value = window.innerWidth
  })
  window.addEventListener('contextmenu', function (e) {
    e.preventDefault()
  })
})
const getWindowWidth = () => {
  windowWidth.value = window.innerWidth
}

const menuLists: any = [
  {
    name: 'components.header.menuLists.menu_index.name',
    link: '/',
    child: [],
  },
  {
    name: 'components.header.menuLists.menu_brand.name',
    link: ``,
    child: [
      {
        name: 'components.header.menuLists.menu_brand.history',
        link: '/brand/course#course',
      },
      {
        name: 'components.header.menuLists.menu_brand.activity',
        link: '/brand/course#activity',
      },
      {
        name: 'components.header.menuLists.menu_brand.honor',
        link: '/brand/course#honor',
      },
    ],
  },
  {
    name: 'components.header.menuLists.menu_dental_service.name',
    link: `/dental-service`,
    child: [...serviceLists],
  },
  {
    name: 'components.header.menuLists.health-care-voucher.name',
    link: `/health-care-voucher`,
    child: [],
  },
  {
    name: 'components.header.menuLists.federation-of-trade-unions-zone.name',
    link: `/federation-of-trade-unions-zone`,
    child: [],
  },
  {
    name: 'components.header.menuLists.menu_news.name',
    link: `/news`,
    child: [
      {
        name: 'components.header.menuLists.menu_news.coverage',
        link: '/news/coverage',
      },
      {
        name: 'components.header.menuLists.menu_news.information',
        link: '/news/information',
      },
      {
        name: 'components.header.menuLists.menu_news.tooth-wiki',
        link: '/news/tooth-wiki',
      },
    ],
  },
  {
    name: 'components.header.menuLists.menu_medical_team.name',
    link: `/medical-team`,
    child: [
      {
        name: 'components.areaTabs.luohu',
        link: '/medical-team',
      },
      {
        name: 'components.areaTabs.futian',
        link: '/medical-team',
      },
      {
        name: 'components.areaTabs.nanshan',
        link: '/medical-team',
      },
      // {
      //   name: 'components.areaTabs.baoan',
      //   link: '/medical-team',
      // },
      // {
      //   name: 'components.areaTabs.longhua',
      //   link: '/medical-team',
      // },
    ],
  },
  {
    name: 'components.header.menuLists.menu_contactUs.name',
    link: '',
    child: [
      {
        name: 'components.header.menuLists.menu_contactUs.come_route',
        link: '/contactUs#contactUs',
      },
      {
        name: 'components.header.menuLists.menu_contactUs.appeal',
        link: '/contactUs#appeal',
      },
      {
        name: 'components.header.menuLists.menu_contactUs.Q&A',
        link: '/contactUs#Q&A',
      },
    ],
  },
]
onMounted(() => {
  getWindowWidth()
  window.addEventListener('resize', getWindowWidth)
})

const route = useRoute()
const appState = useAppState()
const handleMenuChild = (_menu: any, _idx: number) => {
  if (_menu.link.includes('medical-team')) {
    appState.setCurNum(_idx)
    menuBoxBool.value = false
  }
  if (route.name == 'contactUs') {
    appState.setCurNum(_idx)
    menuBoxBool.value = false
  }
  if (route.name == 'brand-course') {
    appState.setCurNum(_idx)
    menuBoxBool.value = false
  }
}
const classNamefilter = (_menu: any, _idx: number) => {
  let className = ''
  if (route.path === '/medical-team') {
    if (_menu.link.includes('medical-team')) {
      if (appState.areaTabCurNum === _idx) {
        className = 'menuChildCurrent'
      }
    }
  } else if (route.path.includes('/brand')) {
    if (_menu.link.includes(appState.brand)) {
      className = 'menuChildCurrent'
    }
  } else if (route.path.includes('/dental-service')) {
    if (_menu.link.includes(appState.dentistryService)) {
      className = 'menuChildCurrent'
    }
  }

  return className
}
const router = useRouter()
const glangs = (_type) => {
  let _a = [
    {
      lable: 'hk',
      value: 't',
    },
    {
      lable: 'cn',
      value: 's',
    },
  ]
  let _b = _a.find((item) => item.value === _type)
  let _str = route.path.slice(0, 3)
  let _arr = [
    '404',
    'test',
    '/news-tooth-wiki',
    '/news-information',
    '/article',
  ]
  if (_arr.some((str) => route.path?.indexOf(str) !== -1)) {
    changlangsfun(_type)
  } else {
    if (_str === '/cn' || _str === '/hk') {
      let _url = route.path
      let _url_new = _url.replace(_url.slice(0, 3), _b ? '/' + _b.lable : '')
      router.push(_url_new)
    } else {
      router.push(`${_b ? '/' + _b.lable : ''}${route.path}`)
    }
  }
}
const changlangsfun = (_type) => {
  zh_tran(_type)
  if (getCookie('zh_choose')) {
    var zh_choose: any = getCookie('zh_choose')
    appState.setLangs(zh_choose)
  }
}

const implantItem = [
  {
    name: 'service.implant',
    imgUrl: 'https://static.cmereye.com/imgs/2024/03/08337fb0f04440b4.png',
    link: '/dental-service/implant',
    isHot: true,
  },
  {
    name: 'service.scaling_and_polishing',
    imgUrl: 'https://static.cmereye.com/imgs/2024/03/8f5e55aae2f7c830.png',
    link: '/dental-service/scaling-and-polishing',
    isHot: true,
  },
  {
    name: 'service.fillings',
    imgUrl: 'https://static.cmereye.com/imgs/2024/03/554ebbcbec3aa2e4.png',
    link: '/dental-service/fillings',
    isHot: true,
  },
  {
    name: 'service.veneers',
    imgUrl: 'https://static.cmereye.com/imgs/2024/06/bcb673f2ee240eaa.png',
    link: '/dental-service/veneers',
    isHot: true,
  },
  {
    name: 'service.toothtray',
    imgUrl: 'https://static.cmereye.com/imgs/2024/06/1e6c96d45a76e78c.png',
    link: '/dental-service/toothtray',
    isHot: true,
  },
  {
    name: 'service.rootCanal',
    imgUrl: 'https://static.cmereye.com/imgs/2024/03/bf608a98bf395702.png',
    link: '/dental-service/rootCanal',
    isHot: false,
  },
  {
    name: 'service.orthodontics',
    imgUrl: 'https://static.cmereye.com/imgs/2024/03/6297f1d28f28b4ba.png',
    link: '/dental-service/orthodontics',
    isHot: false,
  },
  {
    name: 'service.invisalign',
    imgUrl: 'https://static.cmereye.com/imgs/2024/03/3313f092cb1a16cb.png',
    link: '/dental-service/invisiblebraces',
    isHot: false,
  },
  {
    name: 'service.all_ceramic_crowns',
    imgUrl: 'https://static.cmereye.com/imgs/2024/03/608c309d37f7c06f.png',
    link: '/dental-service/all-ceramic-crowns',
    isHot: false,
  },
  {
    name: 'service.children_dentistry',
    imgUrl: 'https://static.cmereye.com/imgs/2024/07/4feb204172b310b6.png',
    link: '/dental-service/children-dentistry',
    isHot: false,
  },
  {
    name: 'service.wisdom_teeth_extraction',
    imgUrl: 'https://static.cmereye.com/imgs/2024/03/2b1b8835b0d80c94.png',
    link: '/dental-service/wisdom-teeth-extraction',
    isHot: false,
  },
  {
    name: 'service.periodontal',
    imgUrl: 'https://static.cmereye.com/imgs/2024/03/c67f78f4d7d88590.png',
    link: '/dental-service/periodontal',
    isHot: false,
  },
  {
    name: 'service.teeth_whitening',
    imgUrl: 'https://static.cmereye.com/imgs/2024/03/20ade6f1ba75d122.png',
    link: '/dental-service/teeth-whitening',
    isHot: false,
  },
  {
    name: 'service.general_oral_examination',
    imgUrl: 'https://static.cmereye.com/imgs/2024/03/62b3b73436691753.png',
    link: '/dental-service/general-oral-examination',
    isHot: false,
  },
]
</script>

<template>
  <div class="NewHeaderMenu">
    <a class="a-header-content-in" href="#contactUsFormNav"><i style="color:red;font-style: normal;">❤</i> 感恩愛牙節 🦷
      進口種植牙 ¥3689/顆 起❗</a>
    <nav class="navbar navbar-expand-lg navbar-light w-100">
      <div class="container-fluid position-relative">
        <div class="navbar-brand d-flex align-items-center justify-content-between">
          <a href="/" class="websiteLOGO"><img src="@/assets/images/LOGO-PC.svg" alt="" /> </a><i
            class="d-none d-lg-block" style="font-style: normal">|</i>
          <div class="governmentPoint">
            <span>香港長者醫療券</span>
            <p>政府指定預約網站</p>
          </div>
        </div>
        <div class="navbar-toggler d-lg-none" data-bs-toggle="offcanvas" data-bs-target="#offcanvasNavbar"
          aria-controls="offcanvasNavbar">
          <span class="navbar-toggler-icon"></span>
        </div>
        <div class="collapse navbar-collapse d-lg-block" id="navbarNav">
          <ul class="navbar-nav ms-auto d-flex align-items-center">
            <!-- <li class="nav-item">
              <a class="nav-link" target="_blank" href="https://www.ckjhk.com/promotion/">{{
                $t('components.header.menuLists.summer-activities.name')
              }}</a>
            </li> -->
            <li class="nav-item dropdown">
              <a class="nav-link dropdown-toggle">{{ $t('components.header.menuLists.menu_brand.name') }}
              </a>
              <ul class="dropdown-menu">
                <li>
                  <a class="dropdown-item" href="/brand/course#course">{{
                    $t('components.header.menuLists.menu_brand.history')
                  }}</a>
                </li>
                <li>
                  <a class="dropdown-item" href="/brand/course#activity">{{
                    $t('components.header.menuLists.menu_brand.activity')
                  }}</a>
                </li>
                <li>
                  <a class="dropdown-item" href="/brand/course#honor">{{
                    $t('components.header.menuLists.menu_brand.honor')
                  }}</a>
                </li>
              </ul>
            </li>
            <li class="nav-item">
              <a class="nav-link dropdown-toggle">{{
                $t('components.header.menuLists.menu_dental_service.name')
              }}</a>
              <ul class="dropdown-menu">
                <li v-for="item in implantItem" :key="item.name">
                  <!-- <nuxt-link class="dropdown-item" :to="item.link">
                    {{ $t(item.name) }}</nuxt-link> -->
                     <a :href="item.link" class="dropdown-item">{{ $t(item.name) }}</a>
                </li>
              </ul>
            </li>
            <li class="nav-item">
              <!-- <nuxt-link class="nav-link" to="/health-care-voucher">{{
                $t('components.header.menuLists.health-care-voucher.name')
              }}</nuxt-link> -->
               <a class="nav-link" href="/health-care-voucher">{{
                $t('components.header.menuLists.health-care-voucher.name')
              }}</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="/federation-of-trade-unions-zone">{{
                $t(
                  'components.header.menuLists.federation-of-trade-unions-zone.name'
                )
              }}</a>
            </li>
            <li class="nav-item dropdown">
              <a class="nav-link dropdown-toggle">{{
                $t('components.header.menuLists.menu_news.name')
              }}</a>
              <ul class="dropdown-menu">
                <li>
                  <a class="dropdown-item" href="/news/coverage">{{
                    $t('components.header.menuLists.menu_news.coverage')
                  }}</a>
                </li>
                <li>
                  <a class="dropdown-item" href="/news/information">{{
                    $t('components.header.menuLists.menu_news.information')
                  }}</a>
                </li>
                <li>
                  <a class="dropdown-item" href="/news/tooth-wiki">{{
                    $t('components.header.menuLists.menu_news.tooth-wiki')
                  }}</a>
                </li>
              </ul>
            </li>
            <li class="nav-item dropdown">
              <a class="nav-link dropdown-toggle">{{
                $t('components.header.menuLists.menu_medical_team.name')
              }}</a>
              <ul class="dropdown-menu">
                <li>
                  <a class="dropdown-item" href="/medical-team">{{
                    $t('components.areaTabs.luohu')
                  }}</a>
                </li>
                <li>
                  <a class="dropdown-item" href="/medical-team">{{
                    $t('components.areaTabs.futian')
                  }}</a>
                </li>
                <li>
                  <a class="dropdown-item" href="/medical-team">{{
                    $t('components.areaTabs.nanshan')
                  }}</a>
                </li>
              </ul>
            </li>
            <li class="nav-item dropdown">
              <a class="nav-link dropdown-toggle">{{
                $t('components.header.menuLists.menu_contactUs.name')
              }}</a>
              <ul class="dropdown-menu">
                <li>
                  <a class="dropdown-item" href="/contactUs#contactUs">{{
                    $t('components.header.menuLists.menu_contactUs.come_route')
                  }}</a>
                </li>
                <li>
                  <a class="dropdown-item" href="/contactUs#appeal">{{
                    $t('components.header.menuLists.menu_contactUs.appeal')
                  }}</a>
                </li>
                <li>
                  <a class="dropdown-item" href="/contactUs#Q&A">{{
                    $t('components.header.menuLists.menu_contactUs.Q&A')
                  }}</a>
                </li>
              </ul>
            </li>
            <li class="nav-item">
              <a class="nav-link" id="accessibilityWidget" tabindex="0"><svg xmlns="http://www.w3.org/2000/svg"
                  width="25" height="28" viewBox="0 0 25 28" fill="none">
                  <path
                    d="M9.5 9H8.1023L0 28H3.95287L5.83103 23.1002H13.1471L15.069 28H19L10.8977 9H9.5ZM7.11954 19.8266L9.47816 13.75L11.8805 19.8266H7.11954Z"
                    fill="#333333" />
                  <path
                    d="M19.3871 9H17.4516L15 14.6875L16.7204 18.6458H20.957L22.2903 22H25L19.3871 9ZM16.7634 16.4167L18.3978 12.25L20.0538 16.4167H16.7634Z"
                    fill="#333333" />
                </svg></a>
            </li>
            <li class="nav-item">
              <a class="nav-link"><svg xmlns="http://www.w3.org/2000/svg" width="22" height="30" viewBox="0 0 22 30"
                  fill="none">
                  <path
                    d="M2.20002 9.94H6.19002C6.17002 10.41 6.15002 10.83 6.13002 11.2H6.78002V11.94H6.07002C6.05002 12.16 6.02002 12.35 6.00002 12.53H6.47002V13.16H5.88002C5.83002 13.34 5.77002 13.48 5.72002 13.58L6.14002 13.89C5.52002 14.24 4.88002 14.54 4.21002 14.79L6.73002 14.61C7.19002 14.37 7.64002 14.11 8.11002 13.84L8.88002 14.36C7.63002 15.11 6.28002 15.73 4.79002 16.18C6.27002 16.11 7.72002 16 9.13002 15.86C8.88002 15.64 8.61002 15.44 8.35002 15.24L9.12002 14.75C10.1 15.49 10.86 16.14 11.39 16.69L10.6 17.24C10.38 17 10.14 16.76 9.89002 16.52C8.86002 16.59 7.89002 16.66 6.96002 16.74V18.14C6.96002 18.8 6.59002 19.14 5.87002 19.14H4.85002L4.65002 18.22C4.96002 18.26 5.26002 18.28 5.55002 18.28C5.75002 18.28 5.86002 18.15 5.86002 17.91V16.82C4.48002 16.89 3.20002 16.95 2.02002 17L1.82002 16.12C2.10002 16.14 2.37002 16.16 2.66002 16.16C3.51002 15.97 4.41002 15.68 5.35002 15.28C4.39002 15.3 3.45002 15.33 2.53002 15.38L2.37002 14.66C2.73002 14.66 2.99002 14.62 3.14002 14.58C3.54002 14.44 3.94002 14.26 4.36002 14.05C4.29002 14.05 4.22002 14.06 4.16002 14.06H3.74002L3.54002 13.48H4.10002C4.53002 13.47 4.82002 13.41 4.95002 13.29C4.97002 13.27 5.00002 13.22 5.02002 13.17H1.38002C1.49002 12.74 1.57002 12.33 1.64002 11.92H0.87002V11.19H1.76002L1.83002 10.31C1.67002 10.45 1.52002 10.59 1.36002 10.71L0.77002 9.99C1.43002 9.51 2.01002 8.85 2.48002 8L3.43002 8.2C3.33002 8.38 3.24002 8.55 3.14002 8.7H6.63002V9.49H2.58002C2.45002 9.65 2.32002 9.79 2.20002 9.93V9.94ZM4.64002 17.7C3.74002 18.24 2.64002 18.7 1.34002 19.06L0.93002 18.17C2.20002 17.88 3.23002 17.5 4.05002 17.03L4.64002 17.7ZM2.45002 12.53H3.80002C3.57002 12.37 3.36002 12.25 3.14002 12.17L3.38002 11.83H2.58002C2.53002 12.07 2.50002 12.31 2.45002 12.53ZM2.71002 10.59C2.69002 10.82 2.67002 11.05 2.65002 11.26H3.91002C3.71002 11.14 3.51002 11.03 3.32002 10.95L3.56002 10.59H2.71002ZM5.15002 12.53C5.17002 12.33 5.19002 12.1 5.21002 11.83H3.59002C3.89002 11.95 4.17002 12.11 4.42002 12.29L4.26002 12.53H5.15002ZM5.28002 10.59H3.70002C4.02002 10.73 4.31002 10.89 4.58002 11.08L4.46002 11.26H5.25002L5.29002 10.59H5.28002ZM7.03002 11.3L6.44002 10.51C7.16002 9.82 7.64002 9 7.91002 8.01L8.94002 8.18C8.84002 8.5 8.74002 8.82 8.62002 9.1H11.67V10.01H10.9C10.68 10.85 10.34 11.57 9.86002 12.15C10.44 12.53 11.1 12.85 11.84 13.08L11.25 13.94C10.45 13.64 9.75002 13.27 9.18002 12.82C8.60002 13.28 7.90002 13.62 7.08002 13.84L6.56002 13.01C7.32002 12.82 7.94002 12.54 8.44002 12.16C8.09002 11.8 7.80002 11.4 7.56002 11L8.27002 10.59C8.51002 10.94 8.79002 11.25 9.10002 11.54C9.46002 11.08 9.74002 10.58 9.92002 10H8.13002C7.82002 10.47 7.46002 10.9 7.04002 11.28L7.03002 11.3ZM11.58 18.25L11.06 19.05C9.98002 18.49 8.87002 18.04 7.73002 17.71L8.23002 16.95C9.45002 17.3 10.57 17.73 11.58 18.25Z"
                    fill="#333333" />
                  <path
                    d="M12.13 21.5899L11.17 20.9699C11.89 20.1799 12.39 19.3299 12.71 18.4199L13.81 18.6599C13.74 18.8599 13.65 19.0599 13.58 19.2399H16.55V20.2399H14.97C15.22 20.5999 15.43 20.9499 15.58 21.2599L14.57 21.6299C14.34 21.1499 14.08 20.6799 13.78 20.2399H13.1C12.81 20.7399 12.49 21.1999 12.13 21.6099V21.5899ZM13.1 23.0699V29.5299H11.97V23.0699H13.1ZM14.86 22.6699L14.02 23.2499C13.66 22.7899 13.18 22.2899 12.58 21.7099L13.42 21.1899C14.04 21.7399 14.52 22.2299 14.86 22.6599V22.6699ZM18.9 23.5699V28.2499H14.38V23.5699H18.9ZM17.85 25.4299V24.4899H15.46V25.4299H17.85ZM17.85 26.3399H15.46V27.2999H17.85V26.3399ZM19.01 29.4799L18.73 28.4499L19.81 28.4899C20.07 28.4899 20.21 28.3099 20.21 27.9599V22.7299H15.76V21.6899H21.34V28.2699C21.34 29.0699 20.91 29.4799 20.05 29.4799H19.02H19.01ZM17.45 21.4099L16.49 20.7899C17.08 20.0599 17.5 19.2699 17.74 18.4299L18.83 18.6699C18.76 18.8599 18.7 19.0499 18.64 19.2299H22V20.2299H20.2C20.43 20.5499 20.62 20.8699 20.78 21.1499L19.77 21.5199C19.55 21.0799 19.3 20.6399 19.01 20.2299H18.19C17.97 20.6599 17.72 21.0599 17.45 21.4199V21.4099Z"
                    fill="#333333" />
                  <path d="M8.89 25.91H4.25V21.01" stroke="#333333" stroke-miterlimit="10" />
                  <path d="M8.59998 24.9099L10.33 25.9099L8.59998 26.8999V24.9099Z" fill="#333333" />
                  <path d="M15.2999 11.5H19.9399V16.4" stroke="#333333" stroke-miterlimit="10" />
                  <path d="M15.59 12.5L13.86 11.5L15.59 10.5V12.5Z" fill="#333333" />
                </svg></a>
              <ul class="dropdown-menu">
                <li>
                  <a id="traditional" class="dropdown-item" @click="glangs('t')">繁體</a>
                </li>
                <li>
                  <a id="simplified" class="dropdown-item" @click="glangs('s')">簡體</a>
                </li>
              </ul>
            </li>
          </ul>
          <div class="header-appointment d-flex align-items-center">
            <a href="https://wa.me/69122011?text=Hello愛康健,我想查詢牙科服務" target="_blank"><svg
                xmlns="http://www.w3.org/2000/svg" width="43" height="43" viewBox="0 0 43 43" fill="none">
                <rect width="42.875" height="42.875" rx="21.4375" fill="#01A853" />
                <path
                  d="M7.97084 35.2881L9.97203 27.8397C8.3528 24.9417 7.83797 21.5538 8.52719 18.307C9.20809 15.0602 11.0432 12.1705 13.6921 10.161C16.341 8.15152 19.6293 7.16337 22.9508 7.37927C26.2723 7.59516 29.4028 8.99849 31.7694 11.3235C34.1359 13.6569 35.5808 16.7625 35.8382 20.0674C36.0956 23.3723 35.149 26.6689 33.1727 29.3344C31.1964 31.9999 28.315 33.8682 25.0682 34.5906C21.8215 35.3131 18.4252 34.848 15.494 33.2703L7.96252 35.2798L7.97084 35.2881ZM15.8594 30.4969L16.3244 30.7709C18.4419 32.0248 20.9247 32.5479 23.3743 32.249C25.8239 31.95 28.0991 30.8539 29.8595 29.1351C31.6199 27.4079 32.7575 25.1576 33.0897 22.7163C33.4218 20.275 32.9485 17.8005 31.7278 15.6664C30.5072 13.5323 28.6056 11.855 26.3304 10.9084C24.0552 9.96173 21.5308 9.78735 19.1477 10.4184C16.7645 11.0495 14.6553 12.4529 13.1524 14.4042C11.6494 16.3556 10.8356 18.7471 10.8439 21.205C10.8439 23.2477 11.4086 25.2406 12.4798 26.9844L12.7704 27.466L11.6494 31.6179L15.8594 30.4969Z"
                  fill="white" />
                <path fill-rule="evenodd" clip-rule="evenodd"
                  d="M27.164 23.1067C26.8899 22.8908 26.5744 22.7331 26.2256 22.6583C25.8852 22.5836 25.5281 22.5836 25.1877 22.6583C24.6728 22.8742 24.3407 23.6714 24.0085 24.0783C23.9338 24.1779 23.8342 24.2443 23.7179 24.2692C23.6017 24.2942 23.4771 24.2776 23.3774 24.2194C21.5008 23.4887 19.9231 22.1435 18.91 20.3997C18.827 20.2918 18.7855 20.1506 18.7938 20.0177C18.8104 19.8766 18.8768 19.752 18.9765 19.6607C19.3501 19.2953 19.6159 18.8469 19.7653 18.3487C19.7985 17.8006 19.674 17.2526 19.4 16.771C19.1924 16.0984 18.7938 15.5005 18.254 15.0438C17.9717 14.9192 17.6645 14.8777 17.3655 14.9275C17.0666 14.9774 16.7843 15.1019 16.5518 15.3095C16.1532 15.65 15.846 16.0735 15.6384 16.5468C15.4308 17.0284 15.3311 17.5432 15.3477 18.0581C15.3477 18.3487 15.3893 18.6393 15.4557 18.9216C15.6384 19.6025 15.9207 20.2502 16.2944 20.8481C16.5601 21.3048 16.8507 21.7532 17.1663 22.1767C18.1959 23.58 19.483 24.7758 20.9611 25.6892C21.7084 26.1542 22.4973 26.5279 23.3276 26.8185C24.1912 27.2088 25.1378 27.3582 26.0845 27.2503C26.6159 27.1673 27.1307 26.9597 27.5625 26.6358C27.9943 26.312 28.3431 25.8885 28.5756 25.3986C28.7085 25.0996 28.75 24.7758 28.6918 24.4519C28.5507 23.7959 27.6705 23.414 27.139 23.0984L27.164 23.1067Z"
                  fill="white" />
              </svg> </a><a href="tel: 852 3892 5049"><svg xmlns="http://www.w3.org/2000/svg" width="43" height="43"
                viewBox="0 0 43 43" fill="none">
                <rect x="0.0625" width="42.875" height="42.875" rx="21.4375" fill="#F8298A" />
                <path
                  d="M30.1449 32.4626C30.0437 32.4626 29.9497 32.4626 29.8485 32.4481C24.7234 31.9638 19.9526 29.8094 16.3021 26.3681C12.6661 22.9124 10.3963 18.3795 9.87588 13.5285C9.83974 13.1381 9.87588 12.755 9.99877 12.379C10.1217 12.0175 10.3313 11.6778 10.606 11.3886C10.9023 11.0849 11.2638 10.8319 11.6614 10.6656C12.0806 10.4994 12.5143 10.4126 12.948 10.4126H16.7286C17.4009 10.4126 18.0442 10.6078 18.5864 10.9837C19.1285 11.3597 19.5261 11.8802 19.7429 12.4802L20.9718 15.9649C21.1597 16.4998 21.1814 17.0637 21.0441 17.606C20.9067 18.1482 20.6104 18.647 20.1911 19.0446L19.5984 19.6013C20.5815 21.0544 21.8826 22.2762 23.4151 23.2016L24.0006 22.6449C24.4198 22.2473 24.9403 21.9654 25.5258 21.8497C26.0969 21.7195 26.7041 21.7412 27.2607 21.922L30.9328 23.0932C31.5689 23.2884 32.1255 23.6715 32.5087 24.192C32.8918 24.6981 33.1014 25.3198 33.1159 25.956V29.5346C33.1303 30.2937 32.8195 31.0312 32.2629 31.5806C31.7063 32.13 30.9328 32.4481 30.1304 32.4626H30.1449ZM12.9553 12.4296C12.8179 12.4296 12.6806 12.4513 12.5432 12.5019C12.4204 12.5525 12.2975 12.6321 12.2107 12.7333C12.1384 12.82 12.0734 12.914 12.0372 13.008C12.0011 13.1164 11.9866 13.2249 12.0011 13.3333C12.471 17.7216 14.5167 21.8208 17.8201 24.9367C21.1091 28.0526 25.4391 30.0046 30.0726 30.4456H30.1449C30.2533 30.4456 30.369 30.4239 30.4702 30.3733C30.5714 30.3227 30.6654 30.2648 30.7449 30.1925C30.9184 30.0118 31.0196 29.766 31.0196 29.5274V25.9488C31.0196 25.7464 30.9473 25.5223 30.8244 25.356C30.6871 25.1897 30.5136 25.0524 30.3039 24.9945L26.6318 23.8306C26.4439 23.7727 26.2487 23.7583 26.0463 23.8089C25.8439 23.8595 25.6704 23.939 25.5403 24.0764L24.9548 24.633C24.5572 25.009 24.0223 25.2259 23.4512 25.2259C23.032 25.2259 22.6199 25.103 22.273 24.8788C20.5019 23.8016 18.9839 22.3774 17.8418 20.693C17.5816 20.3026 17.4587 19.8471 17.5093 19.3989C17.5599 18.9362 17.7695 18.5169 18.1165 18.1915L18.7092 17.6204C18.8466 17.4903 18.9478 17.3168 18.9912 17.136C19.0418 16.9553 19.0273 16.7601 18.9695 16.5938L17.7406 13.1092C17.6683 12.9068 17.531 12.7333 17.3575 12.6104C17.1696 12.4875 16.9599 12.4152 16.7358 12.4152H12.9553V12.4296ZM32.0677 18.459C31.7858 18.459 31.5183 18.3506 31.3232 18.1699C31.128 17.9747 31.0123 17.7216 31.0123 17.4541C31.0123 16.1239 30.4557 14.8443 29.451 13.8972C28.4606 12.9574 27.1089 12.4224 25.6921 12.4224C25.4102 12.4224 25.1427 12.314 24.9331 12.1332C24.7379 11.938 24.6222 11.685 24.6222 11.4175C24.6222 11.15 24.7307 10.897 24.9331 10.7018C25.1283 10.5066 25.4029 10.4126 25.6921 10.4126C27.6655 10.4126 29.5522 11.1645 30.9545 12.4802C32.3424 13.796 33.1375 15.5889 33.1375 17.4614C33.1375 17.7289 33.0291 17.9819 32.8267 18.1771C32.6315 18.3723 32.3569 18.4663 32.0677 18.4663V18.4518V18.459ZM27.8245 18.459C27.5426 18.459 27.2824 18.3506 27.0655 18.1699C26.8703 17.9747 26.7547 17.7216 26.7547 17.4541C26.7547 17.1866 26.639 16.9336 26.4439 16.7384C26.2487 16.5432 25.974 16.4492 25.6849 16.4492C25.3957 16.4492 25.1355 16.3408 24.9258 16.1601C24.7307 15.9649 24.615 15.7118 24.615 15.4443C24.615 15.1768 24.7234 14.9238 24.9258 14.7286C25.121 14.5334 25.3957 14.4394 25.6849 14.4394C26.5306 14.4394 27.333 14.7503 27.9402 15.3214C28.5329 15.8926 28.8727 16.6517 28.8727 17.4614C28.8727 17.5915 28.851 17.7289 28.7859 17.8445C28.7353 17.9674 28.6486 18.0759 28.5474 18.1699C28.4462 18.2638 28.3378 18.3361 28.2004 18.3867C28.0775 18.4374 27.9257 18.459 27.7884 18.459L27.8101 18.4446L27.8245 18.459Z"
                  fill="white" />
              </svg> </a><nuxt-link to="#contactUsFormNav"><svg width="43" height="43" viewBox="0 0 43 43" fill="none"
                xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
                <rect width="42.875" height="42.875" rx="21.4375" fill="#F8298A" />
                <path
                  d="M16.3231 11.0461C16.2618 11.0317 16.2013 11.0249 16.1416 11.0249C15.7909 11.0249 15.4735 11.2583 15.3881 11.606C15.1453 12.5933 15.1453 13.6365 15.3881 14.623C15.4735 14.9708 15.7916 15.2041 16.1416 15.2041C16.2013 15.2041 16.2626 15.1973 16.3231 15.1829C16.7398 15.0852 16.9966 14.6761 16.8965 14.2692C16.7111 13.5138 16.7111 12.7152 16.8965 11.9591C16.9966 11.5522 16.7398 11.1439 16.3231 11.0461Z"
                  fill="white" />
                <path
                  d="M27.1814 11.0461C27.1201 11.0317 27.0596 11.0249 26.9999 11.0249C26.6491 11.0249 26.3318 11.2583 26.2464 11.606C26.0036 12.5933 26.0036 13.6365 26.2464 14.623C26.3318 14.9708 26.6499 15.2041 26.9999 15.2041C27.0596 15.2041 27.1209 15.1973 27.1814 15.1829C27.5981 15.0852 27.8549 14.6761 27.7548 14.2692C27.5694 13.5138 27.5694 12.7152 27.7548 11.9591C27.8549 11.5522 27.5981 11.1439 27.1814 11.0461Z"
                  fill="white" />
                <path
                  d="M30.5747 13.1012H28.5666C28.5844 13.3194 28.6147 13.536 28.6628 13.7484C28.7691 14.224 28.6969 14.7163 28.4587 15.1336C28.2205 15.5509 27.845 15.8441 27.4019 15.9582C27.2708 15.9924 27.1365 16.009 27.0023 16.009C26.2101 16.009 25.528 15.4309 25.3434 14.6038C25.2332 14.1107 25.1672 13.6068 25.1455 13.1003H17.7083C17.7261 13.3186 17.7564 13.5351 17.8045 13.7475C17.9108 14.2232 17.8386 14.7154 17.6004 15.1327C17.3622 15.5501 16.9867 15.8433 16.5436 15.9574C16.4125 15.9915 16.2782 16.0082 16.144 16.0082C15.3518 16.0082 14.6698 15.4301 14.4851 14.603C14.3749 14.1099 14.3089 13.6059 14.2872 13.0995H12.4134C10.9717 13.1012 9.80005 14.3206 9.80005 15.8191V29.7445C9.80005 31.243 10.9717 32.4624 12.4118 32.4624H30.5747C32.0148 32.4624 33.1864 31.243 33.1864 29.7445V15.8191C33.1864 14.3206 32.0148 13.1012 30.5747 13.1012ZM31.6346 29.7445C31.6346 30.3242 31.1589 30.7965 30.5747 30.7965H12.4118C11.8275 30.7965 11.3519 30.3242 11.3519 29.7445V18.2655H31.6346V29.7445Z"
                  fill="white" />
                <rect x="15.6466" y="18.8206" width="11.6932" height="11.6932" fill="url(#pattern0_269_966)" />
                <defs>
                  <pattern id="pattern0_269_966" patternContentUnits="objectBoundingBox" width="1" height="1">
                    <use xlink:href="#image0_269_966" transform="scale(0.0025)" />
                  </pattern>
                  <image id="image0_269_966" width="400" height="400" preserveAspectRatio="none"
                    xlink:href="data:image/png;base64,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" />
                </defs>
              </svg></nuxt-link>
          </div>
        </div>
        <div class="offcanvas offcanvas-end d-lg-none" tabindex="-1" id="offcanvasNavbar"
          aria-labelledby="offcanvasNavbarLabel">
          <div class="offcanvas-header">
            <nuxt-link to="/" class="offcanvas-title" id="offcanvasNavbarLabel"><img src="@/assets/images/LOGO-PC.svg"
                alt="" /> </nuxt-link><button type="button" class="btn-close text-reset offcanvas-btn"
              data-bs-dismiss="offcanvas" aria-label="Close"></button>
          </div>
          <div class="offcanvas-body phoneMenu-body position-relative">
            <ul class="navbar-nav justify-content-end flex-grow-1" id="accordionMenu">
              <li class="nav-item">
                <nuxt-link class="nav-link active" aria-current="page" to="/">{{
                  $t('components.header.menuLists.menu_index.name')
                }}</nuxt-link>
              </li>
              <li class="nav-item">
                <a class="nav-link d-flex justify-content-between" data-bs-toggle="collapse"
                  data-bs-target="#collapseExample1" aria-expanded="false">{{
                    $t('components.header.menuLists.menu_brand.name') }}</a>
                <div class="collapse collapse-horizontal secondaryMenu" id="collapseExample1"
                  data-bs-parent="#accordionMenu">
                  <ul class="navbar-nav">
                    <li class="nav-item">
                      <nuxt-link class="nav-link" to="/brand/course#course">{{
                        $t('components.header.menuLists.menu_brand.history')
                      }}</nuxt-link>
                    </li>
                    <li class="nav-item">
                      <nuxt-link class="nav-link" to="/brand/course#activity">{{
                        $t('components.header.menuLists.menu_brand.activity')
                      }}</nuxt-link>
                    </li>
                    <li class="nav-item">
                      <nuxt-link class="nav-link" to="/brand/course#honor">{{
                        $t('components.header.menuLists.menu_brand.honor')
                      }}</nuxt-link>
                    </li>
                  </ul>
                </div>
              </li>
              <li class="nav-item">
                <a class="nav-link d-flex justify-content-between" data-bs-toggle="collapse"
                  data-bs-target="#collapseExample2" aria-expanded="false">{{
                    $t('components.header.menuLists.menu_dental_service.name')
                  }}</a>
                <div class="collapse collapse-horizontal secondaryMenu" id="collapseExample2"
                  data-bs-parent="#accordionMenu">
                  <ul class="navbar-nav">
                    <li class="nav-item" v-for="item in implantItem" :key="item.name">
                      <nuxt-link class="nav-link" :to="item.link">
                        {{ $t(item.name) }}</nuxt-link>
                    </li>
                  </ul>
                </div>
              </li>
              <li class="nav-item">
                <nuxt-link to="/health-care-voucher" class="nav-link d-flex justify-content-between">{{
                  $t('components.header.menuLists.health-care-voucher.name')
                }}</nuxt-link>
              </li>
              <li class="nav-item">
                <nuxt-link to="/federation-of-trade-unions-zone" class="nav-link d-flex justify-content-between">{{
                  $t(
                    'components.header.menuLists.federation-of-trade-unions-zone.name'
                  )
                }}</nuxt-link>
              </li>
              <li class="nav-item">
                <nuxt-link class="nav-link d-flex justify-content-between" data-bs-toggle="collapse"
                  data-bs-target="#collapseExamplehead2" aria-expanded="false">{{
                    $t('components.header.menuLists.menu_news.name')
                  }}</nuxt-link>
                <div class="collapse collapse-horizontal secondaryMenu" id="collapseExamplehead2"
                  data-bs-parent="#accordionMenu">
                  <ul class="navbar-nav">
                    <li class="nav-item">
                      <nuxt-link class="nav-link" to="/news/coverage">{{
                        $t('components.header.menuLists.menu_news.coverage')
                      }}</nuxt-link>
                    </li>
                    <li class="nav-item">
                      <nuxt-link class="nav-link" to="/news/information">{{
                        $t('components.header.menuLists.menu_news.information')
                      }}</nuxt-link>
                    </li>
                    <li class="nav-item">
                      <nuxt-link class="nav-link" to="/news/tooth-wiki">{{
                        $t('components.header.menuLists.menu_news.tooth-wiki')
                      }}</nuxt-link>
                    </li>
                  </ul>
                </div>
              </li>
              <li class="nav-item">
                <a class="nav-link d-flex justify-content-between" data-bs-toggle="collapse"
                  data-bs-target="#collapseExamplehead3" aria-expanded="false">{{
                    $t('components.header.menuLists.menu_medical_team.name')
                  }}</a>
                <div class="collapse collapse-horizontal secondaryMenu" id="collapseExamplehead3"
                  data-bs-parent="#accordionMenu">
                  <ul class="navbar-nav">
                    <li class="nav-item">
                      <nuxt-link class="nav-link" to="/medical-team">{{
                        $t('components.areaTabs.luohu')
                      }}</nuxt-link>
                    </li>
                    <li class="nav-item">
                      <nuxt-link class="nav-link" to="/medical-team">{{
                        $t('components.areaTabs.futian')
                      }}</nuxt-link>
                    </li>
                    <li class="nav-item">
                      <nuxt-link class="nav-link" to="/medical-team">{{
                        $t('components.areaTabs.nanshan')
                      }}</nuxt-link>
                    </li>
                  </ul>
                </div>
              </li>

              <li class="nav-item">
                <a class="nav-link d-flex justify-content-between" data-bs-toggle="collapse"
                  data-bs-target="#collapseExamplehead4" aria-expanded="false">{{
                    $t('components.header.menuLists.menu_contactUs.name')
                  }}</a>
                <div class="collapse collapse-horizontal secondaryMenu" id="collapseExamplehead4"
                  data-bs-parent="#accordionMenu">
                  <ul class="navbar-nav">
                    <li class="nav-item">
                      <nuxt-link class="nav-link" to="/contactUs#contactUs">{{
                        $t(
                          'components.header.menuLists.menu_contactUs.come_route'
                        )
                      }}</nuxt-link>
                    </li>
                    <li class="nav-item">
                      <nuxt-link class="nav-link" to="/contactUs#appeal">{{
                        $t('components.header.menuLists.menu_contactUs.appeal')
                      }}</nuxt-link>
                    </li>
                    <li class="nav-item">
                      <nuxt-link class="nav-link" to="/contactUs#Q&A">{{
                        $t('components.header.menuLists.menu_contactUs.Q&A')
                      }}</nuxt-link>
                    </li>
                  </ul>
                </div>
              </li>
            </ul>
          </div>
          <div class="offcanvas-footer d-flex justify-content-between align-items-center">
            <div class="fontSizeEdit" id="accessibilityWidget" tabindex="0">
              <span>字體大小</span> <button id="fontDecrease">A</button>
              <button id="fontIncrease">A</button>
            </div>
            <div class="changeFont d-flex">
              <button id="traditional" class="changeFontActive" @click="glangs('t')">
                繁體</button>| <button id="simplified" @click="glangs('s')">簡體</button>
            </div>
          </div>
        </div>
      </div>
    </nav>
  </div>
</template>

<style lang="scss" scoped>
@keyframes menuIconAnim {
  30% {
    background-position-y: 3px;
  }

  55% {
    background-position-y: 15px;
  }

  75% {
    background-position-y: 8px;
  }

  90% {
    background-position-y: 11px;
  }

  100% {
    background-position-y: 10px;
  }
}

@media screen and (min-width: 992px) {
  .NewHeaderMenu {
    position: fixed;
    z-index: 110;
    width: 100%;
    background: #fff;
    top: 0;

    .a-header-content-in {
      display: block;
      width: 100%;
      background: var(---Green, #00a752);
      box-sizing: border-box;
      padding: 6.5px 0;
      color: var(--White, #fff);
      text-align: center;
      font-family: 'Noto Sans Hk';
      font-size: 22px;
      font-style: normal;
      font-weight: 600;
      line-height: normal;
      letter-spacing: 1.1px;
    }
  }

  .pc_header_menu {
    display: flex;
    justify-content: space-between;
    box-sizing: border-box;
    padding-left: clamp(27.5px, 3.645vw, 30px);
    box-shadow: 1px 2px 17.1px 0px rgba(252, 22, 130, 0.5);

    .logo {
      display: flex;
      gap: 0 clamp(18.75px, 1.3028vw, 25px);
      align-items: center;

      &>a:nth-child(1) {
        width: clamp(138px, 9.583vw, 184px);
        height: clamp(27px, 1.875vw, 36px);

        &>img {
          width: 100%;
          height: 100%;
        }
      }

      &>div:nth-child(2) {
        display: flex;
        flex-direction: column;
        align-items: center;
        position: relative;

        &>span:nth-child(1) {
          color: var(--White, #fff);
          font-size: clamp(10.5px, 0.7295vw, 14px);
          font-style: normal;
          font-weight: 400;
          line-height: 130%;
          /* 18.2px */
          letter-spacing: 3.78px;
          border-radius: 2px;
          background: var(---Green, #00a752);
          padding: 2px 6px;
          box-sizing: border-box;
        }

        &>span:nth-child(2) {
          color: var(--Grey-Deep, #4d4d4d);
          font-size: clamp(10.5px, 0.7295vw, 14px);
          font-style: normal;
          font-weight: 400;
          line-height: 130%;
          /* 18.2px */
          letter-spacing: 1.4px;
        }
      }

      &>div:nth-child(2)::before {
        content: '';
        position: absolute;
        width: 1px;
        height: 100%;
        left: clamp(-9.375px, -0.65vw, -12.5px);
        background: #aaa;
      }
    }

    .menu {
      display: flex;
      align-items: center;

      &>div:nth-child(1) {
        display: flex;
        gap: 0 clamp(10.75px, 1.3028vw, 12px);
        margin-right: clamp(11.25px, 0.78125vw, 15px);

        .menuItem {
          position: relative;

          &>a {
            display: flex;
            flex-direction: column;
            align-items: center;

            span {
              color: var(--Grey-Deep, #4d4d4d);
              text-align: center;
              font-size: clamp(10.5px, 0.8458vw, 16px);
              font-style: normal;
              font-weight: 600;
              line-height: 160%;
              /* 35.2px */
            }

            span::after {
              content: '';
              width: 0;
              height: 2px;
              position: absolute;
              left: 50%;
              bottom: 10px;
              transform: translateX(-50%);
              background: var(--textColor);
              transition: all 0.3s;
              border-radius: 2px;
            }
          }

          .menuChild {
            display: none;
          }
        }

        .menuItem::after {
          content: '';
          width: 130%;
          display: inline-block;
          z-index: 3;
          height: 50px;
          background: transparent;
          position: absolute;
          top: 100%;
          left: 50%;
          transform: translateX(-50%);
        }

        .menuItem:hover {
          &>a {
            span {
              color: #fc1682;
              position: relative;
            }

            span::after {
              position: absolute;
              content: '';
              width: 100%;
              height: 2px;
              background: #fc1682;
              bottom: 2px;
              left: 50%;
              transform: translateX(-50%);
            }

            svg {
              path {
                fill: #fc1682;
              }
            }
          }

          .menuChild {
            display: flex;
            flex-direction: column;
            background: #fff;
            position: absolute;
            top: 100%;
            z-index: 99;
            width: 180%;
            box-sizing: border-box;
            padding: 0px clamp(15px, 1.04165vw, 20px) 5px;
            align-items: center;
            left: 50%;
            transform: translate(-50%, 10px);
            filter: drop-shadow(0px 0px 6px rgba(0, 0, 0, 0.15));
            border-radius: 6px;

            .menuChild-item {
              width: 100%;
              text-align: center;
              padding: 0;
              font-weight: 500;
              font-size: clamp(14px, 1.092vw, 20px);
              color: #666666;
              transition: all 0.3s;

              &>a {
                display: block;
                padding: clamp(8px, 0.052vw, 10px) 0 5px;
              }
            }

            .menuChild-item:not(:last-child) {
              border-bottom: 1px solid var(--indexColor2);
            }

            .menuChild-item:hover {
              color: var(--indexColor1);
            }
          }

          .menuChild::before {
            content: '';
            width: 0px;
            height: 0px;
            border: clamp(8px, 0.052vw, 10px) solid;
            border-color: transparent transparent #fff transparent;
            position: absolute;
            top: clamp(-14px, -0.092vw, -18px);
            left: 50%;
            transform: translateX(-50%);
          }
        }

        .menuItem:nth-child(3):hover {
          &>a {
            span {
              color: #fc1682;
              position: relative;
            }

            span::after {
              position: absolute;
              content: '';
              width: 100%;
              height: 2px;
              background: #fc1682;
              bottom: 2px;
              left: 50%;
              transform: translateX(-50%);
            }

            svg {
              path {
                fill: #fc1682;
              }
            }
          }

          .menuChild {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            grid-gap: 0 34px;
            flex-direction: column;
            background: #fff;
            position: absolute;
            top: 100%;
            z-index: 99;
            width: auto;
            box-sizing: border-box;
            padding: clamp(18.75px, 1.3028vw, 25px) clamp(18.75px, 1.3028vw, 25px);
            align-items: center;
            left: 50%;
            transform: translate(-50%, 10px);
            filter: drop-shadow(0px 0px 6px rgba(0, 0, 0, 0.15));
            border-radius: 6px;

            .menuChild-item {
              width: 100%;
              text-align: center;
              padding: 0;
              font-weight: 500;
              font-size: clamp(14px, 1.092vw, 20px);
              color: #666666;
              transition: all 0.3s;
              white-space: nowrap;

              &>a {
                display: block;
                padding: clamp(12px, 0.252vw, 16px) 0 5px;
              }
            }

            .menuChild-item:hover {
              color: var(--indexColor1);
            }

            .menuChild-item:nth-last-child(-n + 2) {
              border-bottom: none;
            }

            .menuChild-item:not(:nth-child(n + 6)) {
              color: var(--Theme-Color, #fc1682);
              position: relative;
            }

            .menuChild-item:not(:nth-child(n + 6))::before {
              content: '';
              position: absolute;
              top: 5px;
              transform: translateX(-50%);
              width: 5px;
              height: 5px;
              border-radius: 50%;
              background: var(--Theme-Color, #fc1682);
            }

            .menuChild-item:not(:nth-child(3n)) {
              position: relative;
            }

            .menuChild-item:not(:nth-child(3n))::after {
              content: '';
              position: absolute;
              width: 1px;
              height: 70%;
              right: clamp(-12.75px, -0.8854vw, -17px);
              top: 50%;
              transform: translateY(-50%);
              border-right: 1px solid var(--indexColor2);
            }
          }

          .menuChild::before {
            content: '';
            width: 0px;
            height: 0px;
            border: clamp(8px, 0.052vw, 10px) solid;
            border-color: transparent transparent #fff transparent;
            position: absolute;
            top: clamp(-14px, -0.092vw, -18px);
            left: 50%;
            transform: translateX(-50%);
          }

          .menuChild::after {
            content: '';
            animation: menuIconAnim 1.5s 0.5s forwards;
            background: url(https://static.cmereye.com/imgs/2024/04/4f39b444ca1b0a1d.png) no-repeat;
            background-position-y: 69.2307692308px;
            background-size: 100% auto;
            bottom: 0;
            content: '';
            display: block;
            height: 69.2307692308px;
            overflow: hidden;
            position: absolute;
            right: 30px;
            width: 100px;
          }
        }

        .menuItem:nth-child(4) {
          &>a {
            span {
              color: #00a752;
              position: relative;
            }

            span::after {
              bottom: 0px;
            }
          }
        }

        .menuItem:nth-child(4):hover {
          &>a {
            span {
              color: #00a752;
              position: relative;
            }

            span::after {
              position: absolute;
              content: '';
              background: #00a752;
              bottom: 2px;
            }

            svg {
              path {
                fill: #00a752;
              }
            }
          }
        }

        .menuItem:nth-child(5) {
          &>a {
            span {
              color: #e60013;
              position: relative;
            }

            span::after {
              bottom: 0px;
            }
          }
        }

        .menuItem:nth-child(5):hover {
          &>a {
            span {
              color: #e60013;
              position: relative;
            }

            span::after {
              position: absolute;
              content: '';
              background: #e60013;
              bottom: 0px;
            }

            svg {
              path {
                fill: #e60013;
              }
            }
          }
        }

        .menuItem:nth-child(8):hover {
          .menuChild {
            width: 200%;
          }
        }

        .menuItem:last-child {
          box-sizing: border-box;
          padding-top: 5px;
        }

        .menuItem:last-child:hover {
          .menuChild {
            width: 350%;
            padding: clamp(7.5px, 0.020825vw, 10px) clamp(15px, 1.04165vw, 20px) 5px;
          }
        }
      }

      .pc_menu_tel {
        color: var(--White, #fff);
        font-size: clamp(12.5px, 0.9458vw, 16px);
        font-style: normal;
        font-weight: 400;
        line-height: 160%;
        /* 35.2px */
        box-sizing: border-box;
        padding: clamp(8.25px, 0.98125vw, 15px) clamp(25px, 3.125vw, 30px) clamp(8.25px, 0.98125vw, 15px) clamp(11.25px, 0.78125vw, 15px);
        background: var(--Theme-Color, #fc1682);
      }
    }
  }
}

/* PC端菜单样式 */
@media (min-width: 992px) {
  .navbar {
    padding: 0;
    box-shadow: 1px 2px 17.1px 0px rgba(252, 22, 130, 0.5);

    &>div {
      .navbar-brand {
        width: 21.35vw;
        max-width: 410px;
        gap: clamp(4px, 0.7vw, 13.5px);

        .websiteLOGO {
          width: 9.58vw;
          max-width: 184px;

          i {
            color: var(--Grey-Light, #e6e6e6);
          }
        }
      }

      .navbar-nav {
        anchor-name: --slider-menu;

        &:has(:nth-child(1) .nav-link:is(:hover, :focus-visible)) {
          --target: --item-1;
          --color: var(--Grey-Dark, #333);
        }

        &>.nav-item:nth-child(1) {
          --anchor: --item-1;
        }

        // 2
        &:has(:nth-child(2) .nav-link:is(:hover, :focus-visible)) {
          --target: --item-2;
          --color: var(--Grey-Dark, #333);
        }

        &>.nav-item:nth-child(2) {
          --anchor: --item-2;
        }

        // 3
        &:has(:nth-child(3) .nav-link:is(:hover, :focus-visible)) {
          --target: --item-3;
          --color: var(--Grey-Dark, #333);
        }

        &>.nav-item:nth-child(3) {
          --anchor: --item-3;
        }

        // 4
        &:has(:nth-child(3) .nav-link:is(:hover, :focus-visible)) {
          --target: --item-3;
          --color: var(--GHV-Green, #008843);
        }

        &>.nav-item:nth-child(3) {
          --anchor: --item-3;
        }

        // 5
        &:has(:nth-child(4) .nav-link:is(:hover, :focus-visible)) {
          --target: --item-4;
          --color: #e60013;
        }

        &>.nav-item:nth-child(4) {
          --anchor: --item-4;
        }

        // 6
        &:has(:nth-child(5) .nav-link:is(:hover, :focus-visible)) {
          --target: --item-5;
          --color: var(--Grey-Dark, #333);
        }

        &>.nav-item:nth-child(5) {
          --anchor: --item-5;
        }

        &:has(:nth-child(6) .nav-link:is(:hover, :focus-visible)) {
          --target: --item-6;
          --color: var(--Grey-Dark, #333);
        }

        &>.nav-item:nth-child(6) {
          --anchor: --item-6;
        }

        &:has(:nth-child(7) .nav-link:is(:hover, :focus-visible)) {
          --target: --item-7;
          --color: var(--Grey-Dark, #333);
        }

        &>.nav-item:nth-child(7) {
          --anchor: --item-7;
        }

        &>.nav-item:nth-child(8) {
          cursor: pointer;

          &:hover {
            svg {
              path {
                fill: #d2337d;
              }
            }
          }
        }

        &>.nav-item:nth-child(9) {
          &:hover {
            svg {
              path {
                fill: #d2337d;
              }
            }
          }
        }

        .nav-item {
          height: 70px;
          display: flex;
          flex-shrink: 0;
          align-items: center;
          position: relative;

          transition: background-color 0.3s ease;

          &:hover {
            .dropdown-toggle::after {
              background: url('https://statichk.cmermedical.com/newCKJ/static/hearderDown-white.svg') no-repeat;
            }

            background: var(--New-Theme-Color, #d2337d);

            &>a {
              color: var(--White, #fff) !important;
            }

            .dropdown-menu {
              display: grid;
              grid-template-columns: 1fr 1fr 1fr;
              gap: 9px;
              padding: 13px 9px;
              position: absolute;
              top: calc(100% + 10px);
              left: 50%;
              transform: translateX(-50%);
              z-index: 99;
              box-shadow: 0 0.5rem 1rem rgba(0, 0, 0, 0.175);
              border-radius: 10px;
              border: 2px solid var(--Grey-Light, #e6e6e6);
              background: var(--White, #fff);

              &::before {
                position: absolute;
                left: 50%;
                top: -12px;
                transform: translateX(-50%);
                content: '';
                width: 0;
                height: 0;
                border-left: 11.5px solid transparent;
                border-right: 11.5px solid transparent;
                border-bottom: 11px solid var(--White, #fff);
              }

              &::after {
                position: absolute;
                top: -12px;
                content: '';
                width: 100%;
                height: 12px;
                background: transparent;
              }

              .dropdown-item {
                color: var(--New-Theme-Color, #d2337d);
                text-align: center;
                font-family: 'Noto Sans TC';
                font-size: 20px;
                font-style: normal;
                font-weight: 700;
                line-height: 160%;
                letter-spacing: 2px;
                padding: 10px;
                width: 200px;
                transition: background-color 0.2s ease;

                &:hover {
                  border-radius: 5px;
                  background: var(--New-Theme-Color, #d2337d);
                  color: white;
                }
              }

              .collapse {
                padding-left: 1rem;
              }

              .dropdown-submenu {
                position: relative;

                .dropdown-menu {
                  position: absolute;
                  left: 100%;
                  top: 0;
                  margin-left: 0.125rem;
                }

                &:hover {
                  .dropdown-menu-three {
                    display: block;
                  }
                }
              }
            }

            .dropdown-menu-three {
              display: none;
            }
          }

          .nav-link {
            anchor-name: var(--anchor);
            text-decoration: none;

            &:focus-visible {
              outline: none;
            }

            padding: 0 clamp(2px, 0.36vw, 7px);
            white-space: nowrap;
            color: #333;
            text-align: center;
            font-family: 'Noto Sans TC';
            font-size: clamp(16px, 1.041vw, 20px);
            font-style: normal;
            font-weight: 700;
            line-height: 160%;
            position: relative;
            letter-spacing: 2px;

            &::after {
              position: absolute;
              bottom: -10px;
              left: 50%;
              margin-left: 0;
              transform: translateX(-50%);
            }
          }

          &>.dropdown-toggle::after {
            background: url('https://statichk.cmermedical.com/newCKJ/static/hearderDown.svg') no-repeat;
            background-size: cover;
            width: 18px;
            height: 12px;
            border: none;
            bottom: -12px;
            content: '';
          }

          &:first-child .nav-link {
            padding-left: 0;
          }

          &:last-child .nav-link {
            padding-right: 0;
          }

          &:last-child .nav-link {
            margin-bottom: 6px;
          }
        }

        &>.nav-item:nth-child(3) {
          .nav-link {
            color: var(--Grey-Dark, #333);
          }
        }

        &>.nav-item:nth-child(4) {
          .nav-link {
            color: var(--GHV-Green, #008843);
          }
        }


        &>.nav-item:nth-child(5) {
          .nav-link {
            color: #e60013;
          }
        }
      }

      .header-appointment {
        margin-left: 40px;
        gap: 15px;

        a {
          border-radius: 50%;
          box-shadow: 0px 4px 4px 0px rgba(77, 77, 77, 0.2);
        }
      }

      // 立即预约
      .pc-phone-number {
        margin-left: 22px;
        padding-left: 15px;
        height: 70px;
        width: 23.38vw;
        max-width: 449px;
        background: var(--Brand-Color, #fc1682);
        color: var(--White, #fff);
        font-family: 'Noto Sans TC';
        font-size: clamp(16px, 1.145vw, 22px);
        font-style: normal;
        font-weight: 400;
        line-height: 160%;
      }
    }
  }

  .navbar-nav .dropdown-menu .dropdown-item[data-bs-toggle='collapse']::after {
    content: '▼';
    float: right;
    font-size: 0.8rem;
    transition: transform 0.3s;
  }

  .navbar-nav .dropdown-menu .dropdown-item[data-bs-toggle='collapse'].collapsed::after {
    content: '►';
  }
}

.navbar {
  background-color: white;
  opacity: 1;
  z-index: 990;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  box-sizing: border-box;
  padding: 0 5.729vw 0 3.645vw;

  &>div {
    .navbar-brand {
      margin-right: 10px;
      flex: 1;
      padding: 0;

      .websiteLOGO {
        display: block;
        max-width: 123px;
      }

      .governmentPoint {
        span {
          border-radius: 2px;
          background: var(---Green, #008843);
          display: inline-flex;
          padding: 2px 6px;
          justify-content: center;
          align-items: center;
          gap: 13px;
          color: #fff;
          text-align: right;
          font-family: 'Noto Sans TC';
          font-size: 14px;
          font-style: normal;
          font-weight: 400;
          line-height: 130%;
          letter-spacing: 3.78px;
        }

        p {
          color: #333;
          text-align: center;
          font-family: 'Noto Sans TC';
          font-size: 14px;
          font-style: normal;
          font-weight: 400;
          line-height: 130%;
          letter-spacing: 1.4px;
        }
      }
    }

    .navbar-toggler {
      border: none;
      padding: 0;

      span {
        width: 20px;
        height: 20px;
        background-image: url('@/assets/images/menu-icon.svg');
      }
    }
  }
}

@media screen and (max-width: 992px) {
  .NewHeaderMenu {
    position: fixed;
    z-index: 110;
    width: 100%;
    background: #fff;
    top: 0;

    .a-header-content-in {
      display: block;
      width: 100%;
      color: var(--White, #fff);
      text-align: center;
      font-family: 'Noto Sans Hk';
      font-size: 3.84615vw;
      font-style: normal;
      font-weight: 500;
      line-height: normal;
      letter-spacing: 0.3846vw;
      background: #00a752;
      box-sizing: border-box;
      padding: 2.05vw 0;
    }
  }

  .pc_header_menu {
    display: flex;
    justify-content: space-between;
    box-sizing: border-box;
    padding-left: clamp(27.5px, 3.645vw, 30px);
    box-shadow: 1px 2px 17.1px 0px rgba(252, 22, 130, 0.5);

    .logo {
      display: flex;
      gap: 0 clamp(18.75px, 1.3028vw, 25px);
      align-items: center;

      &>a:nth-child(1) {
        width: clamp(138px, 9.583vw, 184px);
        height: clamp(27px, 1.875vw, 36px);

        &>img {
          width: 100%;
          height: 100%;
        }
      }

      &>div:nth-child(2) {
        display: flex;
        flex-direction: column;
        align-items: center;
        position: relative;

        &>span:nth-child(1) {
          color: var(--White, #fff);
          font-size: clamp(10.5px, 0.7295vw, 14px);
          font-style: normal;
          font-weight: 400;
          line-height: 130%;
          /* 18.2px */
          letter-spacing: 3.78px;
          border-radius: 2px;
          background: var(---Green, #00a752);
          padding: 2px 6px;
          box-sizing: border-box;
        }

        &>span:nth-child(2) {
          color: var(--Grey-Deep, #4d4d4d);
          font-size: clamp(10.5px, 0.7295vw, 14px);
          font-style: normal;
          font-weight: 400;
          line-height: 130%;
          /* 18.2px */
          letter-spacing: 1.4px;
        }
      }

      &>div:nth-child(2)::before {
        content: '';
        position: absolute;
        width: 1px;
        height: 100%;
        left: clamp(-9.375px, -0.65vw, -12.5px);
        background: #aaa;
      }
    }

    .menu {
      display: flex;
      align-items: center;

      &>div:nth-child(1) {
        display: flex;
        gap: 0 clamp(10.75px, 1.3028vw, 12px);
        margin-right: clamp(11.25px, 0.78125vw, 15px);

        .menuItem {
          position: relative;

          &>a {
            display: flex;
            flex-direction: column;
            align-items: center;

            span {
              color: var(--Grey-Deep, #4d4d4d);
              text-align: center;
              font-size: clamp(10.5px, 0.8458vw, 16px);
              font-style: normal;
              font-weight: 600;
              line-height: 160%;
              /* 35.2px */
            }

            span::after {
              content: '';
              width: 0;
              height: 2px;
              position: absolute;
              left: 50%;
              bottom: 10px;
              transform: translateX(-50%);
              background: var(--textColor);
              transition: all 0.3s;
              border-radius: 2px;
            }
          }

          .menuChild {
            display: none;
          }
        }

        .menuItem::after {
          content: '';
          width: 130%;
          display: inline-block;
          z-index: 3;
          height: 50px;
          background: transparent;
          position: absolute;
          top: 100%;
          left: 50%;
          transform: translateX(-50%);
        }

        .menuItem:hover {
          &>a {
            span {
              color: #fc1682;
              position: relative;
            }

            span::after {
              position: absolute;
              content: '';
              width: 100%;
              height: 2px;
              background: #fc1682;
              bottom: 2px;
              left: 50%;
              transform: translateX(-50%);
            }

            svg {
              path {
                fill: #fc1682;
              }
            }
          }

          .menuChild {
            display: flex;
            flex-direction: column;
            background: #fff;
            position: absolute;
            top: 100%;
            z-index: 99;
            width: 180%;
            box-sizing: border-box;
            padding: 0px clamp(15px, 1.04165vw, 20px) 5px;
            align-items: center;
            left: 50%;
            transform: translate(-50%, 10px);
            filter: drop-shadow(0px 0px 6px rgba(0, 0, 0, 0.15));
            border-radius: 6px;

            .menuChild-item {
              width: 100%;
              text-align: center;
              padding: 0;
              font-weight: 500;
              font-size: clamp(14px, 1.092vw, 20px);
              color: #666666;
              transition: all 0.3s;

              &>a {
                display: block;
                padding: clamp(8px, 0.052vw, 10px) 0 5px;
              }
            }

            .menuChild-item:not(:last-child) {
              border-bottom: 1px solid var(--indexColor2);
            }

            .menuChild-item:hover {
              color: var(--indexColor1);
            }
          }

          .menuChild::before {
            content: '';
            width: 0px;
            height: 0px;
            border: clamp(8px, 0.052vw, 10px) solid;
            border-color: transparent transparent #fff transparent;
            position: absolute;
            top: clamp(-14px, -0.092vw, -18px);
            left: 50%;
            transform: translateX(-50%);
          }
        }

        .menuItem:nth-child(3):hover {
          &>a {
            span {
              color: #fc1682;
              position: relative;
            }

            span::after {
              position: absolute;
              content: '';
              width: 100%;
              height: 2px;
              background: #fc1682;
              bottom: 2px;
              left: 50%;
              transform: translateX(-50%);
            }

            svg {
              path {
                fill: #fc1682;
              }
            }
          }

          .menuChild {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            grid-gap: 0 34px;
            flex-direction: column;
            background: #fff;
            position: absolute;
            top: 100%;
            z-index: 99;
            width: auto;
            box-sizing: border-box;
            padding: clamp(18.75px, 1.3028vw, 25px) clamp(18.75px, 1.3028vw, 25px);
            align-items: center;
            left: 50%;
            transform: translate(-50%, 10px);
            filter: drop-shadow(0px 0px 6px rgba(0, 0, 0, 0.15));
            border-radius: 6px;

            .menuChild-item {
              width: 100%;
              text-align: center;
              padding: 0;
              font-weight: 500;
              font-size: clamp(14px, 1.092vw, 20px);
              color: #666666;
              transition: all 0.3s;
              white-space: nowrap;

              &>a {
                display: block;
                padding: clamp(12px, 0.252vw, 16px) 0 5px;
              }
            }

            .menuChild-item:hover {
              color: var(--indexColor1);
            }

            .menuChild-item:nth-last-child(-n + 2) {
              border-bottom: none;
            }

            .menuChild-item:not(:nth-child(n + 6)) {
              color: var(--Theme-Color, #fc1682);
              position: relative;
            }

            .menuChild-item:not(:nth-child(n + 6))::before {
              content: '';
              position: absolute;
              top: 5px;
              transform: translateX(-50%);
              width: 5px;
              height: 5px;
              border-radius: 50%;
              background: var(--Theme-Color, #fc1682);
            }

            .menuChild-item:not(:nth-child(3n)) {
              position: relative;
            }

            .menuChild-item:not(:nth-child(3n))::after {
              content: '';
              position: absolute;
              width: 1px;
              height: 70%;
              right: clamp(-12.75px, -0.8854vw, -17px);
              top: 50%;
              transform: translateY(-50%);
              border-right: 1px solid var(--indexColor2);
            }
          }

          .menuChild::before {
            content: '';
            width: 0px;
            height: 0px;
            border: clamp(8px, 0.052vw, 10px) solid;
            border-color: transparent transparent #fff transparent;
            position: absolute;
            top: clamp(-14px, -0.092vw, -18px);
            left: 50%;
            transform: translateX(-50%);
          }

          .menuChild::after {
            content: '';
            animation: menuIconAnim 1.5s 0.5s forwards;
            background: url(https://static.cmereye.com/imgs/2024/04/4f39b444ca1b0a1d.png) no-repeat;
            background-position-y: 69.2307692308px;
            background-size: 100% auto;
            bottom: 0;
            content: '';
            display: block;
            height: 69.2307692308px;
            overflow: hidden;
            position: absolute;
            right: 30px;
            width: 100px;
          }
        }

        .menuItem:nth-child(4) {
          &>a {
            span {
              color: #00a752;
              position: relative;
            }

            span::after {
              bottom: 0px;
            }
          }
        }

        .menuItem:nth-child(4):hover {
          &>a {
            span {
              color: #00a752;
              position: relative;
            }

            span::after {
              position: absolute;
              content: '';
              background: #00a752;
              bottom: 2px;
            }

            svg {
              path {
                fill: #00a752;
              }
            }
          }
        }

        .menuItem:nth-child(5) {
          &>a {
            span {
              color: #e60013;
              position: relative;
            }

            span::after {
              bottom: 0px;
            }
          }
        }

        .menuItem:nth-child(5):hover {
          &>a {
            span {
              color: #e60013;
              position: relative;
            }

            span::after {
              position: absolute;
              content: '';
              background: #e60013;
              bottom: 0px;
            }

            svg {
              path {
                fill: #e60013;
              }
            }
          }
        }

        .menuItem:nth-child(8):hover {
          .menuChild {
            width: 200%;
          }
        }

        .menuItem:last-child {
          box-sizing: border-box;
          padding-top: 5px;
        }

        .menuItem:last-child:hover {
          .menuChild {
            width: 350%;
            padding: clamp(7.5px, 0.020825vw, 10px) clamp(15px, 1.04165vw, 20px) 5px;
          }
        }
      }

      .pc_menu_tel {
        color: var(--White, #fff);
        font-size: clamp(12.5px, 0.9458vw, 16px);
        font-style: normal;
        font-weight: 400;
        line-height: 160%;
        /* 35.2px */
        box-sizing: border-box;
        padding: clamp(8.25px, 0.98125vw, 15px) clamp(25px, 3.125vw, 30px) clamp(8.25px, 0.98125vw, 15px) clamp(11.25px, 0.78125vw, 15px);
        background: var(--Theme-Color, #fc1682);
      }
    }
  }
}
</style>