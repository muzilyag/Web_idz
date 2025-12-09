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
        title="LinkedIn">
        <i class="fa-brands fa-linkedin"></i>
      </button>
      
      <button 
        class="card__button" 
        title="Twitter">
        <i class="fa-brands fa-twitter"></i>
      </button>
      
      <button 
        class="card__button" 
        title="Instagram">
        <i class="fa-brands fa-instagram"></i>
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
}

const props = withDefaults(defineProps<Props>(), {
  name: 'John Doe',
  position: 'Cofunder || CEO',
  avatar: defaultAvatar,
})

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
    box-shadow: 
    0 0 10px #2D5981,
    0 0 20px #2D5981,
    0 0 30px #2D5981;
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

.card__button {
    width: 40px;
    height: 40px;
    border-radius: 5px;
    border: 1.7px solid transparent;
    background: 
        linear-gradient(var(--bckgrnd-card), var(--bckgrnd-card)) padding-box,
        var(--gradient-bright) border-box;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 0;
}

.card__button i {
    font-size: 18px;
    background: var(--gradient-bright);
    -webkit-background-clip: text;
    background-clip: text;
    -webkit-text-fill-color: transparent;
}

.card__button:hover {
    scale: 1.1;
    transition: all ease 0.6s;
}

</style>