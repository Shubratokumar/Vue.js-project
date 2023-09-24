<template>
  <div class="profile">
    <div class="flex items-center p-5">
      <img class="profile-img"
        src="../assets/profile2.png"
      />
      <div class="text-left ml-4">
        <h3 class="name mb-1">Eleanor Pena</h3>
        <p class="email">curtis.weaver@example.com</p>
      </div>
    </div>
    <div class="hr-divider w-full"></div>
    <div class="description p-5">
      <div class="coins w-full flex items-center">
        <div class="coin-container flex items-center w-1/2 mr-5">
          <img
            class="p-2"
            src="../assets/gold.png"
          />
          <div class="divider"></div>
          <p class="p-2 font-semibold text-base">21.8K</p>
        </div>
        <div class="coin-container flex items-center w-1/2">
          <img class="p-2" src="../assets/xp.png" />
          <div class="divider"></div>
          <p class="p-2 font-semibold text-base">1/2</p>
        </div>
      </div>
    </div>
    <div class="skills-abilities px-5 pb-5">
      <div class="w-full flex items-center">
        <div class="skills p-2 flex justify-between items-start w-1/2 mr-5">
          <div class="skills-desc text-left">
            <h5 class="title pb-3">Skills</h5>
            <p class="text">Verified:<span class="value"> 6</span></p>
            <p class="text">To develop:<span class="value"> 4</span></p>
            <p class="text">Certificates:<span class="value">10</span></p>
          </div>
          <div class="skills-icon">
            <img
              class="p-2"
              src="../assets/skills.png"
            />
          </div>
        </div>
        <div class="abilities p-2 flex justify-between items-start w-1/2">
          <div class="skills-desc text-left">
            <h3 class="title pb-3">Abilities</h3>
            <p class="text">Validated:<span class="value"> 3</span></p>
            <p class="text">To develop:<span class="value"> 2</span></p>
            <p class="text">Behaviours:<span class="value">14</span></p>
          </div>
          <div class="skills-icon">
            <img
              class="p-2"
              src="../assets/abilities.png"
            />
          </div>
        </div>
      </div>
    </div>
    <div class="expertise px-5 pb-2">
      <div class="expertise-heading flex items-center justify-between">
        <p>Expert In:</p>
        <div class="select">
          <img
            class="p-2"
            src="../assets/select.png"
          />
        </div>
      </div>
      <div class="expertise-list flex items-center flex-wrap">
        <span>Photoshop</span>
        <span>Excel</span>
        <span>Office 365</span>
        <span>Illustrator</span>
      </div>
    </div>
    <div class="known-as px-5 pb-5">
      <div class="expertise-heading flex items-center justify-between">
        <p>Known as:</p>
        <div class="select">
          <img
            class="p-2"
            src="../assets/select.png"
          />
        </div>
      </div>
      <div class="known-as-list flex items-center flex-wrap">
        <span>The social networker</span>
        <span>The imaginative mind</span>
        <span>The skilled communicator</span>
        <span>The passion driven</span>
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
  border-radius: 0.5rem;
  -webkit-box-shadow: 0px 4px 25px 0px rgba(0, 0, 0, 0.1);
  box-shadow: 0px 4px 25px 0px rgba(0, 0, 0, 0.1);
}
.profile-img {
  width: 70px;
  height: 70px;
}
.name {
  color: #101828;
  font-size: 1.5rem;
  font-weight: 700;
  line-height: 2rem;
}
.email {
  color: #98a2b3;
  font-size: 1rem;
  font-weight: 400;
  line-height: 1.5rem;
}
.hr-divider {
  height: 0.0625rem;
  background: #f2f2f2;
}
.coin-container {
  border-radius: 0.5rem;
  border: 1px solid #f2f2f2;
}
.coin-container > p {
  color: #000 !important;
}
.divider {
  width: 0.0625rem;
  height: 3.25rem;
  background: #f2f2f2;
}
.skills {
  border-radius: 0.5rem;
  background: linear-gradient(274deg, #fff4d7 0%, #ffe99d 124.45%);
}
.abilities {
  border-radius: 0.5rem;
  background: linear-gradient(274deg, #ffe99d 0%, #fff4d7 124.45%);
}
.title {
  font-size: 1rem;
  color: #101828 !important;
  font-weight: 500;
}
.text {
  color: #686868 !important;
  font-size: 0.75rem;
  font-weight: 400;
  line-height: 1.25rem;
}
.value {
  color: #101828 !important;
  font-weight: 500;
}
.expertise-heading > p {
  color: #91919f;
  font-size: 1rem;
  font-weight: 500;
}
.expertise-list > span {
  padding: 0.375rem 0.625rem;
  border-radius: 62.5rem;
  background: rgba(68, 204, 136, 0.1);
  color: #4c8;
  font-size: 0.75rem;
  font-weight: 600;
  margin-right: 0.5rem;
  margin-bottom: 0.5rem;
}
.known-as-list > span {
  padding: 0.375rem 0.625rem;
  border-radius: 62.5rem;
  background: rgba(85, 133, 255, 0.10);
  color: #5585FF;
  font-size: 0.75rem;
  font-weight: 600;
  margin-right: 0.5rem;
  margin-bottom: 0.5rem;
}
</style>
