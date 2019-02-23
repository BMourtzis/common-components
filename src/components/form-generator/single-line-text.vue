<template>
  <v-flex
    :key="fieldIndex"
    v-if="field.type === SINGLE_LINE_TEXT"
    xs[field.xs]="true"
    sm[field.sm]="true"
    md[field.md]="true"
  >
    <!-- :md3="field.smallQuarter"
    :md6="field.half"
    :md9="field.largeQuarter"
    :md12="field.full"-->
    <v-text-field
      v-model="model"
      :type="field.fieldType"
      :label="$t(field.label)"
      :rules="field.rules"
      :required="field.required? true: false"
      :counter="field.counter"
      :mask="field.mask"
    ></v-text-field>
  </v-flex>
</template>

<script>
export default {
  props: ["field", "model"]
};
</script>

<style lang="sass">

</style>
