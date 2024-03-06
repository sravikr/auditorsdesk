<script setup>
import { onMounted, ref } from "vue";
import { useToast } from 'primevue/usetoast';
import "./shareholding.css";
let headerHeight = 0; // Initialize with a default value
const products = ref([]);


onMounted(async () => {
  const header = document.querySelector(".site-header");
  if (header) {
    headerHeight = header.clientHeight;

    const sidebar = document.querySelector(".sidebar-menu");
    const mainContentSection = document.querySelector(".main-content-sec");
    if (mainContentSection) {
      mainContentSection.style.marginLeft = `${sidebar.clientWidth}px`;
    }
  }


  // Function to calculate and set the dashboard height
  function setDashboardHeight(selector, topPosition) {
    const dashboardElement = document.querySelector(selector);

    if (dashboardElement) {
      // Calculate the offset top and client height
      const dashboardOffsetTop = dashboardElement.offsetTop;

      // Calculate the desired height
      const dashboardNewHeight =
        window.outerHeight - (dashboardOffsetTop + topPosition);

      // Set the new height
      dashboardElement.style.height = `${dashboardNewHeight}px`;
    }

    // Check if the body has the class and remove overflow hidden if it does
    const bodyElement = document.querySelector("body");
    if (bodyElement.classList.contains("dashboard-body-overflow-hidden")) {
      bodyElement.style.overflow = "visible";
    }
  }

  // Set the body overflow to hidden on page load
  document.addEventListener("DOMContentLoaded", function () {
    const bodyElement = document.querySelector("body");
    bodyElement.classList.add("dashboard-body-overflow-hidden");

    // Call the function to set the dashboard height on load for left sidebar
    setDashboardHeight(".dashboard-w-sidebar-left", 130);
    // Call the function to set the dashboard height on load for right sidebar
    setDashboardHeight(".dashboard-w-sidebar-right ul", 165);
    setDashboardHeight(".dashboard-w-sidebar-right", 145);
  });

  // Set the body overflow to visible on window resize
  window.addEventListener("resize", function () {
    const bodyElement = document.querySelector("body");
    bodyElement.style.overflow = "visible";

    setDashboardHeight(".dashboard-w-sidebar-left", 130);
    // Call the function to set the dashboard height on load for right sidebar
    setDashboardHeight(".dashboard-w-sidebar-right ul", 165);
    setDashboardHeight(".dashboard-w-sidebar-right", 145);
  });
});

const expandedRows = ref([
  
]);
const expandableData = ref([
  {
    id:1,
    name: "Rajat Gupta",
    related_party_transaction: `No data`,
    other_directorships: "view",
    shareholding:
      "view",
      personal_details: "view",
    
  },
  {
    id:2,
    name: "Rajat Gupta",
    related_party_transaction: `No data`,
    other_directorships: "view",
    shareholding:
      "view",
      personal_details: "view",
    
  }, {
    id:3,
    name: "Rajat Gupta",
    related_party_transaction: `No data`,
    other_directorships: "view",
    shareholding:
      "view",
      personal_details: "view",
    
  }, {
    id:4,
    name: "Rajat Gupta",
    related_party_transaction: `No data`,
    other_directorships: "view",
    shareholding:
      "view",
      personal_details: "view",
    
  }, {
    id:5,
    name: "Rajat Gupta",
    related_party_transaction: `No data`,
    other_directorships: "view",
    shareholding:
      "view",
      personal_details: "view",
    
  }, {
    id:6,
    name: "Rajat Gupta",
    related_party_transaction: `No data`,
    other_directorships: "view",
    shareholding:
      "view",
      personal_details: "view",
    
  }, {
    id:7,
    name: "Rajat Gupta",
    related_party_transaction: `No data`,
    other_directorships: "view",
    shareholding:
      "view",
      personal_details: "view",
    
  }, {
    id:8,
    name: "Rajat Gupta",
    related_party_transaction: `No data`,
    other_directorships: "view",
    shareholding:
      "view",
      personal_details: "view",
    
  }, {
    id:9,
    name: "Rajat Gupta",
    related_party_transaction: `No data`,
    other_directorships: "view",
    shareholding:
      "view",
      personal_details: "view",
    
  }, {
    id:10,
    name: "Rajat Gupta",
    related_party_transaction: `No data`,
    other_directorships: "view",
    shareholding:
      "view",
      personal_details: "view",
    
  }, {
    id:11,
    name: "Rajat Gupta",
    related_party_transaction: `No data`,
    other_directorships: "view",
    shareholding:
      "view",
      personal_details: "view",
    
  }, {
    id:12,
    name: "Rajat Gupta",
    related_party_transaction: `No data`,
    other_directorships: "view",
    shareholding:
      "view",
      personal_details: "view",
    
  }, {
    id:13,
    name: "Rajat Gupta",
    related_party_transaction: `No data`,
    other_directorships: "view",
    shareholding:
      "view",
      personal_details: "view",
    
  }, {
    id:14,
    name: "Rajat Gupta",
    related_party_transaction: `No data`,
    other_directorships: "view",
    shareholding:
      "view",
      personal_details: "view",
    
  }, {
    id:15,
    name: "Rajat Gupta",
    related_party_transaction: `No data`,
    other_directorships: "view",
    shareholding:
      "view",
      personal_details: "view",
    
  },

  // Add more dummy data as needed
]);

