<template>
  <div class="body-wrapper">
    <div class="tags">
      <div
        class="tag"
        :style="getTransform"
        v-for="(tag, index) in tags"
        :key="index"
        ref="tag"
      >
        <span class="tag-label">{{ tag }} </span>
      </div>
      <i
        @click="handleTransform"
        class="fa fa-chevron-right icon arrow-right-icon fa-1x"
        aria-hidden="true"
      ></i>
    </div>
    <h2 class="product-title">Gerð</h2>
    <div
      class="product-details"
      v-for="(table, tableIndex) in tableData"
      :key="tableIndex"
    >
      <div class="product-type">
        <h2 class="type capitalize">{{ table.title }}</h2>
        <h2 class="more">Nánar</h2>
      </div>
      <div class="table-details">
        <div
          class="table-row-wrapper"
          v-for="(tableRow, rowsIndex) in table.rows"
          :key="rowsIndex"
          :class="{
            'click-active':
              tableIndex === activetableIndex && rowsIndex === activeRowIndex,
          }"
        >
          <div
            class="circle-wrapper"
            v-if="!clicked"
            @click="handleActiveRow(rowsIndex, tableIndex)"
          >
            <div class="circle"></div>
          </div>
          <div class="table-row">
            <div
              v-for="({ key, value }, rowIndex) in tableRow.row"
              :key="rowIndex"
            >
              <div class="table-data">
                <span class="key">{{ key }}</span>
                <span class="value">{{ value }}</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "BodyWrapper",
  data() {
    return {
      clicked: false,
      tags: ["Gerð", "Aukabúnaður", "Litur", "Innrétting", "Leigutími"],
      activeRowIndex: null,
      activetableIndex: null,
      transformWidth: 0,
      tagIndex: 0,
      tableData: [
        {
          id: 1,
          title: "classic",
          rows: [
            {
              row: [
                { key: "Vélarstærð", value: "1600cc Bensín" },
                { key: "Skipting", value: "Beinskiptur" },
                { key: "Drif", value: "Framhjóladrif" },
                { key: "Co2 frá", value: "95 g/km" },
                { key: "Eyðsla frá ", value: "3,7 l/100km" },
                { key: "Afl og tog", value: "100hö/160nm" },
              ],
            },
            {
              row: [
                { key: "Vélarstærð", value: "1600cc Bensín" },
                { key: "Skipting", value: "Beinskiptur" },
                { key: "Drif", value: "Framhjóladrif" },
                { key: "Co2 frá", value: "95 g/km" },
                { key: "Eyðsla frá ", value: "3,7 l/100km" },
                { key: "Afl og tog", value: "100hö/160nm" },
              ],
            },
            {
              row: [
                { key: "Vélarstærð", value: "1600cc Bensín" },
                { key: "Skipting", value: "Beinskiptur" },
                { key: "Drif", value: "Framhjóladrif" },
                { key: "Co2 frá", value: "95 g/km" },
                { key: "Eyðsla frá ", value: "3,7 l/100km" },
                { key: "Afl og tog", value: "100hö/160nm" },
              ],
            },
            {
              row: [
                { key: "Vélarstærð", value: "1600cc Bensín" },
                { key: "Skipting", value: "Beinskiptur" },
                { key: "Drif", value: "Framhjóladrif" },
                { key: "Co2 frá", value: "95 g/km" },
                { key: "Eyðsla frá ", value: "3,7 l/100km" },
                { key: "Afl og tog", value: "100hö/160nm" },
              ],
            },
            {
              row: [
                { key: "Vélarstærð", value: "1600cc Bensín" },
                { key: "Skipting", value: "Beinskiptur" },
                { key: "Drif", value: "Framhjóladrif" },
                { key: "Co2 frá", value: "95 g/km" },
                { key: "Eyðsla frá ", value: "3,7 l/100km" },
                { key: "Afl og tog", value: "100hö/160nm" },
              ],
            },
          ],
        },
        {
          id: 2,
          title: "Premium",
          rows: [
            {
              row: [
                { key: "Vélarstærð", value: "1600cc Bensín" },
                { key: "Skipting", value: "Beinskiptur" },
                { key: "Drif", value: "Framhjóladrif" },
                { key: "Co2 frá", value: "95 g/km" },
                { key: "Eyðsla frá ", value: "3,7 l/100km" },
                { key: "Afl og tog", value: "100hö/160nm" },
              ],
            },
            {
              row: [
                { key: "Vélarstærð", value: "1600cc Bensín" },
                { key: "Skipting", value: "Beinskiptur" },
                { key: "Drif", value: "Framhjóladrif" },
                { key: "Co2 frá", value: "95 g/km" },
                { key: "Eyðsla frá ", value: "3,7 l/100km" },
                { key: "Afl og tog", value: "100hö/160nm" },
              ],
            },
            {
              row: [
                { key: "Vélarstærð", value: "1600cc Bensín" },
                { key: "Skipting", value: "Beinskiptur" },
                { key: "Drif", value: "Framhjóladrif" },
                { key: "Co2 frá", value: "95 g/km" },
                { key: "Eyðsla frá ", value: "3,7 l/100km" },
                { key: "Afl og tog", value: "100hö/160nm" },
              ],
            },
            {
              row: [
                { key: "Vélarstærð", value: "1600cc Bensín" },
                { key: "Skipting", value: "Beinskiptur" },
                { key: "Drif", value: "Framhjóladrif" },
                { key: "Co2 frá", value: "95 g/km" },
                { key: "Eyðsla frá ", value: "3,7 l/100km" },
                { key: "Afl og tog", value: "100hö/160nm" },
              ],
            },
          ],
        },
      ],
    };
  },
  computed: {
    getTransform() {
      return `transform: translateX(${this.transformWidth}px);`;
    },
  },
  methods: {
    handleActiveRow(rowIndex, tableIndex) {
      this.activeRowIndex = rowIndex;
      this.activetableIndex = tableIndex;
    },
    handleTransform() {
      if (this.tagIndex < this.tags.length) {
        this.transformWidth =
          this.transformWidth - this.$refs.tag[0].clientWidth;
        this.tagIndex = this.tagIndex + 1;
        console.log({ index: this.tagIndex });
      }
    },
  },
};
</script>

