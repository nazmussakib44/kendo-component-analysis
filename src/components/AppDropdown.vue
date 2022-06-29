<template>
  <dropdownlist
      :class="classs"
      :data-items="item"
      :text-field="textField"
      :data-item-key="dataItemKey"
      :value="value"
      :filterable="searchable"
      @change="handleDropdownChange"
      @filterchange="filterChange"
      :value-render="DropdownTemplate"
  >
    <template v-slot:DropdownTemplate="{props}">
      <span class="k-input-inner">
          {{props.value ? props.value[textField] : ''}}
        </span>
    </template>
  </dropdownlist>
</template>

<script>
import { DropDownList } from '@progress/kendo-vue-dropdowns'
import { filterBy } from '@progress/kendo-data-query';


export default {
  name: "AppDropdown",
  components: {
    'dropdownlist': DropDownList,
  },
  watch: {
    dataItem(currentValue, oldValue) {
      this.item = currentValue
    }
  },
  props: {
     id: {
      type: String,
      required: false,
    },
    label: {
      type: String,
      default: '',
      required: false,
    },
    dataItem: {
      type: Array,
      required: true,
    },
    value: {
      type: Object,
      required: false,
    },
    searchable: {
      type: Boolean,
      default: false,
      required: false,
    },
    valueItemKeyOnly: {
      type: Boolean,
      default: false,
      required: false,
    },
    classs: {
      type: String,
      default: '',
      required: false,
    },
    textField: {
      type: String,
      default: 'text',
    },
    dataItemKey: {
      type: String,
      default: 'id',
    }
  },
  data: function () {
    return {
      DropdownTemplate: 'DropdownTemplate',
      item: []
    };
  },
  mounted() {
    this.item = this.$props.dataItem;
  },
  computed: {
    selector_text() {
      return this.$props.textField;
    }
  },
  methods: {
    handleDropdownChange (event) {
      let data = {}
      if (this.$props.id) {
        data = this.$props.valueItemKeyOnly ? {id:this.$props.id, value: event.value[this.$props.dataItemKey]} : {id:this.$props.id, value : event.value}
      }
      else {
        data = this.$props.valueItemKeyOnly ?  event.value[this.$props.dataItemKey] : event.value
      }
      this.$emit('updateDropdownValue', data);
    },
    filterChange (event) {
      const dataMain = this.$props.dataItem.slice();
      this.item = filterBy(dataMain, event.filter);
    },
  }
}
</script>

