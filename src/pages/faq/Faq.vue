<script setup>
import { onMounted, ref } from "vue";
import './faq.css';
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
</script>

<template>
  <div class="main-container">
    <div class="container-fluid">
      <div class="container-negative faq">
        <div class="container-negative-inner">
        <div class="faq-heading">
        <h1>Frequently asked questions</h1>
        <p>Everything you need to know about the product and billing. Can’t find the answer<br/> you’re looking for? Please chat to our friendly team.</p>
        </div>
        
        <Accordion :activeIndex="0">
            <AccordionTab>
                <template #header>
                    <span class="flex align-items-center gap-2 w-full w-100">
                      Is there a free trial available?
                    </span>
                    <span class="material-icons-outlined ms-auto">
</span>
                </template>
                <p class="m-0">
                  Yes, you can try us for free for 30 days. If you want, we’ll provide you with a free, personalized 30-minute onboarding call to get you up and running as soon as possible.
                </p>
            </AccordionTab>
            <AccordionTab>
                <template #header>
                    <span class="flex align-items-center gap-2 w-full w-100">
                      Can I change my plan later?</span>
                        <span class="material-icons-outlined"></span>
                    
                </template>
                <p class="m-0">
                    Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim
                    ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt. Consectetur, adipisci velit, sed quia non numquam eius modi.
                </p>
            </AccordionTab>
            <AccordionTab>
                <template #header>
                    <span class="flex align-items-center gap-2 w-full w-100">
                      What is your cancellation policy?</span>
                        <span class="material-icons-outlined">

</span>
                    
                </template>
                <p class="m-0">
                    At vero eos et accusamus et iusto odio dignissimos ducimus qui blanditiis praesentium voluptatum deleniti atque corrupti quos dolores et quas molestias excepturi sint occaecati cupiditate non provident, similique sunt in culpa qui
                    officia deserunt mollitia animi, id est laborum et dolorum fuga. Et harum quidem rerum facilis est et expedita distinctio. Nam libero tempore, cum soluta nobis est eligendi optio cumque nihil impedit quo minus.
                </p>
            </AccordionTab>
            <AccordionTab>
                <template #header>
                    <span class="flex align-items-center gap-2 w-full w-100">
                      What is your cancellation policy?</span>
                        <span class="material-icons-outlined">

</span>
                    
                </template>
                <p class="m-0">
                    At vero eos et accusamus et iusto odio dignissimos ducimus qui blanditiis praesentium voluptatum deleniti atque corrupti quos dolores et quas molestias excepturi sint occaecati cupiditate non provident, similique sunt in culpa qui
                    officia deserunt mollitia animi, id est laborum et dolorum fuga. Et harum quidem rerum facilis est et expedita distinctio. Nam libero tempore, cum soluta nobis est eligendi optio cumque nihil impedit quo minus.
                </p>
            </AccordionTab>
            <AccordionTab>
                <template #header>
                    <span class="flex align-items-center gap-2 w-full w-100">
                      What is your cancellation policy?</span>
                        <span class="material-icons-outlined">

</span>
                    
                </template>
                <p class="m-0">
                    At vero eos et accusamus et iusto odio dignissimos ducimus qui blanditiis praesentium voluptatum deleniti atque corrupti quos dolores et quas molestias excepturi sint occaecati cupiditate non provident, similique sunt in culpa qui
                    officia deserunt mollitia animi, id est laborum et dolorum fuga. Et harum quidem rerum facilis est et expedita distinctio. Nam libero tempore, cum soluta nobis est eligendi optio cumque nihil impedit quo minus.
                </p>
            </AccordionTab>
            <AccordionTab>
                <template #header>
                    <span class="flex align-items-center gap-2 w-full w-100">
                      What is your cancellation policy?</span>
                        <span class="material-icons-outlined">

</span>
                    
                </template>
                <p class="m-0">
                    At vero eos et accusamus et iusto odio dignissimos ducimus qui blanditiis praesentium voluptatum deleniti atque corrupti quos dolores et quas molestias excepturi sint occaecati cupiditate non provident, similique sunt in culpa qui
                    officia deserunt mollitia animi, id est laborum et dolorum fuga. Et harum quidem rerum facilis est et expedita distinctio. Nam libero tempore, cum soluta nobis est eligendi optio cumque nihil impedit quo minus.
                </p>
            </AccordionTab>
        </Accordion> 
        <section class="faq-featured">
          <AvatarGroup>
            <Avatar image="https://primefaces.org/cdn/primevue/images/avatar/amyelsner.png" size="large" shape="circle" />
            <Avatar image="https://primefaces.org/cdn/primevue/images/avatar/asiyajavayant.png" size="large" shape="circle" />
            <Avatar image="https://primefaces.org/cdn/primevue/images/avatar/onyamalimba.png" size="large" shape="circle" />
        </AvatarGroup>
        <strong>Still have questions?</strong>
        <p>Can’t find the answer you’re looking for? Please chat to our friendly team.</p>
        <button class="btn btn-green">Get in touch</button>

        </section> 
      </div>
      </div>
    </div>
  </div>
</template>
