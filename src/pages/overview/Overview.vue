<script setup>
import { onMounted, ref } from "vue";
// import SectionTitle from "../../components/sectiontitle.vue";
import OverviewDashboardCard from "../../components/OverviewDashboardCard.vue";

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
  { auditor_name: `Sahil Goel
(VS GARG & Associates)`, year: "2020-2022", remarks: 'Yes', width: '150px'  },
  { auditor_name: 'Naveen Goel', year: "2019-2020", remarks: 'No' },
  // Add more dummy data as needed
]);
</script>

<template>
  <div class="main-container">
    <div class="container-fluid">
      <div class="overview-dashboard">
        <SectionTitle title="Overview" other-text="(2022)" />
        <div class="row">
          <div class="col-xl-3">
            <OverviewDashboardCard
              dashboard-number="150 Cr."
              dashboard-sub-title="Net Revenue"
              dashboard-trend-figure="5.39% "
              dashboard-chart="../../assets/chart-revenue.svg"
              svg-icon="../../assets/chart-revenue.svg"
            />
          </div>
          <div class="col-xl-3">
            <OverviewDashboardCard
              dashboard-number="150 Cr."
              dashboard-sub-title="Profit after tax"
              dashboard-trend-figure="5.39% "
              dashboard-chart="../../assets/chart-revenue.svg"
            />
          </div>
          <div class="col-xl-3">
            <OverviewDashboardCard
              dashboard-number="526"
              dashboard-sub-title="Total Assets"
              dashboard-trend-figure="5.39% "
              dashboard-chart="../../assets/chart-revenue.svg"
            />
          </div>
          <div class="col-xl-3">
            <div class="download-form">
              <span>Download Form</span>
              <ul>
                <li>
                  <span class="list-key">MGT-7 FORM <span>(2022)</span></span>
                  <span class="material-symbols-outlined"> download </span>
                </li>
                <li>
                  <span class="list-key">MGT-7 FORM <span>(2022)</span></span>
                  <span class="material-symbols-outlined"> download </span>
                 
                </li>
              </ul>
            </div>
          </div>
        </div>
      </div>
      <div class="overview-detail-container">
        <div class="row">
          <div class="col-xl-6">
            <div class="section-title-w-content">
              <h4>
                <img
                  src="../../assets/icon-company-profile.svg"
                  alt=""
                />Company Profile
              </h4>
              <ul class="section-title-w-content-list">
                <li>
                  <span class="list-key">Legal Name</span>
                  <span>Lenskart Solutions Private Limited</span>
                </li>
                <li>
                  <span class="list-key">Type of Entity</span>
                  <span>Private Limited Indian Non-Government Company.</span>
                </li>
                <li>
                  <span class="list-key">Listing Status</span>

                  <span>Unlisted</span>
                </li>
                <li>
                  <span class="list-key">Date of Incorporation</span>

                  <span>19 May 2008</span>
                </li>

                <li>
                  <span class="list-key">CIN</span>
                  <span>U33100DL2008PTC178355</span>
                </li>
                <li>
                  <span class="list-key">PAN</span>

                  <span>AACCV7324B</span>
                </li>
                <li>
                  <span class="list-key">LEI</span>

                  <span>LEI984500L5O4479DCDCF14 (ISSUED)</span>
                </li>
              </ul>
            </div>
          </div>
          <div class="col-xl-6">
            <div class="section-title-w-content">
              <h4>
                <img
                  src="../../assets/icon-business-information.svg"
                  alt=""
                />Business Information
              </h4>
              <ul class="section-title-w-content-list">
                <li>
                  <span class="list-key">Industry</span>
                  <span>Internet</span>
                </li>
                <li>
                  <span class="list-key">Segment (s)</span>
                  <span>Eye Accessories</span>
                </li>
                <li>
                  <span class="list-key">Employees</span>

                  <span>450</span>
                </li>
              </ul>
            </div>
          </div>
        </div>
        <div class="row">
          <div class="col-l3">
            <div class="section-title-w-content">
              <h4>
                <img src="../../assets/icon-complainces.svg" alt="" />Complaince
                and Reporting
              </h4>
              <ul class="section-title-w-content-list">
                <li>
                  <span class="list-key">Date of Last AGM </span>
                  <span>30th September, 2023</span>
                </li>
                <li>
                  <span class="list-key">E-Filing Status </span>
                  <span>Active</span>
                </li>
                <li>
                  <span class="list-key">Active Compliance</span>
                  <span>Active Compliant</span>
                </li>
              </ul>
            </div>
          </div>
          <div class="col-l9">
            <div class="section-title-w-content">
              <h4>
                <img
                  src="../../assets/icon-identified-peer.svg"
                  alt=""
                />Identified Peers
              </h4>
              <div class="d-flex flex-wrap px-4">
                <strong class="color-primary">Peers</strong>
                <a
                  href=""
                  class="ms-auto text-decoration-none color-primary-green"
                  >Compare with peers
                </a>
              </div>
              <div class="peer-card-sec">
                
                  <div v-for="index in 5" :key="index" class="peer-card">
                    <div class="peer-card-top">
                      <img src="../../assets/icon-peers.svg" alt="" />
                      <div class="peer-card-top-right">
                        <strong>Mobitech Creations</strong>
                        <span>BANKBARODA</span>
                      </div>
                    </div>
                    <div class="peer-card-btm">
                      <ul>
                        <li>
                          <span>Revenue</span>
                          <strong>6.45</strong>
                        </li>
                        <li>
                          <span>G.P %</span>
                          <strong class="color-primary-green">5.39%</strong>
                        </li>
                        <li>
                          <span>N.P%</span>
                          <strong>60.42</strong>
                        </li>
                      </ul>
                    </div>
                  </div>
                
              </div>
            </div>
          </div>
        </div>
        <!-- LAST ROW -->
        <div class="row">
          <div class="col-lg-12">
            <div class="section-title-w-content">
              <h4>
                <img src="../../assets/icon-auditors.svg" alt="" />Auditors
              </h4>
              <div class="container-fluid">
              <div class="row">
                <div class="col-lg-6">
                  
                  <strong class="color-primary mb-3 d-block">Consolidated FS</strong>
                  <div class="table-w-bg-rounded">
                    <div class="card">
                      <DataTable :value="tabledata" :size="large" tableStyle="min-width: 32rem">
                        <Column field="auditor_name" header="Auditor name"></Column>
                        <Column field="year" header="Year"></Column>
                        <Column field="remarks" header="Remarks"></Column>
                      </DataTable>
                    </div>
                  </div>
                </div>
                
                <div class="col-lg-6">
                  <strong class="color-primary mb-3 d-block">Standalone FS</strong>
                  <div class="table-w-bg-rounded">
                    <div class="card">
                      <DataTable :value="tabledata" :size="large" tableStyle="min-width: 32rem">
                        <Column field="auditor_name" header="Auditor name"></Column>
                        <Column field="year" header="Year"></Column>
                        <Column field="remarks" header="Remarks"></Column>
                      </DataTable>
                    </div>
                  </div>
                </div>
              </div>
              </div>
            </div>
          </div>
          
        </div>
      </div>
    </div>
  </div>

</template>
