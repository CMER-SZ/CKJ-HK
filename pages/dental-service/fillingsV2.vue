<script lang="ts" setup>
import { useAppState } from '~/stores/appState'
const appState = useAppState()
appState.setDentistryService('fillings')
useHead({
  title: '補牙',
  meta: [
    {
      hid: 'description',
      name: 'description',
      content:
        '愛康健美國3M補牙首顆半價，使用先進材料修復損壞和蛀牙恢復牙齒健康與美觀,香港熱線: 6933 8128免費預約掛號,羅湖福田深圳灣口岸分店',
    },
    {
      hid: 'Keywords',
      name: 'Keywords',
      content:
        '愛康健 爱康健 CKJ aikangjian 牙科服務 內地牙科 深圳牙科 深圳愛康健口腔醫院 愛康健齒科集團 美容牙科  醫療券 長者醫療券大灣區試點  牙醫 牙医  朱咪咪 掛號 深圳整牙 深圳睇牙 深圳補牙 收費價目表 掛號預約 補牙 牙體復形 補牙材料 補牙費用 瓷粉補牙 銀粉補牙 補牙物料 補牙價錢 補牙收費 補牙洞 牙齒修復 蛀牙治療 專業牙科 敏感牙齒 氟 琺瑯質 深圳睇牙幾多錢',
    },
  ],
})

const introduceJY = {
  title: 'pages.dental-service.fillings.introduce.title',
  content: 'pages.dental-service.fillings.introduce.content',
  mbImg: 'https://static.cmereye.com/imgs/2024/08/7239d7032e2d634b.jpg',
  pcImg: 'https://static.cmereye.com/imgs/2024/04/b1104af283741909.webp',
}

const headerConfig = {
  img: 'https://static.ckjhk.com/ckj-image/488fe47b05bd.webp',
  mbImg: 'https://static.ckjhk.com/ckj-image/b3e5975a2ff2.webp',
  bg: '',
  pageName: 'invisalign-test',
  pcText: [],
  mbText: [],
}

const orthodonticsIntroduceData = {
  title: 'pages.dental-service.fillings.introduce.title',
  content: 'pages.dental-service.fillings.introduce.content',
  mbImg: 'https://static.cmereye.com/imgs/2024/04/908db92c90966e34.webp',
  pcImg: 'https://static.cmereye.com/imgs/2024/02/51bcdbae58f74102.webp',
  tabNavName: 'pages.dental-service.fillings.introduce.tabNavName',
  pageName: 'fillings',
}

const noteData = {
  title: '補牙後建議',
  lists: [
    {
      img: 'https://static.cmereye.com/imgs/2024/02/84e6cc7af16299e7.png',
      text: '避免進食過冷\n或過熱的食物',
    },
    {
      img: 'https://static.cmereye.com/imgs/2024/02/6fda3607b45244cb.png',
      text: '避免咬合\n過硬的食物',
    },
  ],
}

const materialData = {
  title: '補牙材料',
  context: [
    '補牙材料主要分為複合樹脂（俗稱瓷粉）',
    '及銀汞合金（俗稱銀粉）兩種。',
    '複合樹脂是現時最常用的材料。由於銀汞合金氧化後會變成銀黑色，因此較少被選用。',
  ],
  tableLeft: [
    ['類別', '特性', '優點', '缺點'],
    [
      '複合樹脂',
      '多用於修復牙齒的形狀',
      '美觀，接近牙齒天然的顏色與牙釉質有較強的粘合力',
      '強度比銀汞合金稍弱',
    ],
  ],
  tableRight: [
    '銀汞合金',
    '多用於修補小臼齒或大臼齒的蛀牙',
    '堅固，可承受較強的咬合力耐用，不易磨損',
    '氧化後會變銀黑色，欠美觀',
  ],
}

let materialCurrent = ref(1)

let windowWidth = ref(1920)
onMounted(() => {
  getWindowWidth()
  window.addEventListener('resize', getWindowWidth)
})

const getWindowWidth = () => {
  windowWidth.value = window.innerWidth
}

const problemData = {
  title: '<span>補牙</span><span>常見問題</span>',
  lists: [
    {
      Q: 'pages.dental-service.fillings.problem.lists[0].Q',
      A: 'pages.dental-service.fillings.problem.lists[0].A',
    },
    {
      Q: 'pages.dental-service.fillings.problem.lists[1].Q',
      A: 'pages.dental-service.fillings.problem.lists[1].A',
    },
    {
      Q: 'pages.dental-service.fillings.problem.lists[2].Q',
      A: 'pages.dental-service.fillings.problem.lists[2].A',
    },
    {
      Q: 'pages.dental-service.fillings.problem.lists[3].Q',
      A: 'pages.dental-service.fillings.problem.lists[3].A',
    },
    {
      Q: 'pages.dental-service.fillings.problem.lists[4].Q',
      A: 'pages.dental-service.fillings.problem.lists[4].A',
    },
  ],
}
const careData = {
  title: ['蛀牙的常見徵兆'],
  lists: [
    {
      img: 'https://static.cmereye.com/imgs/2024/02/0455d2f9f71e35cb.png',
      text: '咀嚼或咬合時\n感到疼痛',
    },
    {
      img: 'https://static.cmereye.com/imgs/2024/02/ea78194a75b40377.png',
      text: '牙齒出現黑色\n或棕色斑點',
    },
    {
      img: 'https://static.cmereye.com/imgs/2024/02/5e3a51999b0fda41.png',
      text: '牙齒出現牙洞\n或凹陷',
    },
    {
      img: 'https://static.cmereye.com/imgs/2024/02/5a746d8adced4068.png',
      text: '牙齦紅腫、\n出血、下陷',
    },
    {
      img: 'https://static.cmereye.com/imgs/2024/02/e7cf8e3f35476d19.png',
      text: '牙齒對冷熱\n或甜食敏感',
    },
    {
      img: 'https://static.cmereye.com/imgs/2024/02/8e1427cf1f4ecc81.png',
      text: '出現口臭',
    },
  ],
}
const contentData1 = [
  {
    img: 'https://static.cmereye.com/imgs/2024/02/61c99e28e2d65cc0.jpg',
    text: '頻繁食用黏性食物\n和高糖份食物',
  },
  {
    img: 'https://static.cmereye.com/imgs/2024/02/3fea9c1894d15f28.jpg',
    text: '不當口腔衛生習慣',
  },
  {
    img: 'https://static.cmereye.com/imgs/2024/02/8ef84d0d5d91d08c.jpg',
    text: '藥物或手術導致\n唾液分泌減少',
  },
  {
    img: 'https://static.cmereye.com/imgs/2024/02/b70309f502c9cb6c.jpg',
    text: '牙齒擠擁清潔困難',
  },
]
const advantageData = {
  title: '預防蛀牙方法',
  lists: [
    {
      name: '1.定期口腔檢查',
      text: '每年至少進行兩次口腔檢查和清潔。牙醫可以檢查牙齒的健康狀況，發現和處理早期的蛀牙問題。',
    },
    {
      name: '2.定期刷牙',
      text: '每天至少刷牙兩次，早晚各一次，使用牙刷和牙膏。刷牙應該持續兩分鐘，確保清潔到所有牙齒表面和牙齦線。選擇含有氟化物的牙膏，有助於保護牙齒免受酸性攻擊。',
    },
    {
      name: '3.使用牙線或牙間刷',
      text: '定期使用牙線或牙間刷清潔牙齒之間的縫隙和牙齦線。這可以有效去除牙線無法觸及的食物殘渣和細菌，減少蛀牙的風險。',
    },
    {
      name: '4.使用漱口水',
      text: '使用含氟的漱口水可以保護牙齒並減少細菌的生長。漱口水有助於清潔口腔中的難以到達的區域，並降低蛀牙風險。',
    },
    {
      name: '5.控制糖分攝入',
      text: '減少攝取高糖飲食，細菌會利用糖分產生酸性物質，促使蛀牙的形成。適時刷牙或漱口可減少糖分在牙齒上的停留時間。',
    },
    {
      name: '6.避免咀嚼硬物',
      text: '避免咀嚼硬物，如冰塊、堅果或硬糖果。這樣可以減少牙齒破裂或損壞的風險。',
    },
  ],
}
const noteData2 = {
  title: '補牙的作用',
  lists: [
    {
      name: '當牙齒的硬組織（琺瑯質、象牙質）受到破壞後，容易造成小孔，形成蛀牙。為了修復破損的組織及防止蛀牙情況加劇，會以填充物填補牙齒，使牙齒能恢復原來形狀和功能。',
    },
    {
      name: '及早補牙有助於預防進一步的牙齒問題，從而避免需要接受根管治療或種植牙治療等較複雜治療的風險和負擔。',
    },
  ],
}

