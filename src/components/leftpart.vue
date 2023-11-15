<template>
<!-- <div class="m-2 sm:p-12 flex flex-col items-center justify-center w-full lg:w-1/2 relative">
        <h1 class="text-4xl mt-10 sr-only">Coinflip</h1>
        <div>
          <p class="bg-t-light-gray p-3 rounded-lg mt-5 text-center">
            ℹ️ Please connect your wallet to bet
          </p>
        </div>
      </div> -->
      <div class="content-box">
          <div class="button-container swv-dark">
          <button class="swv-button swv-button-trigger justify-center " 
          :class="{ 'active': selectedOption === 'Heads' }"
          @click="selectOption('Heads')">
      HEADS
    </button>
          <div style="width: 5px;"></div>
          <button
      class="swv-button swv-button-trigger justify-center "
      :class="{ 'active': selectedOption === 'Tails' }"
      @click="selectOption('Tails')"
    >
      TAILS
    </button>
  </div>
          <div>
          <input type="number" class="number-input" placeholder="Betting Amount" >
          <p class=" content-second">Wallet Balance : 0.24945 SOL <br> You will be charge<br>0.05125 SOL + 0.003 SOL Fee</p>
          </div> 
          <div class="swv-dark flip">
          <button class="swv-button swv-button-trigger justify-center " >FLIP HEADS</button>
          </div>  
        </div>
</template>

<script>
export default {
    name: 'CoinFlip',
    data() {
     return {
       selectedOption: null
    };
  },
    methods: {
    selectOption(option) {
        this.selectedOption = option;
    }
  }
}
</script>

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
  


  
  .wallet-button {
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
    text-align: center;
    margin: 0 10px;
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
  /* 其他样式属性 */
} 
.active {
    background-color: yellow;
    /* 其他样式属性 */
}

.flip {
  margin-left: 120px;
}

@media (min-width: 1440px) {
    .container {
        max-width:1280px
    }
    .flip {
     margin-left: 150px;
    }
    .button-container {
      display: flex;
      justify-content: space-between; 
      align-items: center; 
      margin: 0 30px;
  }
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
    font-family:DM Sans,Roboto,Helvetica Neue,Helvetica,Arial,sans-serif;
    font-weight:700;
    line-height:48px;
    padding:0 24px;
    border-radius:var(--swv-button-radius);
    font-family: "Arial Black";
    font-size: 18px;
    height: 60px;
    width: 180px;
}

.swv-button > *+* {
  margin-left:13px;
}
.swv-button-trigger {
  font-family: "Arial Black";
  background-color:#212c42cc;
  color: #fff;
  text-align: center;
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