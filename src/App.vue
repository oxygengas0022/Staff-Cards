<template>
  <div
    :style="{
      backgroundImage: `linear-gradient(rgba(0, 0, 0, 0.5),rgba(0, 0, 0, 0.75)), url('/images/tech-company.webp')`,
    }"
    class="container"
  >
    <h1 v-text="heading"></h1>
    <div class="staff-list-container">
      <div v-for="(user, index) in users" :key="index" class="single-user-card">
        <div class="img-info-container">
          <img v-bind:src="user.profilePicture" v-bind:alt="user.fullName" />
          <div class="info-container">
            <h2>{{ user.fullName }}</h2>
            <p><b>Phone Number: </b>{{ user.phoneNumber }}</p>
            <p><b>Country: </b>{{ user.country }}</p>
            <p><b>Address: </b>{{ user.address }}</p>
          </div>
        </div>

        <!-- Toggle Button -->
        <button @click="toggleDescription(index)">
          {{ user.showDescription ? "Hide Description" : "Show Description" }}
        </button>

        <!-- Description (conditionally rendered) -->
        <div v-if="user.showDescription" class="description">
          <p v-text="user.description"></p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const heading = "our staffs";

const users = ref([
  {
    fullName: "Simon Peter",
    description:
      "A passionate Vue.js developer with expertise in creating dynamic user interfaces and single-page applications. Simon enjoys collaborating with teams to build scalable web applications that enhance user experience.",
    profilePicture: "/images/profile-pic1.webp",
    phoneNumber: "+1-234-567-8901",
    country: "United States",
    address: "123 Main St, Springfield, IL",
    showDescription: false,
  },
  {
    fullName: "Alice Johnson",
    description:
      "A skilled front-end developer specializing in Vue.js and React. Alice has a knack for designing beautiful and responsive web applications that meet user needs.",
    profilePicture: "/images/profile-pic2.webp",
    phoneNumber: "+1-234-567-8902",
    country: "Canada",
    address: "456 Maple Ave, Toronto, ON",
    showDescription: false,
  },
  {
    fullName: "Michael Smith",
    description:
      "An enthusiastic software engineer with a focus on Vue.js and back-end integration. Michael loves tackling complex problems and delivering efficient solutions.",
    profilePicture: "/images/profile-pic3.webp",
    phoneNumber: "+1-234-567-8903",
    country: "Australia",
    address: "789 Pine St, Sydney, NSW",
    showDescription: false,
  },
  {
    fullName: "Jessica Brown",
    description:
      "A creative web developer with a strong background in Vue.js and user experience design. Jessica is dedicated to crafting intuitive interfaces that engage users.",
    profilePicture: "/images/profile-pic4.webp",
    phoneNumber: "+1-234-567-8904",
    country: "United Kingdom",
    address: "101 High St, London",
    showDescription: false,
  },
  {
    fullName: "David Wilson",
    description:
      "A motivated full-stack developer with experience in Vue.js and Node.js. David enjoys building robust applications that are both functional and visually appealing.",
    profilePicture: "/images/profile-pic5.webp",
    phoneNumber: "+1-234-567-8905",
    country: "Germany",
    address: "202 Elm St, Berlin",
    showDescription: false,
  },
  {
    fullName: "Emily Davis",
    description:
      "A detail-oriented software developer with expertise in Vue.js and agile methodologies. Emily is passionate about delivering high-quality code and improving development processes.",
    profilePicture: "/images/profile-pic6.webp",
    phoneNumber: "+1-234-567-8906",
    country: "France",
    address: "303 Oak St, Paris",
    showDescription: false,
  },
  {
    fullName: "Chris Martin",
    description:
      "An innovative web developer specializing in Vue.js and responsive design. Chris enjoys creating seamless user experiences and is always eager to learn new technologies.",
    profilePicture: "/images/profile-pic7.webp",
    phoneNumber: "+1-234-567-8907",
    country: "Italy",
    address: "404 Birch St, Rome",
    showDescription: false,
  },
  {
    fullName: "Sophia Lee",
    description:
      "A dynamic software engineer with a focus on Vue.js and cloud technologies. Sophia is passionate about building scalable applications that enhance productivity.",
    profilePicture: "/images/profile-pic8.webp",
    phoneNumber: "+1-234-567-8908",
    country: "Spain",
    address: "505 Cedar St, Madrid",
    showDescription: false,
  },
  {
    fullName: "James Taylor",
    description:
      "A resourceful developer with experience in Vue.js and mobile app development. James loves creating applications that bridge the gap between users and technology.",
    profilePicture: "/images/profile-pic9.webp",
    phoneNumber: "+1-234-567-8909",
    country: "Netherlands",
    address: "606 Walnut St, Amsterdam",
    showDescription: false,
  },
  {
    fullName: "Olivia White",
    description:
      "A passionate front-end developer with expertise in Vue.js and design systems. Olivia focuses on building accessible and user-friendly interfaces.",
    profilePicture: "/images/profile-pic10.webp",
    phoneNumber: "+1-234-567-8910",
    country: "Sweden",
    address: "707 Cherry St, Stockholm",
    showDescription: false,
  },
]);

// toggle functionality

const toggleDescription = (index) => {
  users.value[index].showDescription = !users.value[index].showDescription;
};
</script>

<style>
.container {
  padding: 2rem 1rem;
  background-size: cover;
  background-position: center;
  height: 100vh;
  overflow: auto;
}
.container h1 {
  text-transform: capitalize;
  text-align: center;
  margin-bottom: 2rem;
  font-size: 3rem;
  color: white;
}
.staff-list-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
.single-user-card {
  max-width: 45rem;
  background: white;
  margin-bottom: 2rem;
  border-radius: 0.5rem;
  padding: 1rem;
}
.img-info-container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 2rem;
}
img {
  width: 10rem;
  display: block;
  border: 3px solid greenyellow;
  border-radius: 0.5rem;
}
.info-container h2 {
  font-size: 1.65rem;
  margin-bottom: 0.5rem;
}
.info-container p {
  font-size: 1rem;
  margin-bottom: 0.25rem;
}
.description {
  margin-top: 1rem;
  max-width: 35rem;
}
button {
  background: black;
  color: white;
  border: none;
  padding: 10px;
  cursor: pointer;
  font-size: 1rem;
  margin-top: 10px;
  border-radius: 5px;
}

button:hover {
  opacity: 0.8;
}
@media screen and (min-width: 550px) {
  img {
    width: 15rem;
  }
  .info-container h2 {
    font-size: 2rem;
  }
  .info-container p {
    font-size: 1.15rem;
    text-transform: capitalize;
  }
  .description {
    font-size: 1.35rem;
  }
  .description {
    max-width: 35rem;
  }
}
</style>
