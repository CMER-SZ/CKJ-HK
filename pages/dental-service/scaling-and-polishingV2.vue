<script lang="ts" setup>
import { useAppState } from '~/stores/appState'
import { Autoplay } from 'swiper'
import { toWhatsApp } from '~/assets/js/common'
import { useElementBounding, useWindowSize } from '@vueuse/core'
const appState = useAppState()
appState.setDentistryService('scaling-and-polishing-test')
useHead({
  title: '洗牙',
  meta: [
    {
      hid: 'description',
      name: 'description',
      content:
        '愛康健超聲波洗牙88元，定期進行洗牙可以有效去除牙齒上的牙石和牙菌膜，防止牙齒變色,香港熱線: 6933 8128免費預約掛號,羅湖福田深圳灣口岸分店',
    },
    {
      hid: 'Keywords',
      name: 'Keywords',
      content:
        '愛康健 爱康健 CKJ aikangjian 牙科服務 內地牙科 深圳牙科 深圳睇牙 深圳整牙 愛康健洗牙 免費洗牙 深圳愛康健口腔醫院 愛康健齒科集團 美容牙科 醫療券 長者醫療券大灣區試點 洗牙步驟 無痛洗牙 牙醫 牙医 深圳洗牙 羅湖洗牙 福田洗牙 朱咪咪 掛號預約 收費價目表 洗牙 洗牙費用 洗牙服務 洗牙幾錢 洗牙價錢 深層洗牙 定期洗牙 洗牙推薦 牙齒清潔 清除牙石 牙菌膜 牙石 牙漬 口臭 線上預約 拋光 噴砂洗牙 琺瑯質 敏感牙齒 洗牙幾多錢',
    },
  ],
})

const headerConfig = {
  img: 'https://static.ckjhk.com/ckj-image/6bf140c3e89b.webp',
  mbImg: 'https://static.ckjhk.com/ckj-image/531d4b81b839.webp',
  bg: '',
  pageName: 'scaling-and-polishing-test',
  pcText: [
    '定期洗牙，全方位清潔口腔盲點',
    '愛牙愛己，愛康健細心守護您牙齒健康',
  ],
  mbText: ['定期洗牙', '全方位清潔口腔盲點'],
  linkBtn: `https://wa.me/85269338128?text=Hello愛康健我想預約洗牙`,
}

const orthodonticsIntroduceData = {
  title: '洗牙服務',
  content:
    '提供洗牙和深層洗牙服務，定期洗牙有效去除\n牙齒上的牙垢、牙菌膜和牙結石，更能預防牙\n周病或其他口腔問題。\n\n建議每半年至一年進行一次洗牙，為您的口腔\n健康護航。',
  mbImg: 'https://static.cmereye.com/imgs/2023/10/6caab98f1d6e048f.jpg',
  pcImg: 'https://static.cmereye.com/imgs/2023/10/cc2d7e8addcc8f94.jpg',
  tabNavName: 'pages.dental-service.scaling-and-polishing.introduce.tabNavName',
  pageName: 'scaling-and-polishing-test',
}

const introduceJY = {
  title: '洗牙服務',
  content:
    '提供洗牙和深層洗牙服務，定期洗牙有效去除牙齒上的牙垢、牙菌膜和牙結石，更能預防牙周病或其他口腔問題。<br class="pc" /><br class="pc" />建議每半年至一年進行一次洗牙，為您的口腔健康護航。',
  mbImg: 'https://static.cmereye.com/imgs/2024/11/e2060998e6c2c550.jpg',
  pcImg: 'https://static.cmereye.com/imgs/2024/11/694b54ff0a7831fc.png',
}

const reasonData = {
  title: '為何要定期洗牙？',
  reasonLists: [
    {
      img: 'https://static.cmereye.com/imgs/2023/10/c064878ac3598d1d.jpg',
      context: '預防牙周病',
    },
    {
      img: 'https://static.cmereye.com/imgs/2023/10/50a1890059584dcd.jpg',
      context: '防止蛀牙',
    },
    {
      img: 'https://static.cmereye.com/imgs/2023/10/f69af3e0ebae289f.jpg',
      context: '改善口氣及牙色',
    },
  ],
}

