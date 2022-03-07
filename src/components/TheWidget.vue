<template>
  <div class="widget">
    <div class="header" ref="widgetheader">
      <div class="intro-wrapper">
        <p class="title uppercase">Hyundai</p>
        <h2 class="sub-title uppercase">Tucson Comfort</h2>
      </div>
      <div class="img-wrapper">
        <img alt="image" class="h-full w-full" src="@/assets/car.png" />
      </div>
    </div>
    <WidgetDetails class="desktop-wrapper" />
    <div class="price">
      <div class="action-arrow" @click="handleShowDetails">
        <i class="fa fa-chevron-up"></i>
      </div>
      <div class="price-wrapper">
        <p class="product-name">Leiguverð</p>
        <h2 class="product-price">106.190 kr. /mán.</h2>
      </div>
      <div class="btn-wrapper">
        <span class="label"> Áfram</span>
        <i class="fa fa-arrow-right"></i>
      </div>
    </div>
    <div
      class="show-details"
      v-if="showDetails"
      :style="{ top: `${getHeight}px` }"
    >
      <div class="circle" @click="handleShowDetails">
        <i class="fa fa-chevron-down"></i>
      </div>
      <div class="price">
        <div class="price-wrapper">
          <p class="product-name">Leiguverð</p>
          <h2 class="product-price">106.190 kr. /mán.</h2>
        </div>
        <div class="btn-wrapper">
          <span class="label"> Áfram</span>
          <i class="fa fa-arrow-right"></i>
        </div>
      </div>
      <WidgetDetails />
    </div>
  </div>
</template>

<script>
import WidgetDetails from "./WidgetDetails.vue";
export default {
  name: "TheWidget",
  components: {
    WidgetDetails,
  },
  data() {
    return {
      showDetails: false,
      widgetheaderHeight: 100,
    };
  },
  computed: {
    getHeight() {
      return this.widgetheaderHeight;
    },
  },
  methods: {
    handleShowDetails() {
      this.showDetails = !this.showDetails;
    },
  },
  mounted() {
    this.widgetheaderHeight =
      this.widgetheaderHeight + this.$refs.widgetheader.clientHeight;
  },
};
</script>

<style lang="scss" scoped>
.widget {
  width: 35%;
  background: white;
  height: calc(100% - 88px);
  @apply px-7 bottom-0 right-0 pt-8 fixed;

  .header {
    .intro-wrapper {
      .title {
        font-weight: bold;
        font-size: 16px;
        line-height: 120%;
        margin-bottom: 4px;
        color: $dark-blue;
      }
      .sub-title {
        font-weight: normal;
        font-size: 24px;
        line-height: 120%;
        color: $dark-blue;
        text-transform: uppercase;
        margin-bottom: 16px;
      }
    }

    .img-wrapper {
      height: 303px;
      width: 415px;
      .img {
        width: 100%;
        height: 100%;
      }
    }

    @include mobile {
      @apply flex items-center justify-between;

      .img-wrapper {
        height: 128px;
        width: 179px;
      }
    }
  }

  .price {
    height: 123px;
    background: $light-blue;
    @apply absolute bottom-0 right-0 left-0 flex items-center justify-between pl-7 pr-4;
    .price-wrapper {
      .product-name {
        font-weight: normal;
        font-size: 16px;
        line-height: 120%;
        color: $dark-gray1;
      }
      .product-price {
        font-weight: bold;
        font-size: 26px;
        line-height: 120%;
        letter-spacing: -2px;
        color: $dark-blue;
      }
    }
    .action-arrow {
      top: -11px;
      background: $light-blue;
      @apply cursor-pointer absolute flex justify-center items-center opacity-0 w-6 h-6 rounded-3xl;

      @include mobile {
        @apply opacity-100;
      }
    }
    .btn-wrapper {
      color: $white;
      display: flex;
      justify-content: space-between;
      align-items: center;
      background: $dark-blue;
      border-radius: 4px;
      padding: 8px 16px 8px 24px;
      .label {
        font-weight: bold;
        font-size: 16px;
        line-height: 100%;
        letter-spacing: 0.1px;
        margin-right: 12px;
      }
    }
  }
  @include mobile {
    width: 100%;
    position: inherit;
    padding-top: 88px;

    .desktop-wrapper {
      display: none;
    }
  }

  .show-details {
    background: $light-blue;
    box-shadow: 0px -8px 32px rgba(0, 42, 82, 0.08);
    .price {
      top: 0;
      height: 80px;
    }
    .widget-details {
      margin-top: 80px;
    }

    @apply px-8 py-4 absolute inset-0;

    .circle {
      width: 26px;
      height: 26px;
      position: absolute;
      background: $dark-blue;
      border-radius: 26px;
      color: $white;
      display: flex;
      align-items: center;
      justify-content: center;
      top: -12px;
      left: 30px;
      z-index: 1;
    }
  }
}
</style>
