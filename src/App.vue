<template>
  <q-layout view="hHh LpR fff">

    <q-header elevated class="bg-white text-black header" height-hint="98">
      <q-toolbar>
        <q-toolbar-title style="font-family: mixone; font-weight: bolder; " align="center" id="cv-silva">
           <q-avatar ><!--class="cursor-pointer" -->
             <img src="./assets/images/Mi foto - Daniel Silva.jpg" ><!--@click="modal = true" -->
          </q-avatar>
          CV - Daniel Silva
        </q-toolbar-title>
      </q-toolbar>
      <!-- <q-dialog v-model="modal">
        <q-img src="./assets/images/Mi foto - Daniel Silva.jpg" />
      </q-dialog> -->
      <q-tabs v-model="activeTab" narrow-indicator dense color="primary" @update:model-value="scrollTo">
        <q-tab name="home" @click="scrollTo('home')"><i>Home</i></q-tab>
        <q-tab name="aboutMe" @click="scrollTo('aboutMe')"><i>About me</i></q-tab>
        <q-tab name="projects" @click="scrollTo('projects')"><i>Projects</i></q-tab>
        <q-tab name="contact" @click="scrollTo('contact')"><i>Contact</i></q-tab>
      </q-tabs>
    </q-header>

    <q-page-sticky position="bottom-right" :offset="[18, 18]" style="z-index: 10;">
      <q-fab flat color="white" class="bg-black" icon="assignment_ind" direction="up">
        <q-fab-action class="bg-white">
          <a :href="linkedin" target="_blank">
            <q-avatar size="40px">
              <img src="./assets/images/linkedin.png" alt="LinkedIn">
              <q-tooltip anchor="center right" self="center left" :offset="[10, 10]">
                <strong>LinkedIn</strong>
              </q-tooltip>
            </q-avatar>
          </a>
        </q-fab-action>
        <q-fab-action class="bg-white">
          <a :href="whats" target="_blank">
            <q-avatar size="40px">
              <img src="./assets/images/whatsapp.png" alt="WhatsApp">
              <q-tooltip anchor="center right" self="center left" :offset="[10, 10]">
                <strong>WhatsApp</strong>
              </q-tooltip>
            </q-avatar>
          </a>
        </q-fab-action>
        <q-fab-action class="bg-white">
          <a :href="mail" target="_blank">
            <q-avatar size="40px">
              <img src="./assets/images/mail.png" alt="Mail">
              <q-tooltip anchor="center right" self="center left" :offset="[10, 10]">
                <strong>Mail</strong>
              </q-tooltip>
            </q-avatar>
          </a>
        </q-fab-action>
        <q-fab-action class="bg-white">
          <a :href="github" target="_blank">
            <q-avatar size="40px">
              <img src="./assets/images/github.png" alt="GitHub">
              <q-tooltip anchor="center right" self="center left" :offset="[10, 10]">
                <strong>GitHub</strong>
              </q-tooltip>
            </q-avatar>
          </a>
        </q-fab-action>
      </q-fab>
    </q-page-sticky>

    <q-page-container>
      <div class="q-pa-xs" align="center" id="home">
        <h2 id="principalTitles">
          Hey, I'm Daniel Silva
        </h2>
        <h5 class="q-gutter-xs" id="secondaryTitle">
          <p>
            <i>A junior web developer with a solid programming foundation and willing to learn</i>
          </p>
        </h5>

      </div>
      <div class="q-pa-xs" id="aboutMe" style="align-content: center;">
        <h2 id="principalTitles" align="center">
          About me
        </h2>
        <div class="row justify-center q-gutter-xl">
          <q-card dark bordered class="bg-transparent my-card">
            <q-card-section>
              <div class="text-h6 text-black" align="center"><strong><i>Get to know me!</i> </strong></div>
            </q-card-section>

            <q-separator dark inset color="black" />

            <q-card-section class="text-black">
              <i id="i_description"> {{ description }}</i>
            </q-card-section>
          </q-card>
          <q-card dark bordered class="bg-transparent my-card">
            <q-card-section>
              <div class="text-h6 text-black" align="center"><strong><i>My skills</i> </strong></div>
            </q-card-section>

            <q-separator dark inset color="black" />

            <q-card-section class="text-black">
              <div class="q-pt-sm row q-gutter-md justify-center">
                <q-badge class="skill-badge justify-center" oncopy="return false" style="user-select: none;">JavaScript
                </q-badge>
                <q-badge class="skill-badge justify-center" oncopy="return false" style="user-select: none;">Python
                </q-badge>
                <q-badge class="skill-badge justify-center" oncopy="return false" style="user-select: none;">Java
                </q-badge>
                <q-badge class="skill-badge justify-center" oncopy="return false" style="user-select: none;">HTML
                </q-badge>
                <q-badge class="skill-badge justify-center" oncopy="return false" style="user-select: none;">CSS
                </q-badge>
                <q-badge class="skill-badge justify-center" oncopy="return false" style="user-select: none;">Vue.js
                </q-badge>
                <q-badge class="skill-badge justify-center" oncopy="return false" style="user-select: none;">Node.js
                </q-badge>
                <q-badge class="skill-badge justify-center" oncopy="return false" style="user-select: none;">MongoDB
                </q-badge>
                <q-badge class="skill-badge justify-center" oncopy="return false" style="user-select: none;">MySQL
                </q-badge>
                <q-badge class="skill-badge justify-center" oncopy="return false" style="user-select: none;">GIT
                </q-badge>
                <q-badge class="skill-badge justify-center" oncopy="return false" style="user-select: none;">GitHub
                </q-badge>
              </div>

            </q-card-section>
          </q-card>
        </div>
      </div>
      <div class="q-pa-xs" id="projects" style="background-color: rgba(128, 128, 128, 0.11);">
        <h2 id="principalTitles" style="margin-top: 4%;" align="center">
          Projects
        </h2>
        <h5 class="q-gutter-xs" align="center" id="secondaryTitle">
          <p>
            <i>Here you will find some of the personal projects I create.</i>
          </p>
        </h5>
        <div class="q-pa-md q-gutter-md" align="center">
          <q-card dark class="bg-transparent my-card2">
            <a :href="ahorcado_url" target="_blank">
              <q-img class="col-8" src="./assets/images/pc-ahorcado.jpeg" />
            </a>

            <q-separator />

            <q-card-section vertical align="left" class="text-black col-5">
              <div class="text-h5" align="center"><i>Ahorcado</i> </div>
              <div class="text-subtitle2" align="center"><i>{{ ahorcado }}</i> </div>
              <br><br>
              <div align="center"><q-btn outline :href="ahorcado_url" target="_blank"
                  class="visit_btn"><i>Visit</i></q-btn>
              </div>
            </q-card-section>
          </q-card>
          <q-card dark class="bg-transparent my-card2">
            <a :href="wis_url" target="_blank">
              <q-img class="col-8" src="./assets/images/pc-wis.jpeg" />
            </a>

            <q-separator />

            <q-card-section vertical align="left" class="text-black col-5">
              <div class="text-h5" align="center"><i>Walk In Style</i> </div>
              <div class="text-subtitle2" align="center"><i>{{ wis }}</i> </div>
              <br><br>
              <div align="center"><q-btn outline :href="wis_url" target="_blank" class="visit_btn"><i>Visit</i></q-btn>
              </div>
            </q-card-section>
          </q-card>
          <q-card dark class="bg-transparent my-card2">
            <a :href="paraiso_url" target="_blank">
              <q-img src="./assets/images/pc-paraiso.jpeg" class="col-8" />
            </a>


            <q-separator />

            <q-card-section vertical align="left" class="text-black col-5">
              <div class="text-h5" align="center"><i>Hotel Paraíso</i> </div>
              <div class="text-subtitle2" align="center"><i>{{ paraiso }}</i> </div>
              <br><br>
              <div align="center"><q-btn outline :href="paraiso_url" target="_blank"
                  class="visit_btn"><i>Visit</i></q-btn></div>
            </q-card-section>
          </q-card>
          <q-card dark class="bg-transparent my-card2">
            <a :href="red_url" target="_blank">
              <q-img class="col-8" src="./assets/images/pc-void.jpeg" />
            </a>

            <q-separator />

            <q-card-section vertical align="left" class="text-black col-5">
              <div class="text-h5" align="center"><i>Red Void</i> </div>
              <div class="text-subtitle2" align="center"><i>{{ redvoid }}</i> </div>
              <br><br>
              <div align="center"><q-btn outline :href="red_url" target="_blank" class="visit_btn"><i>Visit</i></q-btn>
              </div>
            </q-card-section>
          </q-card>
        </div>
      </div>
      <div class="q-pa-xs" id="contact" style="align-content: center;" align="center">
        <h2 id="principalTitles" style="margin-top: 4%;" align="center">
          Contact
        </h2>
        <h5 class="q-gutter-xs" align="center" id="secondaryTitle">
          <p>
            <i>Feel free to Contact me by submitting the form below and I will get back to you as soon as possible</i>
          </p>
        </h5>
        <div class="q-pa-md justify-center" style="max-width: 800px;" align="center">
          <q-form @submit.prevent="handleSubmit" @reset="resetForm()" class="q-gutter-md">
            <q-input name="name" outline v-model="formData.name" label="Your name *" hint="Name and surname" required
              class="italic-label-hint" />

            <q-input name="email" outline v-model="formData.email" type="email" label="Your e-mail *" hint="Email"
              required class="italic-label-hint" />

            <q-input name="phone" outline v-model="formData.phone" type="number" label="Your phone" hint="Phone number"
              class="italic-label-hint" />

            <q-input name="message" outline v-model="formData.message" type="textarea" label="Your message *" required
              class="italic-label-hint" />


            <input type="hidden" name="_captcha" value="false" />
            <input type="hidden" name="_template" value="table" />

            <div>
              <q-btn type="submit" color="black" :loading="loading"><i>Submit</i></q-btn>
              <q-btn outline type="reset" color="black" flat class="q-ml-sm"><i>Reset</i></q-btn>
            </div>
          </q-form>

        </div>
      </div>
    </q-page-container>
    <q-footer elevated class="bg-black text-white header">
      <q-toolbar>
        <q-toolbar-title style="font-family: mixone; font-weight: bolder;" align="center"><q-btn flat round dense
            icon="code" :href="insta" target="_blank" />CV - Daniel Silva</q-toolbar-title>
      </q-toolbar>
    </q-footer>


  </q-layout>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'