const problemData = {
  title: '<span>洗牙常見</span><span>問題</span>',
  lists: [
    {
      Q: '定期洗牙頻率是多久？診所洗牙與家中刷牙分別？',
      A: '牙醫一般建議每六個月至一年洗牙一次。但具體頻率應根據個人口腔衛生狀況和牙醫的建議而定。如果您有牙周病或正接受牙齒矯正治療，可能需要更頻繁地洗牙。<br /><br />定期洗牙至關重要，它不僅僅是為了讓牙齒看起來更潔白，更是為了維護口腔健康，預防各種牙齒和牙齦疾病。<br />1. 清除牙菌斑和牙結石： 即使每天認真刷牙和使用牙線，仍然會有難以清除的牙菌斑積聚在牙齒表面，尤其是在牙齒與牙齦交界處以及牙齒排列不整齊的地方。牙菌斑是牙周病的主要致病因素。隨著時間推移，牙菌斑會鈣化形成牙結石，牙結石粗糙的表面更容易吸附牙菌斑，形成惡性循環，導致牙齦發炎、出血，甚至牙周病。洗牙可以有效清除牙菌斑和牙結石，從而預防牙周病。<br />2. 預防牙齦炎和牙周炎： 牙齦炎是牙周病的早期階段，表現為牙齦紅腫、出血。如果不及时治疗，牙齦炎會發展成牙周炎，牙周炎會破壞牙周組織，包括牙齦、牙周韌帶和牙槽骨，最終導致牙齒鬆動甚至脫落。定期洗牙可以去除導致牙齦炎的牙菌斑和牙結石，有效預防牙周病的發生和發展。<br />3. 保持口腔清新，去除口臭： 牙菌斑和牙結石會滋生細菌，產生硫化物，導致口臭。洗牙可以清除這些細菌和污垢，保持口腔清新，消除口臭。<br />4. 早期發現口腔問題： 洗牙過程中，牙醫會檢查您的口腔健康狀況，可以早期發現蛀牙、牙周病等問題，並及時進行治療，避免病情惡化。<br />5. 維持牙齒美白： 洗牙可以去除牙齒表面的色素沉積，例如咖啡、茶、煙漬等，讓牙齒恢復自然潔白。<br />6. 節省醫療費用： 定期洗牙可以預防牙齒和牙齦疾病，避免日後昂貴的治療費用。',
    },
    {
      Q: '什麼是噴沙洗牙?與一般洗牙的分別？',
      A: '噴砂洗牙，又稱為空氣拋光，是一種利用高壓氣流將細小的顆粒噴射到牙齒表面，有效去除牙菌斑、牙結石和外源性色素，例如咖啡、茶、煙、中藥漬等。<br /><br />噴砂洗牙相對舒適： 與一般的超聲波洗牙相比，噴砂洗牙的震動感較小，怕洗牙的患者會感覺更舒適。<br />更有效清潔牙齒縫隙： 噴砂洗牙可以清潔牙刷和牙線難以到達的牙齒縫隙，更有效地清除牙菌斑。<br />噴砂洗牙快速便捷： 噴砂洗牙過程相對快速，通常只需幾分鐘即可完成。<br />有效去除牙漬：噴砂洗牙過可去除咖啡漬、茶漬、煙漬、中藥漬等，所以有一定的美白效果。',
    },
    {
      Q: '洗牙可以美白牙齒嗎？',
      A: '洗牙的主要目的是清除牙結石，維護口腔健康。洗牙本身並不能改變牙齒的顏色，而是去除覆蓋在牙齒表面的牙菌斑、牙結石及外源性色素（如茶漬、咖啡漬），使牙齒恢復其原本的色澤。因此，洗牙後牙齒可能會看起來比較潔白，但這並非真正意義上的美白。若您希望達到更顯著的美白效果，改善牙齒本身的顏色，則建議尋求專業的牙齒美白療程。',
    },
    {
      Q: '洗牙過程需要多久時間?',
      A: '洗牙時間通常在30分鐘至1小時之間，具體時間取決於客人的口腔衛生狀況和牙結石的多少。',
    },
    {
      Q: '沒有提前預約，可以即時洗牙嗎?',
      A: '由於大多數診所洗牙的預約都十分緊湊，通常未能安排即時洗牙。有可能需要等待一段時間。建議您先透過網上或致電預約洗牙，以確保可以獲得及時的服務。',
    },
    {
      Q: '什麼是深層洗牙?',
      A: '深層洗牙是一種治療牙周病的方法之一，並非人人需要。<br /><br />一般洗牙是清潔牙齦線以上、肉眼可見的牙齒表面，去除牙菌斑和牙結石。<br />深層洗牙是牙清潔牙齦線以下、牙根表面的牙菌斑、牙結石和受感染的牙骨質。這個過程更深入、更複雜，通常需要局部麻醉以減輕不適感。<br /><br />如果您有牙周病的症狀，例如牙齦出血、紅腫、疼痛、口臭等，請及時就診，讓牙醫評估是否需要進行深層洗牙。',
    },
    {
      Q: '洗牙會損琺瑯質？',
      A: '洗牙本身並不會損害琺瑯質。洗牙的目的是去除牙結石和牙菌斑，這些沉積物附著在牙齒表面，會引發牙齦炎和牙周病。洗牙過程中，使用的超聲波震動或手動刮除工具並不會直接接觸或磨損琺瑯質。<br /><br />然而，操作不當的洗牙的確有可能造成牙齒損傷。因此，選擇正規的牙科診所和經驗豐富的牙醫至關重要，以確保洗牙過程的安全性及有效性。',
    },
    {
      Q: '哪些疾病患者洗牙前需要特別注意？',
      A: '以下疾病患者在洗牙前需要特別注意，並務必告知醫生自身的健康狀況：<br /><br />心血管疾病患者： 尤其是先天性心臟病或曾患細菌性心內膜炎者，洗牙後有細菌進入血液循環，引發感染的風險。<br />使用心律調節器者： 洗牙的超音波器械產生的電磁效應可能干擾心律調節器的正常運作。<br />凝血功能異常者： 包括服用抗凝血藥物或本身凝血功能較差者，洗牙可能導致出血難以止住，甚至增加感染風險。<br />肺部慢性疾病者： 洗牙時產生的水霧或小水珠可能刺激呼吸道，引發不適或呼吸困難。',
    },
  ],
}

