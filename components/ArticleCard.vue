<template>
  <div class="article-card">
    Article Card
    <NuxtLink :to="slug"><h3>{{ title }}</h3></NuxtLink>
    <div class="author">
      <p>por {{ author }}</p>
      <small>Fecha de publicación {{ date.toLocaleDateString() }}</small>
    </div>
    <figure>
      <img :src="image" :alt="title" />
    </figure>
    <p>{{ description }}</p>
    <div class="actions">
      <!-- <NuxtLink class="btn" :to="slug" >Ir al post</NuxtLink> -->
      <nuxt-link class="btn" :to="slug" >Ir al post</nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ArticleCard',
  props: {
    title: {
      type: String,
      default: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatum.'
    },
    author: {
      type: String,
      default: 'John Doe'
    },
    date: {
      type: Date,
      default: () => new Date()
    },
    image: {
      type: String,
      default: 'https://picsum.photos/500/300'
    },
    description: {
      type: String,
      default: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatum.'
    },
    slug: {
      type: String,
      default: ''
    }
  },
  data() {}
}
</script>

<style lang="scss" scoped>
.article-card {
  @apply block bg-white sm:border sm:rounded-lg p-4;
  h3 {
    @apply font-bold text-xl mb-2 mt-0;
  }
  div.author {
    @apply my-2;
    p {
      @apply m-0;
    }
    small {
      @apply italic;
    }
  }
  figure {
    img {
      @apply w-full;
    }
  }
  p {
    @apply my-4 font-serif;
  }
  div.actions {
    @apply flex gap-2;
    .btn {
      @apply w-full text-center border rounded-full px-8 py-2 bg-gray-200 hover:bg-gray-300;
    }
  }
}
</style>
