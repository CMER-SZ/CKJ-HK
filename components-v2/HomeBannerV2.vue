<script lang="ts" setup>
import { Autoplay, Pagination, Navigation } from 'swiper'

const bannerListV2 = ref([
  {
    name: '灣區長者醫療券banner',
    link: '/health-care-voucher',
    pc: 'https://static.ckjhk.com/ckj-image/d25c5ec24fe5.webp',
    mb: 'https://static.ckjhk.com/ckj-image/008e38b39a5d.webp',
  },
  {
    name: '愛康健裕亨预豹專享優惠',
    link: 'https://bit.ly/裕亨門診睇牙優惠',
    pc: 'https://static.ckjhk.com/page-images/ce0dd33167f6.webp',
    mb: 'https://static.ckjhk.com/page-images/60c96514b3bf.webp',
  },
  {
    name: '深圳希華愛康健医院',
    link: '/contactUs#contactUs',
    pc: 'https://static.ckjhk.com/ckj-image/d4015c1bca34.webp',
    mb: 'https://static.ckjhk.com/ckj-image/45ed1d6b2d5b.webp',
  },
  {
    name: '愛康健30年-慶典',
    link: '/brand/course#course',
    pc: 'https://static.ckjhk.com/page-images/65cc6a95fa1a.webp',
    mb: 'https://static.ckjhk.com/page-images/2eb14f85650f.webp',
  },
])


let services_include_cur_banner = ref(0)
let swiperRefBanner: any = {
  slidePrev: () => { },
  slideNext: () => { },
  slideTo: () => { },
}

const setswiperRefBannerHomeBanner = (swiper: any) => {

  swiperRefBanner = swiper
  console.log('setswiperRefBannerHomeBanner', swiperRefBanner.activeIndex);
  services_include_cur_banner.value = swiperRefBanner.activeIndex
}

const addNumBanner = () => {
  if (swiperRefBanner.activeIndex >= bannerListV2.value.length - 1) {
    swiperRefBanner.slideTo(0)
  }
  swiperRefBanner.slideNext()
  handleProcessBtnClick(swiperRefBanner.activeIndex)
}
const subNumBanner = () => {
  if (swiperRefBanner.activeIndex <= 0) {
    swiperRefBanner.slideTo(3)
  }
  swiperRefBanner.slidePrev()
  handleProcessBtnClick(swiperRefBanner.activeIndex)
}


const handleLineCurBanner = (_value: number) => {
  console.log(_value, 58);

  swiperRefBanner.slideTo(_value)
  handleProcessBtnClick(swiperRefBanner.activeIndex)
}

const handleProcessBtnClick = (i) => {
  services_include_cur_banner.value = swiperRefBanner.activeIndex
  const swiperPoints = document.querySelectorAll('.swiper-pagination-bullet-banner')
  swiperPoints.forEach((item: any, index: number) => {
    if (index == i) {
      item.classList.add('swiper-pagination-bullet-banner-active')
    } else {
      item.classList.remove('swiper-pagination-bullet-banner-active')
    }
  })
}
</script>

<template>
  <div class="HomeBannerV2">
    <Swiper class="indexSwiper" :modules="[Autoplay, Navigation, Pagination]" :slides-per-view="1"
      :autoplay="{ delay: 6000, disableOnInteraction: false }"
      :pagination="{ el: '.swiper-pagination', clickable: true }"
      :navigation="{ nextEl: '.swiper-button-next', prevEl: '.swiper-button-prev' }" :loop="true"
      @swiper="setswiperRefBannerHomeBanner">
      <SwiperSlide v-for="(item, index) in bannerListV2" :key="index">
        <div class="position-relative">
          <img :src="item.pc" :alt="item.name" loading="lazy" :srcset="`${item.mb} 400w, ${item.mb} 640w, ${item.pc}`"
            :sizes="'(max-width: 992px) 100vw, 1216px'">
          <div class="LearnMore" v-if="item.link.length > 0">
            <nuxt-link :to="item.link">了解更多</nuxt-link>
          </div>
        </div>
      </SwiperSlide>
    </Swiper>
    <div class="position-absolute swiper-Title z-2">
      <div class="swiper-Title-Box d-flex align-items-end justify-content-end align-items-lg-center ">
        <div>
          <div class="swiper-button-prev" @click="subNumBanner">
            <svg width=" 13" height="18" viewBox="0 0 13 18" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M10 15L2.5 8.99931L10 3" stroke="#D2337D" stroke-width="4" stroke-miterlimit="10"
                stroke-linecap="square" stroke-linejoin="round" />
            </svg>
          </div>

          <div class="swiper-pagination">
            <span v-for="(item, index) in bannerListV2" :key="index" @click="handleLineCurBanner(index)"
              :class="index == 0 ? 'swiper-pagination-bullet-banner-active' : ''"
              class="swiper-pagination-bullet-banner"></span>
          </div>

          <div class="swiper-button-next" @click="addNumBanner">
            <svg width="13" height="18" viewBox="0 0 13 18" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M3 15L10.5 8.99931L3 3" stroke="#D2337D" stroke-width="4" stroke-miterlimit="10"
                stroke-linecap="square" stroke-linejoin="round" />
            </svg>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
// 轮播图
.homeBannerV2 {
  margin-top: 115px;
  position: relative;
}

