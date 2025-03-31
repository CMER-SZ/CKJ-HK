<script lang="ts" setup>
import { useAppState } from '~/stores/appState'
const appState = useAppState()
appState.setDentistryService('wisdom-teeth-extraction')

useHead({
  title: '拔牙 | 智慧齒',
  meta: [
    {
      hid: 'description',
      name: 'description',
      content:
        '愛康健提供拔牙及智慧齒脫除服務，牙齒可能因嚴重蛀壞或崩裂、嚴重牙周病、過度鬆動、不良位置生長導致附近組織受損和感染，或者出現外觀和結構問題，這些情況可能需要進行拔牙治療，並配合進行牙齒矯正。通常情況下，拔牙不需要進行手術，但如果牙齒歪生或非常接近神經，可能需要進行手術式拔牙。',
    },
    {
      hid: 'Keywords',
      name: 'Keywords',
      content:
        '拔牙 智慧齒脫除 脱智慧齒 拔智齒 智慧齒 拔牙除術 拔牙術 剝智慧齒 愛康健 深圳愛康健 深圳專業牙科中心 愛康健醫院 愛康健口腔醫院 深圳愛康健口腔醫院愛康健 CKJ愛康健齒科集團 深圳口腔專科醫院 愛康健齒科集團 深圳牙科醫院牙科服務內地牙科 深圳口腔專科',
    },
  ],
})

const headerConfig = {
  img: 'https://static.ckjhk.com/ckj-image/9c641fef81cf.webp',
  mbImg: 'https://static.ckjhk.com/ckj-image/2e2658a013d0.webp',
  bg: '',
  pageName: 'scaling-and-polishing-test',
  pcText: [],
  mbText: [],
}

const orthodonticsIntroduceData = {
  title: 'pages.dental-service.wisdom-teeth-extraction.introduce.title',
  content: 'pages.dental-service.wisdom-teeth-extraction.introduce.content',
  mbImg: 'https://static.cmereye.com/imgs/2024/05/9afc2dff4411ce29.webp',
  pcImg: 'https://static.cmereye.com/imgs/2024/05/1c3666b062fda8c9.webp',
  tabNavName:
    'pages.dental-service.wisdom-teeth-extraction.introduce.tabNavName',
  pageName: 'wisdom-teeth-extraction',
}

const reasonData = {
  title: 'pages.dental-service.wisdom-teeth-extraction.reason.title',
  text: 'pages.dental-service.wisdom-teeth-extraction.reason.text',
  imgUrl: 'https://static.cmereye.com/imgs/2023/05/44b6fba4b7e68c38.jpg',
  reasonLists: [
    {
      context:
        'pages.dental-service.wisdom-teeth-extraction.reason.lists[0].context',
    },
    {
      context:
        'pages.dental-service.wisdom-teeth-extraction.reason.lists[1].context',
    },
    {
      context:
        'pages.dental-service.wisdom-teeth-extraction.reason.lists[2].context',
    },
    {
      context:
        'pages.dental-service.wisdom-teeth-extraction.reason.lists[3].context',
    },
    {
      context:
        'pages.dental-service.wisdom-teeth-extraction.reason.lists[4].context',
    },
  ],
  pageName: 'wisdom-teeth-extraction',
}

const issueData = {
  title: ['智慧齒可能', '導致的口腔問題：'],
  imgUrl: 'https://static.cmereye.com/imgs/2023/05/c99ca0ddf73edcbc.jpg',
  issueLists: [
    '由於智慧齒生長位置較後，難以清潔，容易積聚牙菌膜，引致蛀牙',
    '當智慧齒出現橫生或斜生情況，鄰近的牙齒會受到壓力，嚴重更會令牙槽骨萎縮，甚至鬆脫',
    '如出現智慧齒阻生情況，牙齒會被牙齦覆蓋，因而令食物渣滓和細菌藏在牙齦和牙冠之間，造成牙齦發炎和腫脹。嚴重更會使整個面頰出現腫脹，進食時亦會感到痛楚，阻生的智慧齒一般需要進行手術方可拔除',
  ],
}

const noteData = {
  title: '療程後注意事項',
  lists: [
    {
      name: '一般需咬緊棉花或紗布約三十分鐘至一小時止血，其間可如常吞口水',
    },
    {
      name: '進食後以溫水或鹽水輕輕漱口，保持傷口清潔',
    },
    {
      name: '避免觸碰傷口上的凝固血塊，引致出血',
    },
    {
      name: '避免食用堅硬和粗糙的食物',
    },
    {
      name: '避免飲用含酒精飲品',
    },
    {
      name: '避免吃過冷或過熱的食物',
    },
    {
      name: '避免大力漱口或吐痰',
    },
  ],
  text: '*拔牙後，傷口有機會出現腫脹，一般會數天後消退，可按醫生處方服藥或以冷敷消腫及紓緩不適。如傷口持續或大量出血，需盡快聯絡醫生，或視乎嚴重程度前往就近急症室求診。',
}

