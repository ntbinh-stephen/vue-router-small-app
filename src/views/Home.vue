<template>
  <div class="home">
    <h1>All Destinations</h1>
    <div class="destinations">
      <div v-for="destination in destinations" :key="destination.name">
        <router-link
          :to="{
            name: 'DestinationDetails',
            params: { slug: destination.slug },
          }"
        >
          <h2>{{ destination.name }}</h2>
        </router-link>
        <figure>
          <router-link
            :to="{
              name: 'DestinationDetails',
              params: { slug: destination.slug },
            }"
          >
            <!-- khi add params như trên thì sau khi router điều hướng mình sang trang mình cần thì nó cũng sẽ truyền cho trang ấy những param mình khai báo ở trên, giống như modal trong project cty -->
            <img
              :src="require(`@/assets/${destination.image}`)"
              :alt="destination.name"
            />
          </router-link>
        </figure>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import store from "@/store.js";
export default {
  name: "Home",
  components: {},
  data() {
    return {
      destinations: store.destinations,
    };
  },
};
</script>
<style scoped>
.home {
  max-width: 1400px;
  margin: 0 auto;
}
h1 {
  color: black;
}
img {
  max-width: 200px;
}
.destinations {
  display: flex;
  justify-content: space-between;
}
a {
  text-decoration: none;
  color: black;
}
</style>
