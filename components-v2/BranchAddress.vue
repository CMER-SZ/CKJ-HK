<template>
  <section class="BranchAddress" id="BranchAddress">
    <div class="subheading px-20"><span>分店</span> <span>地址</span></div>
    <img
      class="BranchAddress-addressImg ckj-contrain d-block mx-auto"
      src="https://statichk.cmermedical.com/newCKJ/index/BranchAddress/index-address-pc.webp"
      alt=""
    />
    <div class="container-fluid BranchAddress-Box px-20">
      <div class="BranchAddress-Box-pc d-none d-lg-block">
        <ul
          class="nav nav-tabs BranchAddress-Box-pc-navTab position-relative d-flex justify-content-center"
          id="HospitalAddressPc"
          role="tablist"
        >
          <li class="nav-item" role="presentation">
            <button
              class="nav-link active"
              id="luohu-tab"
              data-bs-toggle="tab"
              data-bs-target="#luohu"
              type="button"
              role="tab"
              aria-controls="luohu"
              aria-selected="true"
            >
              羅湖區
            </button>
          </li>
          <li class="nav-item" role="presentation">
            <button
              class="nav-link"
              id="futian-tab"
              data-bs-toggle="tab"
              data-bs-target="#futian"
              type="button"
              role="tab"
              aria-controls="futian"
              aria-selected="false"
            >
              福田區
            </button>
          </li>
          <li class="nav-item" role="presentation">
            <button
              class="nav-link"
              id="nanshan-tab"
              data-bs-toggle="tab"
              data-bs-target="#nanshan"
              type="button"
              role="tab"
              aria-controls="nanshan"
              aria-selected="false"
            >
              南山區
            </button>
          </li>
        </ul>
        <div
          class="tab-content ckj-contrain mx-auto BranchAddress-Box-pc-content position-relative"
          id="HospitalAddressPcContent"
        >
          <div
            class="tab-pane fade show active"
            id="luohu"
            role="tabpanel"
            aria-labelledby="luohu-tab"
          >
           <Carousel :slideItems="carouselItems" :itemsPerPage="4" />
          </div>
          <div
            class="tab-pane fade"
            id="futian"
            role="tabpanel"
            aria-labelledby="futian-tab"
          >





            <div class="w-100  d-flex flex-wrap justify-content-start">
              <div
                class="BranchAddress-Box-pc-content-item position-relative d-flex"
              >
                <div
                  class="BranchAddress-Box-pc-content-item-MedicalCoupon position-absolute d-flex align-items-center hidefalse"
                  :data-has-coupon="false"
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
                  <img
                    src="https://static.cmereye.com/imgs/2024/03/57dee34750b0c30f.webp"
                    alt=""
                  />
                </div>
                <div
                  class="BranchAddress-Box-pc-content-item-right d-flex flex-column"
                >
                  <h4>裕亨口腔診所</h4>
                  <div>
                    <i
                      ><svg
                        xmlns="http://www.w3.org/2000/svg"
                        width="18"
                        height="23"
                        viewBox="0 0 18 23"
                        fill="none"
                      >
                        <path
                          d="M9 0.799805C11.3869 0.799805 13.6761 1.75373 15.364 3.45173C17.0518 5.14973 18 7.45271 18 9.85405C18 13.68 15.3277 17.8496 10.0523 22.4074C9.75898 22.6609 9.38498 22.8001 8.99827 22.7998C8.61157 22.7995 8.23781 22.6596 7.94492 22.4056L7.596 22.101C2.55415 17.6621 0 13.5946 0 9.85405C0 7.45271 0.948212 5.14973 2.63604 3.45173C4.32387 1.75373 6.61305 0.799805 9 0.799805ZM9 6.37165C8.08194 6.37165 7.20149 6.73854 6.55232 7.39162C5.90316 8.0447 5.53846 8.93046 5.53846 9.85405C5.53846 10.7776 5.90316 11.6634 6.55232 12.3165C7.20149 12.9696 8.08194 13.3365 9 13.3365C9.91806 13.3365 10.7985 12.9696 11.4477 12.3165C12.0968 11.6634 12.4615 10.7776 12.4615 9.85405C12.4615 8.93046 12.0968 8.0447 11.4477 7.39162C10.7985 6.73854 9.91806 6.37165 9 6.37165Z"
                          fill="#F8298A"
                        /></svg></i
                    ><span
                      >深圳市福田區福田街道漁農社區裕亨路38號裕亨花園裕亨大廈103</span
                    >
                  </div>
                  <a href="/contactUs#contactUs" class="align-items-end"
                    ><span>分店詳情</span>
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
                      /></svg
                  ></a>
                </div>
              </div>
              <div
                class="BranchAddress-Box-pc-content-item position-relative d-flex"
              >
                <div
                  class="BranchAddress-Box-pc-content-item-MedicalCoupon position-absolute d-flex align-items-center hidefalse"
                  :data-has-coupon="false"
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
                  <img
                    src="https://static.cmereye.com/imgs/2024/06/ca2430f5e9cbec91.webp"
                    alt=""
                  />
                </div>
                <div
                  class="BranchAddress-Box-pc-content-item-right d-flex flex-column"
                >
                  <h4>李川口腔診所</h4>
                  <div>
                    <i
                      ><svg
                        xmlns="http://www.w3.org/2000/svg"
                        width="18"
                        height="23"
                        viewBox="0 0 18 23"
                        fill="none"
                      >
                        <path
                          d="M9 0.799805C11.3869 0.799805 13.6761 1.75373 15.364 3.45173C17.0518 5.14973 18 7.45271 18 9.85405C18 13.68 15.3277 17.8496 10.0523 22.4074C9.75898 22.6609 9.38498 22.8001 8.99827 22.7998C8.61157 22.7995 8.23781 22.6596 7.94492 22.4056L7.596 22.101C2.55415 17.6621 0 13.5946 0 9.85405C0 7.45271 0.948212 5.14973 2.63604 3.45173C4.32387 1.75373 6.61305 0.799805 9 0.799805ZM9 6.37165C8.08194 6.37165 7.20149 6.73854 6.55232 7.39162C5.90316 8.0447 5.53846 8.93046 5.53846 9.85405C5.53846 10.7776 5.90316 11.6634 6.55232 12.3165C7.20149 12.9696 8.08194 13.3365 9 13.3365C9.91806 13.3365 10.7985 12.9696 11.4477 12.3165C12.0968 11.6634 12.4615 10.7776 12.4615 9.85405C12.4615 8.93046 12.0968 8.0447 11.4477 7.39162C10.7985 6.73854 9.91806 6.37165 9 6.37165Z"
                          fill="#F8298A"
                        /></svg></i
                    ><span>深圳市福田區金田路水圍村金莊商業樓2-5樓</span>
                  </div>
                  <a href="/contactUs#contactUs" class="align-items-end"
                    ><span>分店詳情</span>
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
                      /></svg
                  ></a>
                </div>
              </div>
              <div
                class="BranchAddress-Box-pc-content-item position-relative d-flex"
              >
                <div
                  class="BranchAddress-Box-pc-content-item-MedicalCoupon position-absolute d-flex align-items-center hidefalse"
                  :data-has-coupon="false"
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
                  <img
                    src="https://static.cmereye.com/imgs/2024/06/ca0cb58aab091e9c.webp"
                    alt=""
                  />
                </div>
                <div
                  class="BranchAddress-Box-pc-content-item-right d-flex flex-column"
                >
                  <h4>王琦口腔診所</h4>
                  <div>
                    <i
                      ><svg
                        xmlns="http://www.w3.org/2000/svg"
                        width="18"
                        height="23"
                        viewBox="0 0 18 23"
                        fill="none"
                      >
                        <path
                          d="M9 0.799805C11.3869 0.799805 13.6761 1.75373 15.364 3.45173C17.0518 5.14973 18 7.45271 18 9.85405C18 13.68 15.3277 17.8496 10.0523 22.4074C9.75898 22.6609 9.38498 22.8001 8.99827 22.7998C8.61157 22.7995 8.23781 22.6596 7.94492 22.4056L7.596 22.101C2.55415 17.6621 0 13.5946 0 9.85405C0 7.45271 0.948212 5.14973 2.63604 3.45173C4.32387 1.75373 6.61305 0.799805 9 0.799805ZM9 6.37165C8.08194 6.37165 7.20149 6.73854 6.55232 7.39162C5.90316 8.0447 5.53846 8.93046 5.53846 9.85405C5.53846 10.7776 5.90316 11.6634 6.55232 12.3165C7.20149 12.9696 8.08194 13.3365 9 13.3365C9.91806 13.3365 10.7985 12.9696 11.4477 12.3165C12.0968 11.6634 12.4615 10.7776 12.4615 9.85405C12.4615 8.93046 12.0968 8.0447 11.4477 7.39162C10.7985 6.73854 9.91806 6.37165 9 6.37165Z"
                          fill="#F8298A"
                        /></svg></i
                    ><span
                      >深圳市福田區福田街道漁農村社區裕亨路50號海悅華城C107、C108B</span
                    >
                  </div>
                  <a href="/contactUs#contactUs" class="align-items-end"
                    ><span>分店詳情</span>
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
                      /></svg
                  ></a>
                </div>
              </div>
            </div>
          </div>
          <div
            class="tab-pane fade"
            id="nanshan"
            role="tabpanel"
            aria-labelledby="nanshan-tab"
          >
            <div class="w-100 d-flex flex-wrap justify-content-start">
              <div
                class="BranchAddress-Box-pc-content-item position-relative d-flex"
              >
                <div
                  class="BranchAddress-Box-pc-content-item-MedicalCoupon position-absolute d-flex align-items-center hidefalse"
                  :data-has-coupon="false"
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
                  <img
                    src="https://static.cmereye.com/imgs/2024/10/8ec6180a704ba790.webp"
                    alt=""
                  />
                </div>
                <div
                  class="BranchAddress-Box-pc-content-item-right d-flex flex-column"
                >
                  <h4>恒雅口腔門診部</h4>
                  <div>
                    <i
                      ><svg
                        xmlns="http://www.w3.org/2000/svg"
                        width="18"
                        height="23"
                        viewBox="0 0 18 23"
                        fill="none"
                      >
                        <path
                          d="M9 0.799805C11.3869 0.799805 13.6761 1.75373 15.364 3.45173C17.0518 5.14973 18 7.45271 18 9.85405C18 13.68 15.3277 17.8496 10.0523 22.4074C9.75898 22.6609 9.38498 22.8001 8.99827 22.7998C8.61157 22.7995 8.23781 22.6596 7.94492 22.4056L7.596 22.101C2.55415 17.6621 0 13.5946 0 9.85405C0 7.45271 0.948212 5.14973 2.63604 3.45173C4.32387 1.75373 6.61305 0.799805 9 0.799805ZM9 6.37165C8.08194 6.37165 7.20149 6.73854 6.55232 7.39162C5.90316 8.0447 5.53846 8.93046 5.53846 9.85405C5.53846 10.7776 5.90316 11.6634 6.55232 12.3165C7.20149 12.9696 8.08194 13.3365 9 13.3365C9.91806 13.3365 10.7985 12.9696 11.4477 12.3165C12.0968 11.6634 12.4615 10.7776 12.4615 9.85405C12.4615 8.93046 12.0968 8.0447 11.4477 7.39162C10.7985 6.73854 9.91806 6.37165 9 6.37165Z"
                          fill="#F8298A"
                        /></svg></i
                    ><span>深圳市南山區南海大道與工業八路交匯處</span>
                  </div>
                  <a href="/contactUs#contactUs" class="align-items-end"
                    ><span>分店詳情</span>
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
                      /></svg
                  ></a>
                </div>
              </div>
              <div
                class="BranchAddress-Box-pc-content-item position-relative d-flex"
              >
                <div
                  class="BranchAddress-Box-pc-content-item-MedicalCoupon position-absolute d-flex align-items-center hidefalse"
                  :data-has-coupon="false"
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
                  <img
                    src="https://static.cmereye.com/imgs/2024/10/69240bf104904c86.webp"
                    alt=""
                  />
                </div>
                <div
                  class="BranchAddress-Box-pc-content-item-right d-flex flex-column"
                >
                  <h4>恒美口腔門診部</h4>
                  <div>
                    <i
                      ><svg
                        xmlns="http://www.w3.org/2000/svg"
                        width="18"
                        height="23"
                        viewBox="0 0 18 23"
                        fill="none"
                      >
                        <path
                          d="M9 0.799805C11.3869 0.799805 13.6761 1.75373 15.364 3.45173C17.0518 5.14973 18 7.45271 18 9.85405C18 13.68 15.3277 17.8496 10.0523 22.4074C9.75898 22.6609 9.38498 22.8001 8.99827 22.7998C8.61157 22.7995 8.23781 22.6596 7.94492 22.4056L7.596 22.101C2.55415 17.6621 0 13.5946 0 9.85405C0 7.45271 0.948212 5.14973 2.63604 3.45173C4.32387 1.75373 6.61305 0.799805 9 0.799805ZM9 6.37165C8.08194 6.37165 7.20149 6.73854 6.55232 7.39162C5.90316 8.0447 5.53846 8.93046 5.53846 9.85405C5.53846 10.7776 5.90316 11.6634 6.55232 12.3165C7.20149 12.9696 8.08194 13.3365 9 13.3365C9.91806 13.3365 10.7985 12.9696 11.4477 12.3165C12.0968 11.6634 12.4615 10.7776 12.4615 9.85405C12.4615 8.93046 12.0968 8.0447 11.4477 7.39162C10.7985 6.73854 9.91806 6.37165 9 6.37165Z"
                          fill="#F8298A"
                        /></svg></i
                    ><span>深圳市南山區商業文化中心區海岸城西座501</span>
                  </div>
                  <a href="/contactUs#contactUs" class="align-items-end"
                    ><span>分店詳情</span>
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
                      /></svg
                  ></a>
                </div>
              </div>
              <div
                class="BranchAddress-Box-pc-content-item position-relative d-flex"
              >
                <div
                  class="BranchAddress-Box-pc-content-item-MedicalCoupon position-absolute d-flex align-items-center hidefalse"
                  :data-has-coupon="false"
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
                  <img
                    src="https://static.cmereye.com/imgs/2024/06/0028a94a3ed515e0.webp"
                    alt=""
                  />
                </div>
                <div
                  class="BranchAddress-Box-pc-content-item-right d-flex flex-column"
                >
                  <h4>沈虹口腔診所</h4>
                  <div>
                    <i
                      ><svg
                        xmlns="http://www.w3.org/2000/svg"
                        width="18"
                        height="23"
                        viewBox="0 0 18 23"
                        fill="none"
                      >
                        <path
                          d="M9 0.799805C11.3869 0.799805 13.6761 1.75373 15.364 3.45173C17.0518 5.14973 18 7.45271 18 9.85405C18 13.68 15.3277 17.8496 10.0523 22.4074C9.75898 22.6609 9.38498 22.8001 8.99827 22.7998C8.61157 22.7995 8.23781 22.6596 7.94492 22.4056L7.596 22.101C2.55415 17.6621 0 13.5946 0 9.85405C0 7.45271 0.948212 5.14973 2.63604 3.45173C4.32387 1.75373 6.61305 0.799805 9 0.799805ZM9 6.37165C8.08194 6.37165 7.20149 6.73854 6.55232 7.39162C5.90316 8.0447 5.53846 8.93046 5.53846 9.85405C5.53846 10.7776 5.90316 11.6634 6.55232 12.3165C7.20149 12.9696 8.08194 13.3365 9 13.3365C9.91806 13.3365 10.7985 12.9696 11.4477 12.3165C12.0968 11.6634 12.4615 10.7776 12.4615 9.85405C12.4615 8.93046 12.0968 8.0447 11.4477 7.39162C10.7985 6.73854 9.91806 6.37165 9 6.37165Z"
                          fill="#F8298A"
                        /></svg></i
                    ><span
                      >深圳市南山區南海大道海典居裙樓1樓&2樓（海雅百貨對面）</span
                    >
                  </div>
                  <a href="/contactUs#contactUs" class="align-items-end"
                    ><span>分店詳情</span>
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
                      /></svg
                  ></a>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <NewAddress class="d-lg-none" />
  </section>
