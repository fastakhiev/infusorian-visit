<template>
  <main class="page">
    <section class="hero section">
      <div class="glass">
        <p class="eyebrow">3 months</p>
        <h1>Special for my принцесска ❤️</h1>
        <p class="subtitle">
          <!-- Я хотел сделать что-то, чего больше ни у кого нет. -->
        </p>

        <button class="primary-btn" @click="scrollToMemories">
          Открыть
        </button>
      </div>
    </section>

    <section ref="memoriesSection" class="section memories">
      <h2>Наши моменты</h2>

      <div class="photo-grid">
        <article
          v-for="photo in photos"
          :key="photo.src"
          :class="[
            'photo-card',
            `photo-card--${photo.orientation ?? 'vertical'}`
          ]"
        >
          <img :src="photo.src" :alt="photo.caption" />
          <p>{{ photo.caption }}</p>
        </article>
      </div>
    </section>

    <section class="section final">
      <div class="glass">
        <h2>Опа</h2>

        <a class="primary-btn" :href="gameUrl">
          Впереди копы
        </a>
      </div>
    </section>
  </main>
</template>

<script setup>
import { ref } from 'vue'

const memoriesSection = ref(null)

const gameUrl = 'https://zhenka-pechenka.ru'

const photos = [
  {
    src: '/10.jpeg',
    orientation: 'vertical',
    caption: 'Этой фоткой я часто любовался еще до начала отношений'
  },
  {
    src: '/11.jpg',
    orientation: 'vertical',
    caption: 'А это сейчас одна из самых любимых но тебе она не нрав('
  },
  {
    src: '/first.jpeg',
    orientation: 'horizontal',
    caption: '09.02'
  },
  {
    src: '/second.jpeg',
    orientation: 'vertical',
    caption: 'Два дня назад мне впервые написали что меня любят'
  },
  {
    src: '/6.jpeg',
    orientation: 'horizontal',
    caption: 'Три месяца и два дня как мы начали переписываться!'
  },
  {
    src: '/12.jpg',
    orientation: 'vertical',
    caption: 'Месяц'
  },
  {
    src: '/third.jpeg',
    orientation: 'horizontal',
    caption: 'Два месяца и один день как меня впервые назвали дурилкой и еще наконец-то сходили в кино'
  },
  {
    src: '/4.jpeg',
    orientation: 'horizontal',
    caption: 'Тут ты у меня просто самая красивая и самая лучшая!'
  },
  {
    src: '/5.jpeg',
    orientation: 'vertical',
    caption: 'Это просто одна из самых любимых совместных фоток!'
  },
  {
    src: '/7.jpeg',
    orientation: 'vertical',
    caption: 'Это одна из последних и также самых любимых фоток!'
  },
  {
    src: '/8.jpeg',
    orientation: 'horizontal',
    caption: 'А это моя красотка которой я любуюсь и восхищаюсь!'
  },
  {
    src: '/9.jpeg',
    orientation: 'vertical',
    caption: 'Одна из последних кайфовых фоток'
  },
  {
    src: '/13.jpg',
    orientation: 'horizontal',
    caption: 'Меня хоть потом и хуевило но это не важно ведь этот день был очень кайфовым благодаря тебе спасибо тебе большое!'
  },
  {
    src: '/14.jpeg',
    orientation: 'vertical',
    caption: 'На следующий день меня запостили в канал!'
  },
  {
    src: '/15.jpg',
    orientation: 'vertical',
    caption: 'Два дня спустя впервые назвал тебя женой'
  },
  {
    src: '/16.jpeg',
    orientation: 'vertical',
    caption: 'Отметили закрытую сессию и просто классно провели время'
  },
    {
    src: '/17.jpeg',
    orientation: 'horizontal',
    caption: 'Наша первая совместная поездка в другой город'
  },
      {
    src: '/18.jpeg',
    orientation: 'vertical',
    caption: 'Самая милая и красивая девочка!'
  },
      {
    src: '/19.jpeg',
    orientation: 'horizontal',
    caption: 'Наша первый пикник, наконец-то тебе понравилось предложение!'
  },
]