const  expandedData = ref([
{
  financial_year: "2022",
  entity_type: `Company`,
  entity_name: "LENSKART EYETECH PRIVATE LIMITED",
  common_directors:"Yes",

    relationship: "Subsidiary",
    transaction_type: "Others",
    amount: "20,870,000.00",
  },{
  financial_year: "2022",
  entity_type: `Company`,
  entity_name: "LENSKART EYETECH PRIVATE LIMITED",
  common_directors:"Yes",

    relationship: "Subsidiary",
    transaction_type: "Others",
    amount: "20,870,000.00",
  },{
  financial_year: "2022",
  entity_type: `Company`,
  entity_name: "LENSKART EYETECH PRIVATE LIMITED",
  common_directors:"Yes",

    relationship: "Subsidiary",
    transaction_type: "Others",
    amount: "20,870,000.00",
  },{
  financial_year: "2022",
  entity_type: `Company`,
  entity_name: "LENSKART EYETECH PRIVATE LIMITED",
  common_directors:"Yes",

    relationship: "Subsidiary",
    transaction_type: "Others",
    amount: "20,870,000.00",
  },{
  financial_year: "2022",
  entity_type: `Company`,
  entity_name: "LENSKART EYETECH PRIVATE LIMITED",
  common_directors:"Yes",

    relationship: "Subsidiary",
    transaction_type: "Others",
    amount: "20,870,000.00",
  },{
  financial_year: "2022",
  entity_type: `Company`,
  entity_name: "LENSKART EYETECH PRIVATE LIMITED",
  common_directors:"Yes",

    relationship: "Subsidiary",
    transaction_type: "Others",
    amount: "20,870,000.00",
  },{
  financial_year: "2022",
  entity_type: `Company`,
  entity_name: "LENSKART EYETECH PRIVATE LIMITED",
  common_directors:"Yes",

    relationship: "Subsidiary",
    transaction_type: "Others",
    amount: "20,870,000.00",
  },{
  financial_year: "2022",
  entity_type: `Company`,
  entity_name: "LENSKART EYETECH PRIVATE LIMITED",
  common_directors:"Yes",

    relationship: "Subsidiary",
    transaction_type: "Others",
    amount: "20,870,000.00",
  },{
  financial_year: "2022",
  entity_type: `Company`,
  entity_name: "LENSKART EYETECH PRIVATE LIMITED",
  common_directors:"Yes",

    relationship: "Subsidiary",
    transaction_type: "Others",
    amount: "20,870,000.00",
  },{
  financial_year: "2022",
  entity_type: `Company`,
  entity_name: "LENSKART EYETECH PRIVATE LIMITED",
  common_directors:"Yes",

    relationship: "Subsidiary",
    transaction_type: "Others",
    amount: "20,870,000.00",
  },{
  financial_year: "2022",
  entity_type: `Company`,
  entity_name: "LENSKART EYETECH PRIVATE LIMITED",
  common_directors:"Yes",

    relationship: "Subsidiary",
    transaction_type: "Others",
    amount: "20,870,000.00",
  },{
  financial_year: "2022",
  entity_type: `Company`,
  entity_name: "LENSKART EYETECH PRIVATE LIMITED",
  common_directors:"Yes",

    relationship: "Subsidiary",
    transaction_type: "Others",
    amount: "20,870,000.00",
  },{
  financial_year: "2022",
  entity_type: `Company`,
  entity_name: "LENSKART EYETECH PRIVATE LIMITED",
  common_directors:"Yes",

    relationship: "Subsidiary",
    transaction_type: "Others",
    amount: "20,870,000.00",
  },{
  financial_year: "2022",
  entity_type: `Company`,
  entity_name: "LENSKART EYETECH PRIVATE LIMITED",
  common_directors:"Yes",

    relationship: "Subsidiary",
    transaction_type: "Others",
    amount: "20,870,000.00",
  },{
  financial_year: "2022",
  entity_type: `Company`,
  entity_name: "LENSKART EYETECH PRIVATE LIMITED",
  common_directors:"Yes",

    relationship: "Subsidiary",
    transaction_type: "Others",
    amount: "20,870,000.00",
  },{
  financial_year: "2022",
  entity_type: `Company`,
  entity_name: "LENSKART EYETECH PRIVATE LIMITED",
  common_directors:"Yes",

    relationship: "Subsidiary",
    transaction_type: "Others",
    amount: "20,870,000.00",
  },
])


