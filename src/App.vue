<template>
  <div id="app" class="center-box">
    <div class="layout">
      <div class="header">
        <h3>Header</h3>
      </div>
      <div class="layout-center">
        <div class="single-item">
          <DropDownList 
          v-model="dropdownlistValue"
          :data-source="dataSourceArray"
          :data-text-field="'text'"
          :data-value-field="'value'"
          :filter="'contains'"/>
          <div class="demo-data">
            <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Cupiditate a illum nisi non amet, ut velit, aliquid adipisci ipsa voluptates odio nihil asperiores ea voluptatibus nemo dolor cumque iure fuga.</p>
          </div>
          <DropDownList 
          v-model="dropdownlistValue"
          :data-source="dataSourceArray"
          :data-text-field="'text'"
          :data-value-field="'value'"
          :filter="'contains'"/>
          <div class="demo-data">
            <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Cupiditate a illum nisi non amet, ut velit, aliquid adipisci ipsa voluptates odio nihil asperiores ea voluptatibus nemo dolor cumque iure fuga.</p>
          </div>
          <DropDownList 
          v-model="dropdownlistValue"
          :data-source="dataSourceArray"
          :data-text-field="'text'"
          :data-value-field="'value'"
          :filter="'contains'"/>
          <div class="demo-data">
            <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Cupiditate a illum nisi non amet, ut velit, aliquid adipisci ipsa voluptates odio nihil asperiores ea voluptatibus nemo dolor cumque iure fuga.</p>
          </div>
          <DropDownList 
          v-model="dropdownlistValue"
          :data-source="dataSourceArray"
          :data-text-field="'text'"
          :data-value-field="'value'"
          :filter="'contains'"/>
          <div class="demo-data">
            <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Cupiditate a illum nisi non amet, ut velit, aliquid adipisci ipsa voluptates odio nihil asperiores ea voluptatibus nemo dolor cumque iure fuga.</p>
          </div>
          <DropDownList 
          v-model="dropdownlistValue"
          :data-source="dataSourceArray"
          :data-text-field="'text'"
          :data-value-field="'value'"
          :filter="'contains'"/>
          <div class="demo-data">
            <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Cupiditate a illum nisi non amet, ut velit, aliquid adipisci ipsa voluptates odio nihil asperiores ea voluptatibus nemo dolor cumque iure fuga.</p>
          </div>
          <DropDownList 
          v-model="dropdownlistValue"
          :data-source="dataSourceArray"
          :data-text-field="'text'"
          :data-value-field="'value'"
          :filter="'contains'"/>
          <div class="demo-data">
            <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Cupiditate a illum nisi non amet, ut velit, aliquid adipisci ipsa voluptates odio nihil asperiores ea voluptatibus nemo dolor cumque iure fuga.</p>
          </div>
          <DropDownList 
          v-model="dropdownlistValue"
          :data-source="dataSourceArray"
          :data-text-field="'text'"
          :data-value-field="'value'"
          :filter="'contains'"/>
          <div class="demo-data">
            <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Cupiditate a illum nisi non amet, ut velit, aliquid adipisci ipsa voluptates odio nihil asperiores ea voluptatibus nemo dolor cumque iure fuga.</p>
          </div>
          <DropDownList 
          v-model="dropdownlistValue"
          :data-source="dataSourceArray"
          :data-text-field="'text'"
          :data-value-field="'value'"
          :filter="'contains'"/>
          <div class="demo-data">
            <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Cupiditate a illum nisi non amet, ut velit, aliquid adipisci ipsa voluptates odio nihil asperiores ea voluptatibus nemo dolor cumque iure fuga.</p>
            <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Cupiditate a illum nisi non amet, ut velit, aliquid adipisci ipsa voluptates odio nihil asperiores ea voluptatibus nemo dolor cumque iure fuga.</p>
            <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Cupiditate a illum nisi non amet, ut velit, aliquid adipisci ipsa voluptates odio nihil asperiores ea voluptatibus nemo dolor cumque iure fuga.</p>
          </div>
        </div>
        <div class="single-item">
          <DropDownList 
          v-model="dropdownlistValue"
          :data-source="dataSourceArray"
          :data-text-field="'text'"
          :data-value-field="'value'"
          :filter="'contains'"/>
        </div>
        <div class="single-item">
          <DropDownList 
          v-model="dropdownlistValue"
          :data-source="dataSourceArray"
          :data-text-field="'text'"
          :data-value-field="'value'"
          :filter="'contains'"/>
        </div>
      </div>
      <div class="action-menu">
        <Button>Button</Button>  
        <Button>Button</Button>  
      </div>
    </div>
  </div>
</template>

<script>
import { defineComponent } from "vue";
import '@progress/kendo-ui'
import { DropDownList } from '@progress/kendo-vue-dropdowns';
import { Button } from "@progress/kendo-vue-buttons";

export default defineComponent({
  name: "App",
  components:{
    DropDownList,
    Button
  },
  data: function () {
        return {
            dropdownlistValue: "",
            dataSourceArray: [
                { text: 'Small', value: '1' },
                { text: 'Medium', value: '2' },
                { text: 'Large', value: '3' },
                { text: 'X-Large', value: '4' },
                { text: '2X-Large', value: '5' }
            ]
        };
  },
  methods:{
    toggleDialog() {
      this.visibleDialog = !this.visibleDialog;
    },
    updateDropdownValue(value) {
      this.dropdownValue = value;
    },
  }
});
</script>

<style lang="scss">
  @import "~@progress/kendo-theme-bootstrap/dist/all.scss";
  @import "~bootstrap/scss/bootstrap.scss";

.center-box{
  position: relative;
  .layout{
    display: flex;
    flex-direction: column;

    .layout-center{
      flex-grow: 1;
      height: calc(100vh - 176px);
      display: flex;
      .single-item{
        width: 33.33%;
        max-height: 100%;
        overflow-y: auto;
        border-right: 1px solid #ddd;
        padding: 50px;
      }
    }
    .header{
      background-color: #fff;
      width: 100%;
      height: 88px;
      border-bottom: 1px solid #ddd;
    }
    .action-menu{
      border-top: 1px solid #ddd;
      background-color: #fff;
      width: 100%;
      height: 88px;
    }
  }

  
}

</style>