const Plant_brand_series_data = [
  {
    id: '1101',
    name: ['基礎洗牙'],
    price: '88',
    oldPrice: '180',
    img: 'https://static.cmereye.com/imgs/2024/11/01fd99a1cf216221.png',
    compare: [
      'https://static.cmereye.com/static/ckj/imgs/svg/pc3star.svg',
      'https://static.cmereye.com/static/ckj/imgs/svg/pc2star.svg',
      'https://static.cmereye.com/static/ckj/imgs/svg/pc3star.svg',
      'https://static.cmereye.com/static/ckj/imgs/svg/pc5star.svg',
    ],
    lists: [
      '· 超聲波清除牙結石',
      '· 有效預防牙周炎、細菌引起的牙齒疾病',
      '· 有拋光處理',
    ],
    listsM: ['超聲波技術清除牙石', '預防牙患', '牙齒拋光處理'],
    cleanScore: 4,
    whiteningScore: 3,
    comfortScore: 4,
  },
  {
    id: '1102',
    name: ['菌斑導向<i class="d-none d-lg-block">專業</i>洗牙', '含鹽'],
    price: '168',
    oldPrice: '350',
    img: 'https://static.cmereye.com/imgs/2024/11/7d36488bc41e7ad6.png',
    compare: [
      'https://static.cmereye.com/static/ckj/imgs/svg/pc4star.svg',
      'https://static.cmereye.com/static/ckj/imgs/svg/pc4star.svg',
      'https://static.cmereye.com/static/ckj/imgs/svg/pc4star.svg',
      'https://static.cmereye.com/static/ckj/imgs/svg/pc5star.svg',
    ],
    lists: [
      '· 噴砂能深入清潔細小牙縫',
      '· 菌斑導向能及早找出潛在隱患',
      '· 減少一般超聲波洗牙引致的痛楚不適',
      '· 有效清除牙齒上煙、茶、咖啡漬',
    ],
    listsM: [
      '包含菌斑染色+噴砂清洗+超聲波+拋光',
      '分析客人刷牙盲點',
      '噴砂清潔牙縫有效去漬',
    ],
    cleanScore: 3,
    whiteningScore: 2,
    comfortScore: 3,
  },
  {
    id: '1103',
    name: ['菌斑導向<i class="d-none d-lg-block">專業</i>洗牙', '無鹽'],
    price: '168',
    oldPrice: '550',
    img: 'https://static.cmereye.com/imgs/2024/11/958f0c3e3acf223f.png',
    compare: [
      'https://static.cmereye.com/static/ckj/imgs/svg/pc5star.svg',
      'https://static.cmereye.com/static/ckj/imgs/svg/pc5star.svg',
      'https://static.cmereye.com/static/ckj/imgs/svg/pc5star.svg',
      'https://static.cmereye.com/static/ckj/imgs/svg/pc4star.svg',
    ],
    lists: [
      '· 包含菌斑染色+噴砂清洗+超聲波+拋光',
      '· 分析客人刷牙盲點',
      '· 噴砂清潔牙縫有效去漬',
      '· 無鹽噴砂更舒適',
    ],
    listsM: [
      '包含菌斑染色+噴砂清洗+超聲波+拋光',
      '分析客人刷牙盲點',
      '噴砂清潔牙縫有效去漬',
      '無鹽噴砂更舒適',
    ],
    cleanScore: 5,
    whiteningScore: 5,
    comfortScore: 5,
  },
]

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

const cleaningStepList = [
  {
    id: 1,
    title: '口腔檢查',
    img: 'https://static.cmereye.com/imgs/2024/02/6731dba434edd53f.jpg',
  },
  {
    id: 2,
    title: '口腔消毒',
    img: 'https://static.cmereye.com/imgs/2024/02/c8aa8929874fd251.jpg',
  },
  {
    id: 3,
    title: '牙石去除',
    img: 'https://static.cmereye.com/imgs/2024/02/ea678899b066c7cb.jpg',
  },
  {
    id: 4,
    title: '噴砂',
    img: 'https://static.cmereye.com/imgs/2024/02/e134fd577d7f9467.jpg',
  },
  {
    id: 5,
    title: '拋光',
    img: 'https://static.cmereye.com/imgs/2024/02/58ba4fa2a7ff9ffa.jpg',
  },
  {
    id: 6,
    title: '牙周保護',
    img: 'https://static.cmereye.com/imgs/2024/02/c881f0c09986279f.jpg',
  },
]
</script>

