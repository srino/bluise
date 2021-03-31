<template>
  <section>
    <div style="color: white; background: -webkit-linear-gradient(-45deg, rgba(22,23,75,1) 0%, rgba(162,81,92,1) 100%);" class="py-8 md:py-16 text-center">
      <h2 style="font-size:34px" class="text-lg md:text-xl lg:text-4xl xl:text-6xl">A sampling of our work</h2>
      <h3 class="text-base md:text-lg lg:text-xl xl:text-2xl">
        Slow-carb messenger bag mlkshk fingerstache four dollar toast.
      </h3>
    </div>
    <div style="margin-top:14px" class="h-64 grid grid-rows grid-flow-col gap-3">
    <div>
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
         <div>
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
         <div>
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
         <div style="margin-top: 88px;" class="h-64 grid grid-rows grid-flow-col gap-3">
              <div>
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
              <div>
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
              <div>
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
.text-tertiary{
	color:#666;
font-size: 18px;
    line-height: 28px;
    text-align: center;
	font-weight:300;
	width: 90%;
	margin: 0 auto;
	padding-bottom: 40px;
}
p.text-tertiary{
	font-size: 14px;
	line-height:1.8;
}
.text-primary {
  color: #337ab7;
}
a.text-primary:hover,
a.text-primary:focus {
  color: #286090;
}
.portfolio-caption {
    max-width: 100%;
    margin: 0 auto;
    text-align: center;
    padding: 15px;
	display:block;
	min-height:300px;
	z-index:200;
}
.img-float{
	margin: auto;
	right:0;
	bottom:0;
	z-index:-1 !important;
}

</style>
