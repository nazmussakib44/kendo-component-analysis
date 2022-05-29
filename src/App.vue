<template>
  <div id="app">
    <div class="item-wrap">
      <br />
      <br />
      <br />
      <br />
      <br />


      <div class="dropdown-container">
        <p>Regular dropdown from kendo</p>
        <DropDownList :data-items="sports" :default-item="'Select sport ...'">
        </DropDownList>
        <br />
        <br />
        <br />
        <p>Modified dropdown from kendo</p>
        <AppDropdown
          :label="'Type:'"
          :dataItem="dropdownList"
          :textField="'accountName'"
          :dataItemKey="'id'"
          :value="dropdownValue"
          :searchable="true"
          :class="'k-dropdownlist-sm filter-icon'"
          @updateDropdownValue="updateDropdownValue"
        />
      </div>

      <k-dialog
        v-if="visibleDialog"
        :title="'Please confirm'"
        @close="toggleDialog"
      >
        <div>
          <div class="dropdown-item">
            <DropDownList
              :data-items="sports"
              :default-item="'Select sport ...'"
            >
            </DropDownList>
          </div>
        </div>
        <dialog-actions-bar>
          <kbutton @click="toggleDialog">No</kbutton>
          <kbutton @click="toggleDialog">Yes</kbutton>
        </dialog-actions-bar>
      </k-dialog>
    </div>
  </div>
</template>

<script>
import { defineComponent, ref } from "vue";
import { useStore } from "vuex";
import "@progress/kendo-ui";
import { DropDownList } from "@progress/kendo-vue-dropdowns";
import { Dialog, DialogActionsBar, Window } from "@progress/kendo-vue-dialogs";
import { Button } from "@progress/kendo-vue-buttons";
import AppDropdown from "./components/AppDropdown.vue";

export default defineComponent({
  setup() {
    const store = useStore();
    const store_manager = ref(store.state);
    return {
      store_manager,
    };
  },
  name: "App",
  components: {
    DropDownList,
    "k-dialog": Dialog,
    "dialog-actions-bar": DialogActionsBar,
    kbutton: Button,
    AppDropdown,
  },
  data: function () {
    return {
      sports: ["Basketball", "Football", "Tennis", "Volleyball"],
      visibleDialog: false,
      dropdownValue: { id: 0, accountName: "None" },
      dropdownList: [
        { id: 0, accountName: "None" },
        { id: 1, accountName: "All Accounts" },
        { id: 2, accountName: "Active Accounts" },
        { id: 3, accountName: "Inactive Accounts" },
        { id: 4, accountName: "Dormant Accounts" },
        { id: 5, accountName: "Require Actions" },
        { id: 6, accountName: "Recently Accessed Accounts" },
      ],
    };
  },
  methods: {
    toggleDialog() {
      this.visibleDialog = !this.visibleDialog;
    },
    updateDropdownValue(value) {
      this.dropdownValue = value;
    },
  },
});
</script>

<style lang="scss">
@import "~@progress/kendo-theme-bootstrap/dist/all.scss";
@import "~bootstrap/scss/bootstrap.scss";

.item-wrap {
  height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  padding: 30px;
}
.dropdown-container {
  width:100%;
}
</style>