const processData = {
  title: '拔牙及智慧齒脫除過程',
  tabs: ['智慧齒脫除', '手術性脫牙', '非手術性脫牙'],
  context: [
    '拔牙一般無需進行手術，但當牙齒歪生或非常',
    '接近神經，便有可能要進行手術式脫牙',
  ],
  lists: [
    {
      listItem: [
        [
          {
            title: 'Step 1',
            text: '透過口腔檢查及口腔全景X光片，了解智慧齒生長的狀況及準確位置',
            textMb:
              '透過口腔檢查及口腔全景X光片，了解智慧齒生長的狀況及準確位置',
            textIn: '',
          },
          {
            title: 'Step 2',
            text: '注射局部麻醉藥',
            textMb: '注射局部麻醉藥',
            textIn: '',
          },
          {
            title: 'Step 3',
            text: '如智慧齒出現阻生，需把牙齦割開、翻起，將智慧齒切成數個部分再逐一移除',
            textMb:
              '如智慧齒出現阻生，需把牙齦割開、翻起，將智慧齒切成數個部分再逐一移除',
            textIn: '',
          },
        ],
        [
          {
            title: 'Step 4',
            text: '清潔及縫合傷口',
            textMb: '清潔及縫合傷口',
            textIn: '',
          },
          {
            title: 'Step 5',
            text: '手術後腫痛的情況會維持兩至三日，醫生會處方止痛藥和抗生素（需要時服用）舒緩情況，一般約一星期後便完全康復。',
            textMb: '按時服用醫生處方止痛藥和抗生素（如有需要）',
            textIn: '',
          },
        ],
      ],
    },
    {
      listItem: [
        [
          {
            title: 'Step 1',
            text: '注射局部麻醉或全身麻醉藥（特殊情況下）',
            textIn: '',
          },
          {
            title: 'Step 2',
            text: '翻起牙齦',
            textIn: '',
          },
          {
            title: 'Step 3',
            text: '除去部分覆蓋牙齒的牙槽骨，使牙根外露',
            textIn: '',
          },
        ],
        [
          {
            title: 'Step 4',
            text: '把牙齒搖鬆或分割成幾部分取出',
            textIn: '',
          },
          {
            title: 'Step 5',
            text: '縫合傷口',
            textIn: '',
          },
          {
            title: 'Step 6',
            text: '咬緊棉花或紗布止血',
            textIn: '',
          },
        ],
      ],
    },
    {
      listItem: [
        [
          {
            title: 'Step 1',
            text: '局部麻醉',
            textIn: '',
          },
          {
            title: 'Step 2',
            text: '把牙齒搖鬆，拔掉',
            textIn: '',
          },
          {
            title: 'Step 3',
            text: '咬緊棉花或紗布止血',
            textIn: '',
          },
        ],
      ],
    },
  ],
}

const problemData = {
  title: 'pages.dental-service.wisdom-teeth-extraction.problem.title',
  lists: [
    {
      Q: 'pages.dental-service.wisdom-teeth-extraction.problem.lists[0].Q',
      A: 'pages.dental-service.wisdom-teeth-extraction.problem.lists[0].A',
    },
    {
      Q: 'pages.dental-service.wisdom-teeth-extraction.problem.lists[1].Q',
      A: 'pages.dental-service.wisdom-teeth-extraction.problem.lists[1].A',
    },
    {
      Q: 'pages.dental-service.wisdom-teeth-extraction.problem.lists[2].Q',
      A: 'pages.dental-service.wisdom-teeth-extraction.problem.lists[2].A',
    },
    {
      Q: 'pages.dental-service.wisdom-teeth-extraction.problem.lists[3].Q',
      A: 'pages.dental-service.wisdom-teeth-extraction.problem.lists[3].A',
    },
    {
      Q: 'pages.dental-service.wisdom-teeth-extraction.problem.lists[4].Q',
      A: 'pages.dental-service.wisdom-teeth-extraction.problem.lists[4].A',
    },
    {
      Q: 'pages.dental-service.wisdom-teeth-extraction.problem.lists[5].Q',
      A: 'pages.dental-service.wisdom-teeth-extraction.problem.lists[5].A',
    },
    {
      Q: '拔牙的恢復時間？',
      A: '恢復時間因人而異，一般在幾天至一周內逐漸好轉。在術後初期，應避免劇烈運動及食用過硬或過熱的食物，並按照醫師的指示進行口腔護理。',
    },
    {
      Q: '拔牙後要用飲管飲水？',
      A: '這是錯誤的方法，術後數小時內避免用力漱口或吸管飲料，以免影響血塊的形成。建議在家休息並按醫囑服用藥物，如有異常疼痛或出血應立即聯繫我們。',
    },
  ],
}
const point_solution_requires_tooth_extraction = {
  title: '點解需要拔牙',
  lists: [
    {
      name: ['嚴重蛀牙'],
      img: 'https://static.cmereye.com/static/ckj/imgs/wisdom-teeth-extraction/svg1.svg',
    },
    {
      name: ['牙周病'],
      img: 'https://static.cmereye.com/static/ckj/imgs/wisdom-teeth-extraction/svg2.svg',
    },
    {
      name: ['智慧齒問題'],
      img: 'https://static.cmereye.com/static/ckj/imgs/wisdom-teeth-extraction/svg3.svg',
    },
    {
      name: ['牙齒損傷'],
      img: 'https://static.cmereye.com/static/ckj/imgs/wisdom-teeth-extraction/svg4.svg',
    },
    {
      name: ['牙齒矯正', '治療需求'],
      img: 'https://static.cmereye.com/static/ckj/imgs/wisdom-teeth-extraction/svg5.svg',
    },
    {
      name: ['準備假牙'],
      img: 'https://static.cmereye.com/static/ckj/imgs/wisdom-teeth-extraction/svg6.svg',
    },
  ],
  bottomText:
    '拔牙雖然是一個相對直接的手術過程，但只有在無法保存牙齒的情況下才會被考慮。牙科醫生通常會盡一切可能保存自然牙齒，只有在必要時才推薦拔牙。',
}