<template>
  <div>
    <PageHeader v-if="windowWidth < 768" :headerConfig="headerConfig">
      <template #xxxxxxxxxxx-home>
        <div class="banner-in-box">
          <div class="banner-content" style="display: flex">
            <div class="content-title">網上預約限定優惠</div>
            <div class="content-price">
              <div>超聲波洗牙</div>
              <div>
                <img src="~/assets/images/2025031309501301.svg" alt="" />
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
              src="https://static.ckjhk.com/ckj-image/e007cc40d522.webp"
              alt=""
              loading="lazy"
            />
          </div>
          <div class="banner-content" style="display: flex">
            <div class="content-title">網上預約限定優惠</div>
            <div class="content-price">
              <div>超聲波洗牙</div>
              <div>
                <img src="~/assets/images/2025031309501301.svg" alt="" />
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
    <div>
      <section class="ckj-container type-technology">
        <div class="d-flex flex-row align-items-end subheading">
          <span>洗牙技術及</span><span>種類</span>
        </div>
        <div class="type-technology-content">
          <div class="service-cards">
            <div
              v-for="(item, index) in Plant_brand_series_data"
              :key="index"
              class="service-card"
            >
              <div class="card-image">
                <img :src="item.img" :alt="item.name[0]" />
              </div>
              <div class="card-content">
                <div class="card-content-left">
                  <div
                    class="card-content-left-title"
                    :class="index !== 0 ? `title-${item.id}` : ''"
                  >
                    <span
                      v-for="(e, i) in item.name"
                      :key="i"
                      v-html="e"
                    ></span>
                  </div>
                  <div class="rating-row">
                    <div class="rating-item">
                      <span>潔淨度</span>
                      <div class="stars">
                        <img
                          :src="`https://static.ckjhk.com/ckj-image/stars${item.cleanScore}.png`"
                          alt=""
                        />
                      </div>
                    </div>
                    <div class="rating-item">
                      <span>美白度</span>
                      <div class="stars">
                        <img
                          :src="`https://static.ckjhk.com/ckj-image/stars${item.whiteningScore}.png`"
                          alt=""
                        />
                      </div>
                    </div>
                    <div class="rating-item">
                      <span>舒適度</span>
                      <div class="stars">
                        <img
                          :src="`https://static.ckjhk.com/ckj-image/stars${item.comfortScore}.png`"
                          alt=""
                        />
                      </div>
                    </div>
                  </div>
                </div>
                <div class="card-content-right">
                  <div class="price">
                    <div v-if="item.id === '1101'" :class="`price-${item.id}`">
                      <img
                        src="https://static.ckjhk.com/ckj-image/882025032115375801.png"
                        alt=""
                      />
                    </div>
                    <div
                      v-else-if="item.id === '1102'"
                      :class="`price-${item.id}`"
                    >
                      <img
                        src="https://static.ckjhk.com/ckj-image/1682025032115382001.png"
                        alt=""
                      />
                    </div>
                    <div
                      v-else-if="item.id === '1103'"
                      :class="`price-${item.id}`"
                    >
                      <img
                        src="https://static.ckjhk.com/ckj-image/1682025032115383201.png"
                        alt=""
                      />
                    </div>
                    <div>
                      <span class="original-price"
                        >原價¥{{ item.oldPrice }}</span
                      >
                    </div>
                  </div>
                  <div class="features" v-if="windowWidth > 768">
                    <p v-for="(feature, fIndex) in item.lists" :key="fIndex">
                      {{ feature }}
                    </p>
                  </div>
                  <ul class="features" v-if="windowWidth < 768">
                    <li
                      v-for="(featureM, fIndexM) in item.listsM"
                      :key="fIndexM"
                    >
                      {{ featureM }}
                    </li>
                  </ul>
                </div>
              </div>
            </div>
          </div>
          <div class="type-technology-message">
            <p>*長者優惠只限深圳愛康健口腔醫院使用</p>
            <p>
              把握限時優惠，<br class="d-lg-none" />立即預約愛康健專業洗牙服務！
            </p>
          </div>
          <div class="type-technology-btn">
            <PageAnimBtnTypeTwoV2 :str="'WhatsApp預約洗牙'" />
          </div>
        </div>
      </section>
      <section class="ckj-container cleaning-step">
        <div class="cleaning-step-subheading">\ <i>洗牙6步曲</i> /</div>
        <div class="cleaning-step-context" id="implantStep">
          <div
            class="cleaning-step-item"
            v-for="(item, index) in cleaningStepList"
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
      <div class="cleaning-video-bg">
        <section class="ckj-container cleaning-video">
          <div class="d-flex flex-row align-items-end subheading">
            <span>專業消毒</span><span>流程</span>
          </div>
          <div class="cleaning-video-content">
            <div class="cleaning-video-content-iframe">
              <iframe
                width="100%"
                height="100%"
                src="https://www.youtube.com/embed/5rKokT9WBLw?si=kZmC7NGQvwZPNE9f"
                frameborder="0"
              ></iframe>
            </div>
            <div class="cleaning-video-content-text">
              <p>
                以「一醫一診室」、「一機一用一消毒」的無菌治療模式，避免交叉感染機會。
              </p>
              <p>
                瑞士EMS超音波科技採用光學數位掃描，高頻聲納定位，作用於清潔牙結石，預防牙周病和蛀牙。
              </p>
            </div>
          </div>
        </section>
      </div>
      <section class="ckj-container">
        <V2ServiceProblem :problem-data="problemData" :v2-versions="true" />
      </section>
      <BranchAddress />
      <ContactForm-new2 />
    </div>
    <FooterV2 />
    <!-- <FooterV2 /> -->
    <AsideV2 />
  </div>
