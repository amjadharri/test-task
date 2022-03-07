<template>
  <div class="widget-details">
    <div class="left">
      <div class="type detail">
        <p class="label">Gerð</p>
        <p class="value">
          1.600cc Bensín <br />
          Sjálfskipting - Framhjóladrif
        </p>
      </div>
      <div class="color detail">
        <p class="label">Litur</p>
        <p class="value">Kongablár</p>
      </div>
      <div class="accessories detail">
        <p class="label">Aukabúnaður</p>
        <p class="value">Toppbogar</p>
        <p class="value">Nelgd vetrardekk</p>
        <p class="value">Hjólafestingar</p>
      </div>
    </div>
    <div class="right">
      <div class="rental-period detail">
        <p class="label">Hjólafestingar</p>
        <p class="value">12 mán.</p>
      </div>
      <div class="driven detail">
        <p class="label">Akstur á ári</p>
        <p class="value">18.000 km.</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "WidgetDetails",
};
</script>

<style lang="scss" scoped>
.widget-details {
  display: flex;
  justify-content: flex-start;
  align-items: flex-start;
  margin-top: 24px;
  .left {
    margin-right: 20px;
    .type {
      .value {
        font-size: 11px;
      }
    }
    .accessories {
      .label {
        margin-bottom: 6px;
      }
    }
  }
  .detail {
    margin-bottom: 24px;
    .label {
      font-weight: normal;
      font-size: 16px;
      line-height: 120%;
      color: $dark-gray1;
    }
    .value {
      font-weight: bold;
      font-size: 18px;
      line-height: 180%;
      color: $dark-blue;
    }
  }
}
</style>
