<template>
  <div class="w-full">
    <header>
      <h2 class="text-2xl m-8 text-blue-900 font-semibold">719-210-2899</h2>
      <section id="navbar" class="flex justify-between px-8 py-2 bg-gray-100">
        <nav class="w-1/2">
          <button
            class="rounded-md px-2 text-sm text-blue-800"
            @click="scrollTo('home')"
          >
            Home
          </button>
          <button
            class="rounded-md px-2 text-sm text-blue-800"
            @click="scrollTo('hours')"
          >
            Hours
          </button>
          <button
            class="rounded-md px-2 text-sm text-blue-800"
            @click="scrollTo('services')"
          >
            Services
          </button>
          <button
            class="rounded-md px-2 text-sm text-blue-800"
            @click="scrollTo('contact')"
          >
            Contact
          </button>
        </nav>
        <nav class="w-1/2">
          <section class="flex justify-end">
            <button @click="scrollTo('contact')" class="text-blue-800 text-sm">
              📧 allpeaksrv@gmail.com
            </button>
            <button
              @click="scrollTo('contact')"
              class="text-blue-800 text-sm ml-4"
            >
              📱 719.210.2899
            </button>
          </section>
        </nav>
      </section>
    </header>
    <section class="flex">
      <main class="w-1/2 m-auto">
        <h1 class="text-5xl text-center mt-36 font-bold text-blue-900">
          Welcome to All Peaks RV Repair
        </h1>
        <h3 class="text-xl text-center my-6 font-medium text-blue-900">
          Servicing Summit, Park, Lake, Eagle, and Chaffee Counties Colorado
        </h3>
        <p class="my-8 text-blue-900 font-medium">
          All Peaks Mobile RV Repair has the equipment and expertise to repair
          and maintain your Recreational Vehicle . Our emphasis is on
          transparency and professionalism. We pride ourselves on performing the
          highest quality servicing as quickly and efficiently as possible —
          something all our customers appreciate.
        </p>

        <button
          class="text-xl border-blue-800 border-2 p-2 rounded-full text-blue-800 font-light"
          @click="scrollTo('contact')"
        >
          Get in Touch
        </button>

        <div class="h-40" id="spacer"></div>
        <section
          class="text-3xl font-semibold text-blue-800 w-full text-center my-12"
        >
          Services
        </section>
        <p class="my-8 text-blue-900 font-medium">
          At All Peaks Mobile RV Repair, We aim to keep your trip on schedule.
          We keep parts on hand for typical repairs. If a part need to be
          special ordered. We use multiple distributors to get the highest
          quality parts, as quickly as possible. Whatever you need, we have the
          skills to do it right.
        </p>
      </main>
    </section>
    <section class="flex">
      <div class="flex relative">
        <img
          class="w-4/5 m-auto justify-center"
          src="@/assets/mountain.png"
          alt="man on mountain"
        />
        <p
          class="absolute text-white bottom-0 w-1/2 right-0 mr-24 text-xs p-2 drop-shadow-md"
        >
          At 10,000 ft elevation, you will put your rig to the test — if
          anything fails, don't let it ruin your trip. All Peaks Mobile RV
          Repair has the proper equipment and experience to locate, repair
          and/or replace the issue.
        </p>
      </div>
    </section>
    <div class="h-16" id="spacer"></div>

    <section class="flex bg-gray-100 w-4/5 m-auto justify-center">
      <div class="flex">
        <div class="text-blue-800 w-1/2 px-4">
          <h2 class="my-4 font-semibold">Operating Hours & Billing</h2>
          <p class="my-4 text-blue-900">
            Service Call Fee + 1hr. Minimum. We charge per Service Management
            Guide. Holiday fees may apply
          </p>
          <span class="my-4 text-blue-900"
            >Mon - Fri: 9am - 6pm Sat - Sun: 10am - 2pm
          </span>
        </div>
        <img
          class="w-1/2 m-auto justify-center"
          src="@/assets/rv.png"
          alt="man on mountain"
        />
      </div>
    </section>
    <div class="h-36" id="spacer"></div>
    <footer class="w-full bg-gray-100 text-blue-900">
      <h2 class="text-4xl w-full text-center font-semibold pt-4">Contact Us</h2>
      <div class="w-full m-auto text-center mt-2">
        <span class="w-full text-sm">allpeaksrv@gmail.com</span><br />
        <span class="w-full text-center text-sm">719.210.2899</span>
      </div>

      <form
        @submit.prevent="submitForm"
        class="bg-gray-100 mx-8 px-2"
        action=""
      >
        <label for="name">Name *</label><br />
        <input
          v-model="name"
          class="bg-gray-100 w-full h-14 p-2"
          type="text"
          placeholder="Enter your name"
        />
        <hr />
        <label for="email">Email *</label><br />
        <input
          v-model="email"
          class="bg-gray-100 w-full h-14 p-2"
          type="text"
          placeholder="Enter your email"
        />
        <hr />
        <label for="email">Phone *</label><br />
        <input
          v-model="phone"
          class="bg-gray-100 w-full h-14 p-2"
          type="text"
          placeholder="Enter your phone number"
        />
        <hr />
        <label for="subject">Subject</label><br />
        <input
          v-model="subject"
          class="bg-gray-100 w-full h-14 p-2"
          type="text"
          placeholder="Enter the subject"
        />
        <hr />
        <label for="message">Message</label><br />
        <textarea
          v-model="message"
          class="p-2 bg-gray-100 w-full h-28 no-resize"
          type="text"
          placeholder="Type your message here..."
        />
        <button
          type="submit"
          @disabled="!ableToSubmit"
          :class="[
            'w-full text-white font-semibold  text-lg',
            ableToSubmit
              ? 'bg-blue-800 cursor-pointer'
              : 'bg-gray-200 cursor-not-allowed',
          ]"
        >
          Submit
        </button>
        <span class="text-red-700">
          {{ errors }}
        </span>
      </form>
      <br />
      <span class="w-full text-xs text-center justify-center mx-auto flex pb-4">
        ©2021 by All Peaks Mobile RV Repair
      </span>
    </footer>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "Main",
  data() {
    return {
      name: null,
      email: null,
      subject: null,
      message: null,
      phone: null,
    };
  },
  methods: {
    scrollTo(location) {
      if (location === "home") window.scrollTo(0, 0);
      if (location === "services") window.scrollTo(0, 830);
      if (location === "hours") window.scrollTo(0, 1550);
      if (location === "contact") window.scrollTo(0, 2200);
    },
    submitForm(e) {
      e.preventDefault();
      const url = "https://formspree.io/f/mknyrzvw";
      const data = {
        email: this.email,
        message: `name: ${this.name}\nphone: ${this.phone}\nemail: ${this.email}\nsubject: ${this.subject}\nmessage: ${this.message}`,
      };
      axios
        .post(url, data)
        .then(({ data }) => {
          console.log(data);
          if (data.ok) {
            alert(
              "Thank you, your form has been submitted. Please allow 24 hours for a response"
            );
          }
          this.name = null;
          this.email = null;
          this.subject = null;
          this.message = null;
        })
        .catch((err) => {
          console.error(err);
          alert(
            "There was an error submitting your form, please call 719.210.2899 for assistance."
          );
        });
    },
  },
  computed: {
    ableToSubmit() {
      return (
        !!this.name &&
        !!this.email &&
        this.email?.split("")?.includes(".") &&
        this.email?.split("")?.includes("@") &&
        this.email?.length > 4 &&
        this.name?.length > 0
      );
    },
    errors() {
      const errors = [];

      const isValidEmail = (email) => {
        const regex = /^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/;
        return regex.test(email);
      };

      if (!this.phone) {
        errors.push("Please enter a phone number");
      }

      if (!isValidEmail(this.email)) {
        errors.push("Please enter a valid email address");
      }
      if (this.name?.length && !this.email?.length) {
        errors.push("Please enter a valid email");
      }
      if (!this.name?.length && this.email?.length) {
        errors.push("Please enter a name");
      }
      return errors.join(" - ");
    },
  },
};
</script>

<style scoped></style>
