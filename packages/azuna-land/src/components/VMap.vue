<template>
  <div class="map">
    <v-img src="../assets/images/azuna_land_back.png"></v-img>

    <img
      v-for="(item, i) in [
        {
          top: 50,
          left: 9,
          url: require('../assets/images/azuna_land_ki_1.png')
        },
        {
          top: 47,
          left: 12,
          url: require('../assets/images/azuna_land_ki_2.png')
        },
        {
          top: 52,
          left: 78,
          url: require('../assets/images/azuna_land_ki_1.png')
        },
        {
          top: 50,
          left: 75,
          url: require('../assets/images/azuna_land_ki_2.png')
        },
        {
          top: 85,
          left: 65,
          url: require('../assets/images/azuna_land_ki_1.png')
        },
        {
          top: 87,
          left: 62,
          url: require('../assets/images/azuna_land_ki_2.png')
        },
        {
          top: 83,
          left: 78,
          url: require('../assets/images/azuna_land_ki_2.png')
        },
        {
          top: 89,
          left: 13,
          url: require('../assets/images/azuna_land_ki_1.png')
        },
        {
          top: 90,
          left: 10,
          url: require('../assets/images/azuna_land_ki_2.png')
        },
        {
          top: 40,
          left: 95,
          url: require('../assets/images/azuna_land_ki_1.png')
        },
        {
          top: 85,
          left: 20,
          url: require('../assets/images/azuna_land_ki_2.png')
        },
        {
          top: 60,
          left: 32,
          url: require('../assets/images/azuna_land_ki_1.png')
        },
        {
          top: 38,
          left: 3,
          url: require('../assets/images/azuna_land_ki_2.png')
        }
      ]"
      :key="i"
      :style="
        `position: absolute; top: ${item.top}%; left: ${item.left}%; width:3%`
      "
      :src="item.url"
    />

    <div class="hikousen">
      <img
        class="hikousen-inner"
        src="../assets/images/azuna_land_hikousen.png"
      />
    </div>

    <div class="coaster">
      <img
        class="coaster__line"
        src="../assets/images/azuna_land_corster.png"
      />
      <div class="coaster__cars">
        <img
          class="coaster-car__1"
          src="../assets/images/azuna_land_corster_torokko_blue.png"
        />
        <img
          class="coaster-car__2"
          src="../assets/images/azuna_land_corster_torokko_pink.png"
        />

        <span
          v-for="(item, i) in [
            'あれ？',
            'やだやだー！',
            'こんなのトロッコじゃ～ん！'
          ]"
          :key="i"
          :class="`coaster-voice__${i}`"
        >
          {{ item }}
        </span>
      </div>
    </div>

    <div class="kanransha">
      <div class="kanransha__wheel">
        <img
          class="kanransha__wheel-image"
          src="../assets/images/azuna-land_kanransha_front.png"
        />
        <div
          v-for="(imageUrl, i) in [
            require('../assets/images/azuna-land_kanransha_red.png'),
            require('../assets/images/azuna-land_kanransha_blue.png'),
            require('../assets/images/azuna-land_kanransha_pink.png'),
            require('../assets/images/azuna-land_kanransha_red.png'),
            require('../assets/images/azuna-land_kanransha_blue.png'),
            require('../assets/images/azuna-land_kanransha_pink.png'),
            require('../assets/images/azuna-land_kanransha_red.png'),
            require('../assets/images/azuna-land_kanransha_blue.png')
          ]"
          :key="i"
          :class="['kanransha__gondola', `kanransha-gondola__${i}`]"
        >
          <img class="kanransha__gondola-image" :src="imageUrl" />
        </div>
      </div>
    </div>

    <img class="theater" src="../assets/images/azuna_land_theater.png" />

    <div class="horrorhouse">
      <img
        class="horrorhouse__house"
        src="../assets/images/azuna_land_horrorhouse.png"
      />
      <span
        v-for="(item, i) in [
          'ヒヒヒ...',
          'わくわく！',
          'ダンスもうやめたーい！',
          'ぐるぐる...',
          '演技力がすごい!'
        ]"
        :key="i"
        :class="`horrorhouse__voice-${i}`"
      >
        {{ item }}
      </span>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({});
