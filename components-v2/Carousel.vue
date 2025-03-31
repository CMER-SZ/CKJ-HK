<template>
  <div class="carousel-container">
    <!-- 轮播内容 -->
    <div class="carousel-content carousel-inner">
      <div
        v-for="(page, pageIndex) in slidePages"
        :key="pageIndex"
        class="slider"
        :class="{ 'slider-active': pageIndex === currentPage }"
        :style="{
          transform: `translateX(${(pageIndex - currentPage) * 100}%)`,
        }"
      >
        <div
          v-for="(item, itemIndex) in page"
          :key="itemIndex"
          class="BranchAddress-Box-pc-content-item position-relative d-flex"
        >
          <div
            class="BranchAddress-Box-pc-content-item-MedicalCoupon position-absolute d-flex align-items-center"
            :class="{ hidetrue: item.hasCoupon, hidefalse: !item.hasCoupon }"
            :data-has-coupon="item.hasCoupon"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="24"
              height="25"
              viewBox="0 0 24 25"
              fill="none"
            >
              <circle cx="12" cy="12.2734" r="12" fill="white" />
              <rect
                x="7.65503"
                y="10.5613"
                width="7.2"
                height="3.36"
                transform="rotate(45 7.65503 10.5613)"
                fill="#008843"
              />
              <rect
                x="19.8894"
                y="8.9375"
                width="13.0446"
                height="3.36"
                transform="rotate(135 19.8894 8.9375)"
                fill="#008843"
              />
            </svg>
            <span>醫療券</span>
          </div>
          <div class="BranchAddress-Box-pc-content-item-left">
            <img :src="item.imageUrl" alt="" />
          </div>
          <div
            class="BranchAddress-Box-pc-content-item-right d-flex flex-column"
          >
            <h4>{{ item.title }}</h4>
            <div>
              <i>
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  width="18"
                  height="23"
                  viewBox="0 0 18 23"
                  fill="none"
                >
                  <path
                    d="M9 0.799805C11.3869 0.799805 13.6761 1.75373 15.364 3.45173C17.0518 5.14973 18 7.45271 18 9.85405C18 13.68 15.3277 17.8496 10.0523 22.4074C9.75898 22.6609 9.38498 22.8001 8.99827 22.7998C8.61157 22.7995 8.23781 22.6596 7.94492 22.4056L7.596 22.101C2.55415 17.6621 0 13.5946 0 9.85405C0 7.45271 0.948212 5.14973 2.63604 3.45173C4.32387 1.75373 6.61305 0.799805 9 0.799805ZM9 6.37165C8.08194 6.37165 7.20149 6.73854 6.55232 7.39162C5.90316 8.0447 5.53846 8.93046 5.53846 9.85405C5.53846 10.7776 5.90316 11.6634 6.55232 12.3165C7.20149 12.9696 8.08194 13.3365 9 13.3365C9.91806 13.3365 10.7985 12.9696 11.4477 12.3165C12.0968 11.6634 12.4615 10.7776 12.4615 9.85405C12.4615 8.93046 12.0968 8.0447 11.4477 7.39162C10.7985 6.73854 9.91806 6.37165 9 6.37165Z"
                    fill="#F8298A"
                  />
                </svg>
              </i>
              <span>{{ item.address }}</span>
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
  <!-- 导航栏 -->
  <div class="carousel-nav">
    <button @click="prevSlide" class="prev-btn">
      <svg
        xmlns="http://www.w3.org/2000/svg"
        width="11"
        height="16"
        viewBox="0 0 11 16"
        fill="none"
      >
        <path
          d="M9 1.7998L1.5 7.79911L9 13.7998"
          stroke="#F8298A"
          stroke-width="2"
          stroke-miterlimit="10"
          stroke-linecap="square"
          stroke-linejoin="round"
        />
      </svg>
    </button>
    <div
      v-for="(dot, index) in slidePageCount"
      :key="index"
      class="carousel-dot"
      :class="{ active: currentPage === index }"
      @click="goToPage(index)"
    ></div>
    <button @click="nextSlide" class="next-btn">
      <svg
        xmlns="http://www.w3.org/2000/svg"
        width="11"
        height="16"
        viewBox="0 0 11 16"
        fill="none"
      >
        <path
          d="M2 13.7998L9.5 7.79911L2 1.7998"
          stroke="#F8298A"
          stroke-width="2"
          stroke-miterlimit="10"
          stroke-linecap="square"
          stroke-linejoin="round"
        />
      </svg>
    </button>
  </div>
