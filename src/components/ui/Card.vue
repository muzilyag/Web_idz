<template>
  <div class="card">
    <img 
      :src="avatar" 
      :alt="name"
      class="card__avatar"
    >
    <div class="card__content">
        <h5 class="card__name">{{ name }}</h5>
        <h5 class="card__position">{{ position }}</h5>
    </div>

    <div class="card__actions">
      <button 
        class="card__button" 
        @click="openLink(hrenUrl)" 
        title="LinkedIn">
        <img 
          class="button__img" 
          src="../../assets/images/hren.png" 
          alt="hren'">
      </button>
      
      <button 
        class="card__button" 
        @click="openLink(twitterUrl)" 
        title="Twitter">
        <img 
          class="button__img" 
          src="../../assets/images/twitter.png" 
          alt="Twitter">
      </button>
      
      <button 
        class="card__button" 
        @click="openLink(instaUrl)" 
        title="Instagram">
        <img 
          class="button__img" 
          src="../../assets/images/insta.png" 
          alt="Instagram">
      </button>
    </div>
  </div>
</template>

<script setup lang="ts">
import defaultAvatar from '@/assets/images/avatar.jpg'

interface Props {
  name?: string;
  position?: string;
  avatar?: string;
  hrenUrl?: string;
  twitterUrl?: string;
  instaUrl?: string;
}

const props = withDefaults(defineProps<Props>(), {
  name: 'John Doe',
  position: 'Cofunder || CEO',
  avatar: defaultAvatar,
  hrenUrl: '#',
  twitterUrl: '#',
  instaUrl: '#'
})

const openLink = (url: string) => {
  if (url !== '#') {
    window.open(url, '_blank', 'noopener,noreferrer')
  }
}

</script>

<style scoped>
.card {
    padding: 30px 41px 29px 30px;
    background-color: var(--bckgrnd-card);
    border-radius: 10px;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 30px;
}

.card__avatar {
    border-radius: 50%;
    width: 107px;
    height: 115px;
}

.card__content {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 5px;
}

.card__name {
    color: var(--secondary-text);
    font-size: 0.875rem;
    font-weight: 600;
}

.card__position {
    font-size: 1.25rem;
    font-weight: 700;
}

.card__actions {
    display: flex;
    gap: 15px;
}

</style>