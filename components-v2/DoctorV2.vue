<script lang="ts" setup>
import doctorLists_hk from '~/assets/js/doctor'
import doctorLists_zh from '~/assets/js/doctor_zh'

const doctorObjs = {
  doctorLists_hk,
  doctorLists_zh,
}

const locale = useState<string>('locale.setting')

interface Doctor {
  mbImg: string
  imgUrl: string
  name: string
  text: string
  newJobs: string[]
  dentalProfessionId?: string[]
}

const localeList: Doctor[] = doctorObjs[`doctorLists_${locale.value}`] || []

const props = defineProps({
  // 当前显示的牙科类型
  nowType: {
    type: String,
    default: '',
  },
})

// 牙科类型列表
const typeList = ref([
  { id: '101', name: '種植科' },
  { id: '102', name: '修復科' },
  { id: '103', name: '矯正科' },
  { id: '104', name: '牙髓病科' },
  { id: '105', name: '牙周病科' },
  { id: '106', name: '兒童牙科' },
  { id: '107', name: '口腔頜面外科' },
])

let dentalProfessionCur = ref()

const list = ref<Doctor[]>([])

onMounted(() => {
  handletab2(props.nowType)
})

const handletab2 = (id: string) => {
  console.log(id, 'handletab2')

  dentalProfessionCur.value = id
  filteredData(id)
}
const filteredData = (str: string) => {
  list.value = localeList
    .flat() // 将多维数组扁平化
    .filter((doctor) => doctor.dentalProfessionId?.includes(str))
}
</script>

<template>
  <div class="doctor-v2">
    <div>
      <div
        v-for="(item, index) in typeList"
        :key="index"
        :class="{ active: item.id === dentalProfessionCur }"
        @click="handletab2(item.id)"
      >
        {{ item.name }}
      </div>
    </div>
    <div>
      <div v-for="(doctorItem, index) in list" :key="index">
        <div class="doctor-image">
          <div class="img-box">
            <img
              loading="lazy"
              :srcset="`${doctorItem.mbImg} 768w, ${doctorItem.imgUrl}`"
              :src="doctorItem.imgUrl"
              :alt="doctorItem.name"
              :title="doctorItem.name"
            />
          </div>
          <div class="name">
            <div class="doctor-name">
              <span>{{ doctorItem.name }}</span>
              <span>{{ doctorItem.text }}</span>
            </div>
          </div>
        </div>
        <div class="doctor-content">
          <span>{{ doctorItem.newJobs[0] }}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@media screen and (min-width: 992px) {
}
@media screen and (max-width: 991px) {
  .doctor-v2 {
    & > div:nth-child(1) {
      display: flex;
      display: flex;
    }

    .active {
      color: #fff;
      background: var(--Theme-Color, #fc1682);
    }
  }
}
</style>