.indexSwiper {
  z-index: 1;
  overflow: hidden;

  .swiper-wrapper {
    .swiper-slide {
      .LearnMore a {
        z-index: 5;
        position: absolute;
        left: 20px;
        bottom: 10px;
        cursor: pointer;
        flex-shrink: 0;
        padding: 10px 20px;
        border-radius: 10px;
        border: 2px solid var(--Pink-Pale, #ffe9ec);

        background: var(--Blue-Deep, #00aeff);
        box-shadow: 0px 4px 4px 0px rgba(255, 255, 255, 0.25) inset,
          0px 4px 4px 0px rgba(77, 77, 77, 0.2);
        color: var(--White, #FFF);
        text-align: center;
        font-family: "Noto Sans HK";
        font-size: 30px;
        font-style: normal;
        font-weight: 700;
        line-height: 100%;
        letter-spacing: 3px;
        transition: background-color 0.3s ease;

      }
    }
  }

  .swiper-Title {
    bottom: 18px;
    width: fit-content;
    right: 20px;

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
}

.public-swiper-paginationEdit {
  gap: 4px;
  max-width: 162px;

  .swiper-button-prev,
  .swiper-button-next {
    flex-shrink: 0;
    width: 30px;
    height: 30px;
    border-radius: 50%;
    background: white;
    top: initial;
    margin-top: initial;
    position: initial;
    transition: background-color 0.3s ease;
    box-shadow: (0px 0px 5px rgba(0, 0, 0, 0.3));

    svg {
      width: 10px;
    }

    &:hover {
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

@media screen and (min-width:992px) {
  .HomeBannerV2 {
    position: relative;
  }

  :deep(.swiper-Title-Box) {
    &>div {
      display: flex;
      align-items: center;
    }

    .swiper-pagination-bullet-banner {
      width: 18px;
      height: 18px;
      background: #fff;
      opacity: 1;
      margin: 0;
      border-radius: 50%;
      box-shadow: rgba(0, 0, 0, 0.3) 3px 2px 2px;
    }

    .swiper-pagination {
      position: initial;
      display: flex;
      align-items: center;
      gap: 0 10px;
      margin: 0 10px;
    }

    .swiper-pagination-bullet-banner-active {
      background: #d2337d;
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

  // 轮播图
  .indexSwiper {
    margin-top: 120px;

    .swiper-wrapper {
      .swiper-slide {
        .LearnMore a {
          position: absolute;
          left: 32%;
          bottom: 10px;
          transform: translateX(-50%);
          padding: 10px 30px;
          color: var(--White, #FFF);
          text-align: center;
          font-family: "Noto Sans HK";
          font-size: 30px;
          font-style: normal;
          font-weight: 700;
          line-height: 100%;
          letter-spacing: 3px;

          &:hover {
            background-color: var(--White, #fff);
            color: var(--Blue-Deep, #00aeff);
          }
        }
      }
    }

    .swiper-Title {
      left: 65%;
      transform: translateX(-50%);
      padding: 0;
      bottom: 26px;

      &-Box {
        .swiper-paginationEdit {
          gap: 10px;
          height: 30px;

          .swiper-pagination {
            position: static;
            width: auto;
          }

          .swiper-pagination-bullet-banners .swiper-pagination-bullet-banner {
            width: 18px;
            height: 18px;
          }
        }
      }
    }

    .swiper-pagination-bullet-banner {
      width: 12px;
      height: 12px;
      margin: 0 2px !important;
    }

    .swiper-button-next,
    .swiper-button-prev {
      width: 18px;
      height: 18px;
      box-sizing: border-box;
      padding: 4px;

      &>svg {
        width: 100%;
        height: 100%;
        object-fit: cover;
      }
    }
  }

  .swiper-button-prev:after,
  .swiper-button-next:after {
    display: none;
  }

  .position-absolute {
    left: 48%;
    transform: translateX(-50%);
    bottom: 20px;
    z-index: 5;
  }
}

@media screen and (max-width:991px) {
  .indexSwiper {
    margin-top: 100px;

    .swiper-wrapper {
      .swiper-slide {
        .LearnMore a {
          left: 5.33vw;
          bottom: 4vw;
          padding: 2.665vw 5.33vw;
          color: var(--White, #FFF);
          text-align: center;
          font-family: "Noto Sans HK";
          font-size: 5.33vw;
          font-style: normal;
          font-weight: 700;
          line-height: 110%;
          letter-spacing: 0.53vw;
        }
      }
    }

    .swiper-Title {
      left: 50%;
      transform: translateX(-50%);
      padding: 0;
      bottom: 6.933vw;

      &-Box {
        .swiper-paginationEdit {
          height: 0;

          .swiper-pagination {
            position: static;
            width: auto;
          }
        }
      }
    }
  }


  .swiper-button-prev:after,
  .swiper-button-next:after {
    display: none;
  }

  .position-absolute {
    left: auto;
    right: 2.665vw;
    bottom: 2.665vw;
    z-index: 5;
  }

  :deep(.swiper-Title-Box) {
    &>div {
      display: flex;
      align-items: center;
    }

    .swiper-pagination-bullet-banner {
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

    .swiper-pagination-bullet-banner-active {
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
  }
}
</style>