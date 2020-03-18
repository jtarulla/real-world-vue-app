<template>
  <div>
    <h1>This is {{ $route.params.username }} page</h1>
  </div>
</template>

// to avoid using $route.params
<script>
export default {
  props: ['username']
}
</script>