</template>

<script setup lang="ts">


const carouselItems = [
  {
    hasCoupon: true,
    imageUrl: 'https://statichk.cmermedical.com/newCKJ/index/BranchAddress/address-pc1.avif',
    title: '深圳愛康健口腔醫院',
    address: '深圳市羅湖區火車站大廈C區1-8樓',
    href: '/contactUs#contactUs'
  },
  {
    hasCoupon: false,
    imageUrl: 'https://statichk.cmermedical.com/newCKJ/index/BranchAddress/address-pc2.avif',
    title: '深圳希華愛康健醫院',
    address: '深圳市羅湖區南湖街道和平社區和平路火車西站二層G區2層部分、3 - 7層',
    href: '/contactUs#contactUs'
  },
  {
    hasCoupon: false,
    imageUrl: 'https://statichk.cmermedical.com/newCKJ/index/BranchAddress/address-pc3.avif',
    title: '恒潔口腔門診部',
    address: '深圳市羅湖區桂園街道新圍社區深南東路5015號金豐城大廈B座1602、1603',
    href: '/contactUs#contactUs'
  },
  {
    hasCoupon: false,
    imageUrl: 'https://statichk.cmermedical.com/newCKJ/index/BranchAddress/address-pc4.avif',
    title: '康輝口腔門診部',
    address: '深圳市羅湖區建設路深圳火車站皮帶走廊A12-A15.B11-B14及夾層B8--3號鋪',
    href: '/contactUs#contactUs'
  },
  {
    hasCoupon: false,
    imageUrl: 'https://statichk.cmermedical.com/newCKJ/index/BranchAddress/address-pc5.avif',
    title: '富康口腔門診部',
    address: '深圳市火車站南端二樓走廊(火車站大酒店左側)',
    href: '/contactUs#contactUs'
  },
  {
    hasCoupon: false,
    imageUrl: 'https://statichk.cmermedical.com/newCKJ/index/BranchAddress/address-pc6.avif',
    title: '顏麗口腔診所',
    address: '深圳市羅湖區羅湖口岸商業城1091號',
    href: '/contactUs#contactUs'
  }
];
</script>

