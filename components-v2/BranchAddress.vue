<script setup lang="ts">
const carouselItems = ref([
  {
    hasCoupon: true,
    imageUrl:
      'https://statichk.cmermedical.com/newCKJ/index/BranchAddress/address-pc1.avif',
    title: '深圳愛康健口腔醫院',
    address: '深圳市羅湖區火車站大廈C區1-8樓',
    href: '/contactUs#contactUs',
    busRoutes: 'contactUs.addressLists.address_101.busRoutes',
    metroRoutes: 'contactUs.addressLists.address_101.metroRoutes',
    baiduMap: 'https://j.map.baidu.com/b3/j3Yu',
    gaoDeMap: 'https://surl.amap.com/qYXnDyt1l4WZ',
    flag: false,
  },
  {
    hasCoupon: false,
    imageUrl:
      'https://statichk.cmermedical.com/newCKJ/index/BranchAddress/address-pc2.avif',
    title: '深圳希華愛康健醫院',
    address:
      '深圳市羅湖區南湖街道和平社區和平路火車西站二層G區2層部分、3 - 7層',
    href: '/contactUs#contactUs',
    busRoutes: 'contactUs.addressLists.address_106.busRoutes',
    metroRoutes: 'contactUs.addressLists.address_106.metroRoutes',
    baiduMap: 'https://j.map.baidu.com/91/7oOi',
    gaoDeMap: 'https://surl.amap.com/pjaJ5kB1xdkP',
    flag: false,
  },
  {
    hasCoupon: false,
    imageUrl:
      'https://statichk.cmermedical.com/newCKJ/index/BranchAddress/address-pc3.avif',
    title: '恒潔口腔門診部',
    address:
      '深圳市羅湖區桂園街道新圍社區深南東路5015號金豐城大廈B座1602、1603',
    href: '/contactUs#contactUs',
    busRoutes: 'contactUs.addressLists.address_102.busRoutes',
    metroRoutes: 'contactUs.addressLists.address_102.metroRoutes',
    baiduMap: 'https://j.map.baidu.com/36/OZ5',
    gaoDeMap: 'https://surl.amap.com/ai17xY51x1bl',
    flag: false,
  },
  {
    hasCoupon: false,
    imageUrl:
      'https://statichk.cmermedical.com/newCKJ/index/BranchAddress/address-pc4.avif',
    title: '康輝口腔門診部',
    address:
      '深圳市羅湖區建設路深圳火車站皮帶走廊A12-A15.B11-B14及夾層B8--3號鋪',
    href: '/contactUs#contactUs',
    busRoutes: 'contactUs.addressLists.address_103.busRoutes',
    metroRoutes: 'contactUs.addressLists.address_103.metroRoutes',
    baiduMap: 'https://j.map.baidu.com/24/Rxk',
    gaoDeMap: 'https://surl.amap.com/cCdexAVo895',
    flag: false,
  },
  {
    hasCoupon: false,
    imageUrl:
      'https://statichk.cmermedical.com/newCKJ/index/BranchAddress/address-pc5.avif',
    title: '富康口腔門診部',
    address: '深圳市火車站南端二樓走廊(火車站大酒店左側)',
    href: '/contactUs#contactUs',
    busRoutes: 'contactUs.addressLists.address_104.busRoutes',
    metroRoutes: 'contactUs.addressLists.address_104.metroRoutes',
    baiduMap: 'https://j.map.baidu.com/a9/Xgch',
    gaoDeMap: 'https://surl.amap.com/qYXnDyt1l4WZ',
    flag: false,
  },
  {
    hasCoupon: false,
    imageUrl:
      'https://statichk.cmermedical.com/newCKJ/index/BranchAddress/address-pc6.avif',
    title: '顏麗口腔診所',
    address: '深圳市羅湖區羅湖口岸商業城1091號',
    href: '/contactUs#contactUs',
    busRoutes: 'contactUs.addressLists.address_105.busRoutes',
    metroRoutes: 'contactUs.addressLists.address_105.metroRoutes',
    baiduMap: 'https://j.map.baidu.com/d3/Awch',
    gaoDeMap: 'https://surl.amap.com/cRMQscZ1ogUJ',
    flag: false,
  },
  {
    hasCoupon: false,
    imageUrl:
      'https://statichk.cmermedical.com/newCKJ/index/BranchAddress/address-pc7.avif',
    title: '恒樂口腔診所',
    address: '羅湖區火車站綜合大樓夾層A區M層',
    href: '/contactUs#contactUs',
    busRoutes: 'contactUs.addressLists.address_105.busRoutes',
    metroRoutes: 'contactUs.addressLists.address_105.metroRoutes',
    baiduMap: 'https://j.map.baidu.com/d3/Awch',
    gaoDeMap: 'https://surl.amap.com/cRMQscZ1ogUJ',
    flag: false,
  },
])