import { Notify } from 'quasar'

let description = ref("Software Analysis and Development student at SENA, currently doing an internship. Passionate about programming and developing technological solutions, with a solid foundation in programming logic, web development, and databases. I am looking for a job opportunity that allows me to continue learning, strengthen my technical skills, and actively contribute to software development projects.")
let ahorcado = ref("A classic hangman game developed with HTML, CSS, and JavaScript, focusing on basic language logic and user interaction through the DOM.")
let wis = ref("E-commerce website focused on selling footwear, developed with HTML, CSS, and JavaScript, including interactive features to enhance the user experience.")
let paraiso = ref("Website for a resort hotel, built with HTML, CSS, JavaScript, and Vue.js. It showcases rooms, activities, and services with a modern and intuitive design.")
let redvoid = ("Functional social network developed with Vue.js, HTML, CSS, and JavaScript, which allows posting, liking, and commenting. It uses a REST API built with Node.js and MongoDB as the backend.")
const activeTab = ref('home')
let email = ref(import.meta.env.VITE_EMAIL)
let mail = ref(import.meta.env.VITE_MAIL)
let red_url = ref(import.meta.env.VITE_RED)
let paraiso_url = ref(import.meta.env.VITE_HOTEL)
let insta = ref(import.meta.env.VITE_INSTAGRAM)
let linkedin = ref(import.meta.env.VITE_LINKEDIN)
let github = ref(import.meta.env.VITE_GITHUB)
let wis_url = ref(import.meta.env.VITE_WIS)
let whats = ref(import.meta.env.VITE_WHATS)
let ahorcado_url = ref(import.meta.env.VITE_AHORCADO)
let loading = ref(false)
let modal = ref(false)

