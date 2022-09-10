<script setup>
const loginDialog = false;
const signupDialog = false;
const features = ref([
  {
    src: "fontawesome/circle-1-light.svg",
    title: "Add a new listing",
    description: "Add a new rental listing and fill in details about the item",
  },
  {
    src: "fontawesome/circle-2-light.svg",
    title: "Booking Request",
    description:
      "Receive a booking request, and accept or decline depending on availabilty",
  },
  {
    src: "fontawesome/circle-3-light.svg",
    title: "Booking Finalization",
    description:
      "Both user accounts are verified, booking dates will be finalized and payment made via secure PayFast link",
  },
]);

const features1 = ref([
  {
    src: "fontawesome/circle-4-light.svg",
    title: "Delivery and Payment",
    description:
      "Delivery is arranged between the item owner and borrower and rental fee paid out to the item owner.",
  },
  {
    src: "fontawesome/circle-5-light.svg",
    title: "Save Time",
    description:
      "The item is used and we will notify you when it is to be returned",
  },
  {
    src: "fontawesome/circle-6-light.svg",
    title: "Rating and Review",
    description:
      "Once the item and safety deposit is returned each user will rate and review their overall experience",
  },
]);
const partners = ref([
  {
    icon: "fas fa-people",
    title: "Trusted Partners",
    text: "We've teamed up with the best in the business",
  },
]);
const awards = ref([
  {
    icon: "fas fa-trophy",
    title: "Awards and Accolades",
    text: "",
  },
]);

const snackbar = true;
const text =
  "Hello, This website uses cookies to ensure you get the best experience on our website 🍪 👮";

const cards = ref([
  {
    src: "svgs/happy.svg",
    icon: "fas fa-handshake",
    title: "Participate",
    text: " Be part of a community of people that encourage shared ownership, living flexibly and the environment.",
  },
  {
    src: "svgs/mindmap-1.svg",
    icon: "fas fa-coins",
    title: "Access More",
    text: "Access more from people in your local community. Get what you need, for a fraction of the cost.",
  },
  {
    src: "svgs/money-3.svg",
    icon: "fas fa-money-bill-wave",
    title: "Make More",
    text: "Turn the things you hardly use into income generating machines! Make passive income by doing hardly anything!",
  },
  {
    icon: "fas fa-tree",
    src: "svgs/grow-1.svg",
    title: "Reduce waste",
    text: "Decrease the demand for mass produced goods by using what others already own.",
  },
]);
</script>