const wisdom_teeth = {
  title: '智慧齒可能導致的口腔問題',
  lists: [
    {
      name: ['阻生牙齒'],
      text: '智慧齒可能無法完全長出或只部分長出牙齦。這稱為阻生牙。阻生的智慧齒可能長斜或水平長出，對鄰近牙齒造成壓力，導致疼痛或損壞其他牙齒。',
      mbtext:
        '智慧齒可能不完整地長出牙齦，稱為阻生牙。打斜或水平長出的智慧齒可對鄰近牙齒造成壓力，導致疼痛或損壞其他牙齒。',
      img: 'https://static.cmereye.com/static/ckj/imgs/wisdom-teeth-extraction/Vector1.jpg',
    },
    {
      name: ['牙齦炎和感染'],
      text: '部分長出的智慧齒可能在牙齒和牙齦之間形成一個小空隙，這類空隙容易積聚食物殘渣和細菌，導致感染或牙齦炎，稱為周圍冠周炎。',
      mbtext:
        '智慧齒可能在牙齒和牙齦之間形成一個小空隙，這類空隙容易積聚食物殘渣和細菌，導致感染或牙齦炎，稱為周圍冠周炎。',
      img: 'https://static.cmereye.com/static/ckj/imgs/wisdom-teeth-extraction/Vector2.jpg',
    },
    {
      name: ['牙齒擁擠'],
      mbtext:
        '智慧齒可能會對其他牙齒造成壓力，導致原本正常排列的牙齒移動或擁擠，可能妨礙牙齒矯正。',
      text: '智慧齒的長出可能會對牙弓中的其他牙齒施加壓力，導致原本正常排列的牙齒發生移動或擁擠，這可能使得牙齒矯正的效果受到影響。',
      img: 'https://static.cmereye.com/static/ckj/imgs/wisdom-teeth-extraction/Vector3.jpg',
    },
    {
      name: ['囊腫或腫瘤', '的形成'],
      mbtext:
        '在極少數情況下，未能正常長出的智慧齒可能導致囊腫或腫瘤的形成，這會影響到牙齦組織和周圍的骨結構。',
      text: '在極少數情況下，未能正常長出的智慧齒可能導致囊腫或腫瘤的形成，這會影響到牙齦組織和周圍的骨結構。',
      img: 'https://static.cmereye.com/static/ckj/imgs/wisdom-teeth-extraction/Vector4.jpg',
    },
    {
      name: ['難以清潔'],
      mbtext:
        '由於智慧齒位於口腔後部，清潔起來較困難，這可能增加蛀牙和牙周病的風險。',
      text: '由於智慧齒位於口腔後部，清潔起來較困難，這可能增加蛀牙和牙周病的風險。',
      img: 'https://static.cmereye.com/static/ckj/imgs/wisdom-teeth-extraction/Vector5.jpg',
    },
    {
      name: ['慢性疼痛和不適'],
      mbtext:
        '智慧齒可能導致反覆疼痛，或是由於其位置不當造成的咬合問題，進而引起頜骨、頭部或頸部的疼痛。',
      text: '智慧齒可能導致反覆的疼痛，或是由於其位置不當造成的咬合問題，進而引起頜骨、頭部或頸部的疼痛。',
      img: 'https://static.cmereye.com/static/ckj/imgs/wisdom-teeth-extraction/Vector6.jpg',
    },
  ],
  topText: [
    '智慧齒通常在16至25歲間萌出。',
    '由於它們是最後長出的牙齒，有時可能',
    '因為空間不足或位置不正確',
    '而導致多種口腔問題：',
  ],
  bottomText:
    '因為這些潛在問題，牙醫可能會建議在智慧齒尚未造成嚴重問題之前就將它們拔除，尤其是當預見到將來可能發展成更複雜情況時。拔除智慧齒的決定通常基於X光片的評估，\n以及對患者目前和未來口腔健康的考慮。',
}

