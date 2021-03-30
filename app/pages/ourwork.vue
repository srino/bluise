<template>
  <section class="blog">
    <div class="py-8 md:py-16 text-center">
      <h1 class="text-lg md:text-xl lg:text-4xl xl:text-6xl">Services</h1>
      <h2 class="text-base md:text-lg lg:text-xl xl:text-2xl">
        Slow-carb messenger bag mlkshk fingerstache four dollar toast.
      </h2>
    </div>
<div class="flex flex-row ...">

                <div class="flex flex-col-4...">
              <!--portfolioModal1-->
			        <a href="#portfolioModal" class="portfolio-link" data-toggle="modal">

                        <div class="portfolio-hover">

                            <div class="portfolio-hover-content">
                                <i class="fa fa-plus fa-3x"></i>
                            </div>

                        </div>
						 <span class="portfolio-caption">
                        <h3 class="text-primary">Marketplace for US Real Estate Investments</h3>
                  <p class="text-tertiary">Designed and developed a financial marketplace and what if analysis for high net worth individuals investing in Real estate.</p>
						<img src="../img/portfolio/3.jpg" class="img-responsive img-float" alt="">
                    </span>


                    </a>
            </div>
                     <div class="flex flex-col-4...">
              <!--portfolioModal1-->
			        <a href="#portfolioModal" class="portfolio-link" data-toggle="modal">

                        <div class="portfolio-hover">

                            <div class="portfolio-hover-content">
                                <i class="fa fa-plus fa-3x"></i>
                            </div>

                        </div>
						 <span class="portfolio-caption">
                        <h3 class="text-primary">Marketplace for US Real Estate Investments</h3>
                  <p class="text-tertiary">Designed and developed a financial marketplace and what if analysis for high net worth individuals investing in Real estate.</p>
						<img src="../img/portfolio/3.jpg" class="img-responsive img-float" alt="">
                    </span>


                    </a>


            </div>
                     <div class="flex flex-col-4...">
              <!--portfolioModal1-->
			        <a href="#portfolioModal" class="portfolio-link" data-toggle="modal">

                        <div class="portfolio-hover">

                            <div class="portfolio-hover-content">
                                <i class="fa fa-plus fa-3x"></i>
                            </div>

                        </div>
						 <span class="portfolio-caption">
                        <h3 class="text-primary">Marketplace for US Real Estate Investments</h3>
                  <p class="text-tertiary">Designed and developed a financial marketplace and what if analysis for high net worth individuals investing in Real estate.</p>
						<img src="../img/portfolio/3.jpg" class="img-responsive img-float" alt="">
                    </span>


                    </a>


            </div>

</div>
    <Pagination v-if="totalPages > 1" :current-page="currentPage" :total-pages="totalPages" />
  </section>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator';
import { MetaInfo } from 'vue-meta';

const Pagination = () => import('@/components/commons/pagination.vue');

@Component({
  components: {
    Pagination,
  },

  head(): MetaInfo {
    return {
      title: 'Services',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Blog index',
        },
      ],
    };
  },
})
export default class BlogIndex extends Vue {
  currentPage!: number;

  totalPages!: number;

  posts: Post[] = [];

  async asyncData({ params, store }) {
    const page: number = params.page ? parseInt(params.page, 10) : 1;
    const { perPage }: { perPage: number } = store.state;
    const range = page * perPage;

    const posts = store.state.posts.filter((post, index) => {
      const indexPage = index + 1;
      return range - perPage < indexPage && indexPage <= range;
    });

    return {
      currentPage: page,
      totalPages: Math.ceil(store.state.posts.length / perPage),
      posts: posts || [],
    };
  }
}
</script>

<style lang="scss">
// @import url("./css/bootstrap.min.css");
//  @import '../css/bootsrap.min.css';
//  @import '../css/jquery.fancybox.css';
//  @import '../css/style.css';
//  @import '../css/style1.css';
.blog {
  .post {
    @apply shadow-md;
    transition: all 0.2s cubic-bezier(0.64, 0, 0.35, 1);
    &:hover {
      @apply shadow-xl;
    }
  }
}  
</style>
