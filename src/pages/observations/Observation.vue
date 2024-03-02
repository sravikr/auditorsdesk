<script setup>
import { onMounted, ref } from "vue";

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
const tabledata = ref([
  {
    id: "1.",
    ratio: `Revenue Growth (%)`,
    content: "31 mar 2012",
    remarks:
      "The director is changed but the same is not recorded in  director is changed...",
    added_date: "26 May, 2023",
    generated_by: "James Green",
  },
  {
    id: "2.",
    ratio: `Revenue Growth (%)`,
    content: "31 mar 2012",
    remarks:
      "The director is changed but the same is not recorded in  director is changed...",
    added_date: "26 May, 2023",
    generated_by: "James Green",
  },
  {
    id: "3.",
    ratio: `Revenue Growth (%)`,
    content: "31 mar 2012",
    remarks:
      "The director is changed but the same is not recorded in  director is changed...",
    added_date: "26 May, 2023",
    generated_by: "James Green",
  },{
    id: "4.",
    ratio: `Revenue Growth (%)`,
    content: "31 mar 2012",
    remarks:
      "The director is changed but the same is not recorded in  director is changed...",
    added_date: "26 May, 2023",
    generated_by: "James Green",
  },{
    id: "5.",
    ratio: `Revenue Growth (%)`,
    content: "31 mar 2012",
    remarks:
      "The director is changed but the same is not recorded in  director is changed...",
    added_date: "26 May, 2023",
    generated_by: "James Green",
  },
  {
    id: "6.",
    ratio: `Revenue Growth (%)`,
    content: "31 mar 2012",
    remarks:
      "The director is changed but the same is not recorded in  director is changed...",
    added_date: "26 May, 2023",
    generated_by: "James Green",
  },
  {
    id: "7.",
    ratio: `Revenue Growth (%)`,
    content: "31 mar 2012",
    remarks:
      "The director is changed but the same is not recorded in  director is changed...",
    added_date: "26 May, 2023",
    generated_by: "James Green",
  },{
    id: "8.",
    ratio: `Revenue Growth (%)`,
    content: "31 mar 2012",
    remarks:
      "The director is changed but the same is not recorded in  director is changed...",
    added_date: "26 May, 2023",
    generated_by: "James Green",
  },
  {
    id: "9.",
    ratio: `Revenue Growth (%)`,
    content: "31 mar 2012",
    remarks:
      "The director is changed but the same is not recorded in  director is changed...",
    added_date: "26 May, 2023",
    generated_by: "James Green",
  },
  {
    id: "10.",
    ratio: `Revenue Growth (%)`,
    content: "31 mar 2012",
    remarks:
      "The director is changed but the same is not recorded in  director is changed...",
    added_date: "26 May, 2023",
    generated_by: "James Green",
  },
  {
    id: "11.",
    ratio: `Revenue Growth (%)`,
    content: "31 mar 2012",
    remarks:
      "The director is changed but the same is not recorded in  director is changed...",
    added_date: "26 May, 2023",
    generated_by: "James Green",
  },{
    id: "12.",
    ratio: `Revenue Growth (%)`,
    content: "31 mar 2012",
    remarks:
      "The director is changed but the same is not recorded in  director is changed...",
    added_date: "26 May, 2023",
    generated_by: "James Green",
  },
  {
    id: "13.",
    ratio: `Revenue Growth (%)`,
    content: "31 mar 2012",
    remarks:
      "The director is changed but the same is not recorded in  director is changed...",
    added_date: "26 May, 2023",
    generated_by: "James Green",
  },
  {
    id: "14.",
    ratio: `Revenue Growth (%)`,
    content: "31 mar 2012",
    remarks:
      "The director is changed but the same is not recorded in  director is changed...",
    added_date: "26 May, 2023",
    generated_by: "James Green",
  },
  {
    id: "15.",
    ratio: `Revenue Growth (%)`,
    content: "31 mar 2012",
    remarks:
      "The director is changed but the same is not recorded in  director is changed...",
    added_date: "26 May, 2023",
    generated_by: "James Green",
  },{
    id: "16.",
    ratio: `Revenue Growth (%)`,
    content: "31 mar 2012",
    remarks:
      "The director is changed but the same is not recorded in  director is changed...",
    added_date: "26 May, 2023",
    generated_by: "James Green",
  },
  {
    id: "17.",
    ratio: `Revenue Growth (%)`,
    content: "31 mar 2012",
    remarks:
      "The director is changed but the same is not recorded in  director is changed...",
    added_date: "26 May, 2023",
    generated_by: "James Green",
  },
  {
    id: "18.",
    ratio: `Revenue Growth (%)`,
    content: "31 mar 2012",
    remarks:
      "The director is changed but the same is not recorded in  director is changed...",
    added_date: "26 May, 2023",
    generated_by: "James Green",
  },
  {
    id: "19.",
    ratio: `Revenue Growth (%)`,
    content: "31 mar 2012",
    remarks:
      "The director is changed but the same is not recorded in  director is changed...",
    added_date: "26 May, 2023",
    generated_by: "James Green",
  },{
    id: "20.",
    ratio: `Revenue Growth (%)`,
    content: "31 mar 2012",
    remarks:
      "The director is changed but the same is not recorded in  director is changed...",
    added_date: "26 May, 2023",
    generated_by: "James Green",
  },
  
  // Add more dummy data as needed
]);
const showFilterMenu = ref(false);
const toggleFilterMenu = () => {
  showFilterMenu.value = !showFilterMenu.value;
};
</script>

