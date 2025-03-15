<template>
  <section class="service">
    <h1>Направления бизнеса</h1>
    <div class="image-service">
      <div
        v-for="(service, index) in services"
        :key="index"
        class="image-overlay"
      >
        <img :src="service.img" :alt="service.alt" />
        <div class="overlay">
          <h2>{{ service.title }}</h2>
          <p>{{ service.description }}</p>
        </div>
      </div>
    </div>

    <div class="package">
      <h1>Компенсационный пакет</h1>
      <div class="gifts">
        <div
          v-for="(gift, index) in gifts"
          :key="index"
          class="gift-item"
          :class="gift.className"
        >
          <div class="image">
            <img :src="gift.img" :alt="gift.alt" />
          </div>
          <p v-html="gift.description"></p>
        </div>
      </div>
      <div class="line-package"></div>
      <div class="program">
        <h1>Программа дополнительной мотивации</h1>
        <p>доплата 12% от суммы</p>

        <div class="pro-item">
          <div
            v-for="(pro, index) in programItems"
            :key="index"
            class="gift-item"
            :class="pro.className"
          >
            <div class="image">
              <img :src="pro.img" :alt="pro.alt" />
            </div>
            <p>{{ pro.description }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import ser1 from "../assets/ser-1.png";
import ser2 from "../assets/ser-2.png";
import ser3 from "../assets/ser-3.png";
import ser4 from "../assets/ser-4.png";
import ser5 from "../assets/ser-5.png";
import ser6 from "../assets/ser-6.png";

import dmc from "../assets/DMC.svg";
import topt from "../assets/TOPT.svg";
import mobile from "../assets/MOBILE.svg";
import fitnes from "../assets/FITNES.svg";
import hands from "../assets/HANDS.svg";

import saves from "../assets/saves.svg";
import ipateka from "../assets/Icon.svg";

export default {
  data() {
    return {
      services: [
        {
          img: ser1,
          alt: "ser-1",
          title: "Решения Softline",
          description:
            "ГК Softline предлагает клиентам собственную линейку оборудования (ПК, серверы, торговое оборудование и проч.), разработку программных продуктов, облачных решений, решений в области информационной безопасности.",
        },
        {
          img: ser2,
          alt: "ser-2",
          title: "Кибербезопасность",
          description:
            "Softline обладает всеми необходимыми государственными лицензиями для организации проектов по информационной безопасности и аттестации.",
        },
        {
          img: ser3,
          alt: "ser-3",
          title: "Импортозамещение",
          description:
            "ГК Softline обладает широчайшим портфелем решений и услуг для импортозамещения, включая ПО и оборудование собственного производства.",
        },
        {
          img: ser4,
          alt: "ser-4",
          title: "Облачные решения",
          description:
            "Softline использует современные облачные решения как российских, так и международных вендоров для масштабирования бизнеса своих клиентов. Подписки, услуги, трансформация.",
        },
        {
          img: ser5,
          alt: "ser-5",
          title: "Цифровая трансформация и разработка ПО",
          description:
            "Softline использует современные технологи и новые возможности для увеличения производительности бизнеса заказчика. В штате ГК Softline - 2000+ разработчиков, которые трансформируют ПО под нужды конкретного предприятия.",
        },
        {
          img: ser6,
          alt: "ser-6",
          title: "Техническая поддержка Softline",
          description:
            "200+ инженеров, 24 часа в сутки, 7 дней в неделю, 12 месяцев в году, сервисное партнерство с 30+ мировыми производителями.",
        },
      ],
      gifts: [
        { img: dmc, alt: "dmc", description: "Дмс", className: "dmc" },
        {
          img: topt,
          alt: "topt",
          description: "Выходной <br />в день рождения",
          className: "topt",
        },
        {
          img: mobile,
          alt: "mobile",
          description: "Корпоративная <br />мобильная связь",
          className: "mobile",
        },
        {
          img: fitnes,
          alt: "fitnes",
          description: "Корпоративные скидки <br />на спорт",
          className: "fitnes",
        },
        { img: hands, alt: "hands", description: "LTI", className: "hands" },
      ],
      programItems: [
        {
          img: saves,
          alt: "saves",
          description: "Оргтехники",
          className: "saves",
        },
        { img: dmc, alt: "dmc", description: "ДМС", className: "dmc" },
        {
          img: ipateka,
          alt: "ipateka",
          description: "Ипотеки",
          className: "ipateka",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.service {
  margin-top: 120px;

  h1 {
    font-family: Proxima Nova Condensed;
    font-size: 56px;
    font-weight: 600;
    line-height: 56px;
    text-align: center;
    color: #444444;
  }

  .image-service {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 10px;
    padding-top: 50px;

    .image-overlay {
      position: relative;
      width: 615px;
      height: 260px;

      img {
        width: 100%;
        display: block;
      }

      .overlay {
        position: absolute;
        bottom: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background-color: rgba(45, 54, 83, 0.65);
        color: #ffffff;
        display: flex;
        flex-direction: column;
        opacity: 1;
        transition: max-height 0.5s ease, padding 0.5s ease;
        padding: 20px;
        text-align: center;
        overflow: hidden;
        max-height: 80px;
        cursor: pointer;

        h2 {
          margin: 0;
          font-family: Proxima Nova Condensed;
          font-size: 24px;
          font-weight: 600;
          line-height: 24px;
          color: #ffffff;
          text-align: left;
        }

        p {
          display: none;
        }

        &:hover {
          max-height: 100%;
          padding: 20px;

          p {
            display: block;
            font-family: Proxima Nova Condensed;
            font-size: 17px;
            font-weight: 400;
            line-height: 23.8px;
            padding-top: 20px;
            text-align: left;
          }
        }
      }
    }
  }

  .package {
    margin: 120px auto 0;
    width: 91%;
    box-shadow: 0px 0px 40px rgba(0, 0, 0, 0.06);
    background-color: #ffffff;

    h1 {
      padding-top: 80px;
      font-family: Proxima Nova Condensed;
      font-size: 56px;
      font-weight: 600;
      line-height: 56px;
      text-align: center;
      color: #444444;
    }

    .gifts,
    .pro-item {
      padding-bottom: 60px;
      display: flex;
      flex-wrap: wrap;
      justify-content: space-evenly;
      gap: 16px;
      align-items: center;
      padding-left: 50px;

      .gift-item {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 10px;

        .image {
          background-color: #f0f0f0;
          border-radius: 50%;
          width: 110px;
          height: 110px;
          display: flex;
          align-items: center;
          justify-content: center;
        }

        p {
          font-family: Proxima Nova Condensed;
          font-size: 18px;
          font-weight: 400;
          line-height: 19.8px;
          text-align: center;
          color: #444444;
        }
      }
    }

    .line-package {
      width: 80%;
      height: 1px;
      background-color: #0000000f;
      margin: 80px auto 0;
    }
  }

  .program {
    h1 {
      font-family: Proxima Nova Condensed;
      font-size: 40px;
      font-weight: 600;
      line-height: 48px;
      text-align: center;
      text-underline-position: from-font;
      text-decoration-skip-ink: none;
      color: #444444;
    }

    p {
      font-family: Proxima Nova Condensed;
      font-size: 40px;
      font-weight: 600;
      line-height: 48px;
      text-align: center;
      text-underline-position: from-font;
      text-decoration-skip-ink: none;
      color: #b01736;
    }
  }

  @media (max-width: 1030px) {
    .package {
      h1 {
        font-size: 45px !important;
      }
    }

    .gifts,
    .pro-item {
      flex-direction: column;
    }
  }

  .title-slider {
    h1 {
      font-size: 45px !important;
    }
  }
}
@media (max-width: 400px) {
  .service h1 {
    font-size: 40px;
  }
  .service .package h1 {
    font-size: 30px !important;
  }
}
</style>