const carouselItems2 = ref([
  {
    hasCoupon: false,
    imageUrl: 'https://static.cmereye.com/imgs/2024/03/57dee34750b0c30f.webp',
    title: '裕亨口腔診所',
    address: '深圳市福田區福田街道漁農社區裕亨路38號裕亨花園裕亨大廈103',
    href: '/contactUs#contactUs',
    busRoutes: 'contactUs.addressLists.address_204.busRoutes',
    metroRoutes: 'contactUs.addressLists.address_204.metroRoutes',
    baiduMap: 'https://j.map.baidu.com/a8/8R4c',
    gaoDeMap: 'https://surl.amap.com/cSB9Gvz1n4tm',
    flag: false,
  },
  {
    hasCoupon: false,
    imageUrl: 'https://static.cmereye.com/imgs/2024/06/ca2430f5e9cbec91.webp',
    title: '李川口腔診所',
    address: '深圳市福田區金田路水圍村金莊商業樓2-5樓',
    href: '/contactUs#contactUs',
    busRoutes: 'contactUs.addressLists.address_201.busRoutes',
    metroRoutes: 'contactUs.addressLists.address_201.metroRoutes',
    baiduMap: 'https://j.map.baidu.com/ea/Yhh',
    gaoDeMap: 'https://surl.amap.com/cV3xAxv1weYU',
    flag: false,
  },
  {
    hasCoupon: false,
    imageUrl: 'https://static.cmereye.com/imgs/2024/06/ca0cb58aab091e9c.webp',
    title: '王琦口腔診所',
    address: '深圳市福田區福田街道漁農社區裕亨路50號海悅華城C107、C108B',
    href: '/contactUs#contactUs',
    busRoutes: 'contactUs.addressLists.address_202.busRoutes',
    metroRoutes: 'contactUs.addressLists.address_202.metroRoutes',
    baiduMap: 'https://j.map.baidu.com/1f/kY0',
    gaoDeMap: 'https://surl.amap.com/cWYsCwZv13u',
    flag: false,
  },
    {
    hasCoupon: false,
    imageUrl: 'https://ckjhk.com/dental-service/implant/static/store.png',
    title: '富亨口腔門診',
    address: '深圳市福田口岸漁農社區裕亨路3號商業廣場2樓201-214及3樓307',
    href: '/contactUs#contactUs',
    busRoutes: 'contactUs.addressLists.address_204.busRoutes',
    metroRoutes: 'contactUs.addressLists.address_204.metroRoutes',
    baiduMap: 'https://j.map.baidu.com/26/pOk',
    gaoDeMap: 'https://surl.amap.com/cWYsCwZv13u',
    flag: false,
  },
])

const carouselItems3 = ref([
  {
    hasCoupon: false,
    imageUrl: 'https://static.cmereye.com/imgs/2024/10/8ec6180a704ba790.webp',
    title: '恒雅口腔門診部',
    address: '深圳市南山區南海大道與工業八路交匯處',
    href: '/contactUs#contactUs',
    busRoutes: 'contactUs.addressLists.address_301.busRoutes',
    metroRoutes: 'contactUs.addressLists.address_301.metroRoutes',
    baiduMap: 'https://j.map.baidu.com/2e/Pmif',
    gaoDeMap: 'https://surl.amap.com/mb6zUGYY2x3',
    flag: false,
  },
  {
    hasCoupon: false,
    imageUrl: 'https://static.cmereye.com/imgs/2024/10/69240bf104904c86.webp',
    title: '恒美口腔門診部',
    address: '深圳市南山區商業文化中心區海岸城西座501',
    href: '/contactUs#contactUs',
    busRoutes: 'contactUs.addressLists.address_302.busRoutes',
    metroRoutes: 'contactUs.addressLists.address_302.metroRoutes',
    baiduMap: 'https://j.map.baidu.com/36/4FH',
    gaoDeMap: 'https://surl.amap.com/mpPe7ioV7Ao',
    flag: false,
  },
  {
    hasCoupon: false,
    imageUrl: 'https://static.cmereye.com/imgs/2024/06/0028a94a3ed515e0.webp',
    title: '沈虹口腔診所',
    address: '深圳市南山區南海大道海典居裙樓1樓&2樓（海雅百貨對面）',
    href: '/contactUs#contactUs',
    busRoutes: 'contactUs.addressLists.address_303.busRoutes',
    metroRoutes: 'contactUs.addressLists.address_303.metroRoutes',
    baiduMap: 'https://j.map.baidu.com/b8/Mzj',
    gaoDeMap: 'https://surl.amap.com/ZFDrBn1wfaW',
    flag: false,
  },
])

const tabActive = (tab) => {
  // 获取 所有的mobile-item
  const mobileItems = document.querySelectorAll('.mobile-item')

  // 遍历mobile-item
  mobileItems.forEach((item, index) => {
    if (index === tab) {
      item.classList.add('mobile-active')
    } else {
      item.classList.remove('mobile-active')
    }
  })

  // 获取 class mobile-item-luohu
  const mobileItemLuohu = document.querySelector(
    '.mobile-item-luohu'
  ) as HTMLElement | null
  // 获取 class mobile-item-futian
  const mobileItemFutian = document.querySelector(
    '.mobile-item-futian'
  ) as HTMLElement | null
  // 获取 class mobile-item-nanshan
  const mobileItemNanshan = document.querySelector(
    '.mobile-item-nanshan'
  ) as HTMLElement | null

  if (tab === 0) {
    if (mobileItemLuohu) mobileItemLuohu.style.display = 'flex'
    if (mobileItemFutian) mobileItemFutian.style.display = 'none'
    if (mobileItemNanshan) mobileItemNanshan.style.display = 'none'
  } else if (tab === 1) {
    if (mobileItemLuohu) mobileItemLuohu.style.display = 'none'
    if (mobileItemFutian) mobileItemFutian.style.display = 'flex'
    if (mobileItemNanshan) mobileItemNanshan.style.display = 'none'
  } else if (tab === 2) {
    if (mobileItemLuohu) mobileItemLuohu.style.display = 'none'
    if (mobileItemFutian) mobileItemFutian.style.display = 'none'
    if (mobileItemNanshan) mobileItemNanshan.style.display = 'flex'
  }
}

