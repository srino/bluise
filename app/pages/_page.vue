<template>
<div>
  <section class="page" :class="page.slug">
    <div style="color: white; background: -webkit-linear-gradient(-45deg, rgba(22,23,75,1) 0%, rgba(162,81,92,1) 100%);" class="py-8 md:py-16 text-center">
      <h2 style="font-size:34px" class="text-lg md:text-xl lg:text-4xl xl:text-6xl">{{ page.title }}</h2>
      <h3 class="text-base md:text-lg lg:text-xl xl:text-2xl">
        Slow-carb messenger bag mlkshk fingerstache four dollar toast.
      </h3>
    </div>
       <div style="text-align: center;margin-top: 30px;" class="grid grid-cols-3 gap-4">
         <div>
  			   <div class="icon">
              <img
              :alt="page.title"
              class="w-full"
              :src="page.avatar || 'https://source.unsplash.com/random/640x340'"
            />
           </div>
              <strong>100+</strong>
              <p>Years of collective Experience</p>
         </div>
         <div>
  			   <div class="icon">
              <img style="height:67px" src="../img/number-img1.png">
           </div>
              <strong>100+</strong>
              <p>Years of collective Experience</p>
      </div>
         <div>
  			   <div class="icon">
              <img style="height:67px" src="../img/number-img1.png">
           </div>
              <strong>100+</strong>
              <p>Years of collective Experience</p>
      </div>
     </div>
     <div>
         <div  v-html="$md.render(page.content)" style="margin-left: 74px;
    margin-right: 51px;" class="page__content markdown pt-4 md:pt-6 md:pb-24" />
     </div>
  </section>   
  <section style="margin-top: -74px;" class="page">
    <div class="py-8 md:py-16 text-center">
      <h3 style="font-size:34px">Testimonial</h3>
    </div>
       <div style="text-align: center;" class="grid grid-cols-2 gap-4">
         <div>
			<div class="thumbnail adjust1">
				<div class="caption">
						<div class="quote"><i class="fa fa-quote-left fa-2x"></i></div>
						<p>Just want to let you know that the dashboards and UI presentation was a huge success at the user conference!! They loved it, I've had so many people come up to me and express their excitement, So thanks for all your hard work and efforts putting it together. </p>
				<blockquote class="adjust2">
					<p>Micki Nguyen</p> <small><cite title="Source Title">Dallas based Financial Product</cite></small>
				</blockquote>
					</div>
				</div>
         </div>
         <div>
			<div class="thumbnail adjust1">
				<div class="caption">
						<div class="quote"><i class="fa fa-quote-left fa-2x"></i></div>
						<p>Just want to let you know that the dashboards and UI presentation was a huge success at the user conference!! They loved it, I've had so many people come up to me and express their excitement, So thanks for all your hard work and efforts putting it together.
 </p>
				<blockquote class="adjust2">
					<p>Micki Nguyen</p> <small><cite title="Source Title">Dallas based Financial Product</cite></small>
				</blockquote>
					</div>
				</div>
      </div>
     </div>
  </section>
  
  </div>
  <!-- <section class="page" :class="page.slug">
    <h1 class="page__title text-lg md:text-xl lg:text-4xl xl:text-6xl text-center py-8 md:py-16">
      {{ page.title }}
    </h1>

    <div v-html="$md.render(page.content)" class="page__content markdown pt-4 md:pt-6 md:pb-24" />
  </section> -->

</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator';
import { MetaInfo } from 'vue-meta';

@Component({
  // Called to know which transition to apply
  transition(to, from) {
    if (!from) {
      return 'slide-left';
    }

    return 'slide-right';
  },

  head(): MetaInfo {
    return {
      title: this.page.title,
      avatar:this.page.avatar,
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: this.page.seoDescription,
        },
        {
          hid: 'og:image',
          name: 'og:image',
          content: this.page.seoMetaImage,
        },
      ],
    };
  },
})
export default class PageTemplate extends Vue {
  page!: Page;

  async asyncData({ params, payload }): Promise<{ page: Page }> {
    if (payload) {
      return { page: payload };
    }

    try {
      const page = require(`@/content/pages/${params.page}.json`);

      return {
        page,
      };
    } catch (e) {
      throw new Error('Not found');
    }
  }
}
</script>
<style scoped>
.adjust1{
float:left;
width:100%;
}
.adjust1 blockquote{
	padding: 7px 26px;
}
.adjust1 p{
	font-size: 15px;
	margin:0 0 10px 0;
	
}
.icon
{
    padding-bottom: 10px;
    text-align: -webkit-center;
    margin: 10px 0;
}
.inumbers-bg-border {
    border-right: #cbcbcb 1px dashed;
}
.caption {
  padding-top: 8px;
  padding-bottom: 8px;
  margin-left: 30px;
  margin-right: 30px;  text-align: left;
}
.quote {
    color: rgba(0,0,0,.1);
    text-align: left;
    margin-bottom: 16px;
}
.blockquote {
    border: 1px solid #999;

    page-break-inside: avoid;
  }
  .adjust2{
margin:0;
}
</style>
