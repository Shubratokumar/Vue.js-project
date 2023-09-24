<template>
  <div class="profile rounded-lg shadow-xl">
    <div class="flex items-center p-5">
      <img class="profile-img"
        src="../assets/profile2.png"
      />
      <div class="text-left ml-4">
        <h3 class="text-black text-2xl font-bold mb-1">Eleanor Pena</h3>
        <p class="email text-base">curtis.weaver@example.com</p>
      </div>
    </div>
    <hr>
    <div class="description p-5">
      <div class="coins w-full flex items-center">
        <div class="coin-container rounded-lg flex items-center w-1/2 mr-5">
          <img
            class="p-2"
            src="../assets/gold.png"
          />
          <div class="divider"></div>
          <p class="p-2 font-bold text-base text-black">21.8K</p>
        </div>
        <div class="coin-container rounded-lg flex items-center w-1/2">
          <img class="p-2" src="../assets/xp.png" />
          <div class="divider"></div>
          <p class="p-2 font-bold text-base text-black">1/2</p>
        </div>
      </div>
    </div>
    <div class="skills-abilities px-5 pb-5">
      <div class="w-full flex items-center">
        <div class="skills rounded-lg p-2 flex justify-between items-start w-1/2 mr-5">
          <div class="skills-desc text-left">
            <h5 class="text-base text-black font-medium pb-3">Skills</h5>
            <p class="text text-xs">Verified:<span class="font-medium text-black"> 6</span></p>
            <p class="text text-xs">To develop:<span class="font-medium text-black"> 4</span></p>
            <p class="text text-xs">Certificates:<span class="font-medium text-black"> 10</span></p>
          </div>
            <img
              class="p-2"
              src="../assets/skills.png"
            />
        </div>
        <div class="abilities rounded-lg p-2 flex justify-between items-start w-1/2">
          <div class="skills-desc text-left">
            <h3 class="text-base text-black font-medium pb-3">Abilities</h3>
            <p class="text text-xs">Validated:<span class="font-medium text-black"> 3</span></p>
            <p class="text text-xs">To develop:<span class="font-medium text-black"> 2</span></p>
            <p class="text text-xs">Behaviours:<span class="font-medium text-black"> 14</span></p>
          </div>
            <img
              class="p-2"
              src="../assets/abilities.png"
            />
        </div>
      </div>
    </div>
    <div class="expertise px-5 pb-2">
      <div class="flex items-center justify-between pb-3">
        <p class="expertise-title text-base font-medium">Expert In:</p>
          <img
            class="p-2"
            src="../assets/select.png"
          />
      </div>
      <div class="flex items-center flex-wrap">
        <span class="expertise-item text-xs font-semibold mr-2 mb-2">Photoshop</span>
        <span class="expertise-item text-xs font-semibold mr-2 mb-2">Excel</span>
        <span class="expertise-item text-xs font-semibold mr-2 mb-2">Office 365</span>
        <span class="expertise-item text-xs font-semibold mr-2 mb-2">Illustrator</span>
      </div>
    </div>
    <div class="known-as px-5 pb-5">
      <div class="flex items-center justify-between pb-3">
        <p class="known-as-title text-base font-medium">Known as:</p>
          <img
            class="p-2"
            src="../assets/select.png"
          />
      </div>
      <div class="flex items-center flex-wrap">
        <span class="known-as-item text-xs font-semibold mr-2 mb-2">The social networker</span>
        <span class="known-as-item text-xs font-semibold mr-2 mb-2">The imaginative mind</span>
        <span class="known-as-item text-xs font-semibold mr-2 mb-2">The skilled communicator</span>
        <span class="known-as-item text-xs font-semibold mr-2 mb-2">The passion driven</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  computed: { },
  methods: {},
};
</script>

<style scoped>
.profile {
  width: 23.5rem;
  height: 34.8125rem;
  background: #fff;
}
.profile-img {
  width: 70px;
  height: 70px;
}
.email {
  color: #98a2b3;
}
.coin-container {
  border: 1px solid #f2f2f2;
}
.divider {
  width: 0.06rem;
  height: 3.25rem;
  background: #f2f2f2;
}
.skills {
  background: linear-gradient(274deg, #fff4d7 0%, #ffe99d 124.45%);
}
.abilities {
  background: linear-gradient(274deg, #ffe99d 0%, #fff4d7 124.45%);
}
.text {
  color: #686868 ;
}
.expertise-title, .known-as-title {
  color: #91919f;
}
.expertise-item {
  padding: 0.375rem 0.625rem;
  border-radius: 62.5rem;
  background: rgba(68, 204, 136, 0.1);
  color: #4c8;
}
.known-as-item {
  padding: 0.375rem 0.625rem;
  border-radius: 62.5rem;
  background: rgba(85, 133, 255, 0.10);
  color: #5585FF;
}
</style>