</template>

<script setup lang="ts">
import { ref, defineProps, onMounted, onUnmounted } from 'vue'

const props = defineProps<{
  slideItems: {
    hasCoupon: boolean
    imageUrl: string
    title: string
    address: string
    href: string
    baiduMap: string
    //gaoDeMap: string
    busRoutes: string
    metroRoutes: string
    flag: boolean
  }[]
  itemsPerPage: number
}>()

// 当前显示的页面索引
const currentPage = ref(0)
// 每页显示的项目数
const itemsPerPage = props.itemsPerPage
// 计算总页数
const slidePageCount = Math.ceil(props.slideItems.length / itemsPerPage)

// 将幻灯片项目分组为页面
const slidePages = ref<
  {
    hasCoupon: boolean
    imageUrl: string
    title: string
    address: string
    href: string
    baiduMap: string
    //gaoDeMap: string
    busRoutes: string
    metroRoutes: string
    flag: boolean
  }[][]
>([])

for (let i = 0; i < slidePageCount; i++) {
  const start = i * itemsPerPage
  const end = start + itemsPerPage
  slidePages.value.push(props.slideItems.slice(start, end))
}

// 上一页
const prevSlide = () => {
  currentPage.value = (currentPage.value - 1 + slidePageCount) % slidePageCount
}

// 下一页
const nextSlide = () => {
  currentPage.value = (currentPage.value + 1) % slidePageCount
}

// 跳转到指定页面
const goToPage = (index: number) => {
  currentPage.value = index
}

// 自动切换
// let autoSlideInterval: number = ref('')

// onMounted(() => {
//   autoSlideInterval = setInterval(() => {
//     nextSlide()
//   }, 50000)
// })

// onUnmounted(() => {
//   clearInterval(autoSlideInterval)
// })
</script>

<style scoped>
.carousel-container {
  position: relative;
  max-width: 960px;
  margin: 0 auto;
  overflow: visible;
}

.carousel-content {
  position: relative;
  display: flex;
  transition: transform 0.5s ease-in-out;
}
.carousel-inner {
  height: 315px;
  margin-bottom: 30px;
  overflow: visible;
  z-index: 9;
}
.slider {
  position: absolute;
  width: 100%;
  gap: 0 17px;
  display: flex;
  flex-wrap: wrap;
  justify-content: flex-start;
  transition: transform 0.5s ease-in-out;
  display: none;
}

.slider-active {
  transform: translateX(0);
  display: flex;
}

.carousel-nav {
  display: flex;
  justify-content: center;
  align-items: center;
  padding-bottom: 4px;
  position: relative;
  z-index: 1;
}

.prev-btn,
.next-btn {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 30px;
  height: 30px;
  border-radius: 50%;
  box-shadow: 0px 4px 4px rgba(77, 77, 77, 0.2);
  background: none;
  border: none;
  cursor: pointer;
}

.carousel-dot {
  width: 18px;
  height: 18px;
  border-radius: 50%;
  background-color: #fff;
  margin: 0 10px;
  box-shadow: 0px 4px 4px rgba(77, 77, 77, 0.2);
  cursor: pointer;
}

.carousel-dot.active {
  background-color: var(--Pink-Mid, #f670ae);
}

.BranchAddress-Box-pc-content-item {
  width: calc(25% - 10px); /* 假设每个项之间有 10px 的间距 */
  margin-bottom: 20px;
}
</style>