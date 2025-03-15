<template>
  <main>
    <div class="text-main">
      <h1>Softline</h1>
      <p>
        Ведущий поставщик IT-решений и сервисов.* Мы предлагаем комплексные
        IT-решения, облака, программное и аппаратное обеспечение, решения по
        цифровой <br />
        трансформации и кибербезопасности, а также широкий спектр IT-услуг.
      </p>
    </div>

    <div class="navbar" ref="navbar" :class="{ dimmed: showDropdown }">
      <a class="dropdown" @click="toggleDropdown">
        <p>Офисы Softline</p>
        <i :class="{ rotated: showDropdown }">
          <img src="../assets/arrow.svg" alt="arrow" />
        </i>
        <ul v-if="showDropdown" class="dropdown-menu">
          <div class="links">
            <a @click.prevent="navigateTo('link1')">Москва</a>
            <a @click.prevent="navigateTo('link2')"
              >Центр
              <span>Воронеж </span>
              <span>Ярославль</span>
              <span>Белгород</span>
            </a>
            <a @click.prevent="navigateTo('link3')"
              >Северо-Запад
              <span>Санкт-Петербург </span>
              <span>Калининград д</span>
            </a>
            <a @click.prevent="navigateTo('link4')"
              >Юг
              <span>Ростов-на-Дону </span>
              <span>Краснодар </span>
              <span>Волгоград </span>
            </a>
            <a @click.prevent="navigateTo('link5')"
              >Волга
              <span>Казань </span>
              <span>Самара </span>
              <span>Уфа </span>
              <span>Оренбург </span>
              <span>Нижний Новгород </span>
            </a>
            <a @click.prevent="navigateTo('link6')"
              >Урал
              <span>Екатеринбург </span>
              <span>Челябинск </span>
              <span>Пермь </span>
              <span>Сургут </span>
              <span>Тюмень </span>
              <span>Ижевск </span>
            </a>
            <a @click.prevent="navigateTo('link7')"
              >Сибирь
              <span>Новосибирск </span>
              <span>Омск </span>
              <span>Томск </span>
              <span>Красноярск </span>
              <span>Иркутск </span>
            </a>
            <a @click.prevent="navigateTo('link8')"
              >Дальний Восток

              <span> Хабаровск </span>
              <span>Владивосток </span>
            </a>
          </div>
        </ul>
      </a>

      <ul>
        <li
          :class="{ active: activeLink === 'image1' }"
          @click.prevent="changeImage('image1')"
        >
          Все
        </li>
        <li
          :class="{ active: activeLink === 'image2' }"
          @click.prevent="changeImage('image2')"
        >
          Москва
        </li>
        <li
          :class="{ active: activeLink === 'image3' }"
          @click.prevent="changeImage('image3')"
        >
          Центр
        </li>
        <li
          :class="{ active: activeLink === 'image4' }"
          @click.prevent="changeImage('image4')"
        >
          Северо-Запад
        </li>
        <li
          :class="{ active: activeLink === 'image5' }"
          @click.prevent="changeImage('image5')"
        >
          Юг
        </li>
        <li
          :class="{ active: activeLink === 'image6' }"
          @click.prevent="changeImage('image6')"
        >
          Волга
        </li>
        <li
          :class="{ active: activeLink === 'image7' }"
          @click.prevent="changeImage('image7')"
        >
          Урал
        </li>
        <li
          :class="{ active: activeLink === 'image8' }"
          @click.prevent="changeImage('image8')"
        >
          Сибирь
        </li>
        <li
          :class="{ active: activeLink === 'image9' }"
          @click.prevent="changeImage('image9')"
        >
          Дальний восток
        </li>
      </ul>
    </div>

    <div class="image-container">
      <transition name="fade" mode="out-in">
        <img
          v-if="imageSrc"
          :src="imageSrc"
          :key="imageSrc"
          alt="Dynamic Image"
          style="height: 600px"
        />
      </transition>
    </div>

    <div class="maim-image">
      <img src="../assets/Mission.png" alt="Mission" />
    </div>
  </main>
</template>