</script>

<style scoped lang="scss">
.map {
  position: relative;
  overflow: hidden;
}

.kanransha {
  position: absolute;
  top: 10%;
  left: 10%;
  display: inline-block;
  transform: scale(0.7);

  width: 50%;
  padding-top: calc((514 / 490) * 50%);

  background-image: url("../assets/images/azuna-land_kanransha_back.png");
  background-size: contain;

  &__wheel {
    position: absolute;
    top: -10%;
    left: -1%;
    width: 100%;

    animation-name: wheel-spin;
    animation-iteration-count: infinite;
    animation-timing-function: linear;
    animation-duration: 30s;
  }
  &__wheel-image {
    width: 100%;
  }

  &__gondola {
    position: absolute;

    animation-name: gondola-spin;
    animation-iteration-count: infinite;
    animation-timing-function: linear;
    animation-duration: 30s;

    width: 20%;
  }
  &__gondola-image {
    width: 100%;
  }

  .kanransha-gondola {
    &__0 {
      top: 6%;
      left: 12%;
    }
    &__1 {
      top: -5%;
      left: 40%;
    }
    &__2 {
      top: 10%;
      left: 70%;
    }
    &__3 {
      top: 40%;
      left: 80%;
    }
    &__4 {
      top: 68%;
      left: 65%;
    }
    &__5 {
      top: 80%;
      left: 38%;
    }
    &__6 {
      top: 65%;
      left: 10%;
    }
    &__7 {
      top: 35%;
      left: 0%;
    }
  }

  @keyframes wheel-spin {
    0% {
      transform: rotate(0deg);
    }
    100% {
      transform: rotate(360deg);
    }
  }

  @keyframes gondola-spin {
    0% {
      transform: rotate(0deg);
    }
    100% {
      transform: rotate(-360deg);
    }
  }
}

.theater {
  position: absolute;
  top: 50%;
  left: 0%;

  width: 30%;
}

.coaster {
  position: absolute;
  bottom: 50%;
  left: 50%;

  width: 40%;

  &__line {
    width: 100%;
  }

  &__cars {
    position: absolute;
    width: 15%;

    top: 20%;
    left: 51%;

    animation: 20s ease-in-out 0 coaster-move-0;
    animation-iteration-count: infinite;
    animation-direction: alternate;

    @keyframes coaster-move-0 {
      0% {
        top: 20%;
        left: 51%;
        transform: rotate(0deg);
      }
      50% {
        transform: rotate(-40deg);
      }
      100% {
        top: 45%;
        left: 30%;
        transform: rotate(0deg);
      }
    }
  }
}

.coaster-car {
  z-index: 1000;

  &__1 {
    vertical-align: top;
    width: 50%;
  }
  &__2 {
    vertical-align: top;
    width: 50%;
  }
}

%coasterVoiceBase {
  font-family: "Kosugi Maru", sans-serif;
  font-size: 2vw;
  position: absolute;
  white-space: nowrap;

  top: -80%;
  left: 5%;
  transform: translate(-50%, 0);

  background-color: white;
  border-radius: 5px;
}

.coaster-voice {
  &__0 {
    @extend %coasterVoiceBase;

    opacity: 0;
    animation: 10s linear 0 coaster-voice-animation-0;
    animation-iteration-count: infinite;

    @keyframes coaster-voice-animation-0 {
      0%,
      100% {
        opacity: 0;
      }
      10% {
        opacity: 1;
      }
      20% {
        opacity: 0;
      }
    }
  }
  &__1 {
    @extend %coasterVoiceBase;
    opacity: 0;
    animation: 10s linear 4s coaster-voice-animation-1;
    animation-iteration-count: infinite;

    @keyframes coaster-voice-animation-1 {
      0%,
      100% {
        opacity: 0;
      }
      10% {
        opacity: 1;
      }
      20% {
        opacity: 0;
      }
    }
  }
  &__2 {
    @extend %coasterVoiceBase;
    opacity: 0;
    animation: 10s linear 7s coaster-voice-animation-2;
    animation-iteration-count: infinite;

    @keyframes coaster-voice-animation-2 {
      0%,
      100% {
        opacity: 0;
      }
      10% {
        opacity: 1;
      }
      20% {
        opacity: 0;
      }
    }
  }
}

