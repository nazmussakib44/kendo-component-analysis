<template>
    <div class="layout">
        <AppDropdownVue 
            :label="'Type:'" 
        :dataItem="dropdownList" :textField="'accountName'"
        :dataItemKey="'id'" :value="dropdownValue" :searchable="true"
        :class="'k-dropdownlist-sm filter-icon'"
        @updateDropdownValue="updateDropdownValue" />
    </div>
</template>

<script>
import AppDropdownVue from './AppDropdown.vue'
export default {
    components: {
        AppDropdownVue
    },
    data: function() {
        return {
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
        }
    },
    methods:{
        updateDropdownValue(value) {
            this.dropdownValue = value;
        },
    }
}
</script>
