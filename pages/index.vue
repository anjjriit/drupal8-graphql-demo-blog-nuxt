<template>
  <div class="container">
  
    <section class="section">
      <Posts v-if="nodeQuery" :posts="nodeQuery.entities" />
      <Loading v-else />
    </section>
  
  </div>
</template>

<script>
import allPosts from '~/apollo/queries/allPosts'
import Posts from '~/components/Posts'
import Loading from '~/components/Loading'
export default {
  components: { Posts, Loading },
  apollo: {
    nodeQuery: {
      query: allPosts
      //  Server side rendering will work once https://github.com/nuxt-community/apollo-module/pull/10 is merged
      //  prefetch: true, 
    }
  }
}
</script>