const process = {
  title: '拔牙及智慧齒脫除過程',
  topText:
    '拔牙一般不需要進行手術，但若牙齒歪生或非常接近神經，則有機會需要進行手術式脫牙。',
  lists: [
    {
      name: '智慧齒脫除',
      img: 'https://static.cmereye.com/static/ckj/imgs/wisdom-teeth-extraction/process1.webp',
      list: [
        {
          text: '透過口腔檢查及口腔全景X光片，了解智慧齒生長的狀況及準確位置',
        },
        {
          text: '注射局部麻醉藥',
        },
        {
          text: '如智慧齒出現阻生，需把牙齦割開、翻起，將智慧齒切成數個部分再逐一移除',
        },
        {
          text: '清潔及縫合傷口',
        },
        {
          text: '手術後腫痛的情況會維持兩至三日，醫生會處方止痛藥和抗生素（需要時服用）舒緩情況，一般約一星期後便完全康復。',
        },
      ],
    },
    {
      name: '手術性脫牙',
      img: 'https://static.cmereye.com/static/ckj/imgs/wisdom-teeth-extraction/process2.webp',
      list: [
        {
          text: '注射局部麻醉或全身麻醉藥（特殊情況下）',
        },
        {
          text: '翻起牙齦',
        },
        {
          text: '除去部分覆蓋牙齒的牙槽骨，使牙根外露',
        },
        {
          text: '把牙齒搖鬆或分割成幾部分取出',
        },
        {
          text: '縫合傷口',
        },
        {
          text: '咬緊棉花或紗布止血',
        },
      ],
    },
    {
      name: '非手術性脫牙',
      img: 'https://static.cmereye.com/static/ckj/imgs/wisdom-teeth-extraction/process3.webp',
      list: [
        {
          text: '局部麻醉',
        },
        {
          text: '把牙齒搖鬆，拔掉',
        },
        {
          text: '咬緊棉花或紗布止血',
        },
      ],
    },
  ],
}
const precautions = {
  title: '療程後注意事項',
  lists: [
    {
      img: 'https://static.cmereye.com/static/ckj/imgs/wisdom-teeth-extraction/Group1.svg',
      text: '一般需咬緊棉花或紗布約三十分鐘至一小時止血，其間可如常吞口水',
      textMb: '咬緊棉花或紗布約0.5-1小時止血',
    },
    {
      img: 'https://static.cmereye.com/static/ckj/imgs/wisdom-teeth-extraction/Group2.svg',
      text: '避免飲用含酒精飲品',
      textMb: '避免飲用酒精飲品',
    },
    {
      img: 'https://static.cmereye.com/static/ckj/imgs/wisdom-teeth-extraction/Group3.svg',
      text: '進食後以溫水或鹽水輕輕漱口，保持傷口清潔',
      textMb: '以溫水或鹽水漱口清潔傷口',
    },
    {
      img: 'https://static.cmereye.com/static/ckj/imgs/wisdom-teeth-extraction/Group4.svg',
      text: '避免吃過冷或過熱的食物',
      textMb: '避免食用過冷或過熱食物',
    },
    {
      img: 'https://static.cmereye.com/static/ckj/imgs/wisdom-teeth-extraction/Group5.svg',
      text: '避免觸碰傷口上的凝固血塊，引致出血',
      textMb: '避免觸碰傷口上的凝固血塊',
    },
    {
      img: 'https://static.cmereye.com/static/ckj/imgs/wisdom-teeth-extraction/Group6.svg',
      text: '避免大力漱口或吐痰',
      textMb: '避免大力漱口或吐痰',
    },
    {
      img: 'https://static.cmereye.com/static/ckj/imgs/wisdom-teeth-extraction/Group7.svg',
      text: '避免食用堅硬和粗糙的食物',
      textMb: '避免食用堅硬和粗糙的食物',
    },
  ],
  bottomText:
    '*拔牙後，傷口有機會出現腫脹，一般會數天後消退，可按醫生處方服藥或以冷敷消腫及紓緩不適。如傷口持續或大量出血，需盡快聯絡醫生，或視乎嚴重程度前往就近急症室求診。',
}