const showFilterMenu = ref(false);
const toggleFilterMenu = () => {
  showFilterMenu.value = !showFilterMenu.value;
};
const visible = ref(false);

const selectedCities = ref();
const groupedCities = ref([
  {
    label: "Germany",
    code: "DE",
    items: [
      { label: "Berlin", value: "Berlin" },
      { label: "Frankfurt", value: "Frankfurt" },
      { label: "Hamburg", value: "Hamburg" },
      { label: "Munich", value: "Munich" },
    ],
  },
  {
    label: "USA",
    code: "US",
    items: [
      { label: "Chicago", value: "Chicago" },
      { label: "Los Angeles", value: "Los Angeles" },
      { label: "New York", value: "New York" },
      { label: "San Francisco", value: "San Francisco" },
    ],
  },
  {
    label: "Japan",
    code: "JP",
    items: [
      { label: "Kyoto", value: "Kyoto" },
      { label: "Osaka", value: "Osaka" },
      { label: "Tokyo", value: "Tokyo" },
      { label: "Yokohama", value: "Yokohama" },
    ],
  },
]);

const op = ref();
const isToggled = ref(false)

const toggle = (event) => {
    op.value.toggle(event);
    isToggled.value = !isToggled.value

}
const expandRow = (rowData) => {
  console.log("rowData", rowData)
  // Add logic to determine which row is clicked and add it to expandedRows
  // You can use the index or ID of the row to identify it
  const rowIndex = rowData.id;
  if (!expandedRows.value.includes(rowIndex)) {
    expandedRows.value.push(rowIndex);
  } else {
    expandedRows.value = expandedRows.value.filter((row) => row !== rowIndex);
  }
};

const selectedProduct = ref();
const toast = useToast();
const onRowSelect = (event) => {
    toast.add({ severity: 'info', summary: 'Product Selected', detail: 'Name: ' + event.data.name, life: 3000 });
};
const onRowUnselect = (event) => {
    toast.add({ severity: 'warn', summary: 'Product Unselected', detail: 'Name: ' + event.data.name, life: 3000 });
}
const isExpanded = (row) => {
  return row && expandedRows.value.includes(row.id);
};
</script>

