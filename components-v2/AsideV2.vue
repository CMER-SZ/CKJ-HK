<script lang="ts" setup>
import { useAppState } from '~/stores/appState'
import { smallPhoneNum, whatsapplink } from '~/assets/js/common'
import { useWindowScroll, useWindowSize } from '@vueuse/core'
const toPageTop = () => {
  window.scrollTo({
    top: 0,
    behavior: 'smooth',
  })
}

const { width, height } = useWindowSize()
const { x, y } = useWindowScroll()
const route = useRoute()
const coupon = ref('https://bit.ly/愛康健長者醫療券預約')
defineProps({
  langType: {
    default: '',
    type: String,
  },
  showDialogBox: {
    default: false,
    type: Boolean,
  },
})
const appState = useAppState()
const navbarLists = []
let navLiBoxBool = ref(false)
let navFormBool = ref(false)
const handleNavFormNav = () => {
  appState.setIsShowForm(true)
  navLiBoxBool.value = false
}
const navFormClose = () => {
  appState.setIsShowForm(false)
}

const toContactUs = () => {
  if (process.client) {
    const el = document.getElementById('contactUsFormNav')
    if (el) {
      el.scrollIntoView({ behavior: 'smooth' })
    }
  }
}
onMounted(() => {
  window.addEventListener('scroll', hiddenPopupAlert)
  // window.addEventListener('scroll', hidePopupAlertNew)
})
const hiddenPopupAlert = () => {
  if (process.client) {
    const popupAlert = document.getElementById('popup-alert-two')
    if (!popupAlert) return // Early exit if popupAlert is not found
    const contactForm = ref<HTMLElement | null>(null)
    contactForm.value = document.querySelector('.contactForm')
    if (!contactForm.value) return // Early exit if contactForm is not found

    const scrollTop =
      document.documentElement.scrollTop || document.body.scrollTop
    const contactFormTop = contactForm.value.offsetTop
    const targetHeight = contactForm.value.offsetHeight
    const windowHeight =
      window.innerHeight || document.documentElement.clientHeight
    const isInView =
      contactFormTop < scrollTop + windowHeight &&
      contactFormTop + targetHeight > scrollTop

    popupAlert.style.display = isInView ? 'none' : 'flex'
  }
}

// const hidePopupAlertNew = () => {
//   const popupAlert = document.getElementById('popup-alert-two')
//   if (!popupAlert) return
//   popupAlert.style.display = 'none'
//   const scrollTop =
//     document.documentElement.scrollTop || document.body.scrollTop
//   console.log(scrollTop,scrollTop > 500, 'scrollTop')
//   if (scrollTop > 500) {
//     popupAlert.style.display = 'flex'
//   } else {
//     popupAlert.style.display = 'none'
//   }
// }

const centerDialogVisible = ref(false)
const handlecopywechatcode = () => {
  if (navigator.clipboard) {
    navigator.clipboard.writeText('ckjhongkong').then(
      function () {
        // ElMessage({
        //   showClose: true,
        //   message: '已複製到剪切板',
        //   type: 'success',
        // })
        _bool.value = true
      },
      function (err) {
        ElMessage({
          showClose: true,
          message: '操作異常，請刷新頁面試試',
          type: 'warning',
        })
      }
    )
  } else {
    alert('Clipboard API is not supported by your browser.')
  }
}

const handleopenwechat = () => {
  window.location.href = 'weixin://'
}

let _bool = ref(false)

let _opacity = ref(1)
let _visibility: any = ref('unset')
let _top = ref('auto')

const changeConfig = () => {
  if (y.value > (width.value * (580 / 1920)) / 2) {
    _opacity.value = 1
    _visibility.value = 'unset'
    _top.value = '20vh'
  } else {
    _opacity.value = 0
    _visibility.value = 'hidden'
    _top.value = '30vh'
  }
}
watch(y, (n, o) => {
  if (width.value > 768) {
    changeConfig()
  }
})
const pathLink = ref('')
const closeAd = ref(false)

const showOrHide = ref(false)
const handleWhatsApp = () => {
  showOrHide.value = !showOrHide.value
}

