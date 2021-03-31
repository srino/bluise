<template>
  <section class="blog">
    <div style="color: white; background: -webkit-linear-gradient(-45deg, rgba(22,23,75,1) 0%, rgba(162,81,92,1) 100%);" class="py-8 md:py-16 text-center">
      <h2 style="font-size:34px" class="text-lg md:text-xl lg:text-4xl xl:text-6xl">Get In Touch</h2>
      <h3 class="text-base md:text-lg lg:text-xl xl:text-2xl">
       For a free 1x1 meeting (or Skype) to explore how we could be of help <br> or Join for one of our free Innovation workshops!
      </h3>
    </div>
    <div>
         <section class="home">
    <div class="py-24 md:py-36 mx-auto flex flex-wrap flex-col-2 md:flex-row items-center">
      <div class="flex flex-col w-full xl:w-3/5 justify-center lg:items-start overflow-x-hidden">
        <div class="home__welcome markdown" />

<div class="container">
       <form class="contact-form" @submit.prevent="sendEmail">
    <label>Name</label>
    <input type="text" name="name">
    <label>Email</label>
    <input type="email" name="email">
    <label>Message</label>
    <textarea name="message"></textarea>
    <input type="submit" value="Send">
  </form>
    </div>
      </div>
      <div class="flex flex-col w-full xl:w-2/5">
        <img
          alt="Hero"
          class="rounded shadow-xl"
          src="https://source.unsplash.com/random/720x400"
        />
      </div>
    </div>
  </section>
    </div>
    <Pagination v-if="totalPages > 1" :current-page="currentPage" :total-pages="totalPages" />
  </section>
</template>

<script>

import emailjs from 'emailjs-com';

export default {
  name: 'ContactUs',
  data() {
    return {
      name: '',
      email: '',
      message: ''
    }
  },
  methods: {
    sendEmail: (e) => {
      emailjs.sendForm('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', e.target, 'YOUR_USER_ID', {
          name: this.name,
          email: this.email,
          message: this.message
        })
        .then((result) => {
            console.log('SUCCESS!', result.status, result.text);
        }, (error) => {
            console.log('FAILED...', error);
        });
    }
  }
}
</script>

<style lang="scss">
 //@import url("../css/bootstrap.min.css");
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
* {box-sizing: border-box;}
.container {
  display: block;
  margin:auto;
  text-align: center;
  border-radius: 5px;
  background-color: #f2f2f2;
  padding: 20px;
  //width: 50%;
}

label {
  float: left;
}

input[type=text], [type=email], textarea {
  width: 100%;
  padding: 12px;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
  margin-top: 6px;
  margin-bottom: 16px;
  resize: vertical;
}

input[type=submit] {
  background-color: #4CAF50;
  color: white;
  padding: 12px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

input[type=submit]:hover {
  background-color: #45a049;
}

</style>
