<script setup>
import { onMounted, ref } from "vue";
import "./related-party-transaction.css";
let headerHeight = 0; // Initialize with a default value
const products = ref([]);
const responsiveOptions = ref([
  {
    breakpoint: "1400px",
    numVisible: 2,
    numScroll: 1,
  },
  {
    breakpoint: "1199px",
    numVisible: 3,
    numScroll: 1,
  },
  {
    breakpoint: "767px",
    numVisible: 2,
    numScroll: 1,
  },
  {
    breakpoint: "575px",
    numVisible: 1,
    numScroll: 1,
  },
]);

const getSeverity = (status) => {
  switch (status) {
    case "INSTOCK":
      return "success";

    case "LOWSTOCK":
      return "warning";

    case "OUTOFSTOCK":
      return "danger";

    default:
      return null;
  }
};

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

  // Call the generateDummyProducts function to get dummy data
  const data = await generateDummyProducts();
  products.value = data.slice(0, 5);

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

const generateDummyProducts = () => {
  const dummyProducts = [];

  for (let i = 1; i <= 20; i++) {
    dummyProducts.push({
      id: i,
      name: `Product ${i}`,
      price: Math.floor(Math.random() * 100) + 1,
      status: i % 3 === 0 ? "INSTOCK" : i % 3 === 1 ? "LOWSTOCK" : "OUTOFSTOCK",
    });
  }

  return Promise.resolve(dummyProducts);
};