const formData = ref({
  name: '',
  email: '',
  phone: '',
  message: ''
})

async function handleSubmit() {
  loading.value = true
  try {
    const response = await fetch(email.value, {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json',
        'Accept': 'application/json',
      },
      body: JSON.stringify({
        name: formData.value.name,
        email: formData.value.email,
        phone: formData.value.phone,
        message: formData.value.message,
        _captcha: 'false'
      }),
    })

    if (response.ok) {
      Notify.create({
        type: 'positive',
        message: '¡Sent successfully!',
        timeout: 3000
      })
      resetForm()
    } else {
      throw new Error('error sending')
    }
  } catch (error) {
    Notify.create({
      type: 'negative',
      message: 'error sending',
    })
  } finally {
    loading.value = false
  }
}

function resetForm() {
  formData.value = { name: '', email: '', message: '', phone: '' }
}

function scrollTo(tabName) {
  const el = document.getElementById(tabName)
  if (el) {
    const headerOffset = 100
    const elementPosition = el.getBoundingClientRect().top + window.pageYOffset
    const offsetPosition = elementPosition - headerOffset

    window.scrollTo({
      top: offsetPosition,
      behavior: "smooth"
    })
  }
}

const sectionIds = ['home', 'aboutMe', 'projects', 'contact']
let observers = []