.horrorhouse {
  position: absolute;

  top: 50%;
  right: 10%;

  width: 40%;

  &__house {
    width: 100%;
  }

  %voice {
    font-size: 2vw;
    position: absolute;
    white-space: nowrap;
  }

  &__voice-0 {
    @extend %voice;
    left: 10%;
    top: 30%;

    opacity: 0;
    animation: 10s linear 0 voice-animation-0;
    animation-iteration-count: infinite;

    @keyframes voice-animation-0 {
      0%,
      100% {
        opacity: 0;
        transform: rotate(-10deg) scale(1);
      }
      20% {
        opacity: 1;
        transform: rotate(-10deg) scale(1.2);
      }
      30% {
        opacity: 0;
      }
    }
  }

  &__voice-1 {
    @extend %voice;
    left: 80%;
    top: 70%;

    opacity: 0;
    animation: 10s linear 3s voice-animation-1;
    animation-iteration-count: infinite;

    @keyframes voice-animation-1 {
      0%,
      100% {
        opacity: 0;
        transform: rotate(-20deg) translate(0, 0);
      }
      20% {
        opacity: 1;
        transform: rotate(-20deg) translate(10%, -50%);
      }
      30% {
        opacity: 0;
      }
    }
  }

  &__voice-2 {
    @extend %voice;
    left: 50%;
    top: 60%;

    opacity: 0;
    animation: 10s linear 7s voice-animation-2;
    animation-iteration-count: infinite;

    @keyframes voice-animation-2 {
      0%,
      100% {
        opacity: 0;
        transform: rotate(30deg) skew(0, 0);
      }
      20% {
        opacity: 1;
        transform: rotate(30deg) skew(20deg, 10deg);
      }
      30% {
        opacity: 0;
      }
    }
  }

  &__voice-3 {
    @extend %voice;
    left: 80%;
    top: 20%;

    opacity: 0;
    animation: 10s linear 9s voice-animation-3;
    animation-iteration-count: infinite;

    @keyframes voice-animation-3 {
      0%,
      100% {
        opacity: 0;
        transform: rotate(40deg);
      }
      20% {
        opacity: 1;
        transform: rotate(-120deg);
      }
      30% {
        opacity: 0;
        transform: rotate(-200deg);
      }
    }
  }
  &__voice-4 {
    @extend %voice;
    left: 10%;
    top: 70%;

    opacity: 0;
    animation: 10s linear 4s voice-animation-4;
    animation-iteration-count: infinite;

    @keyframes voice-animation-4 {
      0%,
      100% {
        opacity: 0;
        transform: rotate(30deg) translate(0, 0);
      }
      20% {
        opacity: 1;
        transform: rotate(30deg) translate(10%, -50%);
      }
      30% {
        opacity: 0;
      }
    }
  }
}

.hikousen {
  $width: 30%;
  position: absolute;
  top: 10%;
  left: 0%;
  width: $width;
  animation: 30s linear 0 move;
  animation-iteration-count: infinite;

  @keyframes move {
    0%,
    100% {
      transform: translate(-100%, 0);
    }
    90% {
      transform: translate($width * 12, 0);
    }
    93% {
      transform: translate($width * 12, -1000%);
    }
    96% {
      transform: translate(-100%, -1000%);
    }
    99% {
      transform: translate(-100%, 0);
    }
  }

  .hikousen-inner {
    width: 100%;
    animation: 5s ease-in 0 floating;
    animation-iteration-count: infinite;
    @keyframes floating {
      0%,
      100% {
        transform: translateY(0);
      }

      50% {
        transform: translateY(15%);
      }
    }
  }
}
</style>
