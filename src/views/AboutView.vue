<template>
  <nav
    class="
      bg-black
      border-gray-200
      px-2
      sm:px-4
      py-2.5
      rounded
      dark:bg-gray-800
    "
  >
    <div class="container flex flex-wrap justify-between items-center mx-auto">
      <div class="w-1/2 flex">
        <div class="w-1/4">
        <a href="#">
          <img src="../assets/images/netflix-Logo.png" alt="" srcset="" />
        </a>
        </div>
        <div class="w-3/4">
           <ul
          class="
            flex flex-col
            mt-4
            md:flex-row md:space-x-8 md:mt-0 md:text-sm md:font-medium
          "
        >
          <li class="text-white">
            <router-link
              to="/about"
              class="
                block
                py-2
                pr-4
                pl-3
                text-white
                bg-blue-700
                rounded
                md:hover:text-gray-300 md:bg-transparent md:text-blue-700 md:p-0
                dark:text-white
              "
              >Home</router-link
            >
          </li>
          <li>
            <a
              href="#"
              class="
                block
                py-2
                pr-4
                pl-3
                text-gray-700
                border-b border-gray-100
                hover:bg-gray-50
                md:hover:bg-transparent
                md:border-0
                md:hover:text-gray-300
                md:p-0
                dark:text-gray-400
                md:dark:hover:text-white
                dark:hover:bg-gray-700 dark:hover:text-white
                md:dark:hover:bg-transparent
                dark:border-gray-700
              "
              >Tv Shows</a
            >
          </li>
          <li>
            <a
              href="#"
              class="
                block
                py-2
                pr-4
                pl-3
                text-gray-700
                border-b border-gray-100
                hover:bg-gray-50
                md:hover:bg-transparent
                md:border-0
                md:hover:text-gray-300
                md:p-0
                dark:text-gray-400
                md:dark:hover:text-white
                dark:hover:bg-gray-700 dark:hover:text-white
                md:dark:hover:bg-transparent
                dark:border-gray-700
              "
              >Movies</a
            >
          </li>
          <li>
            <a
              href="#"
              class="
                block
                py-2
                pr-4
                pl-3
                text-gray-700
                border-b border-gray-100
                hover:bg-gray-50
                md:hover:bg-transparent
                md:border-0
                md:hover:text-gray-300
                md:p-0
                dark:text-gray-400
                md:dark:hover:text-white
                dark:hover:bg-gray-700 dark:hover:text-white
                md:dark:hover:bg-transparent
                dark:border-gray-700
              "
              >New & Popular</a
            >
          </li>
          <li>
            <a
              href="#"
              class="
                block
                py-2
                pr-4
                pl-3
                text-gray-700
                border-b border-gray-100
                hover:bg-gray-50
                md:hover:bg-transparent
                md:border-0
                md:hover:text-gray-300
                md:p-0
                dark:text-gray-400
                md:dark:hover:text-white
                dark:hover:bg-gray-700 dark:hover:text-white
                md:dark:hover:bg-transparent
                dark:border-gray-700
              "
              >My List</a
            >
          </li>
        </ul>
        </div>
      </div>
      <div class="w-1/2 flex">
      <div class="w-2/4 flex">
       
      </div>
      
       <div class="w-1/2 flex space-x-4 items-center justify-end">
        <div id="search" :class="searchClick ? 'searchActive' : 'search' ">
         
          <font-awesome-icon
            icon="magnifying-glass"
            color="white"
            @click="searchClick = !searchClick"
          />

          <input
            id="searchInput"
            ref="searchInput"
            v-if="searchClick ? true : false"
            v-model="searchValue"
            type="text"
            placeholder="Title , People , genders"
          />
        </div>
      <p class="text-white">DVD</p>
       <font-awesome-icon icon="bell" color="white" />
       <div class="flex" @mouseenter="profileHover = true">
          <div class=" w-8">
            <img
            class="rounded"
              src="https://i.ibb.co/P4Gtz8S/0ddccae723d85a703b798a5e682c23c1.png"
              alt=""
            />
           
          </div>
           <font-awesome-icon icon="caret-down" color="white" />
          <div
            v-if="profileHover"
            @mouseleave="profileHover = false"
            class="profile-settings-frame"
          >
            <div class="profile-settings">
              <div class="flex">
                 <font-awesome-icon icon="pen" color="white" />
                <p>administrar perfiles</p>
              </div>
              <p @click="logout">Netflix Oturumunu Kapat</p>
            </div>
          </div>
        </div>
      </div>
      
      </div>

       
      
      <div class="flex items-start md:order-2 space-x-4 w-2/6">
        <div
          class="
            hidden
            z-50
            my-4
            text-base
            list-none
            bg-white
            rounded
            divide-y divide-gray-100
            shadow
            dark:bg-gray-700 dark:divide-gray-600
          "
          id="dropdown"
        >
          <div class="py-3 px-4">
            <span class="block text-sm text-gray-900 dark:text-white"
              >Bonnie Green</span
            >
            <span
              class="
                block
                text-sm
                font-medium
                text-gray-500
                truncate
                dark:text-gray-400
              "
              >name@flowbite.com</span
            >
          </div>
          <ul class="py-1" aria-labelledby="dropdown">
            <li>
              <a
                href="#"
                class="
                  block
                  py-2
                  px-4
                  text-sm text-gray-700
                  hover:bg-gray-100
                  dark:hover:bg-gray-600
                  dark:text-gray-200
                  dark:hover:text-white
                "
                >Dashboard</a
              >
            </li>
            <li>
              <a
                href="#"
                class="
                  block
                  py-2
                  px-4
                  text-sm text-gray-700
                  hover:bg-gray-100
                  dark:hover:bg-gray-600
                  dark:text-gray-200
                  dark:hover:text-white
                "
                >Settings</a
              >
            </li>
            <li>
              <a
                href="#"
                class="
                  block
                  py-2
                  px-4
                  text-sm text-gray-700
                  hover:bg-gray-100
                  dark:hover:bg-gray-600
                  dark:text-gray-200
                  dark:hover:text-white
                "
                >Earnings</a
              >
            </li>
            <li>
              <a
                href="#"
                class="
                  block
                  py-2
                  px-4
                  text-sm text-gray-700
                  hover:bg-gray-100
                  dark:hover:bg-gray-600
                  dark:text-gray-200
                  dark:hover:text-white
                "
                >Sign out</a
              >
            </li>
          </ul>
        </div>
        <button
          data-collapse-toggle="mobile-menu-2"
          type="button"
          class="
            inline-flex
            items-center
            p-2
            ml-1
            text-sm text-gray-500
            rounded-lg
            md:hidden
            hover:bg-gray-100
            focus:outline-none focus:ring-2 focus:ring-gray-200
            dark:text-gray-400 dark:hover:bg-gray-700 dark:focus:ring-gray-600
          "
          aria-controls="mobile-menu-2"
          aria-expanded="false"
        >
          <span class="sr-only">Open main menu</span>
          <svg
            class="w-6 h-6"
            fill="currentColor"
            viewBox="0 0 20 20"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              fill-rule="evenodd"
              d="M3 5a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 10a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 15a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1z"
              clip-rule="evenodd"
            ></path>
          </svg>
          <svg
            class="hidden w-6 h-6"
            fill="currentColor"
            viewBox="0 0 20 20"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              fill-rule="evenodd"
              d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z"
              clip-rule="evenodd"
            ></path>
          </svg>
        </button>
      </div>
      
    </div>
  </nav>

  <br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br />
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
   
  },
};
</script>
<style scoped>
nav a {
  color: white;
  font-weight: 100;
}
.router-link-exact-active {
  font-weight: 700;
  color: white;
}
#search input{
    margin-left: 5px;
    width: 230px;
    background: transparent;
    border: 0px;
    outline: 0;
    color: white;
}
.searchActive{
    padding-left: 6px;
    margin-right: 0px;
    display: flex;
    align-items: center;
    justify-content: flex-end;
    animation: searchInput 0.3s  ease-out;
    animation-fill-mode: forwards;
    height: 30px;
    background: black;
    border: 1px solid white;
    transition: 0.3s;
}
@keyframes searchInput{
    from{
        width: 0px;
    }to{
        width: 230px;
    }
}
.search{
    transition: 0.3s;
}
.profile-settings-frame-m{
    width: 100%;
    height: 100px;
    position: absolute;
    margin-top:70px;
    margin-right: 7px;
    padding: 0px;
}
.profile-settings{
    position: absolute;
    right: 0;
    width: 180px;
    height: auto;
    background: #000101;
    border: 1px solid gray;
    color:white;
    font-size: 12px;
}

.profile-settings-frame{
    position: absolute;
    margin-top: 40px;
    margin-left: 6%;
}
.profile-settings p{
    width: 100%;
    text-align: center;
    font-size: 12px;
   
}
.profile-settings-m p{
    width: 100%;
    text-align: center;
    font-size: 12px;
    
}
.profile-settings p:hover{
    cursor: pointer;
}
.profile-settings{
    position: absolute;
    width: 160px;
    height: auto;
    background: #000101;
    border: 1px solid gray;
}
</style>