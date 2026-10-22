<script setup>
const dishes = [
  {
    name: '春笋焖咸肉',
    description: '春笋 · 金华火腿 · 慢火煨',
    price: '¥ 48',
    tag: '当季推荐',
    image: 'https://images.unsplash.com/photo-1512621776951-a57141f2eefd?auto=format&fit=crop&w=1000&q=85',
    alt: '新鲜蔬菜与时令食材',
    featured: true,
  },
  {
    name: '酒酿小圆子',
    description: '手搓糯米 · 桂花酒酿',
    price: '¥ 28',
    tag: '每日鲜做',
    image: 'https://images.unsplash.com/photo-1546069901-ba9599a7e63c?auto=format&fit=crop&w=1000&q=85',
    alt: '精心摆盘的时蔬菜品',
  },
  {
    name: '外婆红烧肉',
    description: '土猪五花 · 冰糖 · 三小时',
    price: '¥ 88',
    tag: '人气招牌',
    image: 'https://images.unsplash.com/photo-1547592180-85f173990554?auto=format&fit=crop&w=1000&q=85',
    alt: '适合分享的江南家常菜',
  },
]
</script>

<template>
  <section class="menu-section" id="menu">
    <div class="section-wrap">
      <div class="section-heading">
        <div><div class="intro-kicker"><span class="section-number">02</span><span>ON THE TABLE</span></div><h2>最近，<em>吃点好的。</em></h2></div>
        <a class="underlined-link" href="#visit">查看完整菜单 <span>↗</span></a>
      </div>
      <div class="menu-grid">
        <article v-for="dish in dishes" :key="dish.name" class="dish-card" :class="{ 'dish-featured': dish.featured }">
          <div class="dish-image">
            <img :src="dish.image" :alt="dish.alt" />
            <span class="dish-tag" :class="{ 'tag-light': !dish.featured }">{{ dish.tag }}</span>
          </div>
          <div class="dish-info">
            <div><h3>{{ dish.name }}</h3><p>{{ dish.description }}</p></div>
            <span class="dish-price">{{ dish.price }}</span>
          </div>
        </article>
      </div>
      <p class="menu-footnote">菜单随时令更替，具体菜品以当日供应为准。</p>
    </div>
  </section>
</template>