const trafficList = (index, area) => {
  if (area === 'luoHu') {
    if (carouselItems.value[index].flag) {
      carouselItems.value[index].flag = false
    } else {
      carouselItems.value.forEach((item, indexa) => {
        if (index == indexa) {
          item.flag = true
        } else {
          item.flag = false
        }
      })
    }
  }
  if (area === 'futian') {
    if (carouselItems2.value[index].flag) {
      carouselItems2.value[index].flag = false
    } else {
      carouselItems2.value.forEach((item) => {
        item.flag = false
      })
      carouselItems2.value[index].flag = true
    }
  }
  if (area === 'nanshan') {
    if (carouselItems3.value[index].flag) {
      carouselItems3.value[index].flag = false
    } else {
      carouselItems3.value.forEach((item) => {
        item.flag = false
      })
      carouselItems3.value[index].flag = true
    }
  }
}

onMounted(() => {
  tabActive(0)
})
</script>

<template>
  <section class="BranchAddress" id="BranchAddress">
    <div class="subheading px-20"><span>分店</span> <span>地址</span></div>
    <img class="BranchAddress-addressImg ckj-contrain d-block mx-auto"
      src="https://statichk.cmermedical.com/newCKJ/index/BranchAddress/index-address-pc.webp" alt="" />
    <div class="container-fluid BranchAddress-Box px-20">
      <div class="BranchAddress-Box-pc d-none d-lg-block">
        <ul class="nav nav-tabs BranchAddress-Box-pc-navTab position-relative d-flex justify-content-center"
          id="HospitalAddressPc" role="tablist">
          <li class="nav-item" role="presentation">
            <button class="nav-link active" id="luohu-tab" data-bs-toggle="tab" data-bs-target="#luohu" type="button"
              role="tab" aria-controls="luohu" aria-selected="true">
              羅湖區
            </button>
          </li>
          <li class="nav-item" role="presentation">
            <button class="nav-link" id="futian-tab" data-bs-toggle="tab" data-bs-target="#futian" type="button"
              role="tab" aria-controls="futian" aria-selected="false">
              福田區
            </button>
          </li>
          <li class="nav-item" role="presentation">
            <button class="nav-link" id="nanshan-tab" data-bs-toggle="tab" data-bs-target="#nanshan" type="button"
              role="tab" aria-controls="nanshan" aria-selected="false">
              南山區
            </button>
          </li>
        </ul>
        <div class="tab-content ckj-contrain mx-auto BranchAddress-Box-pc-content position-relative"
          id="HospitalAddressPcContent">
          <div class="tab-pane fade show active" id="luohu" role="tabpanel" aria-labelledby="luohu-tab">
            <Carousel :slideItems="carouselItems" :itemsPerPage="4" />
          </div>
          <div class="tab-pane fade" id="futian" role="tabpanel" aria-labelledby="futian-tab">
            <div class="w-100 d-flex flex-wrap justify-content-start">
              <div class="BranchAddress-Box-pc-content-item position-relative d-flex" v-for="item in carouselItems2"
                :key="item.title">
                <div
                  class="BranchAddress-Box-pc-content-item-MedicalCoupon position-absolute d-flex align-items-center hidefalse"
                  :data-has-coupon="false">
                  <svg xmlns="http://www.w3.org/2000/svg" width="24" height="25" viewBox="0 0 24 25" fill="none">
                    <circle cx="12" cy="12.2734" r="12" fill="white" />
                    <rect x="7.65503" y="10.5613" width="7.2" height="3.36" transform="rotate(45 7.65503 10.5613)"
                      fill="#008843" />
                    <rect x="19.8894" y="8.9375" width="13.0446" height="3.36" transform="rotate(135 19.8894 8.9375)"
                      fill="#008843" />
                  </svg>
                  <span>醫療券</span>
                </div>
                <div class="BranchAddress-Box-pc-content-item-left">
                  <img :src="item.imageUrl" alt="" />
                </div>
                <div class="BranchAddress-Box-pc-content-item-right d-flex flex-column">
                  <h4>{{ item.title }}</h4>
                  <div>
                    <i><svg xmlns="http://www.w3.org/2000/svg" width="18" height="23" viewBox="0 0 18 23" fill="none">
                        <path
                          d="M9 0.799805C11.3869 0.799805 13.6761 1.75373 15.364 3.45173C17.0518 5.14973 18 7.45271 18 9.85405C18 13.68 15.3277 17.8496 10.0523 22.4074C9.75898 22.6609 9.38498 22.8001 8.99827 22.7998C8.61157 22.7995 8.23781 22.6596 7.94492 22.4056L7.596 22.101C2.55415 17.6621 0 13.5946 0 9.85405C0 7.45271 0.948212 5.14973 2.63604 3.45173C4.32387 1.75373 6.61305 0.799805 9 0.799805ZM9 6.37165C8.08194 6.37165 7.20149 6.73854 6.55232 7.39162C5.90316 8.0447 5.53846 8.93046 5.53846 9.85405C5.53846 10.7776 5.90316 11.6634 6.55232 12.3165C7.20149 12.9696 8.08194 13.3365 9 13.3365C9.91806 13.3365 10.7985 12.9696 11.4477 12.3165C12.0968 11.6634 12.4615 10.7776 12.4615 9.85405C12.4615 8.93046 12.0968 8.0447 11.4477 7.39162C10.7985 6.73854 9.91806 6.37165 9 6.37165Z"
                          fill="#F8298A" />
                      </svg></i><span>{{ item.address }}</span>
                  </div>
                  <div>
                    <div>
                      <div class="item-route-title">交通路線</div>
                      <div class="item-route">
                        <div>
                          <div>巴士路線</div>
                          <div v-html="$t(item.busRoutes)"></div>
                        </div>
                        <div>
                          <div>地鐵路線</div>
                          <div v-html="$t(item.metroRoutes)"></div>
                        </div>
                      </div>
                    </div>
                    <a :href="item.baiduMap">百度地圖</a>
                    <!-- <a :href="item.gaoDeMap">高德地圖</a> -->
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="tab-pane fade" id="nanshan" role="tabpanel" aria-labelledby="nanshan-tab">
            <div class="w-100 d-flex flex-wrap justify-content-start">
              <div class="BranchAddress-Box-pc-content-item position-relative d-flex" v-for="item in carouselItems3"
                :key="item.title">
                <div
                  class="BranchAddress-Box-pc-content-item-MedicalCoupon position-absolute d-flex align-items-center hidefalse"
                  :data-has-coupon="false">
                  <svg xmlns="http://www.w3.org/2000/svg" width="24" height="25" viewBox="0 0 24 25" fill="none">
                    <circle cx="12" cy="12.2734" r="12" fill="white" />
                    <rect x="7.65503" y="10.5613" width="7.2" height="3.36" transform="rotate(45 7.65503 10.5613)"
                      fill="#008843" />
                    <rect x="19.8894" y="8.9375" width="13.0446" height="3.36" transform="rotate(135 19.8894 8.9375)"
                      fill="#008843" />
                  </svg>
                  <span>醫療券</span>
                </div>
                <div class="BranchAddress-Box-pc-content-item-left">
                  <img :src="item.imageUrl" alt="" />
                </div>
                <div class="BranchAddress-Box-pc-content-item-right d-flex flex-column">
                  <h4>{{ item.title }}</h4>
                  <div>
                    <i><svg xmlns="http://www.w3.org/2000/svg" width="18" height="23" viewBox="0 0 18 23" fill="none">
                        <path
                          d="M9 0.799805C11.3869 0.799805 13.6761 1.75373 15.364 3.45173C17.0518 5.14973 18 7.45271 18 9.85405C18 13.68 15.3277 17.8496 10.0523 22.4074C9.75898 22.6609 9.38498 22.8001 8.99827 22.7998C8.61157 22.7995 8.23781 22.6596 7.94492 22.4056L7.596 22.101C2.55415 17.6621 0 13.5946 0 9.85405C0 7.45271 0.948212 5.14973 2.63604 3.45173C4.32387 1.75373 6.61305 0.799805 9 0.799805ZM9 6.37165C8.08194 6.37165 7.20149 6.73854 6.55232 7.39162C5.90316 8.0447 5.53846 8.93046 5.53846 9.85405C5.53846 10.7776 5.90316 11.6634 6.55232 12.3165C7.20149 12.9696 8.08194 13.3365 9 13.3365C9.91806 13.3365 10.7985 12.9696 11.4477 12.3165C12.0968 11.6634 12.4615 10.7776 12.4615 9.85405C12.4615 8.93046 12.0968 8.0447 11.4477 7.39162C10.7985 6.73854 9.91806 6.37165 9 6.37165Z"
                          fill="#F8298A" />
                      </svg></i><span>{{ item.address }}</span>
                  </div>
                  <div>
                    <div>
                      <div class="item-route-title">交通路線</div>
                      <div class="item-route">
                        <div>
                          <div>巴士路線</div>
                          <div v-html="$t(item.busRoutes)"></div>
                        </div>
                        <div>
                          <div>地鐵路線</div>
                          <div v-html="$t(item.metroRoutes)"></div>
                        </div>
                      </div>
                    </div>
                    <a :href="item.baiduMap">百度地圖</a>
                    <!-- <a :href="item.gaoDeMap">高德地圖</a> -->
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="BranchAddress-Box-mobile d-lg-none">
        <ul>
          <li @click="tabActive(0)" class="mobile-item mobile-active">
            羅湖區
          </li>
          <li @click="tabActive(1)" class="mobile-item">福田區</li>
          <li @click="tabActive(2)" class="mobile-item">南山區</li>
        </ul>
        <div>
          <div class="mobile-item-luohu">
            <div v-for="(item, index) in carouselItems" :key="index" class="luoHu-item">
              <div :class="item.hasCoupon ? 'img-coupon' : ''">
                <img :src="item.imageUrl" alt="" />
              </div>
              <div>
                <div>{{ item.title }}</div>
                <div>
                  <div>
                    <svg xmlns="http://www.w3.org/2000/svg" width="14" height="17" viewBox="0 0 14 17" fill="none">
                      <path
                        d="M7 0C8.85652 0 10.637 0.737125 11.9497 2.04922C13.2625 3.36131 14 5.14088 14 6.99646C14 9.95291 11.9215 13.1749 7.81846 16.6968C7.59031 16.8927 7.29943 17.0003 6.99866 17C6.69789 16.9997 6.40719 16.8916 6.17939 16.6954L5.908 16.46C1.98656 13.0299 0 9.8869 0 6.99646C0 5.14088 0.737498 3.36131 2.05025 2.04922C3.36301 0.737125 5.14348 0 7 0ZM7 4.30551C6.28596 4.30551 5.60116 4.58902 5.09625 5.09367C4.59135 5.59832 4.30769 6.28278 4.30769 6.99646C4.30769 7.71014 4.59135 8.3946 5.09625 8.89925C5.60116 9.4039 6.28596 9.68741 7 9.68741C7.71404 9.68741 8.39884 9.4039 8.90375 8.89925C9.40866 8.3946 9.69231 7.71014 9.69231 6.99646C9.69231 6.28278 9.40866 5.59832 8.90375 5.09367C8.39884 4.58902 7.71404 4.30551 7 4.30551Z"
                        fill="#F8298A" />
                    </svg>
                  </div>
                  <div>{{ item.address }}</div>
                </div>
                <div class="item-traffic">
                  <div class="traffic-box">
                    <div @click="trafficList(index, 'luoHu')" class="traffic-text"
                      :class="{ 'item-text-active': item.flag }">
                      交通路線
                    </div>
                    <div class="route-traffic" v-if="item.flag">
                      <div>
                        <div>巴士路線</div>
                        <div v-html="$t(item.busRoutes)"></div>
                      </div>
                      <div>
                        <div>地鐵路線</div>
                        <div class="route-traffic-list" v-html="$t(item.metroRoutes)"></div>
                      </div>
                    </div>
                  </div>
                  <a :href="item.baiduMap" target="_blank" class="traffic-text">
                    百度地圖
                  </a>
                  <!-- <a :href="item.gaoDeMap" target="_blank" class="traffic-text">
                    高德地圖
                  </a> -->
                </div>
              </div>
            </div>
          </div>
          <div class="mobile-item-futian">
            <div v-for="(item, index) in carouselItems2" :key="index" class="fuTian-item">
              <div><img :src="item.imageUrl" alt="" /></div>
              <div>
                <div>{{ item.title }}</div>
                <div>
                  <div>
                    <svg xmlns="http://www.w3.org/2000/svg" width="14" height="17" viewBox="0 0 14 17" fill="none">
                      <path
                        d="M7 0C8.85652 0 10.637 0.737125 11.9497 2.04922C13.2625 3.36131 14 5.14088 14 6.99646C14 9.95291 11.9215 13.1749 7.81846 16.6968C7.59031 16.8927 7.29943 17.0003 6.99866 17C6.69789 16.9997 6.40719 16.8916 6.17939 16.6954L5.908 16.46C1.98656 13.0299 0 9.8869 0 6.99646C0 5.14088 0.737498 3.36131 2.05025 2.04922C3.36301 0.737125 5.14348 0 7 0ZM7 4.30551C6.28596 4.30551 5.60116 4.58902 5.09625 5.09367C4.59135 5.59832 4.30769 6.28278 4.30769 6.99646C4.30769 7.71014 4.59135 8.3946 5.09625 8.89925C5.60116 9.4039 6.28596 9.68741 7 9.68741C7.71404 9.68741 8.39884 9.4039 8.90375 8.89925C9.40866 8.3946 9.69231 7.71014 9.69231 6.99646C9.69231 6.28278 9.40866 5.59832 8.90375 5.09367C8.39884 4.58902 7.71404 4.30551 7 4.30551Z"
                        fill="#F8298A" />
                    </svg>
                  </div>
                  <div>{{ item.address }}</div>
                </div>
                <div class="item-traffic">
                  <div class="traffic-box">
                    <div @click="trafficList(index, 'futian')" class="traffic-text"
                      :class="{ 'item-text-active': item.flag }">
                      交通路線
                    </div>
                    <div class="route-traffic" v-if="item.flag">
                      <div>
                        <div>巴士路線</div>
                        <div v-html="$t(item.busRoutes)"></div>
                      </div>
                      <div>
                        <div>地鐵路線</div>
                        <div class="route-traffic-list" v-html="$t(item.metroRoutes)"></div>
                      </div>
                    </div>
                  </div>
                  <a :href="item.baiduMap" target="_blank" class="traffic-text">
                    百度地圖
                  </a>
                  <!-- <a :href="item.gaoDeMap" target="_blank" class="traffic-text">
                    高德地圖
                  </a> -->
                </div>
              </div>
            </div>
          </div>
          <div class="mobile-item-nanshan">
            <div v-for="(item, index) in carouselItems3" :key="index" class="nanShan-item">
              <div><img :src="item.imageUrl" alt="" /></div>
              <div>
                <div>{{ item.title }}</div>
                <div>
                  <div>
                    <svg xmlns="http://www.w3.org/2000/svg" width="14" height="17" viewBox="0 0 14 17" fill="none">
                      <path
                        d="M7 0C8.85652 0 10.637 0.737125 11.9497 2.04922C13.2625 3.36131 14 5.14088 14 6.99646C14 9.95291 11.9215 13.1749 7.81846 16.6968C7.59031 16.8927 7.29943 17.0003 6.99866 17C6.69789 16.9997 6.40719 16.8916 6.17939 16.6954L5.908 16.46C1.98656 13.0299 0 9.8869 0 6.99646C0 5.14088 0.737498 3.36131 2.05025 2.04922C3.36301 0.737125 5.14348 0 7 0ZM7 4.30551C6.28596 4.30551 5.60116 4.58902 5.09625 5.09367C4.59135 5.59832 4.30769 6.28278 4.30769 6.99646C4.30769 7.71014 4.59135 8.3946 5.09625 8.89925C5.60116 9.4039 6.28596 9.68741 7 9.68741C7.71404 9.68741 8.39884 9.4039 8.90375 8.89925C9.40866 8.3946 9.69231 7.71014 9.69231 6.99646C9.69231 6.28278 9.40866 5.59832 8.90375 5.09367C8.39884 4.58902 7.71404 4.30551 7 4.30551Z"
                        fill="#F8298A" />
                    </svg>
                  </div>
                  <div>{{ item.address }}</div>
                </div>
                <di class="item-traffic">
                  <div class="traffic-box">
                    <div @click="trafficList(index, 'nanshan')" class="traffic-text"
                      :class="{ 'item-text-active': item.flag }">
                      交通路線
                    </div>
                    <div class="route-traffic" v-if="item.flag">
                      <div>
                        <div>巴士路線</div>
                        <div v-html="$t(item.busRoutes)"></div>
                      </div>
                      <div>
                        <div>地鐵路線</div>
                        <div v-html="$t(item.metroRoutes)"></div>
                      </div>
                    </div>
                  </div>
                  <a :href="item.baiduMap" target="_blank" class="traffic-text">
                    百度地圖
                  </a>
                  <!-- <a :href="item.gaoDeMap" target="_blank" class="traffic-text">
                    高德地圖
                  </a> -->
                </di>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <NewAddress class="d-lg-none" />
  </section>
