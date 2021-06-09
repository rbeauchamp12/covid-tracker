<template>
  <Header />
  <router-view />
</template>

<!-- adding the import for header -->
<script>
import Header from '@/components/Header'

export default{
  components: {
    Header
  },
}
</script>