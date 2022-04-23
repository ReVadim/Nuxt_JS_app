<template>
  <div class="col-md-4">
    <div class="card my-4">
      <h5 class="card-header">Теги</h5>
      <div class="card-body">
        <div class="d-flex flex-wrap">
          <nuxt-link :to="`/tags/${tag.slug}`" class="m-2 h5" v-for="tag in tags" :key="tag.slug">>#{{tag.name}}</nuxt-link>
        </div>
      </div>
    </div>

    <div class="card my-4">
      <h5 class="card-header">Последние статьи</h5>
      <div class="card-body" v-for="post in aside" :key="post.id">
        <h5 class="card-title">{{post.name}}</h5>
        <img :src="post.image" alt="" class="card-img-top">
        <div v-html="post.description" class="truncate"></div>
        <div class="d-flex">
            <div>Автор: {{ post.author }}<br>Опубликовано: {{ post.created_at }}</br></div>
          </div>
        <nuxt-link :to="`/posts/${post.slug}`" class="card-link">Ссылка на статью</nuxt-link>
        <hr>
      </div>
    </div>
  </div>
</template>

<script>
export default {
name: "aside.vue",
props: ['aside', 'tags']
}
</script>

<style scoped>

</style>