const caseLists = [
  {
    img: 'https://static.cmereye.com/imgs/2024/05/3d2e0abc72e453d0.png',
    name: 'James',
    jos: '大學生',
    context:
      '隻智慧齒成日發炎經常疼痛難眠，聽媽咪話決定係愛康健拔咗智齒，舒服咗好多，之後都會介紹同學去愛康健睇牙。',
  },
  {
    img: 'https://static.cmereye.com/imgs/2024/05/b8a318249a98be4c.png',
    name: '小花',
    jos: '小說作家',
    context:
      '為咗箍牙要拔牙，最初都好驚，但為咗靚無辦法。醫生好溫柔，拔完唔痛。期待一年後牙齒變得整齊。',
  },
  {
    img: 'https://static.cmereye.com/imgs/2024/05/a0c9ad1562da6a8e.png',
    name: '陳伯伯',
    jos: '醫療券使用者',
    context:
      '隻牙已經好鬆就甩，擔心到幾晚訓唔著。呀女帶我睇上深圳睇愛康健，醫生幫我拔牙仲種咗牙，依家安心晒！',
  },
]

let windowWidth = ref(390)
const getWindowWidth = () => {
  windowWidth.value = window.innerWidth
}
onMounted(() => {
  getWindowWidth()
  window.addEventListener('resize', getWindowWidth)
})

// v2 版本data
const serviceList = ref([
  {
    id: 1,
    img: 'https://static.ckjhk.com/ckj-image/4819d18eb167.svg',
    text: '嚴重蛀牙損傷',
  },
  {
    id: 2,
    img: 'https://static.ckjhk.com/ckj-image/bcbc89f69eee.svg',
    text: '牙周病引起<br class="d-md-block" />鬆動牙',
  },
  {
    id: 3,
    img: 'https://static.ckjhk.com/ckj-image/9b9b88a665be.svg',
    text: '阻生齒及埋伏牙',
  },
  {
    id: 4,
    img: 'https://static.ckjhk.com/ckj-image/b30dadf24a65.svg',
    text: '多生齒及畸形牙',
  },
  {
    id: 5,
    img: 'https://static.ckjhk.com/ckj-image/75f293bce905.svg',
    text: '牙齒矯正治療',
  },
  {
    id: 6,
    img: 'https://static.ckjhk.com/ckj-image/83b7b7eb7a0a.svg',
    text: '準備配戴假牙',
  },
])

const wisdomToothContentList = ref([
  {
    name: ['阻生牙齒'],
    text: '智慧齒可能無法完全長出或只部分露出牙齦，稱為阻生牙。阻生智慧齒可能斜長或水平生長，壓迫鄰近牙齒，導致疼痛或損壞。',
    img: 'https://static.ckjhk.com/ckj-image/6818ae4533af.png',
  },
  {
    name: ['牙齦炎和感染'],
    text: '部分長出的智慧齒可能與牙齦間形成空隙，易積聚食物殘渣和細菌，引發感染或牙齦炎，稱為冠周炎。',
    img: 'https://static.ckjhk.com/ckj-image/6e94e560798d.png',
  },
  {
    name: ['牙齒擁擠'],
    text: '智慧齒生長可能擠壓其他牙齒，導致移位或擁擠，影響矯正效果。',
    img: 'https://static.ckjhk.com/ckj-image/c2ace4e9a068.png',
  },
  {
    name: ['囊腫或腫瘤的形成'],
    text: '極少數情況下，未正常長出的智慧齒可能引發囊腫或腫瘤，影響牙齦及周圍骨結構。',
    img: 'https://static.ckjhk.com/ckj-image/3325f7151db3.png',
  },
  {
    name: ['難以清潔'],
    text: '智慧齒位於口腔後部，清潔困難，可能增加蛀牙和牙周病風險。',
    img: 'https://static.ckjhk.com/ckj-image/05ea2cf93583.png',
  },
  {
    name: ['慢性疼痛和不適'],
    text: '智慧齒可能引發反覆疼痛或不當咬合，導致頜骨、頭部或頸部疼痛。',
    img: 'https://static.ckjhk.com/ckj-image/c36395afe128.png',
  },
])