<template>
  <div class="main-container">
    <div class="container-fluid">
      <div class="sidebar-menu-toggle" @click="visible = true">
        <img src="/src/assets/icon-observations-1.svg" alt=" observation" />
        Stackholders
      </div>
      <Sidebar v-model:visible="visible">
        <template #container="{ closeCallback }">
          <div class="sidebar-menu-submenu">
            <span
              class="sidebar-menu-submenu-redirect"
              @click="visible = false"
            >
              <img
                src="/src/assets/icon-observations-1.svg"
                alt=" observation"
              />Observations
            </span>
            <ul>
              <li>
                <a href="">Analysis</a>
                <Avatar
                  severity="secondary"
                  v-badge.secondary="1"
                  size="large"
                  shape="circle"
                >
                  <span class="material-symbols-outlined"> flag </span>
                </Avatar>
              </li>
              <li>
                <a href="">Stackholders</a>
                <Avatar
                  severity="secondary"
                  v-badge.secondary="1"
                  size="large"
                  shape="circle"
                >
                  <span class="material-symbols-outlined"> flag </span>
                </Avatar>
              </li>
              <li>
                <a href=""> Complainces</a>
                <Avatar
                  severity="secondary"
                  v-badge.secondary="1"
                  size="large"
                  shape="circle"
                >
                  <span class="material-symbols-outlined"> flag </span>
                </Avatar>
              </li>
            </ul>
          </div>
        </template>
      </Sidebar>

      <div class="page-title">
        <h3>Directors</h3>
        <div class="filter-sec">
          <div class="filter-menu">
            <IconField iconPosition="left">
              <InputIcon>
                <span class="material-symbols-outlined"> search </span>
              </InputIcon>
              <InputText v-model="value1" placeholder="Search" />
            </IconField>
            <MultiSelect
              v-model="selectedCities"
              :options="groupedCities"
              optionLabel="label"
              optionGroupLabel="label"
              optionGroupChildren="items"
              placeholder="Filter"
              class="w-full filter-multiselect"
              style="max-width: 200px"
            >
              <template #optiongroup="slotProps">
                <div class="flex align-items-center">
                  <div>{{ slotProps.option.label }}</div>
                </div>
              </template>
            </MultiSelect>

            <button class="btn btn-outline-blue btn-export">Export</button>
          </div>
        </div>
      </div>

      <div class="dashboard-w-sidebar">
        <div class="dashboard-w-sidebar-left">
          <div class="table-w-header-blue uppercase wo-padding ratio">
            
            <DataTable
                paginator
                :rows="10"
                :value="expandableData"
                :size="medium"
                tableStyle="min-width: 80rem"
                v-model:expandedRows="expandedRows"
                dataKey="id"  
                :expanded-row-class="customExpandedRowClass"
                :clicked-row="id"
                v-model:selection="selectedProduct"
                @rowSelect="onRowSelect" 
                @rowUnselect="onRowUnselect"
                selectionMode="single" 
                :rowClassName="{ 'parent-row-expanded': isExpanded(row) }"
                
              >
              <template>
                <div>
                  <p-dataTable :value="tableData" :rows="10" :paginator="true" :selectionMode="selectionMode"
                              selectionChange="onRowSelect" dataKey="id" :expandedRows="expandedRows" rowExpandMode="single"
                              rowExpandIcon="pi pi-caret-down" rowCollapseIcon="pi pi-caret-up"
                              rowClassName="{ 'parent-row-expanded': isExpanded(row) }">
                    <p-column field="name" header="Name" style="min-width: 20%"></p-column>
                    <template #expansion>
                      <p-dataTable :value="expandedData" :scrollable="true" scrollHeight="400px" style="min-width: 82rem">
                        </p-dataTable>
                    </template>
                  </p-dataTable>
                </div>
              </template>

                <Column field="name" header="Name" style="min-width: 20%"> 
                  <template #body="slotProps">
                    <div class="d-flex align-items-center">
                      <span class="icon-w-bg green me-2">
                        <img src="/src/assets/icon-flag-table.svg" alt="" />
                      </span>
                      <span class="text-light-grey">{{ slotProps.data.name }}</span>
                      <span :class="{ 'text-primary': isToggled }" @click="toggle" class="material-symbols-outlined filled text-light-grey ms-1">
                        error
                      </span>
                     
                    </div>
                    <OverlayPanel class="event-change-overlay" ref="op">
                        
                          <ul>
                            <li>
                              <span>Event Date</span>
                              <strong>29 Sep, 2019</strong>
                              </li>
                              <li>
                              <span>Event</span>
                              <strong>Change in Designation</strong>
                              </li>
                              <li>
                              <span>Designation After Event</span>
                              <strong>Director</strong>
                              </li>
                            </ul>
                      </OverlayPanel>
                  </template>
                </Column>
                
                <Column  expander field="related_party_transaction" header="Related Party Transaction" style="min-width: 20%" @click="isExpanded">
                </Column>
               
                <Column field="other_directorships" header="Other Directorships"  style="min-width: 20%">
                
              </Column>
              <Column field="shareholding" header="Shareholding"  style="min-width: 20%"></Column>
              <Column field="personal_details" header="Personal Details"  style="min-width: 20%"></Column>
              <template #expansion="expanseProps">
                
                    
                  <DataTable :value="expandedData" scrollable scrollHeight="400px"  tableStyle="min-width: 82rem">
                    <div class="shareholding-inner-data">
                      <span>Shareholding %  