<template>
  <section id="hero">
    <v-snackbar v-model="snackbar">
      {{ text }}

      <template v-slot:action="{ attrs }">
        <v-btn color="pink" text v-bind="attrs" @click="snackbar = false">
          Got it!
        </v-btn>
      </template>
    </v-snackbar>

    <v-container class="px-1 py-0 fill-height">
      <v-slide-x-reverse-transition appear>
        <v-row>
          <v-col
            class="mt-lg-16"
            cols="12"
            sm="12"
            xs="12"
            md="6"
            lg="6"
            xl="6"
          >
            <v-img
              height="70px"
              width="100px"
              src="logos/icon1.svg"
              contain
              class="mt-8 hidden-sm-and-down"
            />
            <v-row class="hidden-md-and-up">
              <v-col cols="2">
                <v-img
                  height="70px"
                  width="100px"
                  src="logos/icon1.svg"
                  contain
                  class="mt-8 ml-3 hidden-md-and-up"
                />
              </v-col>
              <v-col cols="10">
                <p
                  style="
                    margin-top: 20px;
                    color: rgb(34, 34, 34);
                    font-display: swap;
                  "
                  color="rgb(34, 34, 34)"
                  class="ml-2 pa-1 font-weight-bold"
                >
                  Earn an income from renting out what you hardly use to others
                  in your community!
                </p>
              </v-col>
            </v-row>

            <p
              style="
                margin-top: 20px;
                color: rgb(34, 34, 34);
                font-display: swap;
              "
              color="rgb(34, 34, 34)"
              class="pa-3 font-weight-bold hidden-sm-and-down"
            >
              Earn an income from renting out what you hardly use to others in
              your community!
            </p>
            <!-- <p style="color: white;" class="hidden subtitle-1">
                Rent out the things you own, but hardly use, to others for
                short-term periods. Increasing income and access.
              </p> -->

            <p
              class="pa-2"
              color="rgb(34, 34, 34)"
              style="font-size: 18px !important; font-display: swap"
            >
              A central rental marketplace providing easy, affordable, and
              trusted rentals from your local community!
            </p>
            <v-btn
              class="hero-button hidden-sm-and-down font-weight-bold white--text"
              rounded
              color="secondary"
              elevation="8"
              large
              to="items/new"
            >
              <v-icon x-small class="mr-1 text-none">fas fa-plus</v-icon> Add
              Item
            </v-btn>

            <v-btn
              to="/items"
              elevation="8"
              class="ml-4 hero-button hidden-sm-and-down pa-1 app--text"
              large
              rounded
            >
              <v-icon x-small class="pr-1">fas fa-search</v-icon>Browse
            </v-btn>
          </v-col>

          <v-col cols="12" sm="12" xs="12" md="6" lg="6" xl="6">
            <v-img src="landing/hero1.png"></v-img>
          </v-col>
        </v-row>
      </v-slide-x-reverse-transition>
    </v-container>

    <center>
      <div>
        <v-col>
          <v-row style="display: grid; place-items: center" class="pr-16 mr-16">
            <v-btn
              class="hidden-md-and-up white--text font-weight-black"
              rounded
              color="accent"
              elevation="8"
              large
              style="z-index: 99"
              to="items/new"
              fixed
              medium
              bottom
              right
            >
              List an Item.
            </v-btn>
          </v-row>
        </v-col>
      </div>
    </center>

    <v-responsive class="pl-5 pr-5 mx-auto" max-width="1750">
      <v-container fluid>
        <v-row class="mb-4 ml-4 mr-4">
          <v-col
            v-for="card in cards"
            :key="card.title"
            cols="12"
            sm="3"
            md="3"
          >
            <base-info-card align="center" dark v-bind="card" />
          </v-col>
        </v-row>
      </v-container>
    </v-responsive>

    <!-- sign in button here --->

    <v-row style="padding-top: 16px" justify="center">
      <v-col v-for="card in partners" :key="card.title" cols="12" sm="3" md="3">
        <base-info-card align="center" dark v-bind="card" />
      </v-col>
    </v-row>

    <v-row justify="center" style="padding: 8px; margin-bottom: 36px">
      <v-col class="center" cols="6" xs="6" sm="6" md="6" lg="2" xl="2">
        <v-img class="pimg" src="partnerLogos/stitch.jpg"> </v-img>
      </v-col>

      <v-col class="center" cols="6" xs="6" sm="6" md="6" lg="2" xl="2">
        <v-img class="pimg" src="partnerLogos/payfast.jpeg"> </v-img>
      </v-col>

      <v-col class="center" cols="6" xs="6" sm="6" md="6" lg="4" xl="4">
        <v-img class="pimg" src="partnerLogos/genric.jpg"> </v-img>
      </v-col>
      <v-col class="center" cols="6" xs="6" sm="6" md="6" lg="2" xl="2">
        <v-img class="pimg" src="partnerLogos/innovation.jpg"> </v-img>
      </v-col>
      <v-col class="center" cols="6" xs="6" sm="6" md="6" lg="2" xl="2">
        <v-img class="pimg" src="partnerLogos/sab.jpg"> </v-img>
      </v-col>
    </v-row>

    <trees></trees>

    <v-sheet class="pt-8 pt-lg-16">
      <div class="text-center">
        <div
          class="mb-2 text-uppercase font-weight-bold body-2 secondary--text"
        >
          How it works
        </div>
        <h2
          style="font-weight: 400 !important; color: rgb(34, 34, 34) !important"
          class="text-h4 text-lg-h4"
        >
          Earn money from your things
        </h2>
      </div>
      <v-row class="mt-10" max-width="1250">
        <v-col cols="12" md="6" sm="12" xs="12" lg="5" offset-lg="1">
          <div class="pa-3" v-for="(item, i) in features" :key="i">
            <div class="d-flex">
              <div class="mr-2">
                <v-sheet class="mt-1 pa-2">
                  <v-img height="50px" width="50px" :src="item.src"></v-img>
                </v-sheet>
              </div>
              <div>
                <div class="text-h6">{{ item.title }}</div>
                <div class="mt-1 text-subtitle-1">
                  {{ item.description }}
                </div>
              </div>
            </div>
          </div>
        </v-col>
        <v-col cols="12" md="6" sm="12" xs="12" lg="5">
          <div class="pa-3" v-for="(item, i) in features1" :key="i">
            <div class="d-flex">
              <div class="mr-2">
                <v-sheet color="surface" rounded class="pa-2">
                  <v-img height="50px" width="50px" :src="item.src"></v-img>
                </v-sheet>
              </div>
              <div>
                <p class="subtitle-1">{{ item.title }}</p>
                <div class="mt-1 text-subtitle-1">{{ item.description }}</div>
              </div>
            </div>
          </div>
        </v-col>
      </v-row>
    </v-sheet>

    <!-- explore items -->

    <v-row style="padding-top: 16px" justify="center">
      <v-col v-for="card in awards" :key="card.title" cols="12" sm="3" md="3">
        <base-info-card align="center" dark v-bind="card" />
      </v-col>
    </v-row>

    <v-row style="padding: 8px; margin-bottom: 36px !important">
      <v-col class="center" cols="12" sm="6" md="6" lg="4" xl="4">
        <v-img class="img" src="partnerLogos/etrack.png" contain> </v-img>
        <h6 class="mt-1 text-subtitle-1" style="text-align: center">
          <i
            >Most likely to succeed 2022 UCT GSB E-Track Accelerator Programme -
            Peer Award</i
          >
        </h6>
      </v-col>

      <v-col class="center" cols="12" sm="6" md="6" lg="4" xl="4">
        <v-img class="img" src="partnerLogos/akro.png" contain> </v-img>
        <h6 class="mt-1 text-subtitle-1" style="text-align: center">
          <i>Competition winner of the 2021 Akro Africa Leopards Lair Pitch </i>
        </h6>
      </v-col>

      <v-col class="center" sm="6" md="6" lg="4" xl="4">
        <v-img class="img" src="partnerLogos/gsb.png" contain> </v-img>
        <h6 class="mt-1 text-subtitle-1" style="text-align: center">
          <i>Top 7 of Cohort 5 2022 UCT GSB E-Track Accelerator Programme</i>
        </h6>
      </v-col>
    </v-row>

    <v-sheet color="#fff">
      <div class="text-center">
        <h2 class="mb-2 text-uppercase font-weight-bold secondary--text">
          Why choose us?
        </h2>
        <h2
          style="font-weight: 400 !important; color: rgb(34, 34, 34) !important"
          class="text-h4 text-lg-h4"
        >
          Strapp makes it possible for you to
        </h2>
      </div>
      <v-container class="py-4 py-lg-8">
        <v-row>
          <v-col cols="12" md="9" lg="8" xl="6" offset-lg="1">
            <v-row>
              <v-img
                src="landing/money.png"
                max-width="280"
                max-height="280"
              ></v-img>
              <v-col>
                <div class="text-h5 secondary--text text-lg-h5">
                  <strong> Get paid for what you already own! </strong>
                </div>
                <br />
                <p style="font-weight: 400 !important; font-style: Italic">
                  Remember your lawnmower you only use once every 2 weeks?
                  <br />
                  Instead of letting it waste away when you arent using it, rent
                  it out to other community members and make money in the
                  process!
                </p>
              </v-col>
            </v-row>
          </v-col>
        </v-row>
        <v-col cols="12" md="10" lg="7" offset-md="2" offset-lg="4">
          <v-row>
            <v-img
              src="landing/fly.png"
              max-width="280"
              max-height="280"
            ></v-img>
            <v-col>
              <div class="secondary--text text-h5 text-lg-h5">
                <strong> Own less. Access More </strong>
              </div>
              <br />
              <p
                style="
                  font-weight: 400 !important;
                  font-style: Italic;
                  font-size: 18px !important;
                "
              >
                Do what you otherwise couldn't with flexible ownership, allowing
                you quick and easy access to the things you need, when you need
                them, accessing more for less.
              </p>
            </v-col>
          </v-row>
        </v-col>
        <v-col cols="3" sm="12" md="9" lg="7" offset-lg="1">
          <v-row>
            <v-img
              src="landing/rating.png"
              max-width="280"
              max-height="280"
            ></v-img>
            <v-col>
              <div class="secondary--text text-h5 text-lg-h5">
                <strong> Transact Safely </strong>
              </div>
              <br />
              <p
                style="
                  font-weight: 400 !important;
                  font-style: Italic;
                  font-size: 18px !important;
                "
              >
                Supporting you every step of the way by creating tranparency in
                every transaction, thats why all our users go under a thorough
                verification process.
              </p>
            </v-col>
          </v-row>
        </v-col>
        <v-col cols="12" md="9" lg="7" offset-md="3" offset="5">
          <v-row>
            <v-img
              src="landing/community.png"
              max-width="280"
              max-height="280"
            ></v-img>
            <v-col>
              <div class="secondary--text text-h5 text-lg-h5">
                <strong> Build connected communities</strong>
              </div>
              <br />
              <p
                style="
                  font-weight: 400 !important;
                  font-style: Italic;
                  font-size: 18px !important;
                "
              >
                Creating communities built upon flexibility, shared ownership
                and trust, allowing you to access what you need form others in
                your area. Connecting people, experiences and redefining
                ownership.
              </p>
            </v-col>
          </v-row>
        </v-col>
        <v-col cols="12" md="9" lg="7" offset-lg="1">
          <v-row>
            <v-img
              src="landing/enviro.png"
              max-width="280"
              max-height="280"
            ></v-img>
            <v-col>
              <div class="secondary--text text-h5 text-lg-h5">
                <strong> Help the enviroment</strong>
              </div>
              <br />
              <p
                style="
                  font-weight: 400 !important;
                  font-style: Italic;
                  font-size: 18px !important;
                "
              >
                You can save an estimated 350kg of C02 from listing a laptop for
                rent. This is the equivalent of driving 1255 km!
                <br />
                Renting reduces the demand for mass produced goods, helping the
                enviroment as well as your pocket!
              </p>
            </v-col>
          </v-row>
        </v-col>
      </v-container>
    </v-sheet>
  </section>
