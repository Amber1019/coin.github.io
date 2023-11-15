<template>
  <div class="bg">
    <div class="p-2">
      <div class="header flex flex-col sm:flex-row gap-5 justify-between p-2 items-center">
        <h1 class="trading-title p-3 mt-3">TradingTrain</h1>
        <div class="swv-dark">
          <button class="swv-button swv-button-trigger corner-button mt-3"> Select Wallet </button>
        </div>
      </div>
    </div>
    <div class="coin flex flex-col lg:flex-row container justify-center items-center mx-auto rounded-md border-4 border-yellow-500 bg-[#212c42cc] backdrop-blur-sm mb-5 mt-4">
      <leftpart></leftpart>
      <div class="p-12 flex-1">
        <h1 class="text-xl mt-10 mb-4 font-ocr text-center content">Recent Plays</h1>
        <div class="recent-plays rounded-md w-full flex flex-col gap-3 mb-10 font-ocr ">
          <div v-for="(play, index) in recentPlays" :key="index" class="flex flex-row justify-between items-center p-2 bg-t-blue/75 rounded-md ">
            <div>
              <div class="flex flex-row justify-center items-center">
                <img :src="play.icon" :alt="play.alt" width="48">
                <p class="p-2 name">
                  <span class="">{{ play.name }}</span> flipped {{ play.amount }} on {{ play.side }} and
                  <span class="font-bold" :class="{'text-green-500': play.win, 'text-red-500': !play.win}">
                    {{ play.win ? 'doubled!' : 'got rugged.' }}
                  </span>
                </p>
                <p class="px-2 hidden">{{ play.timeAgo }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>


</template>

<script>
import { ref } from 'vue';
import leftpart from './leftpart.vue';

export default {
  name: 'HelloWorld',
  components: {
      leftpart
  },
  props: {
    msg: String
  },
  setup() {
    const selectedOption = ref(null);

    const recentPlays = ref([
      {
        icon: require('@/images/cf_heads.png'),
        alt: 'Coin Icon',
        name: 'Someone',
        amount: '20.00 Graphite',
        side: 'Heads',
        win: true,
        timeAgo: '9 hours ago'
      },
      {
        icon: require('@/images/cf_tails.png'),
        alt: 'Coin Icon',
        name: 'Someone',
        amount: '160.00 Graphite',
        side: 'Tails',
        win: true,
        timeAgo: '1 day ago'
      },
      {
        icon: require('@/images/cf_heads.png'),
        alt: 'Coin Icon',
        name: 'Another Person',
        amount: '50.00 Graphite',
        side: 'Heads',
        win: false,
        timeAgo: '2 days ago'
      },
      {
        icon: require('@/images/cf_heads.png'),
        alt: 'Coin Icon',
        name: 'Yet Another Person',
        amount: '100.00 Graphite',
        side: 'Heads',
        win: true,
        timeAgo: '3 days ago'
      },
      {
        icon: require('@/images/cf_tails.png'),
        alt: 'Coin Icon',
        name: 'Player X',
        amount: '25.00 Graphite',
        side: 'Tails',
        win: true,
        timeAgo: '4 days ago'
      },
      {
        icon: require('@/images/cf_tails.png'),
        alt: 'Coin Icon',
        name: 'Player X',
        amount: '25.00 Graphite',
        side: 'Tails',
        win: false,
        timeAgo: '4 days ago'
      }
    ]);

    const selectOption = (option) => {
      selectedOption.value = option;
    };

    return {
      selectedOption,
      recentPlays,
      selectOption
    };
  }
};

</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.bg {
    background-image: url(@/images/37030.jpg);
    background-repeat: no-repeat;
    background-size:cover;
    background-position:bottom;
    
}
.header{
    margin-top: 60px;
}
 .trading-title {
    font-family: "Arial Black";
    color: #212c42cc;
    font-size: 35px;
    position: absolute;
    top: 5px;
    left: 50px;
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
    
  }
  
  .corner-button {
    position: absolute;
    top: 20px;
    right: 70px;
    padding: 10px;

  }
  

  
  .wallet-button{
    font-family: "Arial Black";
    background-color:#212c42cc;
    color: #fff;
    font-size: 18px;
    border: 0;
    border-radius: 5px;
    height: 60px;
    width: 180px;
  }

*,:before,:after {
    font-family: "Arial Black";
    box-sizing: border-box;
    border-width: 0;
    border-style: solid;
    border-color: #e5e7eb
}
.container {
    width: 100%;
    width: 2000px;
}

@media (min-width: 640px) {
    .container {
        max-width:640px
    }
}

@media (min-width: 768px) {
    .container {
        max-width:768px
    }
}

@media (min-width: 1024px) {
    .container {
        max-width:1024px
    }
}

@media (min-width: 1280px) {
    .container {
        max-width:1170px
    }
}
@media (min-width: 1440px) {
    .container {
        max-width:1280px
    }
}

@media (min-width: 1536px) {
    .container {
        max-width:1536px
    }
}

.flex {
    display: flex
}

.hidden {
    display: none
}

.grid-cols-2 {
    grid-template-columns: repeat(2,minmax(0,1fr))
}

.flex-row {
    flex-direction: row
}

.flex-col {
    flex-direction: column
}


.items-center {
    align-items: center
}

.justify-center {
    justify-content: center
}

.justify-between {
    justify-content: space-between
}

.rounded-lg {
    border-radius: .5rem
}

.rounded-md {
    border-radius: .375rem
}

.border-2 {
    border-width: 2px
}

.border-\[\#ffff5b\] {
    --tw-border-opacity: 1;
    border-color: rgb(255 255 91 / var(--tw-border-opacity))
}
.bg-yellow-500 {
    --tw-bg-opacity: 1;
    background-color: rgb(234 179 8 / var(--tw-bg-opacity))
}
.border-yellow-500{
    border-color: yellow;
} 
.bg-\[\#212c42cc\] {
    background-color: #212c42cc
}

.bg-t-blue\/75 {
    background-color: #2f486fbf
}

.bg-t-light-gray {
    --tw-bg-opacity: 1;
    background-color: rgb(39 39 39 / var(--tw-bg-opacity))
}
.bg-yellow-500 {
    --tw-bg-opacity: 1;
    background-color: rgb(234 179 8 / var(--tw-bg-opacity))
}


.p-12 {
    padding: 3rem;
}

.p-3 {
    padding: .75rem
}

.p-5 {
    padding: 1.25rem
}


.font-bold {
    font-family: "Arial Black";
    font-weight: 700
}

.text-green-500 {
    --tw-text-opacity: 1;
    color: rgb(34 197 94 / var(--tw-text-opacity))
}

.text-red-500 {
    --tw-text-opacity: 1;
    color: rgb(239 68 68 / var(--tw-text-opacity))
}

.content {
  font-size: 20px;
}

.gap-5 {
    gap: 1.25rem
}
@media (min-width: 640px) {
  .sm\:h-12 {
    height: 3rem;
  }
  .sm\:w-\[95vw\] {
    width: 95vw;
  }
  .sm\:flex-row {
    flex-direction: row;
  }
  .sm\:p-12 {
    padding: 3rem;
  }
  .sm\:px-7 {
    padding-left: 1.75rem;
    padding-right: 1.75rem;
  }
  .sm\:py-5 {
    padding-top: 1.25rem;
    padding-bottom: 1.25rem;
  }
}

@media (min-width: 768px) {
  .md\:flex {
    display: flex;
  }
  .md\:w-\[40rem\] {
    width: 40rem;
  }
  .md\:w-\[75\%\] {
    width: 75%;
  }
}

@media (min-width: 1024px) {
  .lg\:w-1\/2 {
    width: 50%;
  }
  .lg\:w-\[45rem\] {
    width: 45rem;
  }
  .lg\:flex-row {
    flex-direction: row;
  }
  .lg\:gap-12 {
    gap: 3rem;
  }
}

@media (min-width: 1280px) {
  .xl\:h-16 {
    height: 4rem;
  }
  .xl\:text-3xl {
    font-size: 1.875rem;
    line-height: 2.25rem;
  }
  .xl\:text-4xl {
    font-size: 2.25rem;
    line-height: 2.5rem;
  }
}
.button-container {
    display: flex;
    justify-content: space-between; 
    align-items: center; 
    margin: 0 30px;
  }

  .headtail-button {
    box-shadow: 3px 3px 5px rgba(0, 0, 0, 0.3); 
  }

  .headtail-button:active,
  .headtail-button:hover {
    background-color: rgb(33, 56, 56); 
  }

  .number-input{
    margin-top: 30px;
    margin-left: 0 auto;
    height: 30px;
    width: 430px;
    border-radius: 10px;
    padding-left: 20px;
  }

  .content {
    margin-left: 0 auto;
    margin-top: 40px;
    color: #ffffff;
  }

  .content-second{
    margin-top: 20px;
    color: #9ca0a8;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
.content-box {
    border: 1px solid #ddd;
    padding: 20px;
    margin-left:70px;
    width: 50%;
    border-radius: 10px;
    background-color: rgba(47, 72, 111, 0.749);
    box-shadow: 3px 3px 5px rgba(0, 0, 0, 0.3);
    position: relative;

  }
.coin {
    height: 100vh; /* 使用视口高度作为高度 */
    text-align: center;
  /* 其他样式属性 */
} 
.active {
    background-color: yellow;
    /* 其他样式属性 */
}
.name {
  text-align: left;
}

.mb-10 {
    margin-bottom: 2.5rem
}
.mb-5 {
    margin-bottom: 1.25rem
}
/* 按鈕 */
.swv-dark{
    --swv-overlay-background-color: rgba(0, 0, 0, .7);
    --swv-modal-background-color: #1e293b;
    --swv-modal-text-color: white;
    --swv-modal-close-button-background-color: #0f172a;
    --swv-modal-close-button-text-color: #64748b;
    --swv-modal-close-button-hover-text-color: white;
    --swv-modal-button-text-color: white;
    --swv-modal-button-hover-background-color: #0f172a;
    --swv-modal-button-outline-color: white;
    --swv-dropdown-background-color: #1e293b;
    --swv-dropdown-item-hover-background-color: #334155;
    --swv-dropdown-text-color: white;
    --swm-modal-shadow: 0px 8px 20px rgba(0, 0, 0, .6);

    --swv-button-background-color: #4f46e5;
    --swv-button-text-color: white;
    --swv-button-outline-color: #3730a3;
    --swv-button-hover-background-color: #4338ca;
    --swv-button-disabled-background-color: #475569;
    --swv-button-disabled-text-color: #94a3b8;
    --swv-overlay-background-color: rgba(200, 200, 200, .8);
    --swv-modal-background-color: white;
    --swv-modal-text-color: #1f2937;
    --swv-modal-close-button-background-color: #f3f4f6;
    --swv-modal-close-button-text-color: #9ca3af;
    --swv-modal-close-button-hover-text-color: #374151;
    --swv-modal-button-text-color: #1f2937;
    --swv-modal-button-hover-background-color: #f3f4f6;
    --swv-modal-button-outline-color: var(--swv-button-outline-color);
    --swv-dropdown-background-color: white;
    --swv-dropdown-item-hover-background-color: #f3f4f6;
    --swv-dropdown-text-color: #1f2937;
    --swm-modal-shadow: 0 25px 25px rgb(0 0 0 / .15);
    --swm-dropdown-shadow: 0px 10px 20px rgba(0, 0, 0, .3);
    --swv-button-radius: 6px;
    --swv-modal-radius: 10px;
    --swv-dropdown-radius: 10px;
    --swv-dropdown-item-radius: 6px;
}
.swv-button {
    background-color:transparent;
    border:none;
    color:var(--swv-button-text-color);
    cursor:pointer;
    display:flex;
    align-items:center;
    text-align: center;
    font-family:DM Sans,Roboto,Helvetica Neue,Helvetica,Arial,sans-serif;
    font-size:16px;
    font-weight:600;
    height:48px;
    line-height:48px;
    padding:0 24px;
    border-radius:var(--swv-button-radius)
}
.swv-button>*+* {
  margin-left:12px
}
.swv-button-trigger {
  font-family: "Arial Black";
  background-color:#212c42cc;
  color: #fff;
}
.swv-button:not([disabled]):focus-visible {
  outline-color:var(--swv-button-outline-color)
}
.swv-button:not([disabled]):hover {
  background-color:var(--swv-button-hover-background-color)
}

.swv-button[disabled] {
  background:var(--swv-button-disabled-background-color);color:var(--swv-button-disabled-text-color);cursor:not-allowed
}



  
</style>