onMounted(() => {
  if (width.value > 768) {
    changeConfig()
  }
  pathLink.value = route.path
})
</script>
<template>
  <div>
    <div class="mobile-sider d-flex flex-column align-items-end">
      <nuxt-link to="/health-care-voucher" class="vertical-text">
        <span>醫療券</span>專區
      </nuxt-link>
      <div
        id="scrollToTopBtn"
        class="scrollToTopBtn d-flex align-items-center"
        @click="toPageTop"
      >
        <span>回頂端</span>
      </div>
    </div>

    <aside class="d-none d-lg-block">
      <div class="contact-widget">
        <a
          href="https://wa.me/85269338128?text=Hello愛康健,我想查詢牙科服務"
          id="YYDB"
          target="_blank"
          class="contact-button"
        >
          <div class="text d-flex align-items-center">WhatsApp</div>
          <div class="circle">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="46"
              height="46"
              viewBox="0 0 46 46"
              fill="none"
            >
              <path
                d="M0.0135704 45.6131L3.28082 33.4524C0.637183 28.721 -0.203346 23.1896 0.921896 17.8888C2.03358 12.588 5.02971 7.87009 9.35443 4.58926C13.6792 1.30844 19.0478 -0.304865 24.4706 0.0476203C29.8935 0.400106 35.0045 2.69126 38.8683 6.48726C42.7321 10.2968 45.091 15.3672 45.5113 20.7629C45.9316 26.1587 44.386 31.5408 41.1594 35.8927C37.9328 40.2445 33.2285 43.2949 27.9277 44.4743C22.6269 45.6538 17.082 44.8946 12.2963 42.3188L0 45.5996L0.0135704 45.6131ZM12.8928 37.7907L13.652 38.2381C17.1091 40.2852 21.1627 41.1393 25.162 40.6512C29.1614 40.1632 32.8761 38.3736 35.7502 35.5673C38.6243 32.7474 40.4816 29.0734 41.0239 25.0876C41.5662 21.1018 40.7934 17.0618 38.8005 13.5776C36.8076 10.0935 33.703 7.35491 29.9884 5.8094C26.2737 4.26389 22.1523 3.97919 18.2615 5.00953C14.3706 6.03987 10.927 8.33103 8.47321 11.517C6.01937 14.7029 4.69077 18.6073 4.70433 22.6202C4.70433 25.9553 5.62621 29.209 7.37508 32.056L7.84959 32.8423L6.01937 39.6209L12.8928 37.7907Z"
                fill="white"
              />
              <path
                fill-rule="evenodd"
                clip-rule="evenodd"
                d="M31.3494 25.7252C30.902 25.3727 30.3868 25.1152 29.8174 24.9931C29.2616 24.8711 28.6786 24.8711 28.1228 24.9931C27.2823 25.3456 26.74 26.6471 26.1977 27.3114C26.0757 27.4741 25.913 27.5825 25.7232 27.6232C25.5334 27.6639 25.33 27.6368 25.1673 27.5419C22.1034 26.3489 19.5276 24.1526 17.8736 21.3056C17.738 21.1294 17.6703 20.8989 17.6838 20.682C17.7109 20.4515 17.8194 20.2481 17.9821 20.099C18.5921 19.5025 19.026 18.7704 19.27 17.957C19.3242 17.0622 19.1209 16.1674 18.6735 15.3811C18.3346 14.283 17.6838 13.3069 16.8026 12.5612C16.3417 12.3579 15.84 12.2901 15.352 12.3714C14.8639 12.4528 14.403 12.6561 14.0234 12.9951C13.3726 13.5509 12.871 14.2423 12.5321 15.0151C12.1932 15.8014 12.0305 16.6419 12.0576 17.4825C12.0576 17.957 12.1254 18.4315 12.2338 18.8924C12.5321 20.0041 12.993 21.0616 13.6031 22.0377C14.0369 22.7833 14.5114 23.5154 15.0266 24.2068C16.7077 26.498 18.8091 28.4502 21.2222 29.9415C22.4424 30.7007 23.7303 31.3108 25.086 31.7853C26.4959 32.4224 28.0415 32.6665 29.587 32.4902C30.4546 32.3547 31.2952 32.0157 32.0001 31.487C32.7051 30.9583 33.2745 30.2669 33.6541 29.467C33.871 28.9789 33.9388 28.4502 33.8439 27.9215C33.6134 26.8505 32.1764 26.2268 31.3087 25.7117L31.3494 25.7252Z"
                fill="white"
              />
            </svg>
          </div> </a
        ><a
          href="tel:(852) 3892 5049"
          id="PC-contactNumber"
          class="contact-button contact-button-phone contact-Phone"
        >
          <div class="text d-flex align-items-center">熱線查詢</div>
          <div class="circle">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="38"
              height="36"
              viewBox="0 0 38 36"
              fill="none"
            >
              <path
                d="M33.1141 36C32.9488 36 32.7954 36 32.6302 35.9764C24.2627 35.1856 16.4735 31.6682 10.5136 26.0498C4.57727 20.4079 0.871504 13.0072 0.0217731 5.08721C-0.037236 4.44984 0.0217709 3.82426 0.222402 3.21049C0.423033 2.62033 0.76529 2.06557 1.21376 1.59344C1.69763 1.0977 2.28772 0.684588 2.93682 0.413113C3.62133 0.141638 4.32943 0 5.03754 0H11.2099C12.3075 0 13.3578 0.318687 14.243 0.932458C15.1281 1.54623 15.7772 2.39606 16.1312 3.37574L18.1376 9.06492C18.4444 9.93836 18.4798 10.859 18.2556 11.7443C18.0313 12.6295 17.5475 13.4439 16.863 14.0931L15.8952 15.002C17.5003 17.3744 19.6246 19.3692 22.1266 20.88L23.0825 19.9711C23.767 19.322 24.6168 18.8616 25.5727 18.6728C26.505 18.4603 27.4964 18.4957 28.4051 18.7908L34.4004 20.7029C35.439 21.0216 36.3477 21.6472 36.9732 22.497C37.5987 23.3233 37.941 24.3384 37.9646 25.377V31.2197C37.9882 32.459 37.4807 33.663 36.572 34.56C35.6632 35.4571 34.4004 35.9764 33.0904 36H33.1141ZM5.04935 3.29311C4.82511 3.29311 4.60088 3.32852 4.37664 3.41115C4.17601 3.49377 3.97538 3.62361 3.83376 3.78885C3.71574 3.93049 3.60952 4.08393 3.55051 4.23738C3.4915 4.41442 3.4679 4.59147 3.49151 4.76852C4.25863 11.9331 7.59853 18.6256 12.992 23.7128C18.3618 28.8 25.4311 31.9869 32.996 32.7069H33.1141C33.2911 32.7069 33.4799 32.6715 33.6451 32.5889C33.8104 32.5062 33.9638 32.4118 34.0936 32.2938C34.3769 31.9987 34.5421 31.5974 34.5421 31.2079V25.3652C34.5421 25.0348 34.4241 24.6689 34.2234 24.3974C33.9992 24.1259 33.716 23.9016 33.3737 23.8072L27.3784 21.9069C27.0715 21.8125 26.7529 21.7889 26.4224 21.8715C26.092 21.9541 25.8087 22.0839 25.5963 22.3082L24.6404 23.2171C23.9913 23.8308 23.1179 24.1849 22.1856 24.1849C21.5011 24.1849 20.8284 23.9843 20.2619 23.6184C17.3704 21.8597 14.8921 19.5344 13.0274 16.7843C12.6025 16.1469 12.4019 15.4033 12.4845 14.6715C12.5671 13.9161 12.9094 13.2315 13.4758 12.7003L14.4436 11.7679C14.6678 11.5554 14.833 11.2721 14.9039 10.977C14.9865 10.682 14.9629 10.3633 14.8685 10.0918L12.8621 4.40262C12.7441 4.07213 12.5199 3.78885 12.2366 3.5882C11.9298 3.38754 11.5875 3.26951 11.2217 3.26951H5.04935V3.29311ZM36.2533 13.137C35.7931 13.137 35.3564 12.96 35.0377 12.6649C34.7191 12.3462 34.5303 11.9331 34.5303 11.4964C34.5303 9.32459 33.6215 7.23541 31.9811 5.68918C30.3642 4.15475 28.1573 3.28131 25.8441 3.28131C25.3839 3.28131 24.9472 3.10426 24.6049 2.80918C24.2863 2.49049 24.0975 2.07738 24.0975 1.64066C24.0975 1.20393 24.2745 0.790819 24.6049 0.472131C24.9236 0.153442 25.3721 0 25.8441 0C29.066 0 32.1463 1.22754 34.4359 3.37574C36.7018 5.52393 38 8.45115 38 11.5082C38 11.9449 37.823 12.358 37.4925 12.6767C37.1739 12.9954 36.7254 13.1488 36.2533 13.1488V13.1252V13.137ZM29.3257 13.137C28.8654 13.137 28.4405 12.96 28.0865 12.6649C27.7678 12.3462 27.579 11.9331 27.579 11.4964C27.579 11.0597 27.3902 10.6466 27.0715 10.3279C26.7529 10.0092 26.3044 9.85574 25.8323 9.85574C25.3603 9.85574 24.9354 9.67869 24.5931 9.38361C24.2745 9.06492 24.0857 8.6518 24.0857 8.21508C24.0857 7.77836 24.2627 7.36525 24.5931 7.04656C24.9118 6.72787 25.3603 6.57443 25.8323 6.57443C27.2132 6.57443 28.5231 7.08197 29.5145 8.01443C30.4822 8.94688 31.0369 10.1862 31.0369 11.5082C31.0369 11.7207 31.0015 11.9449 30.8953 12.1338C30.8127 12.3344 30.6711 12.5115 30.5059 12.6649C30.3406 12.8184 30.1636 12.9364 29.9394 13.019C29.7387 13.1016 29.4909 13.137 29.2667 13.137L29.3021 13.1134L29.3257 13.137Z"
                fill="white"
              />
            </svg>
          </div> </a
        ><a
          href="#contactUsFormNav"
          id="PC-makeAppointment"
          class="contact-button contact-button-number"
        >
          <div class="text d-flex align-items-center">預約表格</div>
          <div class="circle">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="40"
              height="36"
              viewBox="0 0 40 36"
              fill="none"
            >
              <path
                d="M10.8891 0.0325865C10.7913 0.0108613 10.6827 0 10.5849 0C9.99836 0 9.46609 0.39107 9.32488 0.966789C8.92296 2.61791 8.92296 4.35591 9.32488 6.00703C9.46609 6.58275 9.99836 6.97382 10.5849 6.97382C10.6827 6.97382 10.7913 6.96295 10.8891 6.94123C11.5843 6.77829 12.0079 6.09392 11.845 5.42044C11.53 4.16037 11.53 2.82428 11.845 1.56422C12.0079 0.879875 11.5843 0.206399 10.8891 0.0434598V0.0325865Z"
                fill="white"
              />
              <path
                d="M29.0063 0.0325865C28.9085 0.0108613 28.7999 0 28.7021 0C28.1155 0 27.5833 0.39107 27.4421 0.966789C27.0401 2.61791 27.0401 4.35591 27.4421 6.00703C27.5833 6.58275 28.1155 6.97382 28.7021 6.97382C28.7999 6.97382 28.9085 6.96295 29.0063 6.94123C29.7015 6.77829 30.136 6.09392 29.9622 5.42044C29.658 4.16037 29.658 2.82428 29.9622 1.56422C30.1251 0.879875 29.7015 0.206399 29.0063 0.0434598V0.0325865Z"
                fill="white"
              />
              <path
                d="M34.6626 3.45508H31.3061C31.3387 3.82441 31.3821 4.1829 31.469 4.5305C31.6428 5.32347 31.5233 6.149 31.1323 6.84421C30.7304 7.53942 30.1112 8.02826 29.3725 8.22378C29.1553 8.2781 28.9272 8.31067 28.7099 8.31067C27.3847 8.31067 26.2441 7.34389 25.9399 5.96434C25.7553 5.13878 25.6466 4.30236 25.6141 3.45508H13.1981C13.2307 3.82441 13.2741 4.1829 13.361 4.5305C13.5348 5.32347 13.4153 6.149 13.0243 6.84421C12.6224 7.53942 12.0032 8.02826 11.2645 8.22378C11.0473 8.2781 10.8192 8.31067 10.5911 8.31067C9.26581 8.31067 8.12524 7.34389 7.82108 5.96434C7.63642 5.13878 7.5278 4.30236 7.49522 3.45508H4.36678C1.95528 3.45508 0 5.49728 0 7.99568V31.2308C0 33.7292 1.95528 35.7714 4.35592 35.7714H34.6735C37.0741 35.7714 39.0294 33.7401 39.0294 31.2308V7.99568C39.0294 5.49728 37.0741 3.45508 34.6735 3.45508H34.6626ZM36.4332 31.2308C36.4332 32.1976 35.6403 32.9905 34.6626 32.9905H4.34505C3.36741 32.9905 2.57445 32.2084 2.57445 31.2308V12.0692H36.4224V31.2308H36.4332Z"
                fill="white"
              />
              <path
                d="M25.196 17.3587C22.0568 14.2086 16.9622 14.2086 13.8229 17.3587C10.6945 20.5089 10.6945 25.636 13.8229 28.7862C16.9622 31.9363 22.0568 31.9363 25.196 28.7862C28.3245 25.636 28.3245 20.5089 25.196 17.3587ZM23.9469 21.4213L19.7647 26.4507V26.4616C19.7647 26.4616 19.743 26.4724 19.743 26.4833C19.7213 26.505 19.7104 26.5268 19.6887 26.5485C19.6887 26.5485 19.6887 26.5485 19.6778 26.5594C19.667 26.5702 19.6453 26.5919 19.6344 26.6028C19.6127 26.6245 19.5909 26.6354 19.5692 26.6571C19.5584 26.668 19.5366 26.6788 19.5149 26.6897C19.4932 26.7006 19.4715 26.7223 19.4497 26.7332C19.4389 26.744 19.4171 26.7549 19.3954 26.7657C19.3737 26.7766 19.352 26.7983 19.3194 26.7983C19.3085 26.7983 19.2868 26.82 19.2651 26.82C19.2433 26.8309 19.2107 26.8418 19.189 26.8526C19.1782 26.8526 19.1564 26.8635 19.1456 26.8635C19.113 26.8635 19.0913 26.8852 19.0587 26.8852C19.0478 26.8852 19.0261 26.8852 19.0152 26.8961C18.9826 26.8961 18.95 26.8961 18.9175 26.9069C18.9066 26.9069 18.8957 26.9069 18.8849 26.9069C18.8414 26.9069 18.798 26.9069 18.7437 26.9069C18.7002 26.9069 18.6676 26.9069 18.6242 26.9069C18.6133 26.9069 18.6024 26.9069 18.5916 26.9069C18.559 26.9069 18.5373 26.907 18.5047 26.8961C18.4938 26.8961 18.4721 26.8961 18.4612 26.8961C18.4395 26.8961 18.4069 26.8852 18.3852 26.8743C18.3743 26.8743 18.3526 26.8744 18.3417 26.8635C18.32 26.8635 18.2983 26.8526 18.2766 26.8418C18.2548 26.8418 18.244 26.8309 18.2223 26.82C18.2005 26.82 18.1788 26.7983 18.1571 26.7875C18.1462 26.7875 18.1245 26.7766 18.1028 26.7657C18.081 26.7549 18.0702 26.744 18.0484 26.7332C18.0376 26.7223 18.0159 26.7114 17.9941 26.7006C17.9724 26.6897 17.9616 26.6788 17.9398 26.6571C17.929 26.6462 17.9072 26.6354 17.8964 26.6245C17.8964 26.6245 17.8746 26.5919 17.8638 26.5811C17.8529 26.5702 17.8312 26.5485 17.8095 26.5376L15.1699 23.8871C14.6485 23.3657 14.6485 22.5076 15.1699 21.9862C15.6913 21.4648 16.5385 21.4539 17.0599 21.9862L18.6567 23.5938L21.9155 19.6833C22.3935 19.1076 23.2299 19.0424 23.7948 19.5204C24.3596 19.9983 24.4357 20.8456 23.9577 21.4104L23.9469 21.4213Z"
                fill="white"
              />
            </svg>
          </div>
        </a>
      </div>
    </aside>

    <div class="navbar-content-mb">
      <div class="navbar-content-mb-in">
        <div
          @click="handleWhatsApp"
          class="navbar-whatsApp"
          :class="[showOrHide ? 'navbar-whatsApp-open' : '']"
        >
          <img src="@/assets/images/icon_65.svg" alt="" />
          <span>WhatsApp</span>
        </div>
        <div
          :class="[
            showOrHide
              ? 'navbar-content-whatsApp'
              : 'hide-navbar-content-whatsApp',
          ]"
        >
          <nuxt-link class="whatsApp-coupon" id="navMbWhatsapp" :to="coupon">
            <span>醫療券專線</span>
          </nuxt-link>
          <nuxt-link
            class="whatsApp-normal"
            id="navMbWhatsapp"
            :to="whatsapplink"
          >
            <span>一般諮詢</span>
          </nuxt-link>
          <nuxt-link
            class="whatsApp-normal"
            id="navMbWhatsapp"
            :to="'https://api.whatsapp.com/send/?phone=85269338128&text=立即領取2000元種植牙現金券'"
          >
            <span>種牙現金券</span>
          </nuxt-link>
          <nuxt-link
            class="whatsApp-normal"
            id="navMbWhatsapp"
            :to="'https://api.whatsapp.com/send/?phone=85269338128&text=Hello愛康健,想預約超聲波洗牙'"
          >
            <span>預約洗牙</span>
          </nuxt-link>
        </div>
      </div>
      <nuxt-link
        class="navbar-content-mb-in"
        id="navMbTel"
        :to="`tel: +852 ${smallPhoneNum}`"
      >
        <img src="@/assets/images/icon_64.svg" alt="" />
        <div class="navbar-content-mb-in-top">
          <span>立即致電查詢</span>
          <span>{{ smallPhoneNum }}</span>
        </div>
      </nuxt-link>
      <div
        class="navbar-content-mb-in navMbContactFormBtn"
        id="navMbContactFormBtn"
        @click="toContactUs"
      >
        <img
          class="navMbContactFormBtn"
          src="@/assets/images/icon_66.svg"
          alt=""
        />
        <span class="navMbContactFormBtn">預約表格</span>
      </div>
    </div>
  </div>