</template>

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
.banner-image {
  position: absolute;
  z-index: 3;
  top: 1vw;
  left: 42%;
  width: 9.0625vw;
  height: 9.0625vw;
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
  width: 23.9583vw;
  position: absolute;
  left: 35%;
  top: 50%;
  transform: translate(-50%, -50%);
  & > div {
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
    line-height: 100%; /* 176px */
    letter-spacing: 6.6px;
    position: relative;
    z-index: 6;
    bottom: 0;

    border-radius: 0.6942vw 0.6942vw 0px 0px;
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
    & > img {
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
    line-height: 2.2222vw; /* 114.286% */
    letter-spacing: 0.29165vw;
    justify-content: center;
    border-radius: 0px 0px 10px 10px;
    background: var(--White, #fff);
    box-shadow: 0px 4px 4px rgba(77, 77, 77, 0.2);
    & > div:nth-child(1) {
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
      line-height: 2.2222vw; /* 114.286% */
      letter-spacing: 0.29165vw;
      top: -0.9vw;
    }
    & > div:nth-child(1)::after {
      content: '';
      width: 48%;
      height: 2px;
      background: #333;
      position: absolute;
      transform: rotate(-5deg);
      bottom: -40%;
      right: 0;
    }
    & > div:nth-child(1)::before {
      content: '原價 ¥180';
      color: var(--Grey-Dark, #333);
      text-align: center;
      font-family: 'Noto Sans HK';
      font-size: 0.97223vw;
      font-style: normal;
      font-weight: 350;
      line-height: 120%; /* 22.4px */
      position: absolute;
      letter-spacing: 1px;
      bottom: -55%;
      right: 0;
    }

    & > div:nth-child(2) {
      width: 9.739583vw;
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

@media screen and (min-width: 922px) {
  .type-technology {
    margin-top: 30px;
    margin-bottom: 30px;
  }
  .type-technology-content {
    display: flex;
    flex-direction: column;
    margin-top: 17px;
    .service-cards {
      display: flex;
      flex-direction: column;
      gap: 50px 0;
      box-sizing: border-box;
      padding: 0 40.5px;

      .card-image {
        width: 170px;
        height: 170px;
        & > img {
          width: 100%;
          height: 100%;
          object-fit: cover;
        }
      }
      .service-card {
        display: flex;
        gap: 0 22px;
      }
      .card-content {
        display: flex;
        gap: 0 40px;
      }
      .card-content-left {
        display: flex;
        flex-direction: column;
        gap: 10px 0;
        .card-content-left-title {
          box-sizing: border-box;
          padding: 10px 30px;
          border-radius: 10px;
          background: var(--Blue-Deep, #00aeff);
          width: fit-content;
          position: relative;
          & > span:nth-child(1) {
            color: var(--White, #fff);
            text-align: center;
            font-family: 'Noto Sans HK';
            font-size: 24px;
            font-style: normal;
            font-weight: 700;
            line-height: normal;
            letter-spacing: 2.4px;
          }
          & > span:nth-child(2) {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            right: -55px;
            color: var(--Grey-Dark, #333);
            text-align: center;
            font-family: 'Noto Sans HK';
            font-size: 24px;
            font-style: normal;
            font-weight: 700;
            line-height: normal;
            letter-spacing: 2.4px;
            width: 80px;
            height: 80px;
            border: 5px solid #fff;
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            background: #ffe9ec;
          }
        }
        .title-1102 {
          background: #f8298a;
        }
        .title-1103 {
          background: #01a853;
          & > span:nth-child(2) {
            background: #b3e5cc;
          }
        }
        .rating-row {
          padding-left: 30px;
          & > div {
            display: flex;
            align-items: center;
            gap: 0 15px;
          }
          display: flex;
          flex-direction: column;
          gap: 6px 0;
          .rating-item {
            & > span:nth-child(1) {
              color: var(--Grey-Mid, #666);
              font-family: 'Noto Sans TC';
              font-size: 20px;
              font-style: normal;
              font-weight: 700;
              line-height: 160%; /* 32px */
              letter-spacing: 2px;
            }
            .stars {
              width: 136px;
              height: 24px;
              & > img {
                width: 100%;
                height: 100%;
                object-fit: contain;
              }
            }
          }
        }
      }
      .card-content-right {
        min-width: 371px;
        .price {
          display: flex;
          justify-content: flex-end;
          align-items: flex-end;
          gap: 0 28px;
          & > div:nth-child(1) {
            & > img {
              width: 100%;
              height: 100%;
              object-fit: contain;
            }
          }
          & > div:nth-child(2) {
            color: var(--Grey-Deep, #4d4d4d);
            text-align: right;
            font-family: 'Noto Sans HK';
            font-size: 24px;
            font-style: normal;
            font-weight: 700;
            line-height: 160%; /* 38.4px */
            padding-bottom: 5px;
            position: relative;
          }
          & > div:nth-child(2)::before {
            content: '';
            position: absolute;
            width: 100%;
            height: 2px;
            background: #4d4d4d;
            bottom: 50%;
            left: 0;
            transform: rotate(350deg) translateY(-50%);
          }
        }
        .price-1101 {
          width: 104px;
          height: auto;
        }
        .price-1102,
        .price-1103 {
          width: 143px;
          height: auto;
          position: relative;
        }
        .price-1102::before {
          content: '\\性價比之選/';
          color: var(--Brand-Color, #f8298a);
          text-align: center;
          font-family: 'Noto Sans HK';
          font-size: 24px;
          font-style: normal;
          font-weight: 700;
          line-height: normal;
          letter-spacing: 2.4px;
          position: absolute;
          top: -40px;
          left: 65%;
          transform: translateX(-50%);
          white-space: nowrap;
        }
        .price-1103::before {
          content: '長者優惠*';
          color: var(--GHV-Green, #01a853);
          text-align: center;
          font-family: 'Noto Sans HK';
          font-size: 24px;
          font-style: normal;
          font-weight: 700;
          line-height: normal;
          letter-spacing: 2.4px;
          position: absolute;
          top: -40px;
          left: 65%;
          transform: translateX(-50%);
          white-space: nowrap;
        }
        .features {
          p {
            color: var(--Grey-Deep, #4d4d4d);
            font-family: 'Noto Sans HK';
            font-size: 18px;
            font-style: normal;
            font-weight: 400;
            line-height: 200%; /* 36px */
            letter-spacing: 1.8px;
          }
        }
      }
    }
    .type-technology-message {
      display: flex;
      flex-direction: column;
      gap: 8px 0;
      margin-top: 17px;
      p:nth-child(1) {
        color: var(--Grey-Mid, #666);
        text-align: center;
        font-family: 'Noto Sans HK';
        font-size: 18px;
        font-style: normal;
        font-weight: 400;
        line-height: 200%; /* 36px */
        letter-spacing: 1.8px;
      }
      p:nth-child(2) {
        color: var(--Theme-Color, #fc1682);
        text-align: center;
        font-family: 'Noto Sans TC';
        font-size: 20px;
        font-style: normal;
        font-weight: 700;
        line-height: 160%; /* 32px */
        letter-spacing: 2px;
      }
    }
    .type-technology-btn {
      display: flex;
      justify-content: center;
      align-items: center;
      margin-top: 37px;
    }
  }
  .cleaning-step {
    margin-top: 30px;
    margin-bottom: 30px;
    .cleaning-step-subheading {
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
    .cleaning-step-context {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 30px;
      box-sizing: border-box;
      padding: 30px 0 0;
    }
    .cleaning-step-item {
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
        margin-top: 9px;
        width: 100%;
        color: var(--Grey-Dark, #333);
        font-family: 'Noto Sans HK';
        font-size: 20px;
        font-style: normal;
        font-weight: 400;
        line-height: 160%;
        /* 32px */
        letter-spacing: 4px;
        text-align: center;
      }
    }
  }
  .cleaning-video-bg {
    background: linear-gradient(
      180deg,
      rgba(255, 255, 255, 0) 0%,
      var(--Pink-Pale, #ffe9ec) 100%
    );
  }
  .cleaning-video {
    margin-bottom: 30px;
    padding-top: 30px;
    .cleaning-video-content-iframe {
      width: 672px;
      height: 380px;
      margin: 30px auto 0;
      iframe {
        width: 100%;
        height: 100%;
      }
    }
    .cleaning-video-content-text {
      display: flex;
      flex-direction: column;
      margin-top: 24.35px;
      padding-bottom: 26.65px;
      p {
        color: var(--Grey-Dark, #333);
        text-align: center;
        font-family: 'Noto Sans HK';
        font-size: 18px;
        font-style: normal;
        font-weight: 400;
        line-height: 200%; /* 36px */
        letter-spacing: 1.8px;
      }
    }
  }
}

@media screen and (max-width: 991px) {
  .type-technology {
    margin-top: 35px;
    margin-bottom: 40px;
    .type-technology-content {
      margin-top: 20px;
      .service-cards {
        display: flex;
        flex-direction: column;
        gap: 34px 0;
      }
      .card-content {
        display: flex;
        justify-content: space-between;
        .card-content-left {
          display: flex;
          flex-direction: column;
          gap: 10px 0;
          .card-content-left-title {
            color: var(--White, #fff);
            text-align: center;
            font-family: 'Noto Sans HK';
            font-size: 18px;
            font-style: normal;
            font-weight: 700;
            line-height: normal;
            letter-spacing: 1.8px;
            box-sizing: border-box;
            padding: 5px 15px 5px 25px;
            border-radius: 0px 5px 5px 0px;
            background: var(--Blue-Deep, #00aeff);
            position: relative;
            & > span:nth-child(2) {
              position: absolute;
              top: 50%;
              transform: translateY(-50%);
              right: -40px;
              color: var(--Grey-Dark, #333);
              text-align: center;
              font-family: 'Noto Sans HK';
              font-size: 15px;
              font-style: normal;
              font-weight: 500;
              line-height: 160%; /* 24px */
              letter-spacing: 1.5px;
              width: 50px;
              height: 50px;
              border: 3px solid #fff;
              border-radius: 50%;
              display: flex;
              justify-content: center;
              align-items: center;
              background: #ffe9ec;
            }
          }
          .title-1102 {
            background: #f8298a;
          }
          .title-1103 {
            background: #01a853;
            & > span:nth-child(2) {
              background: #b3e5cc;
            }
          }
          .rating-row {
            display: flex;
            flex-direction: column;
            gap: 4px 0;
            .rating-item {
              display: flex;
              gap: 0 7px;
              align-items: center;
              & > span:nth-child(1) {
                color: var(--Grey-Mid, #666);
                font-family: 'Noto Sans HK';
                font-size: 14px;
                font-style: normal;
                font-weight: 500;
                line-height: 120%; /* 16.8px */
              }
              .stars {
                width: 64px;
                height: 12px;
                & > img {
                  width: 100%;
                  height: 100%;
                  object-fit: contain;
                }
              }
            }
          }
        }
        .card-content-right {
          display: flex;
          flex-direction: column;
          gap: 10px 0;
          width: 173px;
          .price {
            display: flex;
            align-items: center;
            justify-content: flex-end;
            padding-right: 18px;
            gap: 0 4px;
            & > div:nth-child(1) {
              & > img {
                width: 100%;
                height: 100%;
                object-fit: contain;
              }
            }
            & > div:nth-child(2) {
              position: relative;
            }
            & > div:nth-child(2)::before {
              content: '';
              position: absolute;
              width: 100%;
              height: 1px;
              background: #4d4d4d;
              bottom: 50%;
              left: 0;
              transform: rotate(350deg) translateY(-50%);
            }
            .price-1101 {
              width: 52px;
              height: auto;
            }
            .price-1102,
            .price-1103 {
              width: 72px;
              height: auto;
              position: relative;
            }
            .price-1102::before {
              content: '\\性價比之選/';
              color: var(--Brand-Color, #f8298a);
              text-align: center;
              font-family: 'Noto Sans HK';
              font-size: 14px;
              font-style: normal;
              font-weight: 700;
              position: absolute;
              top: -20px;
              left: 55%;
              transform: translateX(-50%);
              white-space: nowrap;
            }
            .price-1103::before {
              content: '長者優惠*';
              color: var(--GHV-Green, #01a853);
              text-align: center;
              font-family: 'Noto Sans HK';
              font-size: 12px;
              font-style: normal;
              font-weight: 500;
              line-height: 120%; /* 14.4px */
              position: absolute;
              top: -15px;
              left: 60%;
              transform: translateX(-50%);
              white-space: nowrap;
            }
          }
          .features {
            padding-right: 30px;
            position: relative;
            left: -10px;
            li {
              color: var(--Grey-Deep, #4d4d4d);
              font-family: 'Noto Sans HK';
              font-size: 12px;
              font-style: normal;
              font-weight: 400;
              line-height: 170%; /* 20.4px */
              list-style: disc;
            }
          }
        }
      }
      .card-image {
        display: none;
      }
    }
    .type-technology-message {
      margin-top: 10px;
      & > p:nth-child(1) {
        color: var(--Grey-Mid, #666);
        font-family: 'Noto Sans HK';
        font-size: 12px;
        font-style: normal;
        font-weight: 350;
        line-height: 120%; /* 14.4px */
        margin-left: 20px;
      }
      & > p:nth-child(2) {
        color: var(--Theme-Color, #fc1682);
        text-align: center;
        font-family: 'Noto Sans HK';
        font-size: 16px;
        font-style: normal;
        font-weight: 700;
        line-height: normal;
        letter-spacing: 1.6px;
        margin: 30px auto 0;
      }
    }
    .type-technology-btn {
      display: flex;
      align-items: center;
      justify-content: center;
      margin-top: 30px;
      & > div:nth-child(1) {
        width: 100%;
        height: 100%;
        justify-content: center;
      }
    }
  }
  .cleaning-step-subheading {
    margin-bottom: 5.865vw;

    & > i {
      color: var(--Brand-Color, #f8298a);
      font-family: 'Noto Sans HK';
      font-size: 4.8vw;
      font-style: normal;
      font-weight: 700;
      line-height: normal;
      letter-spacing: 0.48vw;
    }

    color: var(--Grey-Mid, #666);
    text-align: center;
    font-family: 'Noto Sans HK';
    font-size: 4.8vw;
    font-style: normal;
    font-weight: 700;
    line-height: normal;
    letter-spacing: 0.48vw;
  }
  .cleaning-step {
    margin-top: 30px;
    margin-bottom: 30px;
    .cleaning-step-context {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 18px 24px;
      padding: 0 20px;
      .cleaning-step-item {
        position: relative;
        box-sizing: border-box;

        & > div:nth-child(1) {
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
          background: url(https://static.cmereye.com/imgs/2024/11/3b0a5e9326c68638.png)
            no-repeat;
          background-size: cover;
          width: 8vw;
          height: 8vw;
          display: flex;
          align-items: center;
          justify-content: center;
        }
        & > div:nth-child(2) {
          position: relative;
        }
        & > div:nth-child(2)::after {
          content: '';
          position: absolute;
          width: 2.93vw;
          height: 6.4vw;
          background: url(https://static.ckjhk.com/ckj-image/2025032009130001.png)
            no-repeat;
          background-size: cover;
          right: -2.8vw;
          top: 50%;
          transform: translateY(-50%);
        }
        & > div:nth-child(3) {
          color: var(--Grey-Dark, #333);
          /* 手機版/MB-Small Text */
          font-family: 'Noto Sans HK';
          font-size: 3.73vw;
          font-style: normal;
          font-weight: 350;
          line-height: 5.33vw;
          margin-top: 5px;
          text-align: center;
        }
      }
      .implant-step-item:last-child {
        & > div:nth-child(2)::after {
          content: none;
        }
      }
    }
  }
  .cleaning-video {
    .cleaning-video-content {
      padding-bottom: 20px;
      background: linear-gradient(
        181deg,
        rgba(255, 255, 255, 0) 0.52%,
        var(--Pink-Pale, #ffe9ec) 102.02%
      );
      .cleaning-video-content-iframe {
        width: 272px;
        height: 152px;
        margin: 15px auto 30px;
      }
    }
    .cleaning-video-content-text {
      box-sizing: border-box;
      padding: 0 30px;
      p {
        color: var(--Grey-Dark, #333);
        font-family: 'Noto Sans HK';
        font-size: 12px;
        font-style: normal;
        font-weight: 500;
        line-height: 150%; /* 18px */
      }
      display: flex;
      flex-direction: column;
      gap: 10px 0;
    }
  }
  .bottom_info {
    & > div:nth-child(1) {
      color: var(--Theme-Color, #fc1682);
      text-align: center;
      font-family: var(--indexFontFamily);
      font-size: 20px;
      font-style: normal;
      font-weight: 400;
      line-height: 160%; /* 32px */
      display: flex;
      flex-direction: column;
      margin-bottom: 20px;
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
      display: flex;
      justify-content: center;
      color: var(--White, #fff);
      text-align: center;
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
        position: relative;
      }
      & > div:nth-child(1)::after {
        content: '';
        width: 55%;
        height: 2px;
        background: #333;
        position: absolute;
        transform: rotate(-5deg);
        bottom: -50%;
        right: 0;
      }
      & > div:nth-child(1)::before {
        content: '原價 ¥180';
        color: var(--Grey-Dark, #333);
        text-align: center;
        font-family: 'Noto Sans HK';
        font-size: 14px;
        font-style: normal;
        font-weight: 350;
        line-height: 120%; /* 16.8px */
        letter-spacing: 1px;
        position: absolute;
        bottom: -80%;
        right: 0;
      }

      & > div:nth-child(2) {
        width: 37.33vw;
        height: 13.1653vw;
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