</template>

<style lang="scss" scoped>
.c-preview {
  background: white;
  background: -moz-linear-gradient(
    -45deg,
    white 0%,
    #000000 25%,
    #1e539e 50%,
    #ff3083 75%,
    #7800a8 100%
  );
  /* FF3.6-15 */
  background: -webkit-linear-gradient(
    -45deg,
    #000000 0%,
    #000000 25%,
    #1e539e 50%,
    #ff3083 75%,
    #7800a8 100%
  );
  /* Chrome10-25,Safari5.1-6 */
  background: linear-gradient(
    135deg,
    #000000 0%,
    #000000 25%,
    #1e539e 50%,
    #ff3083 75%,
    #7800a8 100%
  );
  /* W3C, IE10+, FF16+, Chrome26+, Opera12+, Safari7+ */
  background-size: 400% 400%;
  background-repeat: no-repeat;
  transition: 0.5s all;

  &:hover {
    background-position: 100% 100%;
  }
}

.zoom-efect {
  transform: scale(1.2);
}

.up {
  transform: translateY(-20px);
  transition: 0.3s ease-out;
}

.center {
  display: grid;
  place-items: center;
}

.example-3d {
  width: 100%;
  height: 400px;
  padding-top: 50px;
  padding-bottom: 50px;
}

