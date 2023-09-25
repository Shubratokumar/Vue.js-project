<template>
  <section class="profile-card rounded-lg shadow-xl">
    <div class="user flex items-center p-5">
      <img class="user__img" src="../assets/profile2.png" />
      <div class="user__info text-left ml-4">
        <h3 class="text-black text-2xl font-bold mb-1">Eleanor Pena</h3>
        <p class="user__info--email text-base">curtis.weaver@example.com</p>
      </div>
    </div>
    <hr />
    <div class="coins p-5">
      <div class="w-full flex items-center">
        <div class="coins__container rounded-lg flex items-center w-1/2 mr-5">
          <img class="p-2" src="../assets/gold.png" />
          <div class="divider"></div>
          <p class="p-2 font-bold text-base text-black">21.8K</p>
        </div>
        <div class="coins__container rounded-lg flex items-center w-1/2">
          <img class="p-2" src="../assets/xp.png" />
          <div class="divider"></div>
          <p class="p-2 font-bold text-base text-black">1/2</p>
        </div>
      </div>
    </div>
    <div class="skills-abilities px-5 pb-5">
      <div class="w-full flex items-center">
        <div
          class="skills rounded-lg p-2 flex justify-between items-start w-1/2 mr-5"
        >
          <div class="text-left">
            <h5 class="text-base text-black font-medium pb-3">Skills</h5>
            <p class="skills--text text-xs">
              Verified:<span class="font-medium text-black"> 6</span>
            </p>
            <p class="skills--text text-xs">
              To develop:<span class="font-medium text-black"> 4</span>
            </p>
            <p class="skills--text text-xs">
              Certificates:<span class="font-medium text-black"> 10</span>
            </p>
          </div>
          <img class="p-2" src="../assets/skills.png" />
        </div>
        <div
          class="abilities rounded-lg p-2 flex justify-between items-start w-1/2"
        >
          <div class="text-left">
            <h3 class="text-base text-black font-medium pb-3">Abilities</h3>
            <p class="abilities--text text-xs">
              Validated:<span class="font-medium text-black"> 3</span>
            </p>
            <p class="abilities--text text-xs">
              To develop:<span class="font-medium text-black"> 2</span>
            </p>
            <p class="abilities--text text-xs">
              Behaviours:<span class="font-medium text-black"> 14</span>
            </p>
          </div>
          <img class="p-2" src="../assets/abilities.png" />
        </div>
      </div>
    </div>
    <div class="expertise px-5 pb-2">
      <div class="flex items-center justify-between pb-3">
        <p class="expertise--title text-base font-medium">Expert In:</p>
        <button class="border-none" @click="collapseExpertise">
          <img
            class="p-2"
            :class="showExpertise ? '' : 'rotate-180'"
            src="../assets/select.png"
          />
        </button>
      </div>
      <div
        class="flex items-center flex-wrap"
        :class="showExpertise ? '' : 'hidden'"
      >
        <span class="expertise--item text-xs font-semibold mr-2 mb-2"
          >Photoshop</span
        >
        <span class="expertise--item text-xs font-semibold mr-2 mb-2"
          >Excel</span
        >
        <span class="expertise--item text-xs font-semibold mr-2 mb-2"
          >Office 365</span
        >
        <span class="expertise--item text-xs font-semibold mr-2 mb-2"
          >Illustrator</span
        >
      </div>
    </div>
    <div class="known-as px-5 pb-5">
      <div class="flex items-center justify-between pb-3">
        <p class="known-as--title text-base font-medium">Known as:</p>
        <button class="border-none" @click="collapseKnownAs">
          <img
            class="p-2"
            :class="showKnownAs ? '' : 'rotate-180'"
            src="../assets/select.png"
          />
        </button>
      </div>
      <div
        class="flex items-center flex-wrap"
        :class="showKnownAs ? '' : 'hidden'"
      >
        <span class="known-as--item text-xs font-semibold mr-2 mb-2"
          >The social networker</span
        >
        <span class="known-as--item text-xs font-semibold mr-2 mb-2"
          >The imaginative mind</span
        >
        <span class="known-as--item text-xs font-semibold mr-2 mb-2"
          >The skilled communicator</span
        >
        <span class="known-as--item text-xs font-semibold mr-2 mb-2"
          >The passion driven</span
        >
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      showExpertise: true,
      showKnownAs: true,
    };
  },
  computed: {},
  methods: {
    collapseExpertise() {
      this.showExpertise = this.showExpertise ? false : true;
    },
    collapseKnownAs() {
      this.showKnownAs = this.showKnownAs ? false : true;
    },
  },
};
</script>

<style lang="scss" scoped>
$background1: #fff;
$background2: #f2f2f2;
$background3: rgba(68, 204, 136, 0.1);
$background4: rgba(85, 133, 255, 0.1);
$gradient1: linear-gradient(274deg, #fff4d7 0%, #ffe99d 124.45%);
$gradient2: linear-gradient(274deg, #ffe99d 0%, #fff4d7 124.45%);
$text-color1: #98a2b3;
$text-color2: #686868;
$text-color3: #91919f;
$text-color4: #4c8;
$text-color5: #5585ff;
$border-primary: 1px solid #f2f2f2;
.profile-card {
  width: 23.5rem;
  background: $background1;
  .user {
    &__img {
      width: 4.37rem;
      height: 4.37rem;
    }
    &__info {
      &--email {
        color: $text-color1;
      }
    }
  }
  .coins {
    &__container {
      border: $border-primary;
      .divider {
        width: 1px;
        height: 3.25rem;
        background: $background2;
      }
    }
  }
  .skills-abilities {
    .skills {
      background: $gradient1;
    }
    .abilities {
      background: $gradient2;
    }
    .skills,
    .abilities {
      &--text {
        color: $text-color2;
      }
    }
  }
  .expertise,
  .known-as {
    &--title {
      color: $text-color3;
    }
    &--item {
      padding: 0.375rem 0.625rem;
      border-radius: 62.5rem;
    }
  }
  .expertise {
    &--item {
      background: $background3;
      color: $text-color4;
    }
  }
  .known-as {
    &--item {
      background: $background4;
      color: $text-color5;
    }
  }
}
</style>