const getUrl = (file) => {
  return new URL(`../../assets/images/${file}.svg`, import.meta.url).href
}

const reasonData = {
  title: '蛀牙5個階段及對應治療方法',
  reasonLists: [
    {
      img: 'https://static.cmereye.com/imgs/2024/04/3888d359e0b7d48d.png',
      mb_img: getUrl('fill5'),
      title: '脫鈣（初期蛀牙）',
      context: '出現白色斑點，牙齒表面粗糙。',
      lists: [
        {
          img: 'https://static.cmereye.com/imgs/2024/04/c03a9e707f02c38a.png',
          name: '氟化治療',
          text: '使用含氟牙膏或氟漱口水來幫助恢復牙齒的礦化。',
        },
      ],
    },
    {
      img: 'https://static.cmereye.com/imgs/2024/04/9f38b6263937f9b6.png',
      mb_img: getUrl('fill4'),
      title: '外層琺瑯質受損',
      context: '牙齒出現黑色斑點或小洞。',
      lists: [
        {
          img: 'https://static.cmereye.com/imgs/2024/04/afa73345f75ba23e.png',
          name: '補牙',
          text: '移除損壞的琺瑯質並填充牙洞。',
        },
      ],
    },
    {
      img: 'https://static.cmereye.com/imgs/2024/04/936c3035a1b735c4.png',
      mb_img: getUrl('fill3'),
      title: '內層象牙質受損',
      context: '牙齒對冷熱或甜食敏感。',
      lists: [
        {
          img: 'https://static.cmereye.com/imgs/2024/04/afa73345f75ba23e.png',
          name: '補牙',
          text: '如果損害未達牙髓，仍可進行補牙修復，但補牙物料需要選用更耐用材質。',
        },
      ],
    },
    {
      img: 'https://static.cmereye.com/imgs/2024/04/b632a48711f84dc2.png',
      mb_img: getUrl('fill2'),
      title: '牙髓及神經受損',
      context: '持續性的疼痛，牙肉紅腫。',
      lists: [
        {
          img: 'https://static.cmereye.com/imgs/2024/04/e4b74d72877b3fc3.png',
          name: '根管治療',
          text: '徹底清除牙髓腔內的感染組織，填充和封閉根管。',
        },
        {
          img: 'https://static.cmereye.com/imgs/2024/04/4d64f6318dd7347a.png',
          name: '牙冠修復',
          text: '在根管治療後，牙齒可能需要一個牙冠來提供額外的強度和保護。',
        },
      ],
    },
    {
      img: 'https://static.cmereye.com/imgs/2024/04/7cad4228b8f92fa0.png',
      mb_img: getUrl('fill1'),
      title: '殘根',
      context: '牙冠部分極度損壞，僅剩牙根。',
      lists: [
        {
          img: 'https://static.cmereye.com/imgs/2024/04/f793cb2ae322224b.png',
          name: '牙冠重建',
          text: '如牙根處於健康情況下，可透過牙冠或其他修復療程來重建牙齒的形狀和功能。',
        },
        {
          img: 'https://static.cmereye.com/imgs/2024/04/f87cd712a227222a.png',
          name: '牙齒移除',
          text: '如牙齒無法修復需拔除的情況下，可考慮種植牙或牙橋療程作填補。',
        },
      ],
    },
  ],
  tText:
    '蛀牙是一個逐步破壞牙齒的過程，它可以分為幾個階段，每個階段對應不同的治療方法。由於每個病例都是獨特的，因此最適合的治療方法將由牙科醫生根據患者具體情況決定。',
  bText: [
    '建議在遇到蛀牙問題時，',
    '及早就醫並諮詢專業牙醫生建議，',
    '以確定最適合您的治療方案。',
  ],
}

const The_benefits_of_resin_filling_teeth = {
  title: '樹脂補牙3大好處',
  lists: [
    {
      name: ['美觀'],
      text: '樹脂材料可以調配成與牙齒自然色相匹配的顏色，從而在美觀上優於傳統的金屬填充物，尤其是在前牙或其他容易看見的牙齒上。',
    },
    {
      name: ['保存', '性高'],
      text: '與傳統金屬填充物不同，樹脂填料通常需要去除較少的牙體組織，因為它們可以直接粘附在牙齒表面上，這有助於保留更多的天然牙齒結構。',
    },
    {
      name: ['安全'],
      text: '樹脂填充物不含金屬，因此對於對某些金屬敏感或擔心金屬汞合金健康影響的人來說，這是一個更安全的選擇。',
    },
  ],
}
const stepData = {
  title: '補牙5部曲',
  lists: [
    {
      title: '第1步',
      img: 'https://static.cmereye.com/imgs/2024/02/7da900517cf80179.jpg',
      name: '清除牙齒蛀壞及脆弱的部分',
    },
    {
      title: '第2步',
      img: 'https://static.cmereye.com/imgs/2024/02/3e6bc9ac0edc0d89.jpg',
      name: '用專用的清潔消毒劑清潔牙齒表面，\n吹乾後，塗上黏固劑',
    },
    {
      title: '第3步',
      img: 'https://static.cmereye.com/imgs/2024/02/8233293d90d88e23.jpg',
      name: '填補牙洞及修補缺損部分',
    },
    {
      title: '第4步',
      img: 'https://static.cmereye.com/imgs/2024/02/631f4e13fa030aab.jpg',
      name: '穩固填充物',
    },
    {
      title: '第5步',
      img: 'https://static.cmereye.com/imgs/2024/02/7a0fb0ea64f3e589.jpg',
      name: '牙齒修形及拋光\n（如蛀牙的程度深，或需要使用麻醉劑）',
    },
  ],
}
const differData: any = {
  title: '補牙物料比較',
  listDatas: [
    {
      name: '',
      firstText: '複合樹脂',
      secondText: '銀汞合金',
    },
    {
      name: '',
      contentType: '2',
      firstText: 'https://static.cmereye.com/imgs/2024/08/c2ee3b604ae82543.png',
      secondText:
        'https://static.cmereye.com/imgs/2024/08/a7651e91206712fd.png',
    },
    {
      name: '特性',
      firstText: '多用於修復牙齒的形狀',
      secondText: '多用於修補小臼齒或大臼齒的蛀牙',
    },
    {
      name: '優點',
      contentType: '1',
      firstText: ['美觀，接近牙齒天然的顏色', '與牙釉質有較強的粘合力'],
      secondText: ['堅固，可承受較強的咬合力', '耐用，不易磨損'],
    },
    {
      name: '缺點',
      firstText: '強度比銀汞合金稍弱',
      secondText: '氧化後會變銀黑色，欠美觀',
    },
  ],
}