</template>


<style lang="scss" scope>
// 手机侧边样式
.mobile-sider {
  position: fixed;
  z-index: 920;
  right: 0;
  bottom: 70px;

  span {
    writing-mode: vertical-rl;
    /* 文字竖排，从右到左 */
    text-orientation: upright;
    /* 文字方向朝上 */
    white-space: nowrap;
    /* 防止文字换行 */
    cursor: pointer;
  }

  .vertical-text {
    border-top-left-radius: 5px;
    border-bottom-left-radius: 5px;
    writing-mode: vertical-rl;
    /* 文字竖排，从右到左 */
    text-orientation: upright;
    /* 文字方向朝上 */
    white-space: nowrap;
    /* 防止文字换行 */

    padding: 4px 1px;
    background: var(--GHV-Green, #01a853);
    color: var(--White, #fff);
    font-family: 'Noto Sans HK';
    font-size: 20px;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
    letter-spacing: 2px;
    transition: box-shadow 0.3s ease;

    &:hover {
      box-shadow: 0 0 10px 5px rgba(0, 136, 67, 0.5);
    }

    span {
      font-size: 24px;
      font-weight: 700;
      letter-spacing: 2.4px;
    }
  }

  .scrollToTopBtn {
    margin-top: 9px;
    border-top-left-radius: 5px;
    border-bottom-left-radius: 5px;
    padding: 4px 3px;
    width: fit-content;
    background-color: white;
    box-shadow: 0px 0px 10px 5px rgba(77, 77, 77, 0.2);
    color: var(--New-Theme-Color, #d2337d);
    text-align: center;
    font-family: 'Noto Sans HK';
    font-size: 16px;
    font-style: normal;
    font-weight: 700;
    line-height: normal;
    letter-spacing: 1.6px;
    transition: box-shadow 0.3s ease;

    &:hover {
      box-shadow: 0px 0px 15px 10px rgba(77, 77, 77, 0.2);
    }
  }
}

// pc侧边栏
.contact-widget {
  position: fixed;
  right: 37px;
  // right: clamp(50px, 9.79vw, 188px);
  top: 341px;
  z-index: 120;
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  gap: 20px;

  .contact-button {
    position: relative;
    cursor: pointer;
    display: inline-flex;
    align-items: center;
    overflow: hidden;
    background: var(--New-Theme-Color, #d2337d);
    border-radius: 69px;
    transition: all 0.3s ease;
    width: 69px;
    height: 69px;
    box-shadow: 0px 0px 15px rgba(0, 0, 0, 0.3);

    .text {
      position: absolute;
      top: 0;
      right: 100px;
      width: 0;
      height: 100%;
      text-align: left;
      border-radius: 100px;
      border: 3px solid var(--New-Theme-Color, #d2337d);
      background: var(--Pink-Pale, #ffe9ec);
      color: var(--New-Theme-Color, #d2337d);
      white-space: nowrap;
      overflow: hidden;
      transition: all 0.3s ease;
      padding-right: 10px;
      padding-left: 20px;
      box-sizing: border-box;
      line-height: normal;
      font-size: 24px;
      font-style: normal;
      font-weight: 700;
    }

    .circle {
      position: absolute;
      right: 0;
      width: 69px;
      height: 69px;
      background: var(--New-Theme-Color, #d2337d);
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      transition: all 0.3s ease;

      svg {
        width: 38px;
      }
    }

    &:hover {
      width: 206px;

      .text {
        width: 206px;
        height: 69px;
        right: 0;
      }
    }
  }

  & > .contact-button:nth-child(1):hover {
    width: 216px;

    .text {
      width: 216px;
      padding-left: 16px;
    }
  }
  & > .contact-button:nth-child(1) {
    background: var(--GHV-Green, #01a853);
    .text {
      border: 3px solid var(--GHV-Green, #01a853);

      border-radius: 100px;
      background: white !important;
      color: var(--GHV-Green, #01a853);
    }
    & > .circle {
      background: var(--GHV-Green, #01a853);

      svg {
        width: 46px;
      }
    }
  }
}

@media screen and (min-width: 960px) {
  // 侧边栏
  .mobile-sider {
    position: fixed;
    z-index: 920;
    right: 0;
    top: 600px;
    bottom: auto;

    span {
      writing-mode: vertical-rl;
      /* 文字竖排，从右到左 */
      text-orientation: upright;
      /* 文字方向朝上 */
      white-space: nowrap;
      /* 防止文字换行 */
      cursor: pointer;
    }

    .vertical-text {
      border-top-left-radius: 10px;
      border-bottom-left-radius: 10px;
      padding: 10px 10px;
      font-size: 24px;
      font-style: normal;
      font-weight: 500;
      line-height: normal;
      letter-spacing: 2.4px;

      span {
        font-size: 30px;
        font-weight: 700;
        letter-spacing: 3px;
      }
    }

    .scrollToTopBtn {
      margin-top: 15px;
      border-top-left-radius: 10px;
      border-bottom-left-radius: 10px;
      padding: 10px;
      width: fit-content;
      box-shadow: 0px 0px 10px 5px rgba(77, 77, 77, 0.2);
      font-size: 24px;
      font-weight: 700;
      letter-spacing: 2.4px;
    }
  }
}

@keyframes whatAppIconAnim {
  0% {
    transform: rotate(0deg);
  }
  5% {
    transform: rotate(-10deg);
  }
  10% {
    transform: rotate(10deg);
  }
  15% {
    transform: rotate(-10deg);
  }
  20% {
    transform: rotate(10deg);
  }
  25% {
    transform: rotate(-10deg);
  }
  30% {
    transform: rotate(10deg);
  }
  35% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(0deg);
  }
}
@keyframes btntestafterAnima {
  0% {
    width: 90%;
    height: 90%;
    border: 10px solid #86f99b;
  }
  19% {
    border: 8px solid rgba(134, 249, 155, 0.5);
    width: calc(100% + 32px);
    height: calc(100% + 32px);
  }
  24% {
    width: calc(100% + 32px);
    height: calc(100% + 32px);
  }
  29% {
    border: 0 solid rgba(134, 249, 155, 0);
    width: calc(100% + 32px);
    height: calc(100% + 32px);
  }
  100% {
    border: 0 solid rgba(134, 249, 155, 0);
    width: calc(100% + 32px);
    height: calc(100% + 32px);
  }
}
@keyframes btntestafterAnimaHover {
  0% {
    width: 90%;
    height: 90%;
    border: 10px solid #86f99b;
  }
  19% {
    border: 10px solid rgba(134, 249, 155, 0.5);
    width: calc(100% + 40px);
    height: calc(100% + 40px);
  }
  24% {
    width: calc(100% + 40px);
    height: calc(100% + 40px);
  }
  29% {
    border: 0 solid rgba(134, 249, 155, 0);
    width: calc(100% + 40px);
    height: calc(100% + 40px);
  }
  100% {
    border: 0 solid rgba(134, 249, 155, 0);
    width: calc(100% + 40px);
    height: calc(100% + 40px);
  }
}
@keyframes animLeftIn {
  from {
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}
@keyframes animTopIn {
  to {
    transform: translateX(-50%);
    opacity: 1;
  }
}
@keyframes iconTopIn {
  20% {
    transform: translateY(7px);
    opacity: 1;
  }
  40% {
    transform: translateY(-3px);
  }
  60% {
    transform: translateY(2px);
  }
  80% {
    transform: translateY(-1px);
  }
  100% {
    transform: none;
    opacity: 1;
  }
}
@keyframes iconBottomIn {
  20% {
    transform: translateY(-7px);
    opacity: 1;
  }
  40% {
    transform: translateY(3px);
  }
  60% {
    transform: translateY(-2px);
  }
  80% {
    transform: translateY(1px);
  }
  100% {
    transform: none;
    opacity: 1;
  }
}
.navbar-content {
  width: 66px;
  position: fixed;
  right: 4.5vw;
  top: 30vh;
  z-index: 50;
  transition: all 1s;
  &-in {
    width: 66px;
    height: 66px;
    margin-bottom: 13px;
    cursor: pointer;
    background: var(--indexColor1);
    border-radius: 33px;
    display: flex;
    justify-content: center;
    align-items: center;
    transition: all 0.3s;
    position: relative;
    .navbarBox {
      position: absolute;
      top: 0;
      right: 66px;
      padding-right: 10px;
      display: none;
      opacity: 0;
      transform: translateX(-20px);
      &::after {
        content: '';
        position: absolute;
        right: -20px;
        top: 23px;
        width: 0;
        height: 0;
        border-top: 10px solid;
        border-left: 20px solid;
        border-bottom: 10px solid;
        border-right: 20px solid;
        border-color: transparent transparent transparent var(--indexColor1);
      }
      &-in {
        transition: all 0.5s;
        background: var(--indexColor1);
        height: 100%;
        padding: 20px;
        justify-content: center;
        align-items: center;
        border-radius: 10px;
        color: #fff;
        .tel {
          white-space: nowrap;
          font-size: 20px;
          font-weight: 600;
        }
        .weChat {
          width: 200px;
          background: var(--indexColor3);
          img {
            width: 100%;
          }
        }
      }
    }
    img {
      width: 40px;
    }
    &:hover {
      background: var(--indexColor3);
      .navbarBox {
        display: flex;
        animation: animLeftIn 1s forwards;
      }
    }
  }
  &-whatApp {
    margin-left: calc(132px - 200px);
    width: 200px;
    position: relative;
    margin-bottom: 30px;
    display: block;
    transition: all 0.3s;
    &-icon {
      position: relative;
      width: 95%;
      &-in {
        width: 100%;
      }
      &-right {
        position: absolute;
        width: calc(51 / 197 * 100%);
        right: 10px;
        bottom: 10px;
        animation: whatAppIconAnim 5s infinite;
        transform-origin: bottom center;
      }
    }
    &-btn {
      display: flex;
      height: 44px;
      margin-top: -25px;
      background: var(--indexColor1);
      border-radius: 50px;
      align-items: center;
      justify-content: center;
      position: relative;
      z-index: 1;
      &-text {
        color: #fff;
        line-height: 1;
        font-size: 23px;
        font-weight: 600;
      }
      &-img {
        width: 66px;
        height: 66px;
        margin: 0 5px;
        position: relative;
        transition: all 0.3s;
        &-in {
          width: 100%;
          height: 100%;
          position: relative;
          z-index: 1;
          background: #32d851;
          border-radius: 50%;
          display: flex;
          justify-content: center;
          align-items: center;
          box-shadow: 0 0 5px rgba(0, 0, 0, 0.25);
        }
        img {
          width: 60%;
          width: 60%;
        }
        &::after {
          content: '';
          position: absolute;
          display: inline-block;
          left: 50%;
          top: 50%;
          transform: translate(-50%, -50%);
          -webkit-transform: translate(-50%, -50%);
          width: 100%;
          height: 100%;
          // border: 10px solid #86F99B;
          z-index: 0;
          border-radius: 70px;
          animation: btntestafterAnima 5.6s infinite;
          transition: all 0.5s;
        }
      }
    }
    &:hover {
      transform: scale(1.08) translateY(-10px);
      .navbar-content-whatApp-btn {
        &-img {
          &::after {
            animation: btntestafterAnimaHover 4s infinite;
          }
        }
      }
    }
    .iconDialogBox {
      position: absolute;
      bottom: 100%;
      left: 50%;
      transform: translateX(-50%);
      color: #fff;
      width: 220px;
      font-size: 22px;
      text-align: center;
      opacity: 0;
      transform: translate(-50%, 20px);
      animation: animTopIn 1s forwards;
      padding-bottom: 20px;
      & > span {
        border-radius: 12px;
        background: var(--indexColor1);
        padding: 20px;
        display: inline-block;
      }
      &-icon {
        position: absolute;
        opacity: 0;
        &[data-ord='1'] {
          left: 60%;
          top: -30px;
          transform: translateY(-40px);
          animation: iconTopIn 2s 0.5s forwards;
        }
        &[data-ord='2'] {
          bottom: 15px;
          left: -15px;
          transform: translateY(40px);
          animation: iconBottomIn 2s 0.5s forwards;
        }
        &[data-ord='3'] {
          bottom: 45px;
          right: 10px;
          transform: translateY(40px);
          animation: iconBottomIn 2s 0.5s forwards;
        }
      }
      &::after {
        content: '';
        position: absolute;
        bottom: 7px;
        left: 50%;
        transform: translateX(-50%);
        width: 0;
        height: 0;
        border-top: 15px solid;
        border-left: 10px solid;
        border-bottom: 0 solid;
        border-right: 10px solid;
        border-color: var(--indexColor1) transparent transparent transparent;
      }
    }
  }
  #navPcTel {
    background-image: url(@/assets/images/navIcon_1.png);
    background-repeat: no-repeat;
    background-position: 43% 57%;
  }
  #navPcWeChat {
    background-image: url(@/assets/images/navIcon_3.png);
    background-repeat: no-repeat;
    background-position: 50%;
  }
  // #navPcWhatsapp{
  //   background-image:url(@/assets/images/navIcon_2.png);
  //   background-repeat: no-repeat;
  //   background-position: 50%;
  // }
  #navPcFaceBook {
    background-image: url(@/assets/images/navIcon_6.png);
  }
  #navPcContactForm {
    background-image: url(@/assets/images/navIcon_5.png);
    background-repeat: no-repeat;
    background-position: 50%;
  }
  &-mb {
    display: none;
  }
  .navForm {
    width: 100vw;
    height: 100vh;
    position: fixed;
    bottom: -100%;
    left: 0;
    overflow: hidden;
    overflow-y: auto;
    background: #fff;
    display: flex;
    justify-content: center;
    z-index: 9999;
    transition: all 0.5s;
    display: none;
    padding: 50px 0;
    &-icon {
      position: absolute;
      right: 30px;
      top: 150px;
      cursor: pointer;
    }
    .qdCode {
      display: flex;
      align-items: center;
      justify-content: center;
      width: 100%;
      height: 100%;
    }
  }
}
.dialogBox {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 999;
  background: rgba(0, 0, 0, 0.3);
  opacity: 0;
  display: none;
  &.show {
    display: block;
    animation: contentIn 1s forwards;
  }
  &-in {
    position: absolute;
    left: 50%;
    top: 0;
    transform: translate(-50%, -50%);
    width: calc(100% - 60px);
    height: auto;
    max-width: 768px;
    z-index: 1000;
    opacity: 0;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    background: #fff;
    padding: 10px 30px 15px;
    border-radius: 10px;
    &.show-in {
      animation: topIn 0.7s ease-out forwards;
    }
    .title {
      font-size: 20px;
      font-weight: 600;
      text-align: center;
    }
    .content {
      font-size: 16px;
      margin: 10px 0 20px;
    }
    .btn {
      display: flex;
      justify-content: center;
    }
  }
}
@keyframes contentIn {
  to {
    opacity: 1;
  }
}
@keyframes topIn {
  50% {
    top: 52%;
  }
  75% {
    top: 49%;
  }
  100% {
    top: 50%;
    opacity: 1;
  }
}
@media (min-width: 768px) and (max-width: 1800px) {
  .navbar-content {
    width: 50px;
    &-in {
      width: 50px;
      height: 50px;
      .navbarBox {
        right: 50px;
        &::after {
          top: 15px;
        }
        &-in {
          padding: 10px;
        }
      }
      img {
        width: 30px;
      }
    }
    &-whatApp {
      margin-left: calc(100px - 150px);
      width: 150px;
      margin-bottom: 20px;
      &-btn {
        margin-top: -20px;
        height: 35px;
        &-text {
          font-size: 16px;
        }
        &-img {
          width: 50px;
          height: 50px;
        }
      }
      .iconDialogBox {
        font-size: 16px;
        width: 170px;
        & > span {
          padding: 15px;
          border-radius: 8px;
        }
        &-icon {
          &[data-ord='1'] {
            width: 40px;
            left: 55%;
            top: -20px;
            transform: translateY(-30px);
          }
          &[data-ord='2'] {
            width: 40px;
            left: -10px;
          }
          &[data-ord='3'] {
            bottom: 30px;
            right: 10px;
            transform: translateY(30px);
          }
        }
      }
    }
    #navPcTel {
      background-size: 60% auto;
    }
    #navPcWeChat {
      background-size: 60% auto;
    }
    #navPcWhatsapp {
      background-size: 60% auto;
    }
    #navPcFaceBook {
      background-size: 100%;
    }
    #navPcContactForm {
      background-size: 60% auto;
    }
  }
}
@media screen and (max-width: 768px) {
  .navbar-content {
    top: auto;
    bottom: 0;
    left: 0;
    width: 100%;
    // background: var(--indexColor3);
    // box-shadow: 0px -1.5px 0px rgba(255, 204, 199, 0.25);
    z-index: 20;
    &-in {
      position: absolute;
      right: 30px;
      top: -164px;
      width: 34px;
      height: 34px;
      background: var(--indexColor3);
      border-radius: 50%;
      display: flex;
      justify-content: center;
      align-items: center;
      display: none;
      img {
        width: 24px;
      }
      &:nth-of-type(4) {
        display: flex;
      }
      &.pageTop {
        display: block;
        width: 40px;
        height: auto;
        background: none;
        right: 12px;
        top: auto;
        bottom: 80px;
        img {
          width: 100%;
          // background-clip: text;
          // mix-blend-mode: difference;
          // box-shadow:2px 2px 0 #fff;
          // filter: drop-shadow(1px 1px 0 #fff)
          // drop-shadow(-1px 1px 0 #fff)
          // drop-shadow(1px -1px 0 #fff)
          // drop-shadow(-1px -1px 0 #fff);
        }
      }
    }
    &-whatApp {
      display: none;
    }
    &-mb {
      z-index: 98;
      width: 100%;
      height: auto;
      background: #fff;
      filter: drop-shadow(0 -3px 5px rgba(252, 22, 130, 0.3));
      position: fixed;
      bottom: 0;
      left: 0;
      display: flex;
      // justify-content: center;
      // justify-content: space-between;
      padding-bottom: constant(safe-area-inset-bottom);
      padding-bottom: env(safe-area-inset-bottom);
      // border-: ;
      .mbcc-boxInAA {
        flex: 1;
        height: 60px;
        &-1 {
          background: url(https://static.cmereye.com/imgs/2023/07/ac801f63f6e35840.png)
            no-repeat;
          background-position: center center;
          animation: fromRight 1s none;
        }
        &-2 {
          background: url(https://static.cmereye.com/imgs/2023/07/c631714e6eab7b74.png)
            no-repeat;
          background-position: center center;
          animation: fromRight 1s none;
        }
        &-3 {
          width: 103px;
          height: 103px;
          min-width: 103px;
          max-width: 103px;
          background: #fff;
          box-shadow: 0px 3px 8px rgba(0, 0, 0, 0.25);
          border-radius: 50%;
          display: flex;
          justify-content: center;
          align-items: center;
          flex-direction: column;
          margin: -30px 10px -10px;
          animation: mbIn3Anim 1s 1s none;
          opacity: 0;
          animation-fill-mode: forwards;
          img {
            width: 28px;
            margin-bottom: 5px;
          }
          span {
            color: #6b6b6b;
            text-align: center;
            font-size: 12.376px;
            font-style: normal;
            font-weight: 600;
            line-height: 1.6;
            letter-spacing: 3.094px;
            &.english {
              line-height: 1;
            }
          }
        }
        &-4 {
          background: url(https://static.cmereye.com/imgs/2023/07/d1ec7e5ab5a240b6.png)
            no-repeat;
          background-position: center center;
          animation: fromLeft 1s none;
        }
        &-5 {
          background: url(https://static.cmereye.com/imgs/2023/07/d067e48cd2a6f7a4.png)
            no-repeat;
          background-position: center center;
          animation: fromLeft 1s none;
        }
      }
      display: flex;
      &-in {
        display: flex;
        // flex-direction: column;
        flex: 1;
        gap: 0 5px;
        justify-content: center;
        align-items: center;
        background: var(--indexColor1);
        color: #fff;
        // margin-top: 10px;
        font-size: 14px;
        line-height: 130%;
        padding: 8px 0 8px;
        &-top {
          display: flex;
          flex-direction: column;
          white-space: nowrap;
          align-items: center;
          color: var(--indexColor1);
          line-height: 130%;
          & > span {
            margin-left: 0px;
          }
          & > span:nth-child(2) {
            color: var(--Grey-Deep, #4d4d4d);
            font-family: 'FakePearl-Regular';
            font-size: 15px;
            font-style: normal;
            font-weight: 600;
            line-height: 130%; /* 24px */
          }
        }
        &-center {
          color: var(--textColor);
        }
        &:nth-child(2) {
          flex: 1.5;
          background: #fff;
          justify-content: flex-start;
          padding-left: 10px;
        }
        &:nth-child(1) {
          position: relative;
          & > div:nth-child(1) {
            display: flex;
            gap: 0 1vw;
            width: 100%;
            box-sizing: border-box;
            padding: 8px 0 8px;
            justify-content: center;
            align-items: flex-end;
          }
        }
      }
      .navbar-whatsApp::before {
        content: '';
        display: inline-block;
        position: absolute;
        top: 10px;
        left: 50%;
        transform: translateX(-50%) rotate(-180deg);
        background: url('https://static.cmereye.com/imgs/2024/10/de9383afa6ddf7b3.png')
          no-repeat;
        width: 10px;
        height: 6px;
        background-size: cover;
        transition: all 0.1s;
      }
      .navbar-whatsApp-open::before {
        transform: translateX(-50%) rotate(0deg);
        transition: all 0.1s;
      }
      .navbar-content-whatsApp {
        display: flex;
        position: absolute;
        left: 0;
        bottom: 110%;
        transition: all 0.1s;
        flex-direction: column;
        background: transparent;
        width: 100%;
        gap: 3px 0;
        opacity: 1;
        z-index: 5;
        box-shadow: none;
        .whatsApp-coupon {
          border-radius: var(--Count, 0px) 5px 5px var(--Count, 0px);
          border: 1px solid var(--White, #fff);
          background: var(---Green, #00a752);
          color: var(--White, #fff);
          text-align: center;
          font-family: 'FakePearl-Regular';
          font-size: 15px;
          font-style: normal;
          font-weight: 400;
          line-height: 280%; /* 24px */
          letter-spacing: 1.5px;
        }
        .whatsApp-normal {
          border-radius: var(--Count, 0px) 5px 5px var(--Count, 0px);
          border: 1px solid var(--White, #fff);
          background: var(--Pink-Mid, #fdd3e3);
          color: var(--Grey-Deep, #4d4d4d);
          text-align: center;
          -webkit-text-stroke-width: 1;
          -webkit-text-stroke-color: var(--White, #fff);
          font-family: 'FakePearl-Regular';
          font-size: 15px;
          font-style: normal;
          font-weight: 400;
          line-height: 280%; /* 24px */
          letter-spacing: 1.5px;
        }
      }
      .hide-navbar-content-whatsApp {
        // display: none;
        position: absolute;
        left: 0;
        bottom: 110%;
        z-index: -1;
        opacity: 0;
        height: 0;
        transition: all 0s;
      }
      & > a:nth-child(2) {
        position: relative;
      }
      & > a:nth-child(2)::after {
        content: '';
        background: url('https://static.cmereye.com/imgs/2024/07/435b0baf462e8715.gif')
          no-repeat;
        filter: drop-shadow(0 -3px 5px rgba(252, 22, 130, 0.3));
        position: absolute;
        bottom: 0;
        right: -10px;
        width: 64px;
        height: 59px;
        background-position: bottom center;
        background-size: cover;
        z-index: 4;
      }
    }
    .navForm {
      display: flex;
    }
  }
  @keyframes mbIn3Anim {
    0% {
      opacity: 0;
      transform: translateY(100%) scale(1);
    }
    30% {
      transform: translateY(-30px) scale(1.3);
      opacity: 1;
    }
    60% {
      transform: translateY(0px) scale(1);
      opacity: 1;
    }
    80% {
      transform: translateY(-5px) scale(1.07);
      opacity: 1;
    }
    100% {
      opacity: 1;
      transform: translateY(0) scale(1);
    }
  }
  @keyframes fromRight {
    from {
      opacity: 0;
      transform: translateX(20px);
    }
    to {
      opacity: 1;
      transform: translateX(0);
    }
  }
  @keyframes fromLeft {
    from {
      opacity: 0;
      transform: translateX(-20px);
    }
    to {
      opacity: 1;
      transform: translateX(0);
    }
  }
  // .is_new_tooth_wiki {
  //   position: relative;
  //   bottom: 70px !important;
  //   left: 50%;
  //   transform: translateX(-50%);
  //   width: 100vw;
  //   // background: #fff;
  //   filter: drop-shadow(0 -3px 5px rgba(252, 22, 130, 0.3));
  //   & > div:nth-child(1) {
  //     display: flex;
  //     justify-content: center;
  //   }
  //   & > div:nth-child(2) {
  //     position: absolute;
  //     top: 15px;
  //     right: 15%;
  //   }
  // }
}
</style>