const courseSurgicalExtractionOfTeeth=ref([
  
])
const courseNonSurgicalToothExtraction=ref([])
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
              <div>智慧齒拔除</div>
              <div>
                <img src="~/assets/images/2025031317413701.svg" alt="" />
              </div>
            </div>
            <div class="content-subscribe">經驗醫生團隊，舒適拔牙技術</div>
          </div>
        </div>
      </template>
    </MobileHeaderV2>
    <PagePcBannerNoHome v-if="windowWidth > 768" :headerConfig="headerConfig">
      <template #xxxxxxxxxxx-home>
        <div class="banner-in-box">
          <div class="banner-content" style="display: flex">
            <div class="content-title">網上預約限定優惠</div>
            <div class="content-price">
              <div>智慧齒拔除</div>
              <div>
                <img src="~/assets/images/2025031317413701.svg" alt="" />
              </div>
            </div>
            <div class="content-subscribe">經驗醫生團隊，舒適拔牙技術</div>
          </div>
        </div>
      </template>
    </PagePcBannerNoHome>
    <div class="wisdom-teeth-extraction">
      <section class="ckj-container wisdom-teeth-extraction-service">
        <div class="d-flex flex-row align-items-end subheading">
          <span>拔牙</span><span>服務</span>
        </div>
        <div class="wisdom-service-content">
          <div class="wisdom-service-content-list">
            <div
              v-for="(item, index) in serviceList"
              :key="index"
              class="wisdom-service-content-list-item"
            >
              <div class="wisdom-service-content-list-item-img">
                <img :src="item.img" alt="" />
              </div>
              <div
                class="wisdom-service-content-list-item-text"
                v-html="item.text"
              ></div>
            </div>
          </div>
          <div class="wisdom-service-content-text">
            <p>牙醫會盡一切可能保存自然牙齒，</p>
            <p>只有在無法保存牙齒時才建議拔牙。</p>
          </div>
        </div>
      </section>
      <section class="ckj-container wisdom-teeth-extraction-charge-item">
        <div class="d-flex flex-row align-items-end subheading">
          <span>拔牙</span><span>服務</span>
        </div>
        <div class="charge-item-content">
          <div>
            <div>項目</div>
            <div>價錢</div>
          </div>
          <div>
            <div>普通前牙拔除</div>
            <div>￥200-300/顆</div>
          </div>
          <div>
            <div>普通後牙拔除</div>
            <div>￥300-500/顆</div>
          </div>
          <div>
            <div>阻生牙拔除</div>
            <div>￥800-2,000/顆</div>
          </div>
          <div>
            <div>複雜阻生牙拔除</div>
            <div>￥3,000-5,000/顆</div>
          </div>
        </div>
        <div class="charge-item-btn">
          <div>
            <PageAnimBtnTypeTwo :str="'網上預約優惠'" />
          </div>
          <div>
            <div>智慧齒拔除</div>
            <div>
              <img
                src="~/assets/images/2025031317413701.svg"
                alt="减￥300/颗"
              />
            </div>
          </div>
        </div>
      </section>
      <section class="ckj-container wisdom-teeth-extraction-wisdom-tooth">
        <div class="d-flex flex-row align-items-end subheading">
          <span>智慧齒</span><span>導致的口腔問題</span>
        </div>
        <div class="wisdom-tooth-content">
          <div>
            <p>智慧齒通常在16至25歲間萌出。</p>
            <p>
              由於它們是最後長出的牙齒，可能因為空間不足<br
                class="d-md-block"
              />或位置不正確而導致多種口腔問題：
            </p>
          </div>
          <div class="wisdom-tooth-content-list">
            <div
              class="wisdom-tooth-content-list-item"
              v-for="(item, index) in wisdomToothContentList"
              :key="index"
            >
              <div>
                <div>{{ item.name[0] }}</div>
                <div>{{ item.text }}</div>
              </div>
              <div><img :src="item.img" :alt="item.name[0]" /></div>
            </div>
          </div>
          <div class="wisdom-tooth-content-text">
            <p>
              為避免智慧齒隱患加劇，牙醫可能會建議及早將它<br
                class="d-md-block"
              />們拔除。
            </p>
          </div>
        </div>
      </section>
      <section class="ckj-container wisdom-teeth-course">
        <div class="d-flex flex-row align-items-end subheading">
          <span>拔牙</span><span>過程</span>
        </div>
        <div class="course">
          <div class="course-text">
            拔牙一般無需進行手術，但當牙齒歪生或非常接近<br
              class="d-md-block"
            />神經，便有可能要進行手術式脫牙。
          </div>
          <div>
            <div>
              <div>智慧齒及手術性拔牙</div>
              <div>非手術性拔牙</div>
            </div>
            <div>

            </div>
          </div>
        </div>
      </section>
    </div>
    <!-- <ServiceIntroduce :introduceData="orthodonticsIntroduceData" /> -->
    <!-- <ServiceProblem :problemData="problemData" /> -->
    <serviceCard />
    <BranchAddress />
    <AppointmentFormV2 />
    <FooterV2 />
    <AsideV2 />
  </div>
</template>


