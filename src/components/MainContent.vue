<script setup lang="ts">
const birdData = {
  name: '白頭翁',
  englishName: 'Chinese bulbul',
  description: '又名白頭鵯。以果實、昆蟲為主食，無法消化小米、穀類。平均壽命約 8~10 年。',
  appearance: '白頭鵯體長約17到22公分，額至頭頂純黑色而富有光澤，兩眼上方至後枕白色，形成一白色枕環。耳羽後部有一白斑，此白環與白斑在黑色的頭部均極為醒目，老鳥的枕羽(後頭部)更潔白，所以又叫「白頭翁」。',
  habitat: '白頭翁和麻雀、綠繡眼合稱「城市三寶」，常成群出現在平原區灌木叢、丘陵樹林地帶，以及校園、公園、庭院、行道中的各種高高的電線與樹上。',
  diet: '以果樹的漿果和種子為主食，並時常飛入果園偷吃果實，還會吃嫩葉嫩芽，尤其是胡蝶蘭的嫩葉嫩芽葉，偶爾啄食昆蟲。'
}

</script>

<template>
  <div class="main-content">
    <div class="bird-image">
        <div class="bird-info">
          <h1>{{ birdData.name }} <span>({{ birdData.englishName }})</span></h1>
          <p class="description">{{ birdData.description }}</p>
        </div>
      </div>
      <div class="info-container">
        <div class="info-box appearance">
          <div class="title-wrapper">
            <h2>外觀</h2>
            <span class="circle"></span>
          </div>
          <p>{{ birdData.appearance }}</p>
        </div>
        <div class="info-box habitat">
          <div class="title-wrapper">
            <h2>棲地</h2>
            <span class="circle"></span>
          </div>
          <p>{{ birdData.habitat }}</p>
        </div>
        <div class="info-box diet">
          <div class="title-wrapper">
            <h2>食性</h2>
            <span class="circle"></span>
          </div>
          <p>{{ birdData.diet }}</p>
        </div>
      </div>
  </div>
</template>

<style lang="scss" scoped>
.main-content {
  flex-grow: 1;
  overflow-y: auto;
  background-color: #fff;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  
  .bird-image {
    height: 634px;
    background-image: url('/bg.webp');
    background-size: 175%;
    background-position: 75% 50%;
    position: relative;
    
    .bird-info {
      position: absolute;
      bottom: 37px;
      right: 45px;
      padding: 25px;
      h1 {
        color: $white;
        font-weight: 700;
        font-size: 48px;
        line-height: 100%;
        margin: 1rem 0;
        text-align: right;
      }
      
      .description {
        color: $white;
        font-weight: 400;
        font-size: 18px;
        line-height: 100%;
        text-align: right;
      }
    }
  }
  
  .info-container {
    flex: 1;
    display: flex;
    padding: 50px;
    gap: 79px;
    overflow-y: auto;
    background-color: $background-color;
    
    .info-box {
      flex: 1;
      border-radius: 8px;
      display: flex;
      gap: 38px;
      .title-wrapper {
        position: relative;
        height: fit-content;
        h2 {
          position: relative;
          z-index: 2;
          writing-mode: vertical-rl; 
          text-orientation: upright; 
          white-space: nowrap;
          margin-top: 0;
          font-weight: 700;
          font-size: 36px;
          line-height: 40px;
          letter-spacing: 0%;
        }
        
        .circle {
          z-index: 0;
          position: absolute;
          right: -15px;
          bottom: -15px;
          width: 26px;
          height: 26px;
          border-radius: 50%;
          background-color: #AA666699;
        }

        .circle::before {
          content: "";
          position: absolute;
          width: 10px;
          height: 10px;
          background-color: $background-color;
          border-radius: 50%;
          top: 50%;
          left: 50%;
          transform: translate(-50%, -50%);
        }
      }

      p {
        color: black;
        font-weight: 400;
        font-size: 16px;
        line-height: 1.5rem;
        letter-spacing: 0%;
        min-width: 200px;
      }
    }
  }
}

@media (max-width: $tablet-breakpoint) {
  .main-content {
    height: auto;
    min-height: 100vh;
  }

  .info-container {
    flex-direction: column;
  }

  .info-container {
    flex: 1;
    gap: 50px;  
  }
}

@media (max-width: $mobile-breakpoint) {
  .sidebar {
    box-shadow: 0px 4px 4px 0px #00000040;
  }
  .main-content {
    min-height: 100vh;
    height: auto;
    box-sizing: border-box;
    .bird-image {
      height: 311px;
      background-position: 60% 50%;
      background-size: 250%; 
      .bird-info {
        bottom: 24px;
        right: 27px;
        padding:0;
        padding-left: 24px;
      }
    }
    
    
    .info-container {
      flex: 1;
      gap: 50px;
    }
  }
}
</style>

