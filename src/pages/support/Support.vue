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

const visible = ref(false);

const value = ref('');
</script>




<template>
  <div class="main-container">
    <div class="container-fluid">
      <div class="container-negative">
        <div class="container-negative-inner">
          <div class="contact-section">
            <a class="contact-section-redirect" href=""
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
                    <Textarea class="w-100" v-model="value" rows="5" cols="30" placeholder="Send us a message" />
                    <label>Message</label>
                  </FloatLabel>
                  <button type="button" class="btn btn-green">Send message</button>
                </TabPanel>
                <TabPanel>
                  <template v-slot:header>
                    <span class="material-icons me-2"> message </span>
                    Live Chat
                  </template>
                  <div class="call-us-sec message">
                  
                  <p class="d-flex align-items-center"><span class="material-symbols-outlined me-2 color-primary-green">
schedule
</span>
Chat working hours: Monday-Friday: 10:00 AM - 7:00 PM IST
                  
                  
                  </p>
                  
                  
                    
                    <button type="button" class="d-flex btn btn-green btn-wide align-items-center"  @click="visible = true" >Start chat</button>
</div>
                </TabPanel>
                <TabPanel>
                  <template v-slot:header>
                    <span class="material-icons-outlined me-2">
                      support_agent
                    </span>
                    Call us
                  </template>
                  <div class="call-us-sec">
                  <strong class="fs-20">Phone</strong>
                  <p class="d-flex align-items-center"><span class="material-symbols-outlined me-2 color-primary-green">
schedule
</span>
                    Monday-Friday: 10:00 AM - 7:00 PM IST
                  
                  
                  </p>
                  
                  <a href="tel:+91-9876543210">+91 98765 43210</a>
                    
                    <button type="button" class="d-flex btn btn-green btn-wide align-items-center"><span class="material-symbols-outlined me-2 align-self-center">
call
</span>Make call</button>
</div>
                </TabPanel>
              </TabView>
            </div>
          </div>

<Dialog class="modal-chat" v-model:visible="visible" modal  :style="{ width: '725px' }" :breakpoints="{ '1199px': '75vw', '575px': '90vw' }">
  <template v-slot:header>
                    <div class="chat-header-active">
                      <span class="active-chat-icon"></span>
                    <strong>You are connected with Phoenix Baker</strong>
                    <span class="active-chat-time">6/25/2023 2:20pm</span>
                  </div>
                  </template>
                  <div class="chat-message-container">
                    <Divider  align="center" type="solid">
                        <strong>Today, March 24</strong>
                    </Divider>
                    <div class="chat-message">
                      <div class="chat-message-inner">
                        <div class="chat-message-avatar">
                          <Avatar image="/src/assets/avatar.png" class="mr-2" size="large" shape="circle" />
                          <span class="active-chat-icon"></span>
                        </div>
                        <div class="chat-message-detail">
                          <div class="chat-message-detail-top">
                            <span class="chat-message-detail-left">Phoenix Baker</span>
                            <span class="chat-message-detail-rt">2:20pm</span>
                          </div>
                          <div class="chat-message-detail-btm">
                            <p>Hey Olivia, can you please review the latest design when you can?</p>
                          </div>
                        </div>
                      </div>

                    </div>
                    <!-- RIGHT -->
                    <div class="chat-message right">
                      <div class="chat-message-inner">
                        <div class="chat-message-detail">
                          <div class="chat-message-detail-top">
                            <span class="chat-message-detail-left">You</span>
                            <span class="chat-message-detail-rt">2:20pm</span>
                          </div>
                          <div class="chat-message-detail-btm">
                            <p>Sure thing, I’ll have a look today.</p>
                          </div>
                        </div>
                    </div>

                    </div>
                    <!-- LEFT -->
                    <div class="chat-message">
                      <div class="chat-message-inner">
                        <div class="chat-message-avatar">
                          <Avatar image="/src/assets/avatar.png" class="mr-2" size="large" shape="circle" />
                          <span class="active-chat-icon"></span>
                        </div>
                        <div class="chat-message-detail">
                          <div class="chat-message-detail-top">
                            <span class="chat-message-detail-left">Phoenix Baker</span>
                            <span class="chat-message-detail-rt">2:20pm</span>
                          </div>
                          <div class="chat-message-detail-btm">
                            <p>Hey Olivia, can you please review the latest design when you can?</p>
                          </div>
                        </div>
                      </div>

                    </div>
                    <!-- RIGHT -->
                    <div class="chat-message right w-bdr">
                      <div class="chat-message-inner">
                        
                        <div class="chat-message-detail">
                          <div class="chat-message-detail-top">
                            <span class="chat-message-detail-left">You</span>
                            <span class="chat-message-detail-rt">2:20pm</span>
                          </div>
                          <div class="chat-message-detail-btm">
                            <div class="chat-message-detail-btm-left">
                              <span class="material-symbols-outlined color-primary-green">
                              draft
                              </span>
                            </div>
                            <div class="chat-message-detail-btm-right">
                              <strong>Tech design requirements.pdf</strong>
                              <span>200 KB</span>
                            </div>
                          </div>
                        </div>
                      </div>

                    </div>
                  </div>
                  <template v-slot:footer>
                   <div class="chat-send-message">
                    <span class="chat-send-attach">
                      <span class="material-symbols-outlined me-2 ">
attach_file
</span>
</span>
<InputText type="text" v-model="value" />
<button class="btn btn-green"> <span class="material-symbols-outlined">
send
</span></button>
                    
                   
                  </div>
                  </template>
   
</Dialog>
        </div>
      </div>
    </div>
  </div>
</template>