<style lang="scss" scoped>
.body-wrapper {
  width: 65%;
  height: 100%;
  padding-top: 88px;
  .tags {
    overflow-x: hidden;
    @apply flex  items-center px-8 py-2 mt-3 relative;
    @include mobile {
      background: $light-gray1;
      padding: 0 16px 0 60%;
      @apply py-4;

      .arrow-right-icon {
        @apply absolute right-4;
      }
    }

    .tag {
      position: relative;
      &:first-child {
        font-size: 14px;
        line-height: 170%;
        background: $light-blue;
        color: $dark-blue;

        @apply py-0 px-4 rounded font-bold;
      }

      &::after {
        content: "";
        background: $light-green;
        top: 10px;
        right: -28px;
        @apply w-1 h-1 rounded absolute;
      }
      margin-right: 44px;
      .tag-label {
        font-size: 14px;
        color: $dark-gray2;
        @apply capitalize;
      }
    }
    .icon {
      color: $dark-blue;
      @include tablet {
        @apply sticky right-0;
      }
      @include mobile {
        @apply sticky right-0;
      }
    }
  }
  .product-title {
    font-size: 20px;
    line-height: 120%;
    color: $dark-blue;
    margin-top: 55px;
    @apply px-8 font-bold;
  }
  .product-details {
    padding: 20px 0 0px 16px;
    background: $white;
    @apply mx-8 mt-11 rounded-lg;
    .product-type {
      font-size: 20px;
      line-height: 120%;
      color: $dark-blue;
      border-bottom: 1px solid $light-blue;
      @apply flex justify-between items-center pr-4 font-bold pb-5;
    }

    .table-details {
      .table-row-wrapper {
        border-bottom: 1px solid $light-blue;

        &.click-active {
          background: $dark-blue;

          .table-row {
            .table-data {
              .key,
              .value {
                color: $white;
              }
            }
          }

          .circle-wrapper {
            .circle {
              &::before {
                content: "";
                background: $dark-blue;
                border-radius: 10px;
                inset: 3px;
                @apply absolute;
              }
            }
          }
        }
        @apply flex  py-4 items-center px-8 pl-0;
        .circle-wrapper {
          padding: 8px;
          border-radius: 20px;
          margin-left: -8px;
          background: $white;
          .circle {
            border: 2px solid $dark-blue;
            @apply w-5 h-5 rounded-3xl cursor-pointer relative;
          }
        }
        .table-row {
          @apply flex flex-wrap justify-between ml-4 w-full;
          .table-data {
            @apply flex flex-col my-1;

            .key {
              font-size: 14px;
              font-weight: bold;
              color: $dark-blue;
            }
            .value {
              font-size: 14px;
              font-weight: normal;
              color: $dark-blue;
            }
          }

          @include mobile {
            @apply justify-start;

            .table-data {
              @apply mr-4;
            }
          }
        }
      }
    }
  }

  @include mobile {
    width: 100%;
    background: $white;
    padding-bottom: 110px;
    height: max-content;
    padding-top: 34px;
    .product-details {
      margin: 20px 0px;
      .product-type {
        padding: 20px 16px;
      }
    }
    .product-title {
      display: none;
    }
  }
}
</style>