<script>
export default {
  name: "Main",
  data() {
    return {
      imageSrc: "",
      activeLink: "image1",
      showDropdown: false,
    };
  },
  mounted() {
    this.changeImage("image1");
  },
  methods: {
    changeImage(image) {
      this.activeLink = image;
      switch (image) {
        case "image1":
          import("../assets/map.png")
            .then((image) => {
              this.imageSrc = image.default;
            })
            .catch((error) => {
              console.error("Error loading image:", error);
              this.imageSrc = "";
            });
          break;
        case "image2":
          import("../assets/moscow.png")
            .then((image) => {
              this.imageSrc = image.default;
            })
            .catch((error) => {
              console.error("Error loading image:", error);
              this.imageSrc = "";
            });
          break;
        case "image3":
          import("../assets/center.png")
            .then((image) => {
              this.imageSrc = image.default;
            })
            .catch((error) => {
              console.error("Error loading image:", error);
              this.imageSrc = "";
            });
          break;
        case "image4":
          import("../assets/1212.png")
            .then((image) => {
              this.imageSrc = image.default;
            })
            .catch((error) => {
              console.error("Error loading image:", error);
              this.imageSrc = "";
            });
          break;
        case "image5":
          import("../assets/Юг.png")
            .then((image) => {
              this.imageSrc = image.default;
            })
            .catch((error) => {
              console.error("Error loading image:", error);
              this.imageSrc = "";
            });
          break;
        case "image6":
          import("../assets/vokga.png")
            .then((image) => {
              this.imageSrc = image.default;
            })
            .catch((error) => {
              console.error("Error loading image:", error);
              this.imageSrc = "";
            });
          break;
        case "image7":
          import("../assets/Урал.png")
            .then((image) => {
              this.imageSrc = image.default;
            })
            .catch((error) => {
              console.error("Error loading image:", error);
              this.imageSrc = "";
            });
          break;
        case "image8":
          import("../assets/Сибирь.png")
            .then((image) => {
              this.imageSrc = image.default;
            })
            .catch((error) => {
              console.error("Error loading image:", error);
              this.imageSrc = "";
            });
          break;
        case "image9":
          import("../assets/Дальний восток.png")
            .then((image) => {
              this.imageSrc = image.default;
            })
            .catch((error) => {
              console.error("Error loading image:", error);
              this.imageSrc = "";
            });
          break;
        default:
          this.imageSrc = "";
      }
    },
    toggleDropdown() {
      this.showDropdown = !this.showDropdown;
    },
    updateNavbarOpacity() {
      const navbar = this.$refs.navbar;

      if (navbar) {
        navbar.style.opacity = this.showDropdown ? "0.3" : "200";
      }
    },

    navigateTo(link) {
      console.log("Navigating to:", link);
      this.showDropdown = false;
    },
  },
};
</script>

<style lang="scss" scoped>
main {
  width: 100%;
  margin-top: 80px;
  text-align: center;

  .navbar {
    border: 3px solid #0000000f;
    padding: 0 40px 0 50px;
    height: 80px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    box-shadow: 0px 0px 40px 0px #0000000f;
    margin-top: 150px;
    width: 100%;
    transition: opacity 0.3s ease;
    ul {
      list-style-type: none;
      padding: 0;
      margin: 0;
      display: flex;
      justify-content: center;
      gap: 20px;
    }

    li {
      font-family: Proxima Nova Condensed;
      font-size: 18px;
      font-weight: 600;
      line-height: 20px;
      cursor: pointer;
      color: #444444;
      position: relative;
      padding-bottom: 5px;
      transition: color 0.3s ease;
    }

    li::after {
      content: "";
      position: absolute;
      left: 0;
      top: 193%;
      width: 0;
      height: 3px;
      background-color: #a30c33;
      transition: width 0.3s;
    }

    li:hover::after,
    li.active::after {
      width: 100%;
    }

    li:hover,
    li.active {
      color: #a30c33;
    }

    .dropdown {
      position: relative;
      cursor: pointer;
      display: flex;

      gap: 15px;
      align-items: center;

      justify-content: space-between;

      p {
        font-family: Proxima Nova Condensed;
        font-size: 24px;
        font-weight: 600;
        line-height: 24px;

        text-underline-position: from-font;
        text-decoration-skip-ink: none;

        color: #444444;
      }
    }

    .dropdown-menu {
      position: absolute;
      top: 29%;
      left: -53px;
      background-color: white;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
      list-style-type: none;
      padding: 10px 0;
      margin-top: 60px;
      width: 1250px;
      height: 272px;
      opacity: 100;
      transition: opacity 0.3s ease;
    }

    .dropdown i {
      transition: transform 0.3s ease;
    }

    .dropdown-menu li {
      padding: 8px 16px;
      cursor: pointer;
    }

    .dropdown-menu li:hover::after {
      display: none;
    }

    .dropdown-menu li:hover {
      background-color: #f0f0f0;
      text-decoration: none;
    }

    .fa-chevron-down {
      transition: transform 0.3s ease;
    }

    .rotated {
      transform: rotate(180deg);
    }
  }
  //  .navbar {
  //   &.dimmed {
  //     opacity:0.3;
  //     transition: opacity 0.3s ease;
  //   }
  // }

  .dropdown-visible {
    opacity: 100 !important;
  }

  .dropdown-menu {
    opacity: 1;
    transition: opacity 0.3s ease;
  }

  .text-main {
    height: 211px;
    margin: 0 auto;
    display: flex;
    align-items: center;
    flex-direction: column;
    justify-content: center;
    gap: 30px;

    h1 {
      font-family: Proxima Nova Condensed;
      font-size: 56px;
      font-weight: 700;
      line-height: 67.2px;
      text-align: center;
      color: #b01736;
    }

    p {
      font-family: "Proxima Nova Condensed";
      font-size: 32px;
      font-weight: 400;
      line-height: 38.4px;
      text-align: center;
      text-underline-position: from-font;
      text-decoration-skip-ink: none;
      letter-spacing: -1.5px;
      word-spacing: 1px;
    }

    color: #444444;
  }
}