</template>


<style lang="scss" scope>
@media screen and (min-width: 992px) {
  .subheading {
    box-sizing: border-box;
    width: fit-content;
    margin: 0 auto;
    padding: 0 10px;
    position: relative;
    background: #fff;
    border-left: none;

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
    top: 55%;
    left: 50%;
    width: 180%;
    height: 2px;
    background: var(--Pink-Pale, #ffe9ec);
    transform: translate(-50%, -50%);
    z-index: -1;
  }

  .BranchAddress {
    .BranchAddress-Box {
      padding-top: 20px;

      &-pc {
        &-navTab {
          border: none;
          width: fit-content;
          margin: 0 auto;
          border-radius: 10px;
          border: 1px solid var(--Grey-Light, #e6e6e6);
          background: var(--White, #fff);

          li {
            button {
              border: 1px solid var(--Grey-Light, #e6e6e6);

              color: var(--Grey-Mid, #666);
              text-align: center;
              background: var(--White, #fff);
              font-family: 'Noto Sans TC';
              font-size: 20px;
              font-style: normal;
              font-weight: 700;
              line-height: 160%;
              letter-spacing: 2px;
              border-radius: 0;
            }

            .active {
              background: var(--New-Theme-Color, #d2337d);
              color: var(--White, #fff);
              position: relative;

              &::after {
                content: '';
                position: absolute;
                left: 50%;
                transform: translateX(-50%);
                top: 100%;
                width: 0;
                height: 0;
                border-left: 8.5px solid transparent;
                /* 左半边透明 */
                border-right: 8.5px solid transparent;
                /* 右半边透明 */
                border-top: 6px solid var(--New-Theme-Color, #d2337d);
                /* 顶部边框形成三角形 */
              }
            }
          }

          &-number {
            left: 100px;
            top: -70px;
            color: var(--Grey-Mid, #666);
            font-family: 'Noto Sans TC';
            font-size: 20px;
            font-style: normal;
            font-weight: 700;
            line-height: 160%;
            letter-spacing: 2px;

            span {
              color: var(--New-Theme-Color, #d2337d);
              font-size: 30px;
              letter-spacing: 3px;
            }
          }

          &>li:nth-child(1) button {
            border-radius: 10px 0px 0px 10px;
          }

          &>li:nth-child(2) button {
            border-left: none;
            border-right: none;
          }

          &>li:nth-child(3) button {
            border-radius: 0px 10px 10px 0px;
          }
        }

        &-content {
          .tab-pane>div {
            gap: 15px;
          }

          margin-top: 28px;

          // max-width: 1113px;
          &-item {

            // 醫療券
            &-MedicalCoupon {
              top: 0;
              left: 0;
              border-radius: 10px 0px;
              background: var(--GHV-Green, #008843);
              padding: 6px 7px 6px 9px;

              svg {
                width: 24px;
                margin-right: 4px;
              }

              color: var(--White, #fff);
              font-family: 'Noto Sans TC';
              font-size: 20px;
              font-style: normal;
              font-weight: 700;
              line-height: 160%;
              letter-spacing: 2px;
            }

            gap: 0;
            width: 470px;
            border-radius: 10px;
            overflow: visible;
            background: var(--White, #fff);
            box-shadow: 0px 4px 4px 0px rgba(77, 77, 77, 0.2);

            // padding: 20px;
            &-left {
              max-width: 190px;
              flex-shrink: 0;

              img {
                min-width: 190px;
                height: 100%;
                max-height: 143px;
              }
            }

            &-right {
              flex-shrink: 0;
              flex: 1;
              // gap: 11.5px;
              padding: 10px 10px 0 0;
              justify-content: flex-start;
              position: relative;

              h4 {
                color: var(--New-Theme-Color, #d2337d);
                font-family: 'Noto Sans TC';
                font-size: 20px;
                font-style: normal;
                font-weight: 700;
                line-height: 160%;
                letter-spacing: 2px;
                padding-left: 15px;
              }

              &>div:nth-child(2) {
                margin-top: 7px;
                padding-left: 15px;
                display: flex;

                i {
                  svg {
                    width: 18px;
                    height: 22px;
                  }
                }

                span {
                  margin-left: 10px;
                  color: var(--Grey-Dark, #333);
                  text-align: justify;
                  font-family: 'Noto Sans HK';
                  font-size: 14px;
                  font-style: normal;
                  font-weight: 350;
                  line-height: 128.571%;
                }
              }

              &>div:nth-child(3) {
                display: flex;
                position: absolute;
                right: auto;
                left: 0;
                bottom: 0;
                padding-left: 15px;
                gap: 0 7px;
                justify-content: space-between;
                margin-right: 10px;

                &>a {
                  box-sizing: border-box;
                  padding: 6px 15.5px;
                  display: flex;
                  align-items: center;
                  justify-content: center;
                  text-decoration-line: underline;
                  text-decoration-style: solid;
                  text-decoration-skip-ink: auto;
                  text-decoration-thickness: auto;
                  text-underline-offset: auto;
                  color: var(--Brand-Color, #f8298a);
                  text-align: justify;
                  font-family: 'Noto Sans HK';
                  font-size: 16px;
                  font-style: normal;
                  font-weight: 700;
                  line-height: normal;
                  letter-spacing: 0px;
                }

                .item-route {
                  cursor: pointer;
                  display: none;
                  flex-direction: column;
                  background: #fff;
                  padding: 10px 15px;
                  border-radius: 10px;
                  box-shadow: 0px 4px 4px 0px rgba(77, 77, 77, 0.2);
                  gap: 10px 0;

                  &>div {
                    display: flex;
                    flex-direction: column;

                    &>div:nth-child(1) {
                      color: var(--Theme-Color, #fc1682);
                      text-align: justify;
                      font-family: 'Noto Sans HK';
                      font-size: 16px;
                      font-style: normal;
                      font-weight: 700;
                      line-height: normal;
                      letter-spacing: 1.6px;
                    }

                    &>div:nth-child(2) {
                      color: var(--Grey-Deep, #4d4d4d);
                      font-size: 16px;
                      font-weight: 400;
                      line-height: 150%;
                      /* 24px */
                      letter-spacing: 1.6px;
                    }
                  }

                  box-sizing: border-box;
                  position: absolute;
                  width: 380px;
                  left: 0;
                  top: 100%;
                  z-index: 25;
                }

                .item-route-title:hover {
                  background: var(--New-Theme-Color, #d2337d);
                  color: var(--White, #fff);
                  border-radius: 10px 10px 0 0;
                }

                .item-route-title:hover~.item-route {
                  display: flex;
                  box-shadow: 1px 2px 17.1px 0px rgba(252, 22, 130, 0.5);
                }

                .item-route-title {
                  cursor: pointer;
                  box-sizing: border-box;
                  padding: 6px 15.5px;
                  color: var(--Brand-Color, #f8298a);
                  font-family: 'Noto Sans HK';
                  font-size: 16px;
                  font-style: normal;
                  font-weight: 500;
                  line-height: 150%;
                  /* 18px */
                  letter-spacing: 0;
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
        }
      }
    }
  }

  // 分店地址
  .BranchAddress {
    padding-top: 45px;
    padding-bottom: 30px;

    &-addressImg {
      margin-top: 20px;
    }
  }

  .BranchAddress-address-table {
    width: 100%;
    max-width: 960px;
    margin: 0 auto;
  }
}

@media screen and (max-width: 991px) {
  .BranchAddress {
    margin-top: 10vw;
  }

  .BranchAddress-Box-mobile {
    &>ul {
      display: flex;
      justify-content: center;
      border-radius: 1.33vw;
      overflow: hidden;
      width: fit-content;
      margin: 0 auto 4vw;
    }

    .mobile-item {
      box-sizing: border-box;
      padding: 8px 7.065vw;
      background: #fff;
      border-top: 1px solid var(--Grey-Light, #e6e6e6);
      border-bottom: 1px solid var(--Grey-Light, #e6e6e6);
      color: var(--Grey-Mid, #666);
      text-align: center;
      font-family: 'Noto Sans HK';
      font-size: 4.265vw;
      font-style: normal;
      font-weight: 700;
      line-height: normal;
      letter-spacing: 0.42vw;
    }

    .mobile-active {
      background: var(--New-Theme-Color, #d2337d);
      color: var(--White, #fff);
      border-color: var(--New-Theme-Color, #d2337d);
      transition: all 0.3s ease;
    }

    .mobile-item:nth-child(1) {
      border-left: 0.265vw solid var(--Grey-Light, #e6e6e6);
    }

    .mobile-item:nth-child(2) {
      border-left: 0.265vw solid var(--Grey-Light, #e6e6e6);
      border-right: 0.265vw solid var(--Grey-Light, #e6e6e6);
    }

    .mobile-item:nth-child(3) {
      border-right: 0.265vw solid var(--Grey-Light, #e6e6e6);
    }

    &>div {
      .img-coupon {
        position: relative;
      }

      .img-coupon::after {
        content: '';
        position: absolute;
        top: 0;
        left: 0;
        width: 19.72vw;
        height: 5.8vw;
        background: url('https://static.ckjhk.com/ckj-image/2025032714504501.svg') no-repeat;
        background-size: contain;
      }

      &>div {

        .luoHu-item,
        .fuTian-item,
        .nanShan-item {
          box-shadow: 0px 4px 4px 0px rgba(77, 77, 77, 0.2);
          display: flex;
          gap: 0 0;

          &>div:nth-child(1) {
            min-width: 30.93vw;
            max-width: 30.93vw;
            // height: 23.2vw;
            // max-height: 23.2vw;
            overflow: hidden;

            &>img {
              width: 100%;
              height: 100%;
              object-fit: cover;
            }
          }

          &>div:nth-child(2) {
            box-sizing: border-box;
            padding: 4px 0 0 0;
            display: flex;
            flex-direction: column;
            justify-content: space-between;

            &>div:nth-child(1) {
              color: var(--Brand-Color, #f8298a);
              font-family: 'Noto Sans HK';
              font-size: 3.733vw;
              font-style: normal;
              font-weight: 500;
              line-height: 150%;
              /* 21px */
              letter-spacing: 0;
              padding-left: 2.65vw;
            }

            &>div:nth-child(2) {
              padding-left: 2.65vw;
              margin-top: 0.53vw;
              display: flex;
              gap: 0 1.065vw;
              height: max-content;
              min-height: 36px;

              &>div:nth-child(2) {
                color: var(--Grey-Dark, #333);
                font-family: 'Noto Sans HK';
                font-size: 3.2vw;
                font-style: normal;
                font-weight: 400;
                line-height: 150%;
                /* 18px */
                letter-spacing: 0;
              }
            }
          }

          .item-traffic {
            display: flex;
            align-items: center;
            gap: 0 0;
            position: relative;
            padding-left: 10px;

            &>div,
            &>a {
              color: var(--Brand-Color, #f8298a);
              text-align: justify;
              font-family: 'Noto Sans HK';
              font-size: 3.2vw;
              font-style: normal;
              font-weight: 500;
              line-height: 150%;
              /* 18px */
              letter-spacing: 0;
              text-decoration-line: underline;
              text-decoration-style: solid;
              text-decoration-skip-ink: auto;
              text-decoration-thickness: auto;
              text-underline-offset: auto;
              text-underline-position: from-font;
            }

            .route-traffic {
              position: absolute;
              top: 100%;
              z-index: 23;
              left: 10px;
              border-radius: 0px 10px 10px 10px;
              background: var(--White, #fff);
              box-sizing: border-box;
              padding: 10px 4vw;
              box-shadow: 1px 2px 17.1px 0px rgba(252, 22, 130, 0.5);
              flex-direction: column;
              gap: 10px 0;
              display: flex;

              &>div {
                &>div:nth-child(1) {
                  font-weight: 400;
                }

                &>div:nth-child(2) {
                  color: var(--Grey-Deep, #4d4d4d);
                }
              }
            }
          }

          .traffic-text {
            box-sizing: border-box;
            padding: 4px 4vw;
            color: var(--Brand-Color, #f8298a);
            text-align: justify;
            font-family: 'Noto Sans HK';
            font-size: 3.2vw;
            font-style: normal;
            font-weight: 500;
            line-height: 150%;
            /* 18px */
            letter-spacing: 0;
            text-decoration-line: underline;
            text-decoration-style: solid;
            text-decoration-skip-ink: auto;
            text-decoration-thickness: auto;
            text-underline-offset: auto;
            text-underline-position: from-font;
          }

          .item-text-active {
            display: flex;
            color: var(--White, #fff);
            background: var(--New-Theme-Color, #d2337d);
            border-radius: 10px 10px 0px 0px;
          }
        }
      }

      .mobile-item-luohu,
      .mobile-item-futian,
      .mobile-item-nanshan {
        display: flex;
        flex-direction: column;
        gap: 16px 0;
        margin: 16px 0 0;
        position: relative;
        z-index: 1;
      }
    }
  }

  .BranchAddress-addressImg {
    width: 100%;
    height: auto;
    margin-top: 15px;

    &>img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  }

  .BranchAddress-Box {
    padding: 0 2.65vw;
  }

  .subheading {
    margin-left: 4vw;
    box-sizing: border-box;
    padding-left: 3.2vw;
    border-left: 2px solid var(--New-Theme-Color, #d2337d);

    span {
      color: var(--Grey-Dark, #333);
      font-family: 'Noto Sans HK';
      font-size: 4.265vw;
      font-style: normal;
      font-weight: 500;
      line-height: 170%;
      letter-spacing: 0.4265vw;
    }

    span:not(:last-child) {
      color: var(--New-Theme-Color, #d2337d);
      font-family: 'Noto Sans HK';
      font-size: 5.6vw;
      font-style: normal;
      font-weight: 700;
      line-height: 150%;
      /* 31.5px */
      letter-spacing: 0.56vw;
    }

    .span_colours {
      color: var(--New-Theme-Color, #d2337d);
      font-family: 'Noto Sans HK';
      font-size: 4.8vw !important;
      font-style: normal;
      font-weight: 500;
      line-height: 170%;
      letter-spacing: 0.48vw !important;
    }
  }
}
</style>