<template>
  <div @mousedown="fieldsAreaDown">
    <el-button v-for="(field) in fields" :key="field.id" size="mini" class="field-area" @click="fieldSelect(field)">
      {{ field.name }}
    </el-button>
  </div>
</template>

<script>
import bus from '@/utils/bus'

export default {
  name: 'FieldsList',
  props: {
    fields: {
      type: Array,
      default: () => []
    },
    element: {
      type: Object,
      default: null
    }
  },
  data() {
    return {
    }
  },
  computed: {

  },
  watch: {

  },
  mounted() {
  },
  methods: {
    fieldSelect(field) {
      bus.$emit('fieldSelect-' + this.element.propValue.viewId, field)
    },
    fieldsAreaDown(e) {
      // ignore
      e.preventDefault()
    }
  }
}
</script>

<style scoped>
.field-area{
  width: 174px;
  margin: 4px 0 0 0;
  text-align: left;
  margin-left: 0px!important;
}

</style>
