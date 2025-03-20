<template>
  <div>
    <!-- 表单提示 -->
    <div class="popover-container">
      <div id="submit-popover" popover>
        <p>請勾選私隱政策以繼續提交。</p>
      </div>
    </div>

    <!-- 表单提交 -->
    <div class="appointmentForm-table ckj-contrain px-20" id="contactUsFormNav">
      <div class="appointmentForm-table-title">
        <span> <i>AI智能</i>預約及查詢系統 </span>
      </div>
      <form
        id="appointmentForm"
        class="needs-validation"
        :class="{ 'was-validated': wasValidated }"
        novalidate
        @submit.prevent="submitForm"
      >
        <div class="appointmentForm-table-Box d-flex flex-column">
          <!-- 姓名和预约日期 -->
          <div
            class="d-flex justify-content-between appointmentForm-table-Box-name"
          >
            <div class="form-group position-relative">
              <label for="name">姓名:</label>
              <input
                type="text"
                id="name"
                class="form-control"
                v-model="formData.name"
                pattern="^[A-Za-z\u4e00-\u9fa5\s]+$"
                required
                placeholder="請填寫"
              />
              <div class="invalid-feedback">請輸入姓名</div>
            </div>
            <div class="form-group position-relative">
              <label for="appointment-date">預約日期:</label>
              <input
                class="form-control"
                placeholder="請填寫"
                type="date"
                id="appointment-date"
                v-model="formData.appointmentDate"
                required
              />
              <div class="invalid-feedback">請選擇預約日期</div>
            </div>
          </div>

          <!-- 诊症服务 -->
          <div class="form-group position-relative">
            <label for="service-type">診症服務（最多4項）</label>
            <div id="service-buttons" class="d-flex flex-wrap service-buttons">
              <span
                v-for="service in services"
                :key="service"
                class="service-button"
                :class="{ selected: selectedServices.includes(service) }"
                @click="toggleService(service)"
              >
                {{ service }}
              </span>
            </div>
            <div
              class="invalid-feedback selectFeedBack"
              v-if="showServiceError"
            >
              請選擇診症服務
            </div>
          </div>

          <!-- 诊症区域和WhatsApp电话 -->
          <div
            class="d-flex justify-content-start appointmentForm-table-Box-option"
          >
            <div class="form-group position-relative">
              <label for="phone-number">診症區域:</label>
              <div class="custom-phone-input position-relative">
                <select class="area-address w-100" v-model="formData.area">
                  <option value="羅湖區">羅湖區</option>
                  <option value="福田區">福田區</option>
                  <option value="南山區">南山區</option>
                </select>
              </div>
            </div>
            <div class="form-group position-relative">
              <label for="phone-number">WhatsApp電話:</label>
              <div class="custom-phone-input">
                <select
                  class="area-code position-absolute"
                  v-model="formData.areaCode"
                >
                  <option value="+852">+852</option>
                  <option value="+86">+86</option>
                  <option value="+886">+886</option>
                </select>
                <input
                  type="tel"
                  class="position-absolute w-100"
                  id="phone-number"
                  v-model="formData.phoneNumber"
                  maxlength="16"
                  placeholder="請填寫"
                  pattern="\d{8,15}"
                  required
                />
                <div class="invalid-feedback">請填寫正確的號碼</div>
              </div>
            </div>
          </div>

          <!-- 备注 -->
          <div class="form-group position-relative">
            <label for="notes">備注（非必填）</label>
            <textarea
              class="form-control"
              id="notes"
              v-model="formData.notes"
              rows="1"
              placeholder="請填寫"
            ></textarea>
          </div>

          <!-- 复选框 -->
          <div
            class="form-group form-radio-group d-lg-flex justify-content-center align-items-center"
          >
            <div
              class="d-lg-flex flex-wrap justify-content-start align-items-center"
            >
              <label class="form-check p-0 d-flex align-items-center">
                <input
                  class="form-check-input custom-radio"
                  type="checkbox"
                  v-model="formData.careVoucher"
                />
                <span class="form-check-label">使用長者醫療券</span>
              </label>
              <label class="form-check p-0 d-flex align-items-center">
                <input
                  class="form-check-input custom-radio"
                  type="checkbox"
                  v-model="formData.cashCoupon"
                />
                <span class="form-check-label">領取2000元種植牙現金券</span>
              </label>
              <label class="form-check p-0 d-flex align-items-center">
                <input
                  class="form-check-input custom-radio"
                  type="checkbox"
                  v-model="formData.acknowledge"
                  required
                />
                <span class="form-check-label"
                  >本人已閱讀並同意有關<a href=""> 私隱政策</a> 聲明</span
                >
              </label>
            </div>
          </div>

          <!-- 提交按钮 -->
          <button
            type="submit"
            class="Appointment-form-btn mx-auto w-100 d-flex justify-content-center align-items-center"
          >
            <span>立即預約</span>
          </button>
          <p class="text-center form-mobile-tip">
            我們將會在10小時內與您聯絡確認預約詳情
          </p>
        </div>
      </form>
    </div>

    <!-- Spinner 加载动画 -->
    <div
      id="overlay"
      class="position-fixed top-0 start-0 w-100 h-100 bg-white"
      :class="{ 'd-none': !isLoading }"
      style="z-index: 99"
    >
      <div class="d-flex justify-content-center align-items-center h-100">
        <div class="spinner-border" role="status">
          <span class="visually-hidden">加载中...</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const services = ref([
  '種植牙',
  '活動假牙及牙橋',
  '洗牙',
  '補牙',
  '杜牙根(根管治療)',
  '牙冠',
  '拔牙及智慧齒拔除',
  '牙周治療',
  '牙齒美白',
  '瓷牙貼片',
  '箍牙(牙齒矯正)',
  '隱形牙套',
  '兒童牙科',
  '口腔檢查',
  '長者牙科',
])