// 植牙6步曲
const implantStepList = [
  {
    id: 1,
    title: '清除蛀壞部分與脆弱處',
    img: 'https://static.cmereye.com/imgs/2024/02/7da900517cf80179.jpg',
    ifImage: true,
  },
  {
    id: 2,
    title: '清潔消毒牙面並塗黏固劑',
    img: 'https://static.cmereye.com/imgs/2024/02/3e6bc9ac0edc0d89.jpg',
    ifImage: true,
  },
  {
    id: 3,
    title: '修補缺損及牙洞',
    img: 'https://static.cmereye.com/imgs/2024/02/8233293d90d88e23.jpg',
    ifImage: true,
  },
  {
    id: 4,
    title: '穩固填充物',
    img: 'https://static.cmereye.com/imgs/2024/02/631f4e13fa030aab.jpg',
    ifImage: true,
  },
  {
    id: 5,
    title: '牙齒修形及拋光',
    img: 'https://static.cmereye.com/imgs/2024/02/7a0fb0ea64f3e589.jpg',
    ifImage: true,
  },
  {
    img: 'https://static.ckjhk.com/ckj-image/ef1c3b8cd6ba.svg',
    ifImage: false,
  },
]

const fillingsPhaseList = [
  {
    id: 1,
    title: '1.脫鈣（初期蛀牙）',
    text: '出現白色斑點，牙齒表面粗糙',
    method: '治療方法：氟化治療 ',
    img: 'https://static.ckjhk.com/ckj-image/b401d219c9ff.png',
    orientationImage: 'https://static.ckjhk.com/ckj-image/d021a34300ad.png',
  },
  {
    id: 2,
    title: '2.外層琺瑯質受損',
    text: '牙齒出現黑色斑點或小洞',
    method: '治療方法：補牙',
    img: 'https://static.ckjhk.com/ckj-image/b67a31009914.png',
    orientationImage: 'https://static.ckjhk.com/ckj-image/299cb29a709e.png',
  },
  {
    id: 3,
    title: '3.內層象牙質受損',
    text: '牙齒對冷熱或甜食敏感',
    method: '治療方法：補牙',
    img: 'https://static.ckjhk.com/ckj-image/b67a31009914.png',
    orientationImage: 'https://static.ckjhk.com/ckj-image/6abc46d564e1.png',
  },
  {
    id: 4,
    title: '4.牙髓及神經受損',
    text: '持續性的疼痛，牙肉紅腫 ',
    method: '治療方法：根管治療、牙冠修復',
    img: 'https://static.ckjhk.com/ckj-image/2fba56d1246c.png',
    orientationImage: 'https://static.ckjhk.com/ckj-image/1b48ab71c33e.png',
  },
  {
    id: 5,
    title: '5.殘根',
    text: '牙冠部分極度損壞，僅剩牙根',
    method: '治療方法：拔牙及種植牙',
    img: 'https://static.ckjhk.com/ckj-image/1665fbffc03b.png',
    orientationImage: 'https://static.ckjhk.com/ckj-image/06994d1f1eff.png',
  },
]
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
              <div>美國樹脂補牙</div>
              <div>
                <img src="~/assets/images/2025031311165802.svg" alt="" />
              </div>
            </div>
            <div class="content-subscribe">
              <div>其他物料</div>
              <div>
                <img src="~/assets/images/2025031311165801.svg" alt="" />
              </div>
            </div>
          </div>
        </div>
      </template>
    </MobileHeaderV2>
    <PagePcBannerNoHomeV2 v-if="windowWidth > 768" :headerConfig="headerConfig">
      <template #xxxxxxxxxxx-home>
        <div class="banner-in-box">
          <div class="banner-image">
            <img
              src="https://static.ckjhk.com/ckj-image/f0f71d7dd9c6.webp"
              alt=""
              loading="lazy"
            />
          </div>
          <div class="banner-content" style="display: flex">
            <div class="content-title">網上預約限定優惠</div>
            <div class="content-price">
              <div>美國樹脂補牙</div>
              <div>
                <img src="~/assets/images/2025031311165802.svg" alt="" />
              </div>
            </div>
            <div class="content-subscribe">
              <div>其他物料</div>
              <div>
                <img src="~/assets/images/2025031311165801.svg" alt="" />
              </div>
            </div>
          </div>
        </div>
      </template>
    </PagePcBannerNoHomeV2>
    <div class="fillings">
      <section class="ckj-container fillings-key-points">
        <div class="d-flex flex-row align-items-end subheading">
          <span>考慮補牙時的</span><span>3大重點</span>
        </div>
        <div class="fillings-key-points-content">
          <div>
            <div>
              <img
                src="https://static.ckjhk.com/ckj-image/2a94410bde53.svg"
                alt=""
              />
            </div>
            <div>
              <p>
                樹脂材料可調配成牙齒自然色，比金屬填料更美觀，尤其適合前牙。
              </p>
            </div>
          </div>
          <div>
            <div>
              <img
                src="https://static.ckjhk.com/ckj-image/18942d393901.svg"
                alt=""
              />
            </div>
            <div>
              <p>
                樹脂填料能直接粘附牙齒，可保留更多天然牙結構，減少移除牙體。
              </p>
            </div>
          </div>
          <div>
            <div>
              <img
                src="https://static.ckjhk.com/ckj-image/be84c8e60794.svg"
                alt=""
              />
            </div>
            <div>
              <p>
                樹脂填充物不含金屬，適合對金屬敏感或擔心汞合金健康影響的人。
              </p>
            </div>
          </div>
        </div>
      </section>
      <section class="ckj-container fillings-materiel">
        <div class="d-flex flex-row align-items-end subheading">
          <span>4大推薦</span><span>補牙物料</span>
        </div>
        <div class="fillings-materiel-content">
          <div class="fillings-materiel-content-title">網上預約專享</div>
          <div class="fillings-materiel-content-lists">
            <div>
              <div class="fillings-materiel-content-lists-item">
                <div>美國常規樹脂填充</div>
                <div>
                  <div>
                    <div>
                      <div>耐用度</div>
                      <div>
                        <img
                          src="https://static.ckjhk.com/ckj-image/stars2.png"
                          alt=""
                        />
                      </div>
                    </div>
                    <div>
                      <div>美觀度</div>
                      <div>
                        <img
                          src="https://static.ckjhk.com/ckj-image/stars3.png"
                          alt=""
                        />
                      </div>
                    </div>
                  </div>
                  <div>
                    <div>原價 ¥300/顆</div>
                    <div>
                      <img
                        src="https://static.ckjhk.com/ckj-image/00582315ff51.svg"
                        alt="美國常規樹脂填充"
                      />
                    </div>
                  </div>
                </div>
              </div>
              <div class="fillings-materiel-content-lists-item">
                <div>美國聲波樹脂填充 (一般補牙)</div>
                <div>
                  <div>
                    <div>
                      <div>耐用度</div>
                      <div>
                        <img
                          src="https://static.ckjhk.com/ckj-image/stars4.png"
                          alt=""
                        />
                      </div>
                    </div>
                    <div>
                      <div>美觀度</div>
                      <div>
                        <img
                          src="https://static.ckjhk.com/ckj-image/stars4.png"
                          alt=""
                        />
                      </div>
                    </div>
                  </div>
                  <div>
                    <div>原價 ¥550/顆</div>
                    <div>
                      <img
                        src="https://static.ckjhk.com/ckj-image/096c1081c305.svg"
                        alt="美國聲波樹脂填充 (一般補牙)"
                      />
                    </div>
                  </div>
                </div>
              </div>
              <div class="fillings-materiel-content-lists-item">
                <div>超強納米樹脂填充 (大牙)</div>
                <div>
                  <div>
                    <div>
                      <div>耐用度</div>
                      <div>
                        <img
                          src="https://static.ckjhk.com/ckj-image/stars5.png"
                          alt=""
                        />
                      </div>
                    </div>
                    <div>
                      <div>美觀度</div>
                      <div>
                        <img
                          src="https://static.ckjhk.com/ckj-image/stars4.png"
                          alt=""
                        />
                      </div>
                    </div>
                  </div>
                  <div>
                    <div>原價 ¥800/顆</div>
                    <div>
                      <img
                        src="https://static.ckjhk.com/ckj-image/096c1081c305.svg"
                        alt="超強納米樹脂填充 (大牙)"
                      />
                    </div>
                  </div>
                </div>
              </div>
              <div class="fillings-materiel-content-lists-item">
                <div>美學分層樹脂修復 (門牙、前牙)</div>
                <div>
                  <div>
                    <div>
                      <div>耐用度</div>
                      <div>
                        <img
                          src="https://static.ckjhk.com/ckj-image/stars5.png"
                          alt=""
                        />
                      </div>
                    </div>
                    <div>
                      <div>美觀度</div>
                      <div>
                        <img
                          src="https://static.ckjhk.com/ckj-image/stars5.png"
                          alt=""
                        />
                      </div>
                    </div>
                  </div>
                  <div>
                    <div>原價 ¥1500/顆</div>
                    <div>
                      <img
                        src="https://static.ckjhk.com/ckj-image/096c1081c305.svg"
                        alt="美學分層樹脂修復 (門牙、前牙)"
                      />
                    </div>
                  </div>
                </div>
              </div>
            </div>
            <div>
              <img
                class="d-none d-md-block"
                src="https://static.ckjhk.com/ckj-image/2031cae320a4.svg"
                alt="趋势"
              />
              <img
                class="d-md-none"
                src="https://static.ckjhk.com/ckj-image/a5fd0197ded9.svg"
                alt="趋势"
              />
            </div>
          </div>
          <div class="fillings-materiel-content-btn">
            以上優惠只限網上預約客戶
          </div>
        </div>
      </section>
      <section class="ckj-container fillings-compare">
        <div class="d-flex flex-row align-items-end subheading">
          <span>考慮補牙時的</span><span>3大重點</span>
        </div>
        <div class="fillings-compare-content">
          <div class="fillings-compare-content-table">
            <div></div>
            <div>複合樹脂</div>
            <div>銀汞合金</div>
            <div></div>
            <div>
              <img
                src="https://static.ckjhk.com/ckj-image/4da033c70187.png"
                alt=""
              />
            </div>
            <div>
              <img
                src="https://static.ckjhk.com/ckj-image/2ab611c9dd74.png"
                alt=""
              />
            </div>
            <div>特性</div>
            <div>主要修復牙齒形狀</div>
            <div>修補小大臼齒的蛀牙</div>
            <div>優點</div>
            <div>
              <ul>
                <li>美觀，色澤近似天然牙齒</li>
                <li>較易粘合牙釉質</li>
              </ul>
            </div>
            <div>
              <ul>
                <li>堅固，能承受較大咬合力</li>
                <li>耐用，不易磨損</li>
              </ul>
            </div>
            <div>缺點</div>
            <div>強度遜於銀汞合金</div>
            <div>氧化後呈銀黑色，影響美觀</div>
          </div>
        </div>
      </section>
      <section class="ckj-container fillings-step">
        <div class="fillings-step-title">\ <i>補牙5步曲</i> /</div>
        <div class="fillings-step-content">
          <div
            class="fillings-step-item"
            v-for="(item, index) in implantStepList.slice(0, 5)"
            :key="index"
          >
            <div>{{ item.id }}</div>
            <div>
              <img :src="item.img" :alt="item.title" />
            </div>
            <div>{{ item.title }}</div>
          </div>
          <div class="fillings-step-item-last">
            <img :src="implantStepList[5].img" alt="" />
          </div>
        </div>
      </section>
      <section class="ckj-container fillings-cause">
        <div class="d-flex flex-row align-items-end subheading">
          <span>常見</span><span>蛀牙成因</span>
        </div>
        <div class="fillings-cause-content">
          <div class="d-lg-none">
            <div>
              <img
                src="https://static.ckjhk.com/ckj-image/8bc77d771ab2.png"
                alt=""
              />
            </div>
            <div><span>常吃黏性、</span><br /><span>高糖份食物</span></div>
          </div>
          <div>
            <div>
              <img
                src="https://static.ckjhk.com/ckj-image/8eed78768218.png"
                alt=""
              />
            </div>
            <div><span>不當口腔</span><br /><span>衛生習慣</span></div>
          </div>
          <div>
            <div>
              <img
                src="https://static.ckjhk.com/ckj-image/f8fa18191bec.png"
                alt=""
              />
            </div>
            <div><span>藥物或手術</span><br /><span>致唾液減少</span></div>
          </div>
          <div>
            <div>
              <img
                src="https://static.ckjhk.com/ckj-image/bc1d758eb55e.png"
                alt=""
              />
            </div>
            <div><span>牙齒擁擠</span><br /><span>清潔困難</span></div>
          </div>
        </div>
      </section>

      <section class="ckj-container fillings-phase">
        <div class="d-flex flex-row align-items-end subheading">
          <span>蛀牙5個階段</span><span>及對應治療方法</span>
        </div>
        <div class="fillings-phase-content">
          <div
            class="fillings-phase-content-item"
            v-for="item in fillingsPhaseList"
            :key="item.id"
          >
            <div class="fillings-phase-content-item-l">
              <img :src="item.orientationImage" :alt="item.title" />
            </div>
            <div class="fillings-phase-content-item-r">
              <div class="fillings-phase-content-item-text">
                <div>{{ item.title }}</div>
                <div>{{ item.text }}</div>
                <div>{{ item.method }}</div>
              </div>
              <div class="fillings-phase-content-item-float">
                <img :src="item.img" :alt="item.title" />
              </div>
            </div>
          </div>
        </div>
      </section>
      <section class="ckj-container fillings-prevent-tooth-decay">
        <div class="d-flex flex-row align-items-end subheading">
          <span>預防蛀牙</span><span>方法</span>
        </div>
        <div class="fillings-prevent-tooth-decay-content">
          <div>
            <div>
              <img
                src="https://static.ckjhk.com/ckj-image/65b2db68a05a.png"
                alt=""
              />
            </div>
            <div>定期口腔檢查</div>
          </div>
          <div>
            <div>
              <img
                src="https://static.ckjhk.com/ckj-image/8eed78768218.png"
                alt=""
              />
            </div>
            <div>定期刷牙</div>
          </div>
          <div>
            <div>
              <img
                src="https://static.ckjhk.com/ckj-image/d333d87febb7.png"
                alt=""
              />
            </div>
            <div>
              使用牙線<br class="d-md-none" />或牙<i class="d-md-none">間</i>刷
            </div>
          </div>
          <div>
            <div>
              <img
                src="https://static.ckjhk.com/ckj-image/fb3a2fe90510.png"
                alt=""
              />
            </div>
            <div>使用漱口水</div>
          </div>
          <div>
            <div>
              <img
                src="https://static.ckjhk.com/ckj-image/8bc77d771ab2.png"
                alt=""
              />
            </div>
            <div>控制糖分攝入</div>
          </div>
          <div>
            <div>
              <img
                src="https://static.ckjhk.com/ckj-image/50e42d71bf1e.png"
                alt=""
              />
            </div>
            <div>避免咀嚼硬物</div>
          </div>
        </div>
      </section>
      <section class="ckj-container fillings-problem">
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
    left: 48%;
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
    left: 40%;
    top: 55%;
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
      font-size: 1.7442vw;
      font-style: normal;
      font-weight: 900;
      line-height: 2.2222vw; /* 114.286% */
      letter-spacing: 0.29165vw;
      justify-content: center;
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
        top: -0.9vw;
      }

      & > div:nth-child(2) {
        width: 3.54165vw;
        & > svg {
          width: 100%;
          height: 100%;
          object-fit: cover;
        }
      }
    }
    .content-subscribe {
      box-sizing: border-box;
      padding: 0;
      border-radius: 0px 0px 10px 10px;
      background: var(--White, #fff);
      box-shadow: 0px 4px 4px rgba(77, 77, 77, 0.2);
    }
  }

  .fillings-key-points {
    box-sizing: border-box;
    padding: 30px 0;
    margin-top: 45px;
    .fillings-key-points-content {
      margin-top: 30px;
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 0 30px;
      & > div {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 20px 0;
        & > div:nth-child(1) {
          & > img {
            filter: drop-shadow(0 0 10px rgba(0, 0, 0, 0.5));
          }
        }
        & > div:nth-child(2) {
          p {
            color: #000;
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
  }
  .fillings-materiel {
    box-sizing: border-box;
    padding: 30px 0;
    .fillings-materiel-content {
      display: flex;
      flex-direction: column;
      align-items: center;
      .fillings-materiel-content-title {
        color: #000;
        text-align: center;
        font-family: 'Noto Sans TC';
        font-size: 20px;
        font-style: normal;
        font-weight: 700;
        line-height: 160%; /* 32px */
        letter-spacing: 2px;
        margin: 20px auto;
      }
      .fillings-materiel-content-lists {
        display: flex;
        justify-content: space-between;
        & > div:nth-child(1) {
          display: flex;
          flex-direction: column;
          align-items: center;
          gap: 20px 0;
        }
        & > div:nth-child(2) {
          box-sizing: border-box;
          padding-top: 60px;
        }
        .fillings-materiel-content-lists-item {
          display: flex;
          flex-direction: column;
          gap: 0 0;
          & > div:nth-child(1) {
            color: var(--White, #fff);
            font-family: 'Noto Sans HK';
            font-size: 24px;
            font-style: normal;
            font-weight: 700;
            line-height: normal;
            letter-spacing: 2.4px;
            box-sizing: border-box;
            padding: 5px 30px;
            border-radius: 20px;
            background: var(--Blue-Deep, #00aeff);
            width: fit-content;
          }
          & > div:nth-child(2) {
            display: flex;
            gap: 0 110px;
            align-items: flex-end;
            & > div:nth-child(2) {
              display: flex;
              align-items: flex-end;
              & > div:nth-child(1) {
                color: var(--Grey-Deep, #4d4d4d);
                text-align: right;
                font-family: 'Noto Sans HK';
                font-size: 24px;
                font-style: normal;
                font-weight: 700;
                line-height: 160%; /* 38.4px */
                position: relative;
              }
              & > div:nth-child(1)::after {
                content: '';
                width: 100%;
                height: 2px;
                position: absolute;
                top: 25%;
                left: 50%;
                transform: rotate(350deg) translate(-50%, -50%);
                background: #4d4d4d;
              }
              & > div:nth-child(2) {
                position: relative;
                bottom: -14px;
                width: 129px;
                height: auto;
                & > img {
                  width: 100%;
                  height: 100%;
                  object-fit: cover;
                }
              }
            }
            & > div:nth-child(1) {
              display: flex;
              flex-direction: column;
              gap: 4px 0;
              & > div {
                display: flex;
                align-items: center;
                gap: 0 10px;
                & > div:nth-child(1) {
                  color: var(--Grey-Dark, #333);
                  font-family: 'Noto Sans TC';
                  font-size: 20px;
                  font-style: normal;
                  font-weight: 700;
                  line-height: 160%; /* 32px */
                  letter-spacing: 2px;
                }
                & > div:nth-child(2) {
                  width: 136px;
                  height: 24px;
                  & > img {
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
      .fillings-materiel-content-lists-item:nth-child(2),
      .fillings-materiel-content-lists-item:nth-child(3) {
        & > div:nth-child(1) {
          background: var(--Brand-Color, #f8298a);
        }
      }
      .fillings-materiel-content-btn {
        margin-top: 35px;
        color: var(--White, #fff);
        text-align: justify;
        font-family: 'Noto Sans HK';
        font-size: 30px;
        font-style: normal;
        font-weight: 700;
        line-height: normal;
        letter-spacing: 3px;
        background: var(--Brand-Color, #f8298a);
        box-sizing: border-box;
        padding: 5px 20px 3px 30px;
        border-radius: 30px;
        position: relative;
      }

      .fillings-materiel-content-btn::after {
        content: '';
        position: absolute;
        top: 50%;
        left: -40px;
        transform: translateY(-50%);
        border: none !important;
        width: 61px;
        height: 60px;
        border: 10px solid #f8298a;
        background: url('https://static.ckjhk.com/ckj-image/2e53d06edd29.png')
          no-repeat;
        background-size: contain;
        z-index: 3;
      }
    }
  }

  .fillings-compare {
    box-sizing: border-box;
    padding: 30px 0;
    .fillings-compare-content-table {
      margin-top: 70px;
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      & > div {
        display: flex;
        align-items: center;
        justify-content: center;
        color: var(--Grey-Deep, #4d4d4d);
        text-align: center;
        font-family: 'Noto Sans HK';
        font-size: 18px;
        font-style: normal;
        font-weight: 400;
        line-height: 200%; /* 36px */
        letter-spacing: 1.8px;
        ul {
          li {
            list-style: disc;
          }
        }
      }
      & > div:nth-child(3n + 2) {
        border-right: 7px solid #f8298a;
        border-left: 7px solid #f8298a;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        width: 380px;
      }
      & > div:nth-child(6),
      & > div:nth-child(5) {
        padding: 0 !important;
        & > img {
          width: 100%;
          height: 100%;
          object-fit: cover;
        }
      }
      & > div:nth-child(2) {
        border-radius: 10px 10px 0 0;
        border-top: 7px solid #f8298a;
        border-radius: 10px 10px 0px 0px;
        background: var(--Brand-Color, #f8298a);
        position: relative;
      }

      & > div:nth-child(2)::after {
        content: '\\  最常用 /';
        color: var(--Brand-Color, #f8298a);
        text-align: center;
        font-family: 'Noto Sans HK';
        font-size: 28px;
        font-style: normal;
        font-weight: 700;
        line-height: normal;
        position: absolute;
        top: -150%;
        left: 52%;
        transform: translateX(-50%);
      }
      & > div:nth-child(2)::before {
        content: '';
        position: absolute;
        top: -24px;
        left: 50%;
        transform: translateX(-50%);
        width: 44px;
        height: 28px;
        background: url(~/assets/images/group3910.svg) no-repeat;
        background-size: contain;
        z-index: 1;
      }

      & > div:nth-child(3) {
        border-radius: 10px 10px 0px 0px;
        border-top: 3px solid var(--Grey-Lightest, #f2f2f2);
        background: var(--Blue-Deep, #00aeff);
      }
      & > div:nth-child(2),
      & > div:nth-child(3) {
        color: var(--White, #fff);
        text-align: center;
        font-family: 'Noto Sans HK';
        font-size: 24px;
        font-style: normal;
        font-weight: 700;
        line-height: normal;
        letter-spacing: 2.4px;
        box-sizing: border-box;
        padding: 5px 0;
      }
      & > div:nth-child(14) {
        border-radius: 0 0 10px 10px;
        border-bottom: 7px solid #f8298a;
      }
      & > div:nth-child(3n + 1) {
        background: var(--Brand-Color, #f8298a);

        color: var(--White, #fff);
        text-align: center;
        font-family: 'Noto Sans HK';
        font-size: 18px;
        font-style: normal;
        font-weight: 700;
        line-height: 200%; /* 36px */
        letter-spacing: 1.8px;
        box-sizing: border-box;
        padding: 10px 0;
      }
      & > div:nth-child(3n + 3) {
        border-right: 3px solid var(--Grey-Lightest, #f2f2f2);
      }
      & > div:nth-child(1),
      & > div:nth-child(4) {
        background: transparent;
      }

      & > div:nth-child(7) {
        border-radius: 10px 0px 0px 0px;
      }
      & > div:nth-child(13) {
        border-radius: 0px 0px 0px 10px;
        box-sizing: border-box;
        margin-bottom: 5px;
      }
      & > div:nth-child(7),
      & > div:nth-child(8),
      & > div:nth-child(9),
      & > div:nth-child(10),
      & > div:nth-child(11),
      & > div:nth-child(12) {
        position: relative;
      }
      & > div:nth-child(8)::after,
      & > div:nth-child(9)::after,
      & > div:nth-child(11)::after,
      & > div:nth-child(12)::after {
        content: '';
        position: absolute;
        left: auto;
        bottom: 0;
        right: 0;
        width: 100%;
        background: #f3f3f3;
        height: 3px;
      }
      & > div:nth-child(7)::after,
      & > div:nth-child(10)::after {
        content: '';
        position: absolute;
        left: 0;
        bottom: 0;
        width: 100%;
        height: 3px;
        background: #e5e7eba2;
      }
      & > div:nth-child(15) {
        border-bottom: 3px solid var(--Grey-Lightest, #f2f2f2);
      }
    }
  }
  .fillings-step {
    box-sizing: border-box;
    padding: 30px 0;
    .fillings-step-title {
      color: var(--Grey-Deep, #4d4d4d);
      text-align: center;
      font-family: 'Noto Sans HK';
      font-size: 30px;
      font-style: normal;
      font-weight: 700;
      line-height: normal;
      letter-spacing: 3px;
      & > i {
        color: var(--Brand-Color, #f8298a);
        font-family: 'Noto Sans HK';
        font-size: 30px;
        font-style: normal;
        font-weight: 700;
        line-height: normal;
        letter-spacing: 3px;
      }
    }
    .fillings-step-content {
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
          position: relative;
        }
        & > div:nth-child(2)::after {
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
          text-align: center;
        }
      }
    }
    .fillings-step-item:nth-child(5) {
      & > div:nth-child(2)::after {
        content: none;
      }
    }
    .fillings-step-item-last {
      display: flex;
      align-items: center;
      justify-content: center;
    }
  }

  .fillings-cause {
    box-sizing: border-box;
    padding: 30px 0;
    .fillings-cause-content {
      margin-top: 20px;
      display: flex;
      justify-content: center;
      gap: 0 18px;
      & > div {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        position: relative;
        & > div:nth-child(2) {
          color: var(--Grey-Dark, #333);
          text-align: center;
          font-family: 'Noto Sans HK';
          font-size: 18px;
          font-style: normal;
          font-weight: 400;
          line-height: 150%; /* 27px */
          letter-spacing: 1.8px;
        }
      }
    }
  }

  .fillings-phase {
    box-sizing: border-box;
    padding: 30px 0;
    .fillings-phase-content {
      max-width: 725px;
      margin: 0 auto;
      box-sizing: border-box;
      padding: 25px 0 0;
      & > div {
        box-sizing: border-box;
        padding: 10px 0;
      }
      .fillings-phase-content-item {
        position: relative;
        display: flex;
        align-items: center;
        box-sizing: border-box;
        padding: 0 16px 0 133px;
        justify-content: space-between;
        .fillings-phase-content-item-l {
          background: url('https://static.ckjhk.com/ckj-image/d1d86bf9ce38.png')
            no-repeat;
          background-size: contain;
          width: 125.177px;
          height: 148.648px;
          left: 8px;
          top: 0;
          position: absolute;
          box-sizing: border-box;
          padding: 36px 18px 24px;
          & > img {
            width: 100%;
            height: 100%;
            object-fit: contain;
          }
        }
        .fillings-phase-content-item-r {
          .fillings-phase-content-item-text {
            & > div:nth-child(1) {
              border-radius: 0px 277.457px 277.457px 0px;
              background: var(--Brand-Color, #f8298a);
              box-sizing: border-box;
              padding: 10px 30px;
              color: var(--White, #fff);
              font-family: 'Noto Sans HK';
              font-size: 24px;
              font-style: normal;
              font-weight: 700;
              line-height: normal;
              letter-spacing: 2.4px;
              margin-bottom: 12px;
              width: fit-content;
            }
            & > div:nth-child(2),
            & > div:nth-child(3) {
              padding-left: 30px;
            }
            & > div:nth-child(2) {
              color: var(--Grey-Dark, #333);
              font-family: 'Noto Sans HK';
              font-size: 20px;
              font-style: normal;
              font-weight: 400;
              line-height: 160%; /* 32px */
              letter-spacing: 4px;
            }
            & > div:nth-child(3) {
              color: var(--Brand-Color, #f8298a);
              font-family: 'Noto Sans HK';
              font-size: 20px;
              font-style: normal;
              font-weight: 400;
              line-height: 160%;
              letter-spacing: 4px;
            }
          }
          border-radius: 0px 27.746px 0px 0px;
          box-sizing: border-box;
          padding: 15px 16px 15px 0;
          background: var(
            --Pale-pink-Grad-Reversed,
            linear-gradient(
              0deg,
              rgba(255, 255, 255, 0) 0%,
              var(--Pink-Pale, #ffe9ec) 100%
            )
          );
          display: flex;
          align-items: flex-start;
          width: 100%;
          justify-content: space-between;
          .fillings-phase-content-item-float {
            width: 131.775px;
            height: 131.775px;
            position: relative;
            & > img {
              width: 100%;
              height: 100%;
              object-fit: contain;
            }
          }
          .fillings-phase-content-item-float::after {
            content: '';
            position: absolute;
            top: 0;
            left: -43px;
            background: url(~/assets/images/2025032614245601.svg) no-repeat;
            width: 43px;
            height: 46px;
            background-size: contain;
          }
        }
      }
    }
  }

  .fillings-prevent-tooth-decay {
    box-sizing: border-box;
    padding: 30px 0;
    .fillings-prevent-tooth-decay-content {
      margin-top: 20px;
      display: flex;
      gap: 0 7px;
      & > div {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;

        & > div:nth-child(1) {
          box-sizing: border-box;
          padding: 0 20px;
          & > img {
            width: 100%;
            height: 100%;
            object-fit: contain;
          }
        }
        & > div:nth-child(2) {
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

  .fillings-problem {
    :deep(.problem) {
      margin-top: 0;
      box-sizing: border-box;
      padding: 30px 28px;
    }
  }

  @keyframes btntestafterAnima {
    0% {
      width: 90%;
      height: 90%;
      border: 10px solid #f8298a;
    }
    19% {
      border: 10px solid #f8298abf;
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
}

@media screen and (max-width: 991px) {
  .fillings {
    max-width: 100vw;
    overflow-x: hidden;
  }
  .fillings-key-points {
    margin: 30px 0;
    .fillings-key-points-content {
      margin-top: 10px;
      display: flex;
      flex-direction: column;
      gap: 21px 0;
      box-sizing: border-box;
      padding: 0 20px;
      & > div {
        display: flex;
        align-items: center;
        gap: 0 15px;
        & > div:nth-child(1) {
          min-width: 53.129px;
          height: 53.129px;
          & > img {
            width: 100%;
            height: 100%;
            object-fit: contain;
          }
        }
        & > div:nth-child(2) {
          color: #000;
          text-align: justify;
          font-family: 'Noto Sans HK';
          font-size: 14px;
          font-style: normal;
          font-weight: 350;
          line-height: 150%; /* 21px */
        }
      }
    }
  }
  .fillings-materiel {
    margin: 30px 0;
    .fillings-materiel-content-title {
      opacity: 0;
      display: none;
    }
    .fillings-materiel-content {
      box-sizing: border-box;
      padding: 0 0 0 20px;
      margin-top: 13.5px;
    }

    .fillings-materiel-content-lists {
      position: relative;
      & > div:nth-child(1) {
        display: flex;
        flex-direction: column;
        gap: 20px 0;
      }
      & > div:nth-child(2) {
        position: absolute;
        top: 0;
        right: -1px;
        width: 56px;
        height: 450px;
        & > img {
          width: 100%;
          height: 100%;
          object-fit: contain;
        }
      }
    }
    .fillings-materiel-content-lists-item {
      display: flex;
      flex-direction: column;
      & > div:nth-child(1) {
        color: var(--White, #fff);
        text-align: right;
        font-family: 'Noto Sans HK';
        font-size: 16px;
        font-style: normal;
        font-weight: 700;
        line-height: normal;
        letter-spacing: 1.6px;
        box-sizing: border-box;
        padding: 3px 15px;
        border-radius: 20px;
        background: var(--Blue-Deep, #00aeff);
        width: fit-content;
      }
      & > div:nth-child(2) {
        display: flex;
        justify-content: space-between;
        box-sizing: border-box;
        padding: 0 40px 0 0;
        & > div:nth-child(1) {
          margin-top: 10px;
          display: flex;
          flex-direction: column;
          gap: 6px 0;
          padding-left: 16px;
          & > div {
            display: flex;
            align-items: center;
            gap: 0 7px;
            & > div:nth-child(1) {
              color: var(--Grey-Dark, #333);
              font-family: 'Noto Sans HK';
              font-size: 12px;
              font-style: normal;
              font-weight: 350;
              line-height: 120%; /* 14.4px */
            }
            & > div:nth-child(2) {
              width: 84px;
              height: 16px;
              & > img {
                width: 100%;
                height: 100%;
                object-fit: contain;
              }
            }
          }
        }
        & > div:nth-child(2) {
          display: flex;
          align-items: flex-end;
          & > div:nth-child(1) {
            color: var(--Grey-Deep, #4d4d4d);
            text-align: right;
            font-family: 'Noto Sans HK';
            font-size: 12px;
            font-style: normal;
            font-weight: 700;
            line-height: 160%; /* 19.2px */
            position: relative;
          }
          & > div:nth-child(1)::after {
            content: '';
            width: 100%;
            height: 2px;
            position: absolute;
            top: 25%;
            left: 50%;
            transform: rotate(351deg) translate(-50%, -50%);
            background: #4d4d4d;
          }
          & > div:nth-child(2) {
            width: 54px;
            height: auto;
            position: relative;
            bottom: -8px;
            & > img {
              width: 100%;
              height: 100%;
              object-fit: contain;
            }
          }
        }
      }
    }
    .fillings-materiel-content-lists-item:nth-child(2),
    .fillings-materiel-content-lists-item:nth-child(4) {
      & > div:nth-child(1) {
        background: var(--Brand-Color, #f8298a);
      }
    }
    .fillings-materiel-content-btn {
      margin-top: 35px;
      color: var(--White, #fff);
      text-align: justify;
      font-family: 'Noto Sans HK';
      font-size: 16px;
      font-style: normal;
      font-weight: 700;
      line-height: 24px; /* 150% */
      letter-spacing: 1.6px;
      box-sizing: border-box;
      padding: 3px 10px 3px 20px;
      background: var(--Brand-Color, #f8298a);
      border-radius: 20px;
      position: relative;
      width: fit-content;
      margin: 35px auto 0;
    }

    .fillings-materiel-content-btn::after {
      content: '';
      position: absolute;
      top: 50%;
      left: -25px;
      transform: translateY(-50%);
      border: none !important;
      width: 43px;
      height: 42px;
      border: 5px solid #f8298a;
      background: url('https://static.ckjhk.com/ckj-image/2e53d06edd29.png')
        no-repeat;
      background-size: contain;
      z-index: 3;
    }
  }

  .fillings-compare {
    box-sizing: border-box;
    padding: 30px 0 0;
    .fillings-compare-content-table {
      margin-top: 55px;
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      box-sizing: border-box;
      padding: 0 15px;
      & > div {
        display: flex;
        align-items: center;
        justify-content: center;
        text-align: center;
        color: var(--Grey-Deep, #4d4d4d);
        font-family: 'Noto Sans HK';
        font-size: 12px;
        font-style: normal;
        font-weight: 350;
        line-height: 150%; /* 18px */
        ul {
          padding-left: 25px;
          li {
            list-style: disc;
            color: var(--Grey-Deep, #4d4d4d);
            font-family: 'Noto Sans HK';
            font-size: 12px;
            font-style: normal;
            font-weight: 350;
            line-height: 150%; /* 18px */
            text-align: left;
          }
        }
      }
      & > div:nth-child(3n + 2) {
        border-right: 3px solid #f8298a;
        border-left: 3px solid #f8298a;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        width: 139.595px;
        box-sizing: border-box;
        padding: 5px 10px;
      }
      & > div:nth-child(3n + 3) {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        width: 139.595px;
        box-sizing: border-box;
        padding: 5px 10px;
        text-align: left;
        border-right: 1px solid var(--Grey-Lightest, #f2f2f2);
      }
      & > div:nth-child(6),
      & > div:nth-child(5) {
        padding: 0 !important;
        & > img {
          width: 100%;
          height: 100%;
          object-fit: cover;
        }
      }
      & > div:nth-child(2) {
        border-radius: 10px 10px 0 0;
        border-top: 3px solid #f8298a;
        border-radius: 10px 10px 0px 0px;
        background: var(--Brand-Color, #f8298a);
        position: relative;
      }
      & > div:nth-child(2)::after {
        content: '\\  最常用 /';
        color: var(--Brand-Color, #f8298a);
        text-align: center;
        font-family: 'Noto Sans HK';
        font-size: 12px;
        font-style: normal;
        font-weight: 700;
        line-height: normal;
        position: absolute;
        top: -125%;
        left: 52%;
        transform: translateX(-50%);
      }
      & > div:nth-child(2)::before {
        content: '';
        position: absolute;
        top: -24px;
        left: 50%;
        transform: translateX(-50%);
        width: 44px;
        height: 29px;
        background: url(~/assets/images/group3910.svg) no-repeat;
        background-size: contain;
        z-index: 1;
      }

      & > div:nth-child(3) {
        border-radius: 10px 10px 0px 0px;
        background: var(--Blue-Deep, #00aeff);
        border-top: 1px solid var(--Grey-Lightest, #f2f2f2);
      }

      & > div:nth-child(2),
      & > div:nth-child(3) {
        color: var(--White, #fff);
        text-align: center;
        font-family: 'Noto Sans HK';
        color: var(--White, #fff);
        text-align: center;
        font-family: 'Noto Sans HK';
        font-size: 16px;
        font-style: normal;
        font-weight: 700;
        line-height: normal;
        letter-spacing: 1.6px;
        box-sizing: border-box;
        padding: 5px 0;
      }

      & > div:nth-child(14) {
        border-radius: 0 0 10px 10px;
        border-bottom: 3px solid #f8298a;
      }
      & > div:nth-child(3n + 1) {
        background: var(--Brand-Color, #f8298a);

        color: var(--White, #fff);
        text-align: center;
        font-family: 'Noto Sans HK';
        font-size: 12px;
        font-style: normal;
        font-weight: 500;
        line-height: 120%; /* 14.4px */
        letter-spacing: 1.8px;
        box-sizing: border-box;
        padding: 10px 0;
        position: relative;
        right: -1px;
      }
      & > div:nth-child(1),
      & > div:nth-child(4) {
        background: transparent;
      }

      & > div:nth-child(7) {
        border-radius: 10px 0px 0px 0px;
      }
      & > div:nth-child(13) {
        border-radius: 0px 0px 0px 10px;
        box-sizing: border-box;
        margin-bottom: 5px;
      }
      & > div:nth-child(7),
      & > div:nth-child(8),
      & > div:nth-child(9),
      & > div:nth-child(10),
      & > div:nth-child(11),
      & > div:nth-child(12) {
        position: relative;
      }
      & > div:nth-child(8)::after,
      & > div:nth-child(9)::after,
      & > div:nth-child(11)::after,
      & > div:nth-child(12)::after {
        content: '';
        position: absolute;
        left: auto;
        bottom: 0;
        right: 0;
        width: 100%;
        background: #f3f3f3;
        height: 3px;
      }
      & > div:nth-child(7)::after,
      & > div:nth-child(10)::after {
        content: '';
        position: absolute;
        left: 0;
        bottom: 0;
        width: 100%;
        height: 3px;
        background: #e5e7eba2;
      }
      & > div:nth-child(15) {
        border-bottom: 1px solid var(--Grey-Lightest, #f2f2f2);
      }
    }
  }

  .fillings-step {
    margin: 30px 0;
    display: flex;
    flex-direction: column;

    .fillings-step-title {
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

    .fillings-step-content {
      margin-top: 20px;
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 7.2vw 4.8vw;
      box-sizing: border-box;
      padding: 0 20px;
      .fillings-step-item {
        position: relative;

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
          top: 50%;
          right: -2vw;
          z-index: -1;
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
          margin-top: 1.33vw;
          text-align: center;
        }
      }
      .fillings-step-item:nth-child(5) {
        & > div:nth-child(2)::after {
          content: none;
        }
      }
      .fillings-step-item-last {
        display: flex;
        align-items: center;
        justify-content: center;
        & > img {
          transform: scale(1.5);
        }
      }
    }
  }
  .fillings-cause {
    margin: 30px 0;
    .fillings-cause-content {
      box-sizing: border-box;
      padding: 0 15px;
      display: flex;
      gap: 0 7px;
      margin-top: 10px;
      & > div {
        display: flex;
        align-items: center;
        flex-direction: column;
        justify-content: center;
        & > div:nth-child(2) {
          span {
            color: var(--Grey-Dark, #333);
            text-align: center;
            font-family: 'Noto Sans HK';
            font-size: 14px;
            font-style: normal;
            font-weight: 500;
            line-height: 150%; /* 21px */
            letter-spacing: 0.7px;
          }
        }
      }
    }
  }
  .fillings-phase {
    margin: 30px 0;
    .fillings-phase-content {
      margin-top: 20px;
      display: flex;
      flex-direction: column;
      box-sizing: border-box;
      padding: 0 12px 0 18px;
    }
    .fillings-phase-content-item {
      display: flex;
      justify-content: space-between;
      position: relative;
    }
    .fillings-phase-content-item-l {
      background: url('https://static.ckjhk.com/ckj-image/d1d86bf9ce38.png')
        no-repeat;
      background-size: contain;
      width: 69px;
      height: 88px;
      left: 0;
      top: 0;
      position: absolute;
      box-sizing: border-box;
      padding: 20.5px 10px 17.5px;
      & > img {
        width: 100%;
        height: 100%;
        object-fit: contain;
      }
    }
    .fillings-phase-content-item-r {
      border-radius: 0px 10px 0px 0px;
      background: var(
        --Pale-pink-Grad-Reversed,
        linear-gradient(
          0deg,
          rgba(255, 255, 255, 0) 0%,
          var(--Pink-Pale, #ffe9ec) 100%
        )
      );
      display: flex;
      align-items: center;
      margin-left: 75px;
      box-sizing: border-box;
      padding: 6px 0 12px;
      width: 90%;
      justify-content: space-between;
    }
    .fillings-phase-content-item-text {
      & > div:nth-child(1) {
        color: var(--White, #fff);
        font-family: 'Noto Sans HK';
        font-size: 16px;
        font-style: normal;
        font-weight: 500;
        line-height: 20px; /* 250% */
        letter-spacing: 1.6px;
        width: fit-content;
        box-sizing: border-box;
        padding: 5px 10px 5px 15px;
        border-radius: 0px 100px 100px 0px;
        background: var(--Brand-Color, #f8298a);
        margin-bottom: 7px;
      }
      & > div:nth-child(2),
      & > div:nth-child(3) {
        padding-left: 10px;
      }
      & > div:nth-child(2) {
        color: var(--Grey-Dark, #333);
        font-family: 'Noto Sans HK';
        font-size: 12px;
        font-style: normal;
        font-weight: 400;
        line-height: 150%; /* 18px */
        letter-spacing: 0.6px;
      }
      & > div:nth-child(3) {
        color: var(--Brand-Color, #f8298a);
        font-family: 'Noto Sans HK';
        font-size: 12px;
        font-style: normal;
        font-weight: 400;
        line-height: 150%;
        letter-spacing: 0.6px;
      }
    }
    .fillings-phase-content-item-float {
      width: 70px;
      height: 70px;
      position: relative;
      right: 0px;
      & > img {
        width: 100%;
        height: 100%;
        object-fit: cover;
      }
    }
    .fillings-phase-content-item:nth-child(4) {
      .fillings-phase-content-item-l {
        padding: 20.5px 0px 17.5px 2px;
        img {
          transform: scale(1.2);
        }
      }
      .fillings-phase-content-item-float {
        width: 83px;
        right: -8px;
        position: relative;
        right: 0px;
        & > img {
          width: 100%;
          height: 100%;
          object-fit: cover;
        }
      }
    }
    .fillings-phase-content-item:nth-child(5) {
      .fillings-phase-content-item-l {
        padding: 20.5px 0px 17.5px;
      }
    }
    .fillings-phase-content-item-float::after {
      content: '';
      position: absolute;
      top: 0;
      left: -10px;
      background: url(~/assets/images/2025032614245601.svg) no-repeat;
      width: 23px;
      height: 24px;
      background-size: contain;
    }
  }
  .fillings-prevent-tooth-decay {
    margin: 30px 0 45px;
    .fillings-prevent-tooth-decay-content {
      margin-top: 10px;
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 45px 25px;
      box-sizing: border-box;
      padding: 0 30px;
      justify-items: center;
      & > div {
        width: 90px;
        height: 90px;
        display: flex;
        align-items: center;
        flex-direction: column;
        & > div:nth-child(1) {
          box-sizing: border-box;
          padding: 10px 8px;
          & > img {
            width: 100%;
            height: 100%;
            object-fit: contain;
          }
        }
        & > div:nth-child(2) {
          color: var(--Grey-Dark, #333);
          text-align: center;
          font-family: 'Noto Sans HK';
          font-size: 14px;
          font-style: normal;
          font-weight: 500;
          line-height: 120%; /* 21px */
          letter-spacing: 0.7px;
          white-space: nowrap;
          i {
            font-style: normal;
          }
        }
      }
    }
  }
  .fillings-problem {
    margin: 50px 0 30px;
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
    left: 48%;
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
    left: 40%;
    top: 55%;
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
      font-size: 1.7442vw;
      font-style: normal;
      font-weight: 900;
      line-height: 2.2222vw; /* 114.286% */
      letter-spacing: 0.29165vw;
      justify-content: center;
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
        top: -0.9vw;
      }

      & > div:nth-child(2) {
        width: 3.54165vw;
        & > svg {
          width: 100%;
          height: 100%;
          object-fit: cover;
        }
      }
    }
    .content-subscribe {
      box-sizing: border-box;
      padding: 0;
      border-radius: 0px 0px 10px 10px;
      background: var(--White, #fff);
      box-shadow: 0px 4px 4px rgba(77, 77, 77, 0.2);
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
    bottom: -60%;
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
    .content-price,
    .content-subscribe {
      min-height: 10.665vw;
      gap: 0 8px;
      padding: 2.65vw;

      & > div:nth-child(1) {
        color: var(--Grey-Dark, #333);
        text-align: right;
        text-shadow: 1.3px 1.333px 1.333px #faeaf2,
          1.33px -1.333px 1.333px #faeaf2, -1.33px 1.333px 1.333px #faeaf2,
          -1.33px -1.333px 1.333px #faeaf2;
        font-family: 'Noto Sans HK';
        font-size: 8.533vw;
        font-style: normal;
        font-weight: 900;
        line-height: 6.23vw;
        letter-spacing: 1.28vw;
      }
      & > div:nth-child(2) {
        width: 13.5vw;
        height: 11.03vw;
        & > svg,
        & > img {
          width: 100%;
          height: 100%;
          object-fit: cover;
        }
      }
    }
    .content-subscribe {
      box-sizing: border-box;
      padding: 0;
      border-radius: 0px 0px 10px 10px;
      background: var(--White, #fff);
      box-shadow: 0px 4px 4px rgba(77, 77, 77, 0.2);
      & > div:nth-child(1) {
        font-size: 6.93vw;
        letter-spacing: 1.065vw;
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
  }
}
</style>