<template>
  <div class="main-container">
    <div class="container-fluid">
      <div class="sidebar-menu-toggle">
        <img src="/src/assets/icon-observations-1.svg" alt=" observation" />
        Observations
      </div>
      <div class="page-title">
        <h3>Analysis</h3>
      </div>

      <div class="tab-container">
        <TabView class="common-tab">
          <TabPanel header="Ratio">
            <!-- BLUE PANEL -->
            <section class="blue-panel">
              <div class="blue-panel-title">
                <h3>Recent</h3>
              </div>

              <div class="blue-panel-content">
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
                      size="large"
                      shape="circle"
                    />
                    James Green
                  </div>
                </div>
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
                      size="large"
                      shape="circle"
                    />
                    James Green
                  </div>
                </div>
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
                      size="large"
                      shape="circle"
                    />
                    James Green
                  </div>
                </div>
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
                      size="large"
                      shape="circle"
                    />
                    James Green
                  </div>
                </div>
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
                      size="large"
                      shape="circle"
                    />
                    James Green
                  </div>
                </div>
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
                      size="large"
                      shape="circle"
                    />
                    James Green
                  </div>
                </div>
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
                      size="large"
                      shape="circle"
                    />
                    James Green
                  </div>
                </div>
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
                      size="large"
                      shape="circle"
                    />
                    James Green
                  </div>
                </div>
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
                      size="large"
                      shape="circle"
                    />
                    James Green
                  </div>
                </div>
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
                      size="large"
                      shape="circle"
                    />
                    James Green
                  </div>
                </div>
              </div>
            </section>
            <!-- BLUE PANEL -->
            <section class="blue-panel">
              <div class="blue-panel-title">
                <h3>1 hour ago</h3>
              </div>

              <div class="blue-panel-content">
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
                      size="large"
                      shape="circle"
                    />
                    James Green
                  </div>
                </div>
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
                      size="large"
                      shape="circle"
                    />
                    James Green
                  </div>
                </div>
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
                      size="large"
                      shape="circle"
                    />
                    James Green
                  </div>
                </div>
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
                      size="large"
                      shape="circle"
                    />
                    James Green
                  </div>
                </div>
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
                      size="large"
                      shape="circle"
                    />
                    James Green
                  </div>
                </div>
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
                      size="large"
                      shape="circle"
                    />
                    James Green
                  </div>
                </div>
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
                      size="large"
                      shape="circle"
                    />
                    James Green
                  </div>
                </div>
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
                      size="large"
                      shape="circle"
                    />
                    James Green
                  </div>
                </div>
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
                      size="large"
                      shape="circle"
                    />
                    James Green
                  </div>
                </div>
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
                      size="large"
                      shape="circle"
                    />
                    James Green
                  </div>
                </div>
              </div>
            </section>
            <!-- BLUE PANEL -->
            <section class="blue-panel">
              <div class="blue-panel-title">
                <h3>1 day ago</h3>
              </div>

              <div class="blue-panel-content">
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
                      size="large"
                      shape="circle"
                    />
                    James Green
                  </div>
                </div>
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
                      size="large"
                      shape="circle"
                    />
                    James Green
                  </div>
                </div>
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
                      size="large"
                      shape="circle"
                    />
                    James Green
                  </div>
                </div>
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
                      size="large"
                      shape="circle"
                    />
                    James Green
                  </div>
                </div>
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
                      size="large"
                      shape="circle"
                    />
                    James Green
                  </div>
                </div>
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
                      size="large"
                      shape="circle"
                    />
                    James Green
                  </div>
                </div>
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
                      size="large"
                      shape="circle"
                    />
                    James Green
                  </div>
                </div>
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
                      size="large"
                      shape="circle"
                    />
                    James Green
                  </div>
                </div>
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
                      size="large"
                      shape="circle"
                    />
                    James Green
                  </div>
                </div>
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
                      size="large"
                      shape="circle"
                    />
                    James Green
                  </div>
                </div>
              </div>
            </section>
            <!-- Common Table -->
            <div class="table-w-bg-rounded ratio">
              <div class="card">
                <DataTable paginator :rows="10" 
                  :value="tabledata"
                  :size="large"
                  tableStyle="min-width: 80rem"
                >
                  <Column field="id" header=""></Column>
                  <Column field="ratio" header="Ratio"></Column>
                  <Column field="content" header="Content"></Column>
                  <Column field="remarks" header="Remarks" width="150"></Column>
                  <Column field="added_date" header="Added Date"></Column>
                  <Column
                    field="generated_by"
                    header="
                  Generated by"
                  >
                    <template #body>
                      <div class="d-flex align-items-center">
                        <Avatar
                          image="https://primefaces.org/cdn/primevue/images/avatar/asiyajavayant.png"
                          class="me-2"
                          size="small"
                          shape="circle"
                        />
                        James Green
                      </div>
                    </template>
                  </Column>
                  <Column field="view" header="">
                    <template #body>
                      <div class="d-flex align-items-center">
                      View
                      <span class="material-symbols-outlined ms-3 fs-18">
                        visibility
                      </span>
                    </div>
                    </template>
                  </Column>
                  <Column
                    headerStyle="width: 5rem; text-align: center"
                    bodyStyle="text-align: center; overflow: visible"
                  >
                    <template #body>
                      <span class="material-symbols-outlined ms-3 fs-18">
                        more_vert
                      </span>
                    </template>
                  </Column>
                </DataTable>
                  
              </div>
            </div>
          </TabPanel>
          <TabPanel header="Balance Sheet">
            <p class="m-0">
              Sed ut perspiciatis unde omnis iste natus error sit voluptatem
              accusantium doloremque laudantium, totam rem aperiam, eaque ipsa
              quae ab illo inventore veritatis et quasi architecto beatae vitae
              dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit
              aspernatur aut odit aut fugit, sed quia consequuntur magni dolores
              eos qui ratione voluptatem sequi nesciunt. Consectetur, adipisci
              velit, sed quia non numquam eius modi.
            </p>
          </TabPanel>
          <TabPanel header="Income Statements">
            <p class="m-0">
              At vero eos et accusamus et iusto odio dignissimos ducimus qui
              blanditiis praesentium voluptatum deleniti atque corrupti quos
              dolores et quas molestias excepturi sint occaecati cupiditate non
              provident, similique sunt in culpa qui officia deserunt mollitia
              animi, id est laborum et dolorum fuga. Et harum quidem rerum
              facilis est et expedita distinctio. Nam libero tempore, cum soluta
              nobis est eligendi optio cumque nihil impedit quo minus.
            </p>
          </TabPanel>
          <TabPanel header="Cashflow">
            <p class="m-0">
              At vero eos et accusamus et iusto odio dignissimos ducimus qui
              blanditiis praesentium voluptatum deleniti atque corrupti quos
              dolores et quas molestias excepturi sint occaecati cupiditate non
              provident, similique sunt in culpa qui officia deserunt mollitia
              animi, id est laborum et dolorum fuga. Et harum quidem rerum
              facilis est et expedita distinctio. Nam libero tempore, cum soluta
              nobis est eligendi optio cumque nihil impedit quo minus.
            </p>
          </TabPanel>
        </TabView>
        <div class="filter-sec">
          <a
            href="javascript:void(0)"
            @click="toggleFilterMenu"
            class="common-icon-w-bg"
            ><img src="../../assets/icon-filter.svg" alt="filter"
          /></a>
          <div class="filter-menu" v-if="showFilterMenu">
            <IconField iconPosition="left">
              <InputIcon>
                <img src="../../assets/icon-search.svg" alt=""
              /></InputIcon>
              <InputText v-model="value1" placeholder="Search" />
            </IconField>
            <Dropdown
              v-model="selectedCity"
              :options="cities"
              optionLabel="name"
              placeholder="My Observations"
              class="w-full md:w-14rem"
            />
            <Dropdown
              v-model="selectedCity"
              :options="cities"
              optionLabel="name"
              placeholder="Sort by"
              class="w-full md:w-14rem"
            />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