<style lang="scss" scope>
// 分店地址
.BranchAddress {
  margin-top: 45px;
  &-addressImg {
    width: 100%;
    // max-width: 672px;
    margin-top: 10px;
    // margin: 10px 0;
  }
}
.BranchAddress-Box {
  // padding-top: 16px;
  // padding-bottom: 18px;
  // background: var(--Pink-Pale, #ffe9ec);

  &-mobile {
    .nav-tabs {
      border-radius: 5px;
      overflow: hidden;
      border: none;

      .nav-item {
        background: var(--White, #fff);
        padding: 0;
        border: 1px solid var(--Grey-Lightest, #f2f2f2);
        button {
          border: none;
          width: 110px;
          color: var(--Grey-Mid, #666);
          text-align: center;
          font-family: 'Noto Sans HK';
          font-size: 16px;
          font-style: normal;
          font-weight: 700;
          line-height: normal;
          letter-spacing: 1.6px;
          border-radius: 0;
          transition: background-color 0.3s ease;
        }

        .active {
          color: var(--White, #fff);
          background: var(--New-Theme-Color, #d2337d);
        }
      }

      & > .nav-item:nth-child(1) {
        border-radius: 5px 0 0 5px;
        overflow: hidden;
      }
      & > .nav-item:nth-child(2) {
        border-left: none;
        border-right: none;
      }

      & > .nav-item:nth-child(3) {
        border-radius: 0px 5px 5px 0px;
        overflow: hidden;
      }
    }

    // 轮播内容
    &-content {
      &-swiper {
        #HospitalAddress {
          max-width: 340px;
        }

        .number-card {
          padding-left: 15px;
        }

        &-number {
          color: var(--Grey-Mid, #666);
          font-family: 'Noto Sans HK';
          font-size: 16px;
          font-style: normal;
          font-weight: 700;
          line-height: normal;
          letter-spacing: 1.6px;

          span {
            color: var(--New-Theme-Color, #d2337d);

            font-size: 24px;
            line-height: 32px;
            letter-spacing: 4.8px;
          }
        }

        &-pageControl {
          gap: 10px;
          margin: 10px 0;

          .carousel-control-prev,
          .carousel-control-next,
          .carousel-indicators {
            position: static;
            opacity: 1;
          }

          .carousel-indicators {
            padding: 0;
            margin: 0;

            button {
              width: 18px;
              height: 18px;
              background-color: white;
              border-radius: 50%;
              opacity: 1;
            }

            .active {
              background-color: var(--New-Theme-Color, #d2337d);
            }
          }
        }

        &-item {
          border-radius: 5px;
          background: var(--White, #fff);
          box-shadow: 0px 4px 4px 0px rgba(77, 77, 77, 0.2);
          padding: 11px 8px 10px 12px;
          gap: 10px;
          margin-top: 12px;

          &-left {
            flex-shrink: 0;

            img {
              max-width: 103px;
            }

            & > div {
              margin-top: 13px;
              gap: 4px;

              svg {
                width: 18px;
                height: 18px;
              }

              span {
                color: var(--GHV-Green, #008843);
                font-family: 'Noto Sans HK';
                font-size: 14px;
                font-style: normal;
                font-weight: 500;
                line-height: 130%;
              }
            }
          }

          &-right {
            flex-shrink: 0;
            flex: 1;
            gap: 7px;

            h4 {
              color: var(--New-Theme-Color, #d2337d);
              font-family: 'Noto Sans HK';
              font-size: 18px;
              font-style: normal;
              font-weight: 700;
              line-height: normal;
              letter-spacing: 1.8px;
            }

            & > div {
              i {
                flex-shrink: 0;

                width: 18px;
                height: 17px;
                margin-right: 2px;

                svg {
                  vertical-align: top;
                }
              }

              span {
                color: var(--Grey-Mid, #666);
                font-family: 'Noto Sans HK';
                font-size: 14px;
                font-style: normal;
                font-weight: 350;
                line-height: 120%;
              }
            }

            & > a {
              width: 150px;
              display: inline-flex;
              padding: 2px 20px;
              height: 37px;
              gap: 10px;
              border-radius: 5px;
              background: var(--New-Theme-Color, #d2337d);
              color: var(--White, #fff);
              text-align: center;

              font-family: 'Noto Sans HK';
              font-size: 16px;
              font-style: normal;
              font-weight: 700;
              line-height: normal;
              letter-spacing: 1.6px;

              svg {
                width: 28px;
              }
            }
          }
        }
      }
    }
  }
}

.BranchAddress-address-table {
  width: 100%;
  max-width: 960px;
  margin: 0 auto;
}

.subheading {
  margin-left: 15px;
  box-sizing: border-box;
  padding-left: 12px;
  border-left: 2px solid var(--Pink-Pale, #ffe9ec);

  span {
    color: var(--Grey-Dark, #333);
    font-family: 'Noto Sans HK';
    font-size: 18px;
    font-style: normal;
    font-weight: 500;
    line-height: 170%;
    letter-spacing: 1.8px;
  }

  span:not(:last-child) {
    color: var(--New-Theme-Color, #d2337d);
    font-family: 'Noto Sans HK';
    font-size: 21px;
    font-style: normal;
    font-weight: 700;
    line-height: 150%;
    /* 31.5px */
    letter-spacing: 2.1px;
  }
}

@media screen and (min-width: 960px) {
  .subheading {
    box-sizing: border-box;
    width: fit-content;
    margin: 0 auto;
    padding: 0 10px;
    position: relative;
    background: #fff;

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
    top: 50%;
    left: 50%;
    width: 180%;
    height: 2px;
    background: var(--Pink-Pale, #ffe9ec);
    transform: translate(-50%, -50%);
    z-index: -1;
  }

  // 分店地址
  .BranchAddress {
 
    padding-top: 45px;
    padding-bottom: 30px;
    &-addressImg {
      margin-top: 20px;
    }
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

          & > li:nth-child(1) button {
            border-radius: 10px 0px 0px 10px;
          }

          & > li:nth-child(2) button {
            border-left: none;
            border-right: none;
          }

          & > li:nth-child(3) button {
            border-radius: 0px 10px 10px 0px;
          }
        }

        &-content {
          .tab-pane > div {
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

            gap: 15px;
            width: 470px;
            border-radius: 10px;
            overflow: hidden;
            background: var(--White, #fff);
            box-shadow: 0px 4px 4px 0px rgba(77, 77, 77, 0.2);
            // padding: 20px;
            &-left {
              max-width: 190px;
              flex-shrink: 0;
              img {
                height: 100%;
              }
            }

            &-right {
              flex-shrink: 0;
              flex: 1;
              // gap: 11.5px;
              padding: 10px 10px 10px 0;
              h4 {
                color: var(--New-Theme-Color, #d2337d);
                font-family: 'Noto Sans TC';
                font-size: 20px;
                font-style: normal;
                font-weight: 700;
                line-height: 160%;
                letter-spacing: 2px;
              }

              & > div {
                margin-top: 7px;
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

              a {
                display: inline-flex;
                flex: 1;
                max-width: 180px;
                // gap: 20px;
                color: var(--Brand-Color, #f8298a);
                // padding: 10px 20px;
                // border-radius: 10px;
                // border: 2px solid var(--New-Theme-Color, #d2337d);
                // background: var(--New-Theme-Color, #d2337d);
                // box-shadow: 0px 4px 4px 0px rgba(255, 255, 255, 0.25) inset,
                //   0px 4px 4px 0px rgba(255, 255, 255, 0.25);
                // color: var(--White, #fff);

                font-family: 'Noto Sans HK';
                font-size: 14px;
                font-style: normal;
                font-weight: 500;
                line-height: 18px;
                &:hover {
                  opacity: 0.8;
                }

                svg {
                  width: 28px;
                }
              }
            }
          }
        }
      }
    }
  }
}
</style>