.swiper {
  height: 100%;
  width: 100%;
  border-radius: 20px;

  .swiper-slide {
    display: flex;
    border-radius: 20px;
    justify-content: center;
    align-items: center;
    width: 300px;
    height: 300px;
    text-align: center;

    font-weight: bold;
    // font-size: $font-size-large * 2;
    background-color: whitesmoke;
    background-position: center;
    background-size: cover;
    color: white;
  }

  .swiper-pagination {
    .swiper-pagination-bullet.swiper-pagination-bullet-active {
      background-color: white;
      margin-top: 50px;
    }
  }
}
</style>

<style>
.vsc-popup-button {
  background-color: var(--vsc-bg-button);
  bottom: 30%;
}

.whatsapp-chat {
  --whatsapp: #46c056;
  --vsc-bg-header: var(--whatsapp);
  --vsc-bg-button: var(--whatsapp);
  --vsc-outline-color: var(--whatsapp);
}

.hero-button {
  padding: 1rem 4rem;
  border-radius: 100rem;
  color: white;
  width: 10rem;
  font-weight: 700;
  transition: 0.5s;
  box-shadow: 0px 8px 15px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease 0s;
}

.hero-button:hover {
  width: 11rem;
  box-shadow: 0px 15px 20px rgba(46, 229, 157, 0.4);
  transform: translateY(-7px);
}

/* .svg-border-waves .v-image {
  position: absolute;
  bottom: 0;
  left: 0;
  height: 3rem;
  width: 100%;
  overflow: hidden;
}
.svg-border-waves img {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  margin-bottom: -2px;
  z-index: 2;
} */

/*Particle BG Effect*/

.particle-bg {
  position: absolute;
  top: 2%;
  left: 80%;
  z-index: 2;
}

.particle-bg img {
  animation: spin 27s linear infinite;
}

@keyframes spin {
  100% {
    transform: rotate(360deg);
  }
}

.background-shape {
  position: absolute;
  animation-name: bobbingAnim;
  animation-duration: 2s;
  padding: 0 7px 7px;
  top: 75%;

  animation-iteration-count: infinite;
  animation-play-state: running;
}

@keyframes bobbingAnim {
  0% {
    transform: translate(0px, 0px);
    animation-timing-function: ease-in-out;
  }

  50% {
    transform: translate(0px, 14px);
    animation-timing-function: ease-in-out;
  }

  100% {
    transform: translate(0px, 0px);
    animation-timing-function: ease-in-out;
  }
}

.background-shape img {
  max-width: 90%;
}

.img {
  /* height: auto; */
  max-height: 70px !important;
  width: auto;
}

.pimg {
  /* height: auto; */
  max-height: 100px !important;
  max-width: 100px;
}
</style>