:
15%</span><span>
Number of shares  
:
1,18,75,887</span>
<span>
Cessation Date
:
12 Mar, 2010</span>
                      </div>
                        </DataTable>
                
            </template>
                
              </DataTable>
            
          </div>
          
        </div>
        <div class="dashboard-w-sidebar-right">
          <div class="dashboard-w-sidebar-top">
            <strong>Observations</strong>
            <div class="sidebar-action">
              <span class="material-symbols-outlined"> open_in_new </span>
              <span class="material-symbols-outlined"> filter_alt </span>
              <span class="material-symbols-outlined"> add </span>
            </div>
          </div>
          <div class="sidebar-action-search">
            <AutoComplete
              class="sidebar-action-search-autocomplete"
              v-model="value"
              :suggestions="items"
              @complete="search"
            />
          </div>
          <div class="sidebar-action-list">
            <ul>
              <li>
                <div class="panel-card">
                  <div class="panel-card-header">
                    <strong>Revenue Growth (%)</strong>
                    <span>31 mar 2012</span>
                  </div>
                  <div class="panel-card-body">
                    The director is changed but the same is not recorded in
                    director is changed
                    <span class="more-text">...More</span>
                  </div>

                  <div class="panel-card-footer">
                    <Avatar
                      image="https://primefaces.org/cdn/primevue/images/avatar/asiyajavayant.png"
                      class="mr-2"
                      size="small"
                      shape="circle"
                    />
                    James Green
                  </div>
                </div>
              </li>
              <li>
                <div class="panel-card">
                  <div class="panel-card-header">
                    <strong>Revenue Growth (%)</strong>
                    <span>31 mar 2012</span>
                  </div>
                  <div class="panel-card-body">
                    The director is changed but the same is not recorded in
                    director is changed
                    <span class="more-text">...More</span>
                  </div>

                  <div class="panel-card-footer">
                    <Avatar
                      image="https://primefaces.org/cdn/primevue/images/avatar/asiyajavayant.png"
                      class="mr-2"
                      size="small"
                      shape="circle"
                    />
                    James Green
                  </div>
                </div>
              </li>
              <li>
                <div class="panel-card">
                  <div class="panel-card-header">
                    <strong>Revenue Growth (%)</strong>
                    <span>31 mar 2012</span>
                  </div>
                  <div class="panel-card-body">
                    The director is changed but the same is not recorded in
                    director is changed
                    <span class="more-text">...More</span>
                  </div>

                  <div class="panel-card-footer">
                    <Avatar
                      image="https://primefaces.org/cdn/primevue/images/avatar/asiyajavayant.png"
                      class="mr-2"
                      size="small"
                      shape="circle"
                    />
                    James Green
                  </div>
                </div>
              </li>
              <li>
                <div class="panel-card">
                  <div class="panel-card-header">
                    <strong>Revenue Growth (%)</strong>
                    <span>31 mar 2012</span>
                  </div>
                  <div class="panel-card-body">
                    The director is changed but the same is not recorded in
                    director is changed
                    <span class="more-text">...More</span>
                  </div>

                  <div class="panel-card-footer">
                    <Avatar
                      image="https://primefaces.org/cdn/primevue/images/avatar/asiyajavayant.png"
                      class="mr-2"
                      size="small"
                      shape="circle"
                    />
                    James Green
                  </div>
                </div>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