const selectedServices = ref([])
const formData = ref({
  name: '',
  appointmentDate: '',
  area: '羅湖區',
  areaCode: '+852',
  phoneNumber: '',
  notes: '',
  careVoucher: false,
  cashCoupon: false,
  acknowledge: false,
})

const wasValidated = ref(false)
const showServiceError = ref(false)
const isLoading = ref(false)

const toggleService = (service) => {
  const index = selectedServices.value.indexOf(service)
  if (index === -1) {
    if (selectedServices.value.length >= 4) {
      selectedServices.value.shift()
    }
    selectedServices.value.push(service)
  } else {
    selectedServices.value.splice(index, 1)
  }
}

const submitForm = async () => {
  wasValidated.value = true
  showServiceError.value = selectedServices.value.length === 0

  if (!formData.value.acknowledge) {
    document.getElementById('submit-popover').showPopover()
    return
  }

  if (
    selectedServices.value.length === 0 ||
    !document.getElementById('appointmentForm').checkValidity()
  ) {
    return
  }

  isLoading.value = true

  const fullPhoneNumber = formData.value.areaCode + formData.value.phoneNumber
  const formattedSelectedServices = selectedServices.value.join(',')

  const bodyData = new FormData()
  bodyData.append('name', formData.value.name)
  bodyData.append('appointmentDate', formData.value.appointmentDate)
  bodyData.append('area', formData.value.area)
  bodyData.append('phone', fullPhoneNumber)
  bodyData.append('service', formattedSelectedServices)
  bodyData.append('notes', formData.value.notes)
  bodyData.append('careVoucher', formData.value.careVoucher ? '是' : '否')
  bodyData.append('cashCoupon', formData.value.cashCoupon ? '是' : '否')
  bodyData.append('source', window.location.href)

  try {
    const response = await fetch('https://admin.ckjhk.com/api.php/cms/addmss', {
      method: 'POST',
      body: bodyData,
    })

    if (response.ok) {
      window.location.href = '/SuccessfulForm.html'
    } else {
      alert('提交失败，请检查输入的信息')
    }
  } catch (error) {
    console.error('Error:', error)
    alert('网络错误，请稍后再试')
  } finally {
    isLoading.value = false
  }
}

onMounted(() => {
  const today = new Date().toISOString().split('T')[0]
  document.getElementById('appointment-date').setAttribute('min', today)
})
</script>

<style lang="scss" scoped>
// 表单