const expandableData = ref([
  {
    name: "Rajat Gupta",
    related_party_transaction: `No data`,
    other_directorships: "view",
    shareholding:
      "view",
      personal_details: "view",
    
  },
  {
    name: "2.",
    related_party_transaction: `Revenue Growth (%)`,
     other_directorships: "31 mar 2012",
    shareholding:
      "The director is changed but the same is not recorded in  director is changed...",
    personal_details: "26 May, 2023",
    generated_by: "James Green",
  },
  {
    name: "3.",
    related_party_transaction: `Revenue Growth (%)`,
     other_directorships: "31 mar 2012",
    shareholding:
      "The director is changed but the same is not recorded in  director is changed...",
    personal_details: "26 May, 2023",
    generated_by: "James Green",
  },
  {
    name: "4.",
    related_party_transaction: `Revenue Growth (%)`,
     other_directorships: "31 mar 2012",
    shareholding:
      "The director is changed but the same is not recorded in  director is changed...",
    personal_details: "26 May, 2023",
    generated_by: "James Green",
  },
  {
    name: "5.",
    related_party_transaction: `Revenue Growth (%)`,
     other_directorships: "31 mar 2012",
    shareholding:
      "The director is changed but the same is not recorded in  director is changed...",
    personal_details: "26 May, 2023",
    generated_by: "James Green",
  },
  {
    name: "6.",
    related_party_transaction: `Revenue Growth (%)`,
     other_directorships: "31 mar 2012",
    shareholding:
      "The director is changed but the same is not recorded in  director is changed...",
    personal_details: "26 May, 2023",
    generated_by: "James Green",
  },
  {
    name: "7.",
    related_party_transaction: `Revenue Growth (%)`,
     other_directorships: "31 mar 2012",
    shareholding:
      "The director is changed but the same is not recorded in  director is changed...",
    personal_details: "26 May, 2023",
    generated_by: "James Green",
  },
  {
    name: "8.",
    related_party_transaction: `Revenue Growth (%)`,
     other_directorships: "31 mar 2012",
    shareholding:
      "The director is changed but the same is not recorded in  director is changed...",
    personal_details: "26 May, 2023",
    generated_by: "James Green",
  },
  {
    name: "9.",
    related_party_transaction: `Revenue Growth (%)`,
     other_directorships: "31 mar 2012",
    shareholding:
      "The director is changed but the same is not recorded in  director is changed...",
    personal_details: "26 May, 2023",
    generated_by: "James Green",
  },
  {
    name: "10.",
    related_party_transaction: `Revenue Growth (%)`,
     other_directorships: "31 mar 2012",
    shareholding:
      "The director is changed but the same is not recorded in  director is changed...",
    personal_details: "26 May, 2023",
    generated_by: "James Green",
  },
  {
    name: "11.",
    related_party_transaction: `Revenue Growth (%)`,
     other_directorships: "31 mar 2012",
    shareholding:
      "The director is changed but the same is not recorded in  director is changed...",
    personal_details: "26 May, 2023",
    generated_by: "James Green",
  },
  {
    name: "12.",
    related_party_transaction: `Revenue Growth (%)`,
     other_directorships: "31 mar 2012",
    shareholding:
      "The director is changed but the same is not recorded in  director is changed...",
    personal_details: "26 May, 2023",
    generated_by: "James Green",
  },
  {
    name: "13.",
    related_party_transaction: `Revenue Growth (%)`,
     other_directorships: "31 mar 2012",
    shareholding:
      "The director is changed but the same is not recorded in  director is changed...",
    personal_details: "26 May, 2023",
    generated_by: "James Green",
  },
  {
    name: "14.",
    related_party_transaction: `Revenue Growth (%)`,
     other_directorships: "31 mar 2012",
    shareholding:
      "The director is changed but the same is not recorded in  director is changed...",
    personal_details: "26 May, 2023",
    generated_by: "James Green",
  },
  {
    name: "15.",
    related_party_transaction: `Revenue Growth (%)`,
     other_directorships: "31 mar 2012",
    shareholding:
      "The director is changed but the same is not recorded in  director is changed...",
    personal_details: "26 May, 2023",
    generated_by: "James Green",
  },
  {
    name: "16.",
    related_party_transaction: `Revenue Growth (%)`,
     other_directorships: "31 mar 2012",
    shareholding:
      "The director is changed but the same is not recorded in  director is changed...",
    personal_details: "26 May, 2023",
    generated_by: "James Green",
  },
  {
    name: "17.",
    related_party_transaction: `Revenue Growth (%)`,
     other_directorships: "31 mar 2012",
    shareholding:
      "The director is changed but the same is not recorded in  director is changed...",
    personal_details: "26 May, 2023",
    generated_by: "James Green",
  },
  {
    name: "18.",
    related_party_transaction: `Revenue Growth (%)`,
     other_directorships: "31 mar 2012",
    shareholding:
      "The director is changed but the same is not recorded in  director is changed...",
    personal_details: "26 May, 2023",
    generated_by: "James Green",
  },
  {
    name: "19.",
    related_party_transaction: `Revenue Growth (%)`,
     other_directorships: "31 mar 2012",
    shareholding:
      "The director is changed but the same is not recorded in  director is changed...",
    personal_details: "26 May, 2023",
    generated_by: "James Green",
  },
  {
    name: "20.",
    related_party_transaction: `Revenue Growth (%)`,
     other_directorships: "31 mar 2012",
    shareholding:
      "The director is changed but the same is not recorded in  director is changed...",
    personal_details: "26 May, 2023",
    generated_by: "James Green",
  },

  // Add more dummy data as needed
]);
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
          <div class="table-w-bg-rounded ratio">
            <DataTable
                paginator
                :rows="10"
                :value="expandableData"
                :size="large"
                tableStyle="min-width: 80rem"
                v-model:expandedRows="expandedRows"
                dataKey="id"
              >
                <Column field="name" header="Name">
                  <template #body="data">
                    <div class="d-flex align-items-center">
                      {{data.name}}
                      <span class="material-symbols-outlined ms-3 fs-18">
                        visibility
                      </span>
                    </div>
                  </template>
                </Column>
                
                <Column  field="related_party_transaction" header="Related Party Transaction">
                  <template expander #body="data">
                    <div class="d-flex align-items-center">
                      Related Party Transaction
                      <span expander class="material-symbols-outlined ms-3 fs-18">
                        visibility
                      </span>
                    </div>
                  </template>
                </Column>
               
                <Column field="other_directorships" header="Other Directorships">
                
              </Column>
              <Column field="shareholding" header="Shareholding"></Column>
              <Column field="personal_details" header="Personal Details"></Column>
              <template #expansion="slotProps">
                <div class="p-3">
                    
                    <DataTable>
                        asdfasdf
                    </DataTable>
                </div>
            </template>
                
              </DataTable>
            <!-- <DataTable
              v-model:expandedRows="expandedRows"
              :value="products"
              dataKey="id"
              @rowExpand="onRowExpand"
              @rowCollapse="onRowCollapse"
              tableStyle="min-width: 60rem"
            >
              <Column expander style="width: 5rem" />
              <Column field="name" header="Name"></Column>
              <Column header="Image">
                <template #body="slotProps">
                  <img
                    :src="`https://primefaces.org/cdn/primevue/images/product/${slotProps.data.image}`"
                    :alt="slotProps.data.image"
                    class="shadow-4"
                    width="64"
                  />
                </template>
              </Column>
              <Column field="price" header="Price">
                <template #body="slotProps">
                  {{ formatCurrency(slotProps.data.price) }}
                </template>
              </Column>
              <Column field="category" header="Category"></Column>
              <Column field="rating" header="Reviews">
                <template #body="slotProps">
                  <Rating
                    :modelValue="slotProps.data.rating"
                    readonly
                    :cancel="false"
                  />
                </template>
              </Column>
              <Column header="Status">
                <template #body="slotProps">
                  <Tag
                    :value="slotProps.data.inventoryStatus"
                    :severity="getSeverity(slotProps.data)"
                  />
                </template>
              </Column>
              <template #expansion="slotProps">
                <div class="p-3">
                  <h5>Orders for {{ slotProps.data.name }}</h5>
                  <DataTable :value="slotProps.data.orders">
                    <Column field="id" header="Id" sortable></Column>
                    <Column
                      field="customer"
                      header="Customer"
                      sortable
                    ></Column>
                    <Column field="date" header="Date" sortable></Column>
                    <Column field="amount" header="Amount" sortable>
                      <template #body="slotProps">
                        {{ formatCurrency(slotProps.data.amount) }}
                      </template>
                    </Column>
                    <Column field="status" header="Status" sortable>
                      <template #body="slotProps">
                        <Tag
                          :value="slotProps.data.status.toLowerCase()"
                          :severity="getOrderSeverity(slotProps.data)"
                        />
                      </template>
                    </Column>
                    <Column headerStyle="width:4rem">
                      <template #body>
                        <Button icon="pi pi-search" />
                      </template>
                    </Column>
                  </DataTable>
                </div>
              </template>
            </DataTable> -->
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