<style lang="scss" scoped>
@media screen and(min-width: 992px) {
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
      font-size: 1.927vw;
      font-style: normal;
      font-weight: 900;
      line-height: 2.2222vw; /* 114.286% */
      letter-spacing: 0.29165vw;
      justify-content: center;
      & > div:nth-child(1) {
        position: relative;
        color: var(--Grey-Dark, #333);
        text-align: right;
        text-shadow: 1.3px 1.333px 1.333px #faeaf2,
          1.33px -1.333px 1.333px #faeaf2, -1.33px 1.333px 1.333px #faeaf2,
          -1.33px -1.333px 1.333px #faeaf2;
        font-family: 'Noto Sans HK';
        font-size: 1.927vw;
        font-style: normal;
        font-weight: 900;
        line-height: 2.2222vw; /* 114.286% */
        letter-spacing: 0.29165vw;
        top: auto;
      }

      & > div:nth-child(2) {
        width: 10.252083vw;
        & > svg {
          width: 100%;
          height: 100%;
          object-fit: cover;
        }
      }
    }
    .content-subscribe {
      box-shadow: 0px 5.333px 5.333px rgba(77, 77, 77, 0.2);
      border-radius: 0px 0px 13.333px 13.333px;
      color: var(--Grey-Dark, #333);
      text-align: center;
      text-shadow: 0px 1.111px 1.111px rgba(0, 0, 0, 0.25);
      font-family: 'Noto Sans HK';
      font-size: 1.38890625vw;
      font-style: normal;
      font-weight: 900;
      line-height: 1.157vw; /* 83.333% */
      letter-spacing: 0.1369vw;
    }
  }
}
@media screen and(max-width: 991px) {
  .wisdom-teeth-extraction-service {
    margin: 30px 0;
    .wisdom-service-content {
      display: flex;
      flex-direction: column;
      gap: 18px 0;
      .wisdom-service-content-list {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        justify-items: center;
        gap: 24px 10px;
        box-sizing: border-box;
        padding: 0 15px;
        .wisdom-service-content-list-item {
          display: flex;
          justify-content: center;
          align-items: center;
          flex-direction: column;
          position: relative;
          max-width: 94px;
          .wisdom-service-content-list-item-img {
            width: 94px;
            height: 94px;
            display: flex;
            justify-content: center;
            align-items: center;
          }
          .wisdom-service-content-list-item-text {
            margin-top: 10px;
            color: #000;
            text-align: center;
            font-family: 'Noto Sans HK';
            font-size: 14px;
            font-style: normal;
            font-weight: 350;
            line-height: 150%; /* 21px */
            letter-spacing: 0.7px;
            white-space: nowrap;
            position: absolute;
            top: 75%;
          }
        }
      }
      .wisdom-service-content-text {
        display: flex;
        flex-direction: column;
        align-items: center;
        margin-top: 8px;
        & > p {
          color: var(--Brand-Color, #f8298a);
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
  .wisdom-teeth-extraction-charge-item {
    margin: 30px 0;
    .charge-item-content {
      margin: 15px 15px 0 15px;
      box-sizing: border-box;
      border-radius: 10px;
      overflow: hidden;
      & > div {
        box-sizing: border-box;
        padding: 7px 23px;
        display: flex;
        justify-content: space-between;
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
      & > div:nth-child(odd) {
        background: #fff7f8;
      }
      & > div:nth-child(1) {
        background: var(--Brand-Color, #f8298a);
        border-radius: 10px 10px 0 0;
        & > div {
          color: #fff;
        }
      }
      & > div:last-child {
        border-radius: 0 0 10px 10px;
      }
      box-shadow: 0px 4px 4px 0px rgba(77, 77, 77, 0.2);
    }
    .charge-item-btn {
      margin: 28px 25px 0 20px;
      & > div:nth-child(1) {
        margin-left: 15px;
      }
      :deep(.animbtntypetwo-in) {
        span {
          background: var(--Brand-Color, #f8298a);
          box-shadow: 10px 10px 20px #f8298abf;
          padding: 2px 16px 2px 28px;
          &::after {
            animation: btntestafterAnima 5.6s infinite;
          }
        }
      }
      :deep(.animbtntypetwo-in::after) {
        animation: btntestafterAnima 5.6s infinite;
      }
      :deep(.animbtntypetwo::after) {
        content: '';
        position: absolute;
        top: 50%;
        left: -20px;
        transform: translateY(-50%);
        border: none !important;
        width: 45px;
        height: 45px;
        border: 5px solid #f8298a;
        background: url('https://static.ckjhk.com/ckj-image/f2e85ef51231.svg')
          no-repeat;
        background-size: contain;
        z-index: 3;
      }
      & > div:nth-child(2) {
        margin-top: 10px;
        display: flex;
        align-items: center;
        justify-content: flex-end;
        gap: 0 5px;
        & > div:nth-child(1) {
          color: var(--Brand-Color, #f8298a);
          text-align: center;
          font-family: 'Noto Sans HK';
          font-size: 16px;
          font-style: normal;
          font-weight: 700;
          line-height: normal;
          letter-spacing: 1.6px;
        }
        & > div:nth-child(2) {
          width: 166px;
          height: 49.297px;
          & > img {
            width: 100%;
            height: 100%;
            object-fit: contain;
          }
        }
      }
    }
  }
  .wisdom-teeth-extraction-wisdom-tooth {
    margin: 30px 0;
    .wisdom-tooth-content {
      display: flex;
      flex-direction: column;
      margin-top: 20px;
      & > div:nth-child(1) {
        text-align: center;
        p {
          color: var(--Grey-Deep, #4d4d4d);
          text-align: center;
          font-family: 'Noto Sans HK';
          font-size: 14px;
          font-style: normal;
          font-weight: 500;
          line-height: 150%; /* 21px */
          letter-spacing: 0.7px;
        }
      }
      .wisdom-tooth-content-list {
        box-sizing: border-box;
        padding: 15px 20px;
        display: flex;
        flex-direction: column;
        gap: 6px 0;
        .wisdom-tooth-content-list-item {
          display: flex;
          align-items: center;
          gap: 0 14px;
          box-sizing: border-box;
          padding: 14px 16px;
          background: var(--White, #fff);
          border: 2px solid var(--Theme-Color, #fc1682);
          border-left: 20px solid var(--Theme-Color, #fc1682);
          border-radius: 10px;
          & > div:nth-child(1) {
            & > div:nth-child(1) {
              color: var(--Theme-Color, #fc1682);
              text-align: justify;
              font-family: 'Noto Sans HK';
              font-size: 14px;
              font-style: normal;
              font-weight: 500;
              line-height: 150%; /* 21px */
              letter-spacing: 0.7px;
            }
            & > div:nth-child(2) {
              color: var(--Grey-Deep, #4d4d4d);
              font-family: 'Noto Sans HK';
              font-size: 12px;
              font-style: normal;
              font-weight: 400;
              line-height: 150%;
              letter-spacing: 0.6px;
            }
          }
          & > div:nth-child(2) {
            min-width: 86px;
            height: 86px;
            & > img {
              width: 100%;
              height: 100%;
              object-fit: contain;
              filter: drop-shadow(0px 0px 6px rgba(252, 22, 130, 0.4));
            }
          }
        }
        .wisdom-tooth-content-list-item:nth-child(even) {
          border: 2px solid var(--Blue-Deep, #00aeff);
          border-left: 20px solid var(--Blue-Deep, #00aeff);
          & > div:nth-child(1) {
            & > div:nth-child(1) {
              color: var(--Blue-Deep, #00aeff);
            }
          }
        }
      }
      .wisdom-tooth-content-text {
        box-sizing: border-box;
        padding: 0 20px;
        & > p {
          color: var(--Grey-Deep, #4d4d4d);
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

  .banner-in-box {
    position: absolute;
    bottom: 0;
    left: 0;
    height: 100vw;
    width: 100%;
    z-index: 22;
    box-sizing: border-box;
    padding-bottom: 0;
    top: 0;
    bottom: 0;
    transform: translateY(0px);
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
      font-size: 1.927vw;
      font-style: normal;
      font-weight: 900;
      line-height: 2.2222vw; /* 114.286% */
      letter-spacing: 0.29165vw;
      justify-content: center;
      & > div:nth-child(1) {
        position: relative;
        color: var(--Grey-Dark, #333);
        text-align: right;
        text-shadow: 1.3px 1.333px 1.333px #faeaf2,
          1.33px -1.333px 1.333px #faeaf2, -1.33px 1.333px 1.333px #faeaf2,
          -1.33px -1.333px 1.333px #faeaf2;
        font-family: 'Noto Sans HK';
        font-size: 1.927vw;
        font-style: normal;
        font-weight: 900;
        line-height: 2.2222vw; /* 114.286% */
        letter-spacing: 0.29165vw;
        top: auto;
      }

      & > div:nth-child(2) {
        width: 10.252083vw;
        & > svg {
          width: 100%;
          height: 100%;
          object-fit: cover;
        }
      }
    }
  }
  .banner-content {
    position: relative;
    align-items: flex-start;
    justify-content: flex-end;
    width: 86.665vw;
    left: 50%;
    top: auto;
    bottom: -58%;
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
      min-height: auto;
      gap: 0 8px;
      padding: 2.65vw 0 0 0;
      font-family: 'Noto Sans HK';
      font-size: 4.265vw;
      font-style: normal;
      font-weight: 900;
      line-height: 3.73vw;
      letter-spacing: 0.82vw;
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

      & > div:nth-child(2) {
        width: 40.265vw;
        height: auto;
        & > img {
          width: 100%;
          height: 100%;
          object-fit: contain;
        }
      }
    }
    .content-subscribe {
      padding: 1vw 0 2.65vw 0;
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