.image-container {
  margin-top: 30px;
}

/* Transition CSS for Fade Effect Only */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.6s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

.maim-image {
  margin-top: 120px;
}
.links {
  display: flex;
  gap: 32px;
  margin-left: 28px;
  flex-wrap: wrap;
  a {
    font-family: Proxima Nova;
    font-size: 18px;
    font-weight: 600;
    line-height: 20px;
    color: #444444;
    text-underline-position: from-font;
    text-decoration-skip-ink: none;
    display: flex;
    flex-direction: column;
    gap: 11px;
    text-align: center;
    align-content: stretch;
    align-items: baseline;

    span {
      font-family: Proxima Nova;
      font-size: 18px;
      font-weight: 400;
      line-height: 20px;

      text-underline-position: from-font;
      text-decoration-skip-ink: none;
    }
  }
}
.dropdown i {
  transition: transform 0.3s ease;
}

.dropdown .rotated {
  transform: rotate(180deg);
}
@media (max-width: 1030px) {
  main {
    margin-top: 140px;

    .text-main {
      p {
        font-size: 22px !important;
      }
    }
  }
  .image-container img {
    height: 360px !important;
  }
  main .navbar .dropdown p {
    font-size: 15px;
  }
  main .navbar li {
    font-size: 11px;
  }
  main .navbar .dropdown {
    gap: 10px;
    align-items: center;
    padding-top: 4px;
  }
  main .navbar ul {
    padding-top: 10px;
  }
  .dropdown img {
    height: 21px;

    margin-top: 6px;
  }
  .maim-image img {
    height: 291px !important;
  }
  .service .package h1 {
    font-size: 30px !important;
  }

  main .navbar .dropdown-menu {
    width: 760px;
    height: 450px;
  }

  @media (max-width: 600px) {
    main .navbar {
      height: 150px;
      display: flex;
      align-items: center;
      justify-content: center;
      main .navbar ul {
        flex-wrap: wrap;
        justify-content: center;
      }
      flex-direction: column-reverse;
      main .navbar li::after {
        top: 48%;
      }
    }
    .image-container img {
      height: 200px;
    }
    .maim-image img {
      height: 200px !important;
    }

    main .navbar ul {
      flex-wrap: wrap;
    }
    main .navbar .dropdown-menu {
      width: 415px;
      height: auto;
      z-index: 1000;
    }
    .links {
      flex-direction: column;
    }
    main .navbar .dropdown-menu {
      left: -104%;
    }
    .image-container img {
      height: 210px !important;
    }
    .maim-image img {
      height: 160px !important;
    }
    .service .package h1 {
      font-size: 35px !important;
    }
    .service .program p {
      font-size: 25px;
    }
  }
  main .navbar li::after {
    top: 90%;
  }
}
   @media (max-width: 400px) {
    .image-container img {
        height: 185px !important;
    }
        .maim-image img {
        height: 141px !important;
    }
        main .text-main p {
        font-size: 20px !important;
    }
    }
</style>
