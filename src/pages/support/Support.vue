<script setup>
import { onMounted, ref } from "vue";
import "./support.css";
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
});
const value = ref('');
</script>




<template>
  <div class="main-container">
    <div class="container-fluid">
      <div class="container-negative">
        <div class="container-negative-inner">
          <div class="contact-section">
            <a href=""
              ><span class="material-icons-outlined"> chevron_left </span
              >Contact Us</a
            >
            <h2>Contact Customer Care</h2>
            <p>Our friendly team would love to hear from you.</p>
            <div class="contact-inner-tab">
              <TabView>
                <TabPanel>
                  <template v-slot:header>
                    <span class="material-icons me-2"> email </span>
                    SEnd message
                  </template>
                  <FloatLabel>
                    <Textarea v-model="value" rows="5" cols="30" placeholder="Send us a message" />
                    <label>Message</label>
                  </FloatLabel>
                </TabPanel>
                <TabPanel>
                  <template v-slot:header>
                    <span class="material-icons me-2"> message </span>
                    Live Chat
                  </template>
                  <p class="m-0">
                    Sed ut perspiciatis unde omnis iste natus error sit
                    voluptatem accusantium doloremque laudantium, totam rem
                    aperiam, eaque ipsa quae ab illo inventore veritatis et
                    quasi architecto beatae vitae dicta sunt explicabo. Nemo
                    enim ipsam voluptatem quia voluptas sit aspernatur aut odit
                    aut fugit, sed quia consequuntur magni dolores eos qui
                    ratione voluptatem sequi nesciunt. Consectetur, adipisci
                    velit, sed quia non numquam eius modi.
                  </p>
                </TabPanel>
                <TabPanel>
                  <template v-slot:header>
                    <span class="material-icons-outlined me-2">
                      support_agent
                    </span>
                    Call us
                  </template>

                  <p class="m-0">
                    At vero eos et accusamus et iusto odio dignissimos ducimus
                    qui blanditiis praesentium voluptatum deleniti atque
                    corrupti quos dolores et quas molestias excepturi sint
                    occaecati cupiditate non provident, similique sunt in culpa
                    qui officia deserunt mollitia animi, id est laborum et
                    dolorum fuga. Et harum quidem rerum facilis est et expedita
                    distinctio. Nam libero tempore, cum soluta nobis est
                    eligendi optio cumque nihil impedit quo minus.
                  </p>
                </TabPanel>
              </TabView>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