function scrollToMemories() {
  memoriesSection.value?.scrollIntoView({
    behavior: 'smooth'
  })
}
</script>

<style scoped>
* {
  box-sizing: border-box;
}

.page {
  min-height: 100vh;
  color: white;
  background:
    radial-gradient(circle at top, rgba(255, 122, 182, 0.35), transparent 35%),
    linear-gradient(135deg, #12071f, #25113a, #0f0718);
  font-family: Inter, system-ui, -apple-system, BlinkMacSystemFont, sans-serif;
  overflow-x: hidden;
}

.section {
  min-height: 100vh;
  padding: 48px 20px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.hero {
  text-align: center;
}

.glass {
  width: min(680px, 100%);
  padding: 36px 28px;
  border: 1px solid rgba(255, 255, 255, 0.16);
  border-radius: 28px;
  background: rgba(255, 255, 255, 0.08);
  box-shadow: 0 24px 80px rgba(0, 0, 0, 0.35);
  backdrop-filter: blur(18px);
  animation: fadeUp 0.9s ease both;
}

.eyebrow {
  margin: 0 0 12px;
  color: #ffb3d1;
  font-size: 14px;
  letter-spacing: 0.18em;
  text-transform: uppercase;
}

h1 {
  margin: 0;
  font-size: clamp(36px, 8vw, 72px);
  line-height: 1;
}

h2 {
  margin: 0 0 24px;
  font-size: clamp(30px, 6vw, 52px);
  text-align: center;
}

.subtitle {
  margin: 22px auto 32px;
  max-width: 520px;
  color: rgba(255, 255, 255, 0.78);
  font-size: 18px;
  line-height: 1.6;
}

.primary-btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  min-height: 52px;
  padding: 0 28px;
  border: 0;
  border-radius: 999px;
  color: white;
  background: linear-gradient(135deg, #ff4f9a, #8f5cff);
  font-size: 16px;
  font-weight: 700;
  text-decoration: none;
  cursor: pointer;
  box-shadow: 0 12px 30px rgba(255, 79, 154, 0.35);
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.primary-btn:hover {
  transform: translateY(-3px);
  box-shadow: 0 18px 40px rgba(255, 79, 154, 0.45);
}

.memories {
  flex-direction: column;
}

.photo-grid {
  width: min(980px, 100%);
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 18px;
}

.photo-card {
  padding: 10px;
  border-radius: 24px;
  background: rgba(255, 255, 255, 0.09);
  backdrop-filter: blur(14px);
  animation: fadeUp 0.8s ease both;
}

.photo-card img {
  width: 100%;
  aspect-ratio: 3 / 4;
  object-fit: cover;
  border-radius: 18px;
  display: block;
}

.photo-card--horizontal {
  grid-column: span 2;
}

.photo-card--horizontal img {
  aspect-ratio: 4 / 3;
}

.photo-card p {
  margin: 12px 6px 4px;
  color: rgba(255, 255, 255, 0.84);
  font-size: 14px;
  line-height: 1.4;
  text-align: center;
}

.final {
  text-align: center;
}

.final p {
  margin: 0 auto 28px;
  max-width: 520px;
  color: rgba(255, 255, 255, 0.8);
  font-size: 18px;
  line-height: 1.7;
}

@keyframes fadeUp {
  from {
    opacity: 0;
    transform: translateY(24px);
  }

  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@media (max-width: 800px) {
  .section {
    padding: 36px 16px;
  }

  .photo-grid {
    grid-template-columns: repeat(2, 1fr);
  }

  .glass {
    padding: 30px 22px;
  }
}

@media (max-width: 480px) {
  .photo-grid {
    grid-template-columns: 1fr;
  }

  .photo-card--horizontal {
    grid-column: span 1;
  }

  .primary-btn {
    width: 100%;
  }
}
</style>