.appointmentForm-table {
  padding-top: 30px;
  padding-bottom: 34px;

  &-title {
    text-align: center;
    position: relative;
    i {
      font-style: normal;
    }

    span {
      color: var(--New-Theme-Color, #d2337d);
      text-align: center;
      font-family: 'Noto Sans HK';
      font-size: 26px;
      font-style: normal;
      font-weight: 700;
      line-height: 160%;
      position: relative;

      // &::after {
      //   background: url("https://statichk.cmermedical.com/newCKJ/form-icon-text.avif")
      //     no-repeat;
      //   content: "真人客服回覆";
      //   display: inline-block;
      //   height: 59px;
      //   position: absolute;
      //   right: -50px;
      //   top: -40px;
      //   width: 140px;
      //   color: var(--White, #fff);
      //   font-family: "Noto Sans HK";
      //   font-size: 16px;
      //   font-style: normal;
      //   font-weight: 400;
      //   line-height: 2;
      //   letter-spacing: 1.6px;
      // }
    }

    &::after {
      content: 'Enquiry Form';
      position: absolute;
      left: 50%;
      bottom: -20px;
      transform: translateX(-50%);
      color: var(--Grey-Light, #e6e6e6);
      text-align: center;
      font-family: 'Noto Sans HK';
      font-size: 18px;
      font-style: normal;
      font-weight: 500;
      line-height: 150%; /* 27px */
    }
  }

  &-Box {
    gap: 13px;
    margin-top: 40px;
    .form-group {
      .invalid-feedback {
        position: absolute;
        text-align: right;
        top: 0;
      }

      label {
        color: var(--New-Theme-Color, #d2337d);
        font-family: 'Noto Sans HK';
        font-size: 15px;
        font-style: normal;
        font-weight: 500;
        line-height: 160%;
        letter-spacing: 1.5px;
      }

      input,
      textarea {
        border-radius: 5px;
        background: var(--Grey-Lightest, #f2f2f2);
        color: var(--Grey-Dark, #333);
        font-family: 'Noto Sans HK';
        font-size: 15px;
        font-style: normal;
        font-weight: 500;
        line-height: 160%;
        letter-spacing: 1.5px;
        padding: initial;
        padding-left: 8px;
        padding-right: 8px;
        border-radius: 5px;
      }
    }

    &-name {
      gap: 7px;

      .form-group {
        width: 50%;
      }
    }

    &-option {
      gap: 7px;

      & > .form-group:nth-child(1) {
        width: 90px;

        .area-address {
          padding-left: 8px;
          border: none;
          background: var(--Grey-Lightest, #f2f2f2);
          color: var(--Grey-Dark, #333);
          border-radius: 5px;
          background-image: none;
          appearance: none;
          -webkit-appearance: none;
          -moz-appearance: none;
          background-image: url('/static/img/footer/select-arrowDown.svg');
          background-repeat: no-repeat;
          background-position: right 7px center;
        }
      }

      & > .form-group:nth-child(2) {
        flex: 1;

        .custom-phone-input {
          .area-code {
            padding-left: 8px;
            width: 60px;
            z-index: 2;
            border: none;
            background: none;
            color: var(--Grey-Dark, #333);
            background-image: none;
            appearance: none;
            -webkit-appearance: none;
            -moz-appearance: none;
            background-image: url('/static/img/footer/select-code.svg');
            background-repeat: no-repeat;
            background-position: right 0px center;
          }

          input {
            text-indent: 60px;
            padding-left: 8px;
            padding-right: 8px;
            border-radius: 5px;
            background: var(--Grey-Lightest, #f2f2f2);
            color: var(--Grey-Dark, #333);
            font-family: 'Noto Sans HK';
            font-size: 15px;
            font-style: normal;
            font-weight: 500;
            line-height: 160%;
            letter-spacing: 1.5px;
          }
        }
      }
    }

    // 勾选
    .form-radio-group {
      .custom-radio {
        margin-top: 0;
        margin-left: 0;
        margin-right: 10px;
        -webkit-appearance: none;
        appearance: none;
        width: 16px;
        height: 16px;
        padding: 4px;
        border-radius: 50%;
        background-color: white;
        outline: none;
        cursor: pointer;
        position: relative;
        box-shadow: none !important;

        /* 当单选按钮被选中时改变背景颜色 */
        &:checked {
          &::after {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 8px;
            height: 8px;
            border-radius: 50%;
          }
        }

        /* 给单选按钮添加点击变色效果 */
        &:focus-visible {
          border: none;
        }
      }

      div {
        & > .form-check:nth-child(1),
        & > .form-check:nth-child(2) {
          cursor: pointer;
          .custom-radio {
            border: 2px solid #4caf50;
            &:checked {
              &::after {
                background-color: #4caf50;
              }
            }
          }

          span {
            color: var(--GHV-Green, #008843);
            font-family: 'Noto Sans HK';
            font-size: 18px;
            font-style: normal;
            font-weight: 700;
            line-height: normal;
            letter-spacing: 1.8px;
          }
        }

        & > .form-check:nth-child(3) {
          cursor: pointer;
          .custom-radio {
            border: 2px solid var(--New-Theme-Color, #d2337d);

            &:checked {
              &::after {
                background-color: var(--New-Theme-Color, #d2337d);
              }
            }
          }
          span {
            color: var(--Grey-Mid, #666);
            text-align: center;
            font-family: 'Noto Sans HK';
            font-size: 14px;
            font-style: normal;
            font-weight: 350;
            line-height: 120%;
            a {
              color: var(--New-Theme-Color, #d2337d);
            }
          }
        }
      }
    }
  }

  // 提交按钮
  .Appointment-form-btn {
    max-width: 184px;
    margin-top: 21px;
    border: none;
    padding: 8px 0;
    border-radius: 35px;
    background: var(--Blue-Deep, #00aeff);
    box-shadow: 3px 3px 12.4px 0px rgba(0, 174, 255, 0.5);
    gap: 17px;
    color: var(--White, #fff);
    font-family: 'Noto Sans HK';
    font-size: 22.035px;
    font-style: normal;
    font-weight: 700;
    line-height: normal;
    letter-spacing: 2.204px;
    transition: all 0.3s ease;
    position: relative;
    animation: btntestAnima-btn 5.6s infinite;

    svg {
      width: 28px;
    }

    &:hover {
      // animation: btntestafterAnima 2s infinite;
      // background: white;
      // color: var(--New-Theme-Color, #d2337d);
      // opacity: 0.8;

      svg {
        path {
          // stroke: var(--New-Theme-Color, #d2337d);
        }
      }
    }

    &::after {
      animation: btntestafterAnima 5.6s infinite;
      border: 8px solid var(--Blue-Light, #b9d9fc);
      border-radius: 70px;
      content: '';
      display: inline-block;
      height: 90%;
      left: 50%;
      position: absolute;
      top: 50%;
      transform: translate(-50%, -50%);
      -webkit-transform: translate(-50%, -50%);
      transition: all 0.5s;
      width: 90%;
      z-index: 0;
    }
  }

  @keyframes btntestafterAnima {
    0% {
      border: 7px solid var(--Blue-Light, #b9d9fc);
      height: 110%;
      width: 110%;
    }

    19% {
      border: 7px solid rgba(185, 217, 252, 0.5);
      height: calc(100% + 28px);
      width: calc(100% + 28px);
    }

    24% {
      height: calc(100% + 28px);
      width: calc(100% + 28px);
    }

    29% {
      border: 0 solid rgba(185, 217, 252, 0);
      height: calc(100% + 28px);
      width: calc(100% + 28px);
    }

    to {
      border: 0 solid rgba(185, 217, 252, 0);
      height: calc(100% + 28px);
      width: calc(100% + 28px);
    }
  }

  @keyframes btntestAnima-btn {
    5% {
      transform: scale(0.95);
      -webkit-transform: scale(0.95);
    }

    8% {
      transform: scale(1);
      -webkit-transform: scale(1);
    }
  }

  // 提示
  .form-mobile-tip {
    margin-top: 9px;
    color: var(--Grey-Mid, #666);
    text-align: center;
    font-family: 'Noto Sans HK';
    font-size: 14px;
    font-style: normal;
    font-weight: 350;
    line-height: 120%;
  }
}

// 弹窗
.popover-container [popover] {
  background: #fef0f0;
  color: #f56c6c;
  font-weight: 400;
  padding: 1rem 1.5rem;
  border-radius: 5px;
  max-width: 32ch;
  line-height: 1.4;
  top: 2rem;
  border: 1px solid #ebeef5;
  margin: 0 auto;
  transition: opacity 0.3s, transform 0.4s, top 0.4s;
}

/*   IS-OPEN STATE   */
.popover-container [popover]:popover-open {
  translate: 0 0;
}

/*   EXIT STATE   */
.popover-container [popover] {
  transition: translate 0.7s ease-out, display 0.7s ease-out allow-discrete;
  translate: 0 -22rem;
}

@starting-style {
  .popover-container [popover]:popover-open {
    translate: 0 -22rem;
  }
}

/* 服务多选样式 */
.service-buttons {
  gap: 8px 10px;

  .service-button {
    display: inline-block;
    border-radius: 5px;
    background: var(--Grey-Lightest, #f2f2f2);
    padding: 5px 13px;
    cursor: pointer;
    transition: all 0.3s ease;
    color: var(--Grey-Dark, #333);
    text-align: center;
    font-family: 'Noto Sans HK';
    font-size: 14px;
    font-style: normal;
    font-weight: 350;
    line-height: 120%;
  }
}

/* 选中状态的服务按钮样式 */
.service-button.selected {
  border-radius: 5px;
  border: 1px solid var(--New-Theme-Color, #d2337d);
  background: var(--Pink-Pale, #ffe9ec);
  display: inline-flex;
  align-items: center;
  flex-direction: row-reverse;
  padding: 5px 6px;
  font-weight: 700;
  gap: 5px;

  &::after {
    content: '';
    display: block;
    width: 14px;
    height: 14px;
    background: url('/static/img/seveiceSelect.svg') no-repeat center center;
    background-size: cover;
  }
}

/* 错误提示样式 */
.invalid-feedback {
  color: red;
  display: none;
}

@media screen and (min-width: 960px) {
  .appointmentForm-table {
    // max-width: 1100px;
    margin: 0 auto;

    &-title {
      span {
        font-size: 50px;
        font-weight: 700;
        line-height: 130%;
        color: var(--Grey-Dark, #333);
        font-family: 'Noto Sans HK';
        font-size: 24px;
        font-style: normal;
        font-weight: 700;
        line-height: normal;
        letter-spacing: 2.4px;

        &::before {
          content: '';
          position: absolute;
          background-size: none;
          background: var(--Pink-Pale, #ffe9ec);
          width: 60px;
          height: 2px;
          left: -72px;
          top: 50%;
          transform: translateY(-50%);
        }

        &::after {
          content: '';
          position: absolute;
          background-size: none;
          background: var(--Pink-Pale, #ffe9ec);
          width: 60px;
          height: 2px;
          right: -72px;
          top: 50%;
          transform: translateY(-50%);
        }

        i {
          color: var(--New-Theme-Color, #d2337d);
          font-size: 30px;
          font-weight: 700;
          letter-spacing: 3px;
        }
      }

      &::after {
        bottom: -30px;
        font-size: 18px;
        font-style: normal;
        font-weight: 400;
        line-height: 200%;
        letter-spacing: 1.8px;
      }
    }

    &-Box {
      gap: 16px;
      margin-top: 32px;
      .form-group {
        label {
          font-size: 24px;
          font-weight: 700;
          line-height: normal;
          letter-spacing: 2.4px;
        }

        input,
        textarea {
          font-size: 20px;
          font-weight: 500;
          line-height: normal;
          letter-spacing: 2px;
          padding: 3px;
          padding-left: 20px;
          padding-right: 20px;
          border-radius: 0px;
        }
      }

      &-name {
        gap: 28px;
      }

      //  区域选择
      &-option {
        gap: 28px;

        & > .form-group:nth-child(1) {
          width: 390px;

          .area-address {
            padding-left: 20px;
            padding-right: 20px;
            border-radius: 0px;
            height: 38px;
            color: var(--Grey-Dark, #333);
            font-family: 'Noto Sans HK';
            font-size: 20px;
            font-style: normal;
            font-weight: 400;
            line-height: 160%;
            letter-spacing: 3px;
            background-size: 14px 23px;
            background-position: right 20px center;
          }
        }

        & > .form-group:nth-child(2) {
          flex: 1;

          .custom-phone-input {
            .area-code {
              height: 38px;
              padding-left: 20px;
              width: 100px;
              z-index: 2;
              border: none;
              color: var(--Grey-Dark, #333);
              font-family: 'Noto Sans HK';
              font-size: 20px;
              font-style: normal;
              font-weight: 400;
              line-height: 160%;
              letter-spacing: 3px;
              background-size: 10px 20px;
              background-position: right 0px center;
            }

            input {
              text-indent: 116px;
              padding-left: 0;
              padding-right: 20px;
              border-radius: 5px;
              background: var(--Grey-Lightest, #f2f2f2);
              color: var(--Grey-Dark, #333);
              font-family: 'Noto Sans HK';
              font-family: FakePearl;
              font-size: 20px;
              font-style: normal;
              font-weight: 400;
              line-height: 160%;
              letter-spacing: 3px;
            }
          }
        }
      }

      // 勾选
      .form-radio-group {
        margin-top: 10px;

        .custom-radio {
          margin-right: 16px;
          width: 35px;
          height: 35px;
          padding: 10px;

          /* 当单选按钮被选中时改变背景颜色 */
          &:checked {
            &::after {
              width: 20px;
              height: 20px;
            }
          }
        }

        div {
          gap: 10px 86px;
          width: 700px;
          & > .form-check:nth-child(1),
          & > .form-check:nth-child(2) {
            cursor: pointer;
            .custom-radio {
              border: 5px solid #4caf50;
              &:checked {
                &::after {
                  background-color: #4caf50;
                }
              }
            }

            span {
              font-size: 24px;
              font-style: normal;
              font-weight: 700;
              line-height: normal;
              letter-spacing: 2.4px;
            }
          }

          & > .form-check:nth-child(3) {
            cursor: pointer;
            .custom-radio {
              border: 5px solid var(--New-Theme-Color, #d2337d);

              &:checked {
                &::after {
                  background-color: var(--New-Theme-Color, #d2337d);
                }
              }
            }
            span {
              font-family: 'Noto Sans HK';
              font-size: 24px;
              font-style: normal;
              font-weight: 700;
              line-height: normal;
              letter-spacing: 2.4px;
              a {
                color: var(--New-Theme-Color, #d2337d);
                text-decoration: underline;
              }
            }
          }
        }
      }
    }

    // 提交按钮
    .Appointment-form-btn {
      max-width: 250px;
      margin-top: 30px;
      font-size: 30px;
      font-weight: 700;
      letter-spacing: 3px;
      padding: 11px 0px;
      border-radius: 40px;
      gap: 24px;
      border: 2px solid var(--Blue-Deep, #00aeff);

      box-shadow: 0px 4px 4px 0px rgba(255, 255, 255, 0.25) inset,
        0px 4px 4px 0px rgba(255, 255, 255, 0.25);

      svg {
        width: 39px;
      }

      &:hover {
        background: #ff9900;
        // box-shadow: 3px 3px 12.4px 0px rgba(0, 174, 255, 0.5);
        border: 2px solid #ff9900;
      }
    }

    // 提示
    .form-mobile-tip {
      margin-top: 8px;
      color: var(--Grey-Mid, #666);
      text-align: center;

      font-family: 'Noto Sans HK';
      font-size: 20px;
      font-style: normal;
      font-weight: 400;
      line-height: 160%;
      letter-spacing: 4px;
    }
  }

  // 多选

  /* 服务多选样式 */
  .service-buttons {
    gap: 15px 20px;

    .service-button {
      display: inline-block;
      border-radius: 10px;
      border: 2px solid var(--Grey-Lightest, #f2f2f2);
      background: var(--Grey-Lightest, #f2f2f2);
      padding: 6px 32px;
      font-size: 22px;
      font-style: normal;
      font-weight: 500;
      line-height: normal;
      transition: all 0.3s ease;

      &:hover {
        border: 2px solid var(--New-Theme-Color, #d2337d);
        background: var(--Pink-Pale, #ffe9ec);
      }
    }
  }

  /* 选中状态的服务按钮样式 */
  .service-button.selected {
    border-radius: 5px;
    border: 2px solid var(--New-Theme-Color, #d2337d);
    background: var(--Pink-Pale, #ffe9ec);
    display: inline-flex;
    align-items: center;
    flex-direction: row-reverse;
    padding: 6px 20px;
    gap: 10px;

    &::after {
      content: '';
      display: block;
      width: 20px;
      height: 18px;
      background: url('/static/img/seveiceSelect.svg') no-repeat center center;
      background-size: cover;
    }
  }
}
</style>