onMounted(() => {
  sectionIds.forEach(id => {
    const el = document.getElementById(id)
    if (el) {
      const observer = new IntersectionObserver(
        ([entry]) => {
          if (entry.isIntersecting) {
            activeTab.value = id
          }
        },
        { threshold: 0.8 }
      )
      observer.observe(el)
      observers.push(observer)
    }
  })
})

onBeforeUnmount(() => {
  observers.forEach(observer => observer.disconnect())
})
</script>
<style>
.my-card {
  width: 90%;
  max-width: 550px;
}

.my-card2 {
  width: 90%;
  max-width: 750px;
}

.header {
  align-content: center;
}

@font-face {
  font-family: mixone;
  src: url(./assets/fonts/MIXONE.ttf);
}

.italic-label-hint .q-field__label,
.italic-label-hint .q-field__messages,
.italic-label-hint .q-toggle__label {
  font-style: italic;
}


.skill-badge {
  width: 70px;
  height: 30px;
  background-color: rgb(175, 175, 175);
  color: black;
  transition: 0.2s;
}

.skill-badge:hover {
  width: 85px;
  height: 35px;
  font-weight: bold;
}

/* JavaScript */
.skill-badge:hover:first-child {
  background-color: #F0DB4F;
  color: #323330;
}

/* Python */
.skill-badge:hover:nth-child(2) {
  background-color: #306998;
  color: #FFD43B;
}

/* Java */
.skill-badge:hover:nth-child(3) {
  background-color: rgb(209, 209, 209);
  color: #ED1D25;
}

/* HTML */
.skill-badge:hover:nth-child(4) {
  background-color: #E34C26;
  color: #EBEBEB;
}

/* CSS */
.skill-badge:hover:nth-child(5) {
  background-color: #2565AE;
  color: #D5F3FE;
}

/* Vue */
.skill-badge:hover:nth-child(6) {
  background-color: #41B883;
  color: #35495E;
}

/* Node */
.skill-badge:hover:nth-child(7) {
  background-color: #3C873A;
  color: #303030;
}

/* Mongo */
.skill-badge:hover:nth-child(8) {
  background-color: #3FA037;
  color: #E8E7D5;
}

/* SQL */
.skill-badge:hover:nth-child(9) {
  background-color: #00758F;
  color: #F29111;
}

/* git */
.skill-badge:hover:nth-child(10) {
  background-color: #F1502F;
  color: #EBEBEB;
}

/* github */
.skill-badge:hover:last-child {
  background-color: #211F1F;
  color: #FFFFFF;
}

body {
  position: relative;
  margin: 0;
}

body::before {
  content: "";
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: url("./assets/images/background.jpg");
  background-size: cover;
  background-position: center;
}

#projects__row-img {
  width: 700px;
}

#i_description {
  font-size: 16px;
}

@keyframes fadeInSide {
  from {
    opacity: 0;
    transform: translateX(-50px);
  }

  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(50px);
  }

  to {
    opacity: 1;
    transform: translateY(0);
  }
}

#principalTitles {
  font-family: mixone;
  font-weight: bolder;
  margin: 0px;
  animation: fadeInSide 1s ease-out;
  transition: 0.3s;
}

#secondaryTitle {
  animation: fadeInUp 1s ease-out;
}

#aboutMe {
  height: 85dvh;
}

#home {
  height: 85dvh;
  align-content: center;
  background-color: rgba(128, 128, 128, 0.11);
}

@media screen and (max-width:500px) and (min-width:320px) {
  #secondaryTitle {
    font-size: 20px;
  }

  #principalTitles {
    font-size: 50px;
  }

  #i_description {
    font-size: 15px;
  }

  .my-card2 {
    display: flex;
    flex-direction: column-reverse;
  }

  #aboutMe {
    height: auto;
  }

  #home {
    height: 80dvh;
  }
}

@media screen and (max-width:1155px) and (min-width:501px) {
  #aboutMe {
    height: auto;
  }
}
</style>