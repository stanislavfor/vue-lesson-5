<template>
  <div class="wrapper">
    <header class="header" id="blog-section">
      <div class="container">
        <div class="header__inner">
          <picture>
            <img class="header__logo" src="@/assets/images/logo.png" alt="">
          </picture>
          <nav class="header__nav">
            <ul class="header__nav-list header__list">
              <li class="header__list-item">
                <a class="header__list-link" href="projects.html">Проекты</a>
              </li>
              <li class="header__list-item">
                <a class="header__list-link" href="blog.html">Блог</a>
              </li>
              <li class="header__list-item">
                <a class="header__list-link" href="index.html#main-section">Домой</a>
              </li>
              <li class="header__list-item">
                <a class="header__list-link" href="#contact-section">Контакты</a>
              </li>
            </ul>
            <div class="icon-menu">
              <span></span>
              <span></span>
              <span></span>
            </div>
          </nav>
          <div class="header__plate"></div>
        </div>
      </div>
    </header>
    <main class="main">
      <section class="main-blog-details-section"></section>
      <section class="main-blog-details">
        <div class="blog-details">
          <blog-posts :posts="filteredPosts"></blog-posts>
        </div>
        <div class="sidebar">
          <h2>Тэги</h2>
          <button class="smooth-button" v-for="tag in tags" :key="tag" @click="filterPosts(tag)">{{ tag }}</button>
          <button class="smooth-button" @click="filterPosts('')">Все Тэги</button>
        </div>
      </section>
    </main>
    <footer class="footer" id="contact-section">
      <div class="container">
        <div class="footer__inner">
          <div class="footer__logo">
            <picture>
              <img class="footer__logo-img" src="@/assets/images/logo.png" alt="">
            </picture>
            <br>
            <br>
            <br>
            <p class="footer__logo-text"></p>
            <div class="header__list-item">
              <a class="header__list-link" href="index.html#main-section">Домой</a>
            </div>
            <br>
            <div class="header__list-item">
              <a class="header__list-link" href="projects.html">Проекты</a>
            </div>
            <br>
            <div class="header__list-item">
              <a class="header__list-link" href="blog.html">Блог</a>
            </div>
            <br>
            <div class="header__list-item">
              <a class="header__list-link" href="index.html#achievements">Наши успехи</a>
            </div>
          </div>
          <ul class="footer__social">
            <li class="footer__social-item">
              <a class="footer__social-link" href="#">
                <picture>
                  <img class="footer__social-link-img" src="@/assets/images/tw.png" alt="">
                </picture>
              </a>
            </li>
            <li class="footer__social-item">
              <a class="footer__social-link" href="#">
                <picture>
                  <img class="footer__social-link-img" src="@/assets/images/li.png" alt="">
                </picture>
              </a>
            </li>
            <li class="footer__social-item">
              <a class="footer__social-link" href="#">
                <picture>
                  <img class="footer__social-link-img" src="@/assets/images/tw.png" alt="">
                </picture>
              </a>
            </li>
            <li class="footer__social-item">
              <a class="footer__social-link" href="#">
                <picture>
                  <img class="footer__social-link-img" src="@/assets/images/li.png" alt="">
                </picture>
              </a>
            </li>
            <li class="footer__social-item">
              <a class="footer__social-link" href="#">
                <picture>
                  <img class="footer__social-link-img" src="@/assets/images/tw.png" alt="">
                </picture>
              </a>
            </li>
          </ul>
          <div class="footer__contacts">
            <h4 class="footer__contacts-title">Контакты</h4>
            <br>
            <br>
            <p class="footer__contacts-address">55 East Birchwood Ave. Brooklyn, New York 11201</p>
            <a class="footer__contacts-email" href="mailto:contact@interno.com">contact@interno.com</a>
            <a href="tel:1234567890" class="footer__contacs-phone">(123) 456 - 7890</a>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'BlogDetailsComponent',
  data() {
    return {
      selectedTag: '',
      posts: [
        {
          title: 'Создадим лучший макет перепланировки',
          date: '26 Декабря, 2024',
          tag: 'Кухня',
          content: [
            { type: 'img', src: require('@/assets/images/details-1.png') },
            { type: 'text', text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque nisl eros, pulvinar facilisis justo mollis, auctor consequat urna. Morbi a bibendum metus. Donec scelerisque sollicitudin enim eu venenatis. Duis tincidunt laoreet ex, in pretium orci vestibulum eget. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Aliquam volutpat aliquam luctus. Pellentesque vitae aliquam nunc. Sed laoreet metus nec purus luctus, quis luctus lorem consequat. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia curae; Fusce vel interdum elit, at congue lorem. Vestibulum pellentesque, orci in gravida fermentum, purus libero varius urna, ut vehicula velit nulla a nisl. Sed aliquet, nisi eget sagittis tincidunt, nisi elit consectetur nunc, ut congue nisl nisi vitae nunc. Proin consectetur, nisi id ullamcorper varius, nisi nisi aliquam nisi, eget aliquam nisi nisi eget nisi.' },
            { type: 'img', src: require('@/assets/images/details-2.png') },
            { type: 'text', text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque nisl eros, pulvinar facilisis justo mollis, auctor consequat urna. Morbi a bibendum metus. Donec scelerisque sollicitudin enim eu venenatis. Duis tincidunt laoreet ex, in pretium orci vestibulum eget. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Aliquam volutpat aliquam luctus. Pellentesque vitae aliquam nunc. Sed laoreet metus nec purus luctus, quis luctus lorem consequat. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia curae; Fusce vel interdum elit, at congue lorem. Vestibulum pellentesque, orci in gravida fermentum, purus libero varius urna, ut vehicula velit nulla a nisl. Sed aliquet, nisi eget sagittis tincidunt, nisi elit consectetur nunc, ut congue nisl nisi vitae nunc. Proin consectetur, nisi id ullamcorper varius, nisi nisi aliquam nisi, eget aliquam nisi nisi eget nisi.' }
          ]
        },
        {
          title: 'Design sprints are great',
          date: '22 Декабря, 2024',
          tag: 'Дизайн',
          content: [
            { type: 'img', src: require('@/assets/images/details-3.png') },
            { type: 'text', text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque nisl eros, pulvinar facilisis justo mollis, auctor consequat urna. Morbi a bibendum metus. Donec scelerisque sollicitudin enim eu venenatis. Duis tincidunt laoreet ex, in pretium orci vestibulum eget. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Aliquam volutpat aliquam luctus. Pellentesque vitae aliquam nunc. Sed laoreet metus nec purus luctus, quis luctus lorem consequat. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia curae; Fusce vel interdum elit, at congue lorem. Vestibulum pellentesque, orci in gravida fermentum, purus libero varius urna, ut vehicula velit nulla a nisl. Sed aliquet, nisi eget sagittis tincidunt, nisi elit consectetur nunc, ut congue nisl nisi vitae nunc. Proin consectetur, nisi id ullamcorper varius, nisi nisi aliquam nisi, eget aliquam nisi nisi eget nisi.' },
            { type: 'img', src: require('@/assets/images/details-4.png') },
            { type: 'text', text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque nisl eros, pulvinar facilisis justo mollis, auctor consequat urna. Morbi a bibendum metus. Donec scelerisque sollicitudin enim eu venenatis. Duis tincidunt laoreet ex, in pretium vestibulum eget. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Aliquam volutpat aliquam luctus. Pellentesque vitae aliquam nunc. Sed laoreet metus nec purus luctus, quis luctus lorem consequat. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia curae.' }
          ]
        },
        {
          title: 'Лучшие интерьерные идеи по низкой цене',
          date: '22 Декабря, 2024',
          tag: 'Здания',
          content: [
            { type: 'img', src: require('@/assets/images/details-5.png') },
            { type: 'text', text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque nisl eros, pulvinar facilisis justo mollis, auctor consequat urna. Morbi a bibendum metus. Donec scelerisque sollicitudin enim eu venenatis. Duis tincidunt laoreet ex, in pretium vestibulum eget. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Aliquam volutpat aliquam luctus. Pellentesque vitae aliquam nunc. Sed laoreet metus nec purus luctus, quis luctus lorem consequat. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia curae.' },
            { type: 'img', src: require('@/assets/images/details-6.png') },
            { type: 'text', text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque nisl eros, pulvinar facilisis justo mollis, auctor consequat urna. Morbi a bibendum metus. Donec scelerisque sollicitudin enim eu venenatis. Duis tincidunt laoreet ex, in pretium vestibulum eget. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Aliquam volutpat aliquam luctus. Pellentesque vitae aliquam nunc. Sed laoreet metus nec purus luctus, quis luctus lorem consequat. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia curae.' }
          ]
        },
        {
          title: 'Спальные интерьеры и возможности дизайнеров',
          date: '9 Декабря, 2024',
          tag: 'Спальня',
          content: [
            { type: 'img', src: require('@/assets/images/details-7.png') },
            { type: 'text', text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque nisl eros, pulvinar facilisis justo mollis, auctor consequat urna. Morbi a bibendum metus. Donec scelerisque sollicitudin enim eu venenatis. Duis tincidunt laoreet ex, in pretium vestibulum eget. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Aliquam volutpat aliquam luctus. Pellentesque vitae aliquam nunc. Sed laoreet metus nec purus luctus, quis luctus lorem consequat. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia curae.' }
          ]
        },
        {
          title: 'Лучшие интерьерные решения для офисов',
          date: '25 Декабря, 2024',
          tag: 'Архитектура',
          content: [
            { type: 'img', src: require('@/assets/images/details-8.png') },
            { type: 'text', text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque nisl eros, pulvinar facilisis justo mollis, auctor consequat urna. Morbi a bibendum metus. Donec scelerisque sollicitudin enim eu venenatis. Duis tincidunt laoreet ex, in pretium vestibulum eget. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Aliquam volutpat aliquam luctus. Pellentesque vitae aliquam nunc. Sed laoreet metus nec purus luctus, quis luctus lorem consequat. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia curae.' }
          ]
        },
        {
          title: 'Жизнь без дизайнерских решений',
          date: '10 Декабря, 2024',
          tag: 'Архитектура',
          content: [
            { type: 'img', src: require('@/assets/images/details-9.png') },
            { type: 'text', text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque nisl eros, pulvinar facilisis justo mollis, auctor consequat urna. Morbi a bibendum metus. Donec scelerisque sollicitudin enim eu venenatis. Duis tincidunt laoreet ex, in pretium vestibulum eget. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Aliquam volutpat aliquam luctus. Pellentesque vitae aliquam nunc. Sed laoreet metus nec purus luctus, quis luctus lorem consequat. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia curae.' }
          ]
        },
        {
          title: 'Квартиры и офисы - делаем лучше',
          date: '05 Декабря, 2024',
          tag: 'Планировка',
          content: [
            { type: 'img', src: require('@/assets/images/details-10.png') },
            { type: 'text', text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque nisl eros, pulvinar facilisis justo mollis, auctor consequat urna. Morbi a bibendum metus. Donec scelerisque sollicitudin enim eu venenatis. Duis tincidunt laoreet ex, in pretium vestibulum eget. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Aliquam volutpat aliquam luctus. Pellentesque vitae aliquam nunc. Sed laoreet metus nec purus luctus, quis luctus lorem consequat. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia curae; Fusce vel interdum elit, at congue lorem. Vestibulum pellentesque, orci in gravida fermentum, purus libero varius urna, ut vehicula velit nulla a nisl. Sed aliquet, nisi eget sagittis tincidunt, nisi elit consectetur nunc, ut congue nisl nisi vitae nunc. Proin consectetur, nisi id ullamcorper varius, nisi nisi aliquam nisi, eget aliquam nisi nisi eget nisi.' },
            { type: 'img', src: require('@/assets/images/details-11.png') }
          ]
        }
      ],
      tags: ['Кухня', 'Спальня', 'Здания', 'Архитектура', 'Планировка', 'Дизайн']
    };
  },
  computed: {
    filteredPosts() {
      if (this.selectedTag) {
        return this.posts.filter(post => post.tag === this.selectedTag);
      }
      return this.posts;
    }
  },
  methods: {
    filterPosts(tag) {
      this.selectedTag = tag;
    }
  },
  components: {
    'blog-posts': {
      props: ['posts'],
      template: `
        <div>
          <div v-for="post in posts" :key="post.title">
            <h2>{{ post.title }}</h2>
            <p class="blog-details__article-date">{{ post.date }}</p>
            <p class="blog-details__article-tags">{{ post.tag }}</p>
            <div v-for="(content, index) in post.content" :key="index">
              <picture v-if="content.type === 'img'">
                <img class="blog-details__article-img" :src="content.src" alt="">
              </picture>
              <p v-if="content.type === 'text'" class="blog-details__article-text">{{ content.text }}</p>
            </div>
          </div>
        </div>
      `
    }
  }
};
</script>

<style scoped>
/* Add "scoped" attribute to limit CSS to this component only */
@import '@/assets/css/main.css';
@import '@/assets/css/media.css';
@import '@/assets/css/normalise.css';
</style>
