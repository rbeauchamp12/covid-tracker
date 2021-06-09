<template>
  <Header />
    <div class="container mx-auto">
      <router-view />
    </div>

</template>

<!-- adding the import for header -->
<script>
import Header from '@/components/Header'

export default {
  components: {
    Header,
  },
}

</script>