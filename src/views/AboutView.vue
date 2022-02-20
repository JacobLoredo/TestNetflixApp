<template>
  <div class="flex justify-start items-center h-14  fixed w-full bg-black" :class="windowTop > 0 ? ' transition duration-150' : 'transition duration-150'">
    <div class="flex flex-row ">
      <div class="flex-initial w-32">
        <img src="../assets/images/netflix-Logo.png" alt="" srcset="" />
      </div>
      <div class="flex-initial w-auto  space-x-4">
        <router-link to="/about" active-class="text-white font-bold">Home</router-link>
        <router-link to="/" active-class="text-white">Tv Shows</router-link>
        <router-link to="/" active-class="text-white">Movies</router-link>
        <router-link to="/" active-class="text-white">New & Popular</router-link>
        <router-link to="/" active-class="text-white">My List</router-link>
      </div>
        <div class="flex-initial w-32 items-end">
          <div  id="search" :class="searchClick ? 'searchActive' : 'search' ">
            <i class="fa-solid fa-user"></i>
                    <i @click="searchClick = !searchClick" class="fas fa-search" ></i>
                    <input id="searchInput" ref="searchInput" v-if="searchClick ? true : false" v-model="searchValue" type="text" placeholder="İçerik , kişi , tür">
                </div>
        </div>
     
    </div>
  </div>
  
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
</template>

<script>
export default {
  data() {
    return {
      windowTop: 0,
      searchClick: false,
      searchValue: "",
      acilirMenu: "display:none",
      gozatShow: false,
      profileHover: false,
    };
  },
  mounted() {
    var that = this;
    window.addEventListener("scroll", function () {
      that.windowTop = window.scrollY;
    });
  },
  watch: {
    searchValue() {
      this.$store.state.searchValue = this.searchValue;
      if (this.searchValue.length == 1 && this.searchClick == true) {
        this.$router.push({ name: "search" });
      } else if (this.searchValue.length == 0) {
        this.$router.go(-1);
      }
    },
    searchClick(gelenveri) {
      this.searchClick = gelenveri;
      if (
        this.searchClick == false &&
        this.searchValue.length >= 1 &&
        this.$store.state.popup == false
      ) {
        this.searchValue = "";
        this.$router.go(-1);
      }
    },
  },
  methods: {
    gozatMenu(gelen) {
      if (gelen == "over") {
        this.acilirMenu = "display:flex; transition:0.3s";
      } else if (gelen == "menuleave") {
        this.acilirMenu = "display:none; transition:0.3s";
      }
    },
    gozatClick() {
      this.gozatShow = !this.gozatShow;
    },
    logout() {
      this.$store.state.token = "";
      this.$store.state.userEmail = "";
      this.$store.state.userLocalID = "";
      localStorage.removeItem("token");
      localStorage.removeItem("userEmail");
      localStorage.removeItem("localId");
      this.$router.push("/login");
    },
  },
};
</script>
<style scoped>
a{
   color: white;
}
</style>