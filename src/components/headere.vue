<template>
  <header class="header">
    <div class="container">
      <nav class="nav">
        <input
          type="checkbox"
          id="menu-toggle"
          class="menu-toggle"
          v-model="isMenuOpen"
        />
        <label for="menu-toggle" class="menu-icon">
          <i
            :class="isMenuOpen ? 'fas fa-times rotate' : 'fas fa-bars rotate'"
          ></i>
        </label>
        <div class="logo">
          <img src="../assets/logo (5) 1.svg" alt="logo" />
        </div>
        <ul class="list" :class="{ 'list--open': isMenuOpen }">
          <li><a href="#Облачные решения">Облачные решения</a></li>
          <li><a href="#Кибербезопасность">Кибербезопасность</a></li>
          <li><a href="#Импортозамещение">Импортозамещение</a></li>
          <li><a href="#Цифровая трансформация">Цифровая трансформация</a></li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<style lang="scss" scoped>
.header {
  padding-top: 31px;
  border: 1px solid #d9d9d9;
  height: 85px;

  .nav {
    display: flex;
    align-items: center;
    width: 100%;
    justify-content: space-around;
    position: relative;

    .menu-toggle {
      display: none;
    }

    .menu-icon {
      display: none;
      cursor: pointer;
      font-size: 24px;
      color: #444444;
    }

    .menu-icon i {
      transition: transform 0.3s ease;
    }

    .menu-icon .fa-bars {
      transform: rotate(0deg);
    }

    .menu-icon .fa-times {
      transform: rotate(180deg);
    }

    .list {
      display: flex;
      align-items: center;
      gap: 20px;

      li a {
        color: #444444;
        font-family: Proxima Nova Condensed;
        font-size: 18px;
        font-weight: 600;
        line-height: 20px;
        text-underline-position: from-font;
        text-decoration-skip-ink: none;
      }
    }

    @media (max-width: 1030px) {
      .menu-icon {
        display: block;
        z-index: 10;
      }

      .list {
        position: absolute;
        top: 100%;
        right: 0;
        margin-top: 23px;
        background-color: white;
        width: 100%;
        flex-direction: column;
        align-items: center;
        gap: 15px;
        padding: 20px 0;
        box-shadow: 0px 8px 16px rgba(77, 66, 66, 0.2);

        visibility: hidden;
        opacity: 0;
        transform: translateY(-20px);
        transition: visibility 0s 0.3s, opacity 0.3s ease, transform 0.3s ease;

        &--open {
          visibility: visible;
          opacity: 1;
          transform: translateY(0);
          transition-delay: 0s;
        }
      }
  
    }
  }
}
</style>

<script>
export default {
  name: "Header",
  data() {
    return {
      isMenuOpen: false,
    };
  },
};
</script>
