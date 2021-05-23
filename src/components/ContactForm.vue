<template>
  <div>
    <form name="contact" id="form" class="send" @submit.prevent="submitForm">
      <div>
        <input name="name" type="text" placeholder="Name" v-model="name" required> 
      </div>
      <div>
        <input name="phone" type="tel" placeholder="Phone" v-model="phone" required> 
      </div>
      <div>
        <input name="email" type="email" placeholder="Email" v-model="email" required> 
      </div> 
      <div>
        <textarea name="message" cols="30" rows="10" placeholder="Message" v-model="message" required></textarea> 
      </div> 
      <div>
        <button @click="validateForm" type="submit">Send</button>
      </div>
      <div class="errors">
      <ul>
        <li v-for="error in errors" :key="error">{{error}}</li>
      </ul>
    </div>
    </form> 
  </div>
</template>

<script>
  import emailjs from 'emailjs-com'
  const nameRegex = /^[a-zA-Z]+(([',. -][a-zA-Z ])?[a-zA-Z]*)*$/ 
  const phoneRegex = /^[\+]?[(]?[0-9]{3}[)]?[-\s\.]?[0-9]{3}[-\s\.]?[0-9]{4,6}$/
  const emailRegex = /^[\w-\.]+@([\w-]+\.)+[\w-]{2,4}$/
  export default {
    data() {
      return {
        name: null, 
        phone: null, 
        email: null, 
        message: null,
        errors: []
      }
    },
    methods: {
      validateForm(e) {  
        this.errors = []
        //name 
        if(!this.name) { 
          this.errors.push('Please enter your name')
        }else if(!this.name.match(nameRegex)){
          this.errors.push('Please enter a valid name')
        }
        //phone 
        if(!this.phone) { 
          this.errors.push('Please enter your phone number')
        }else if(!this.phone.match(phoneRegex)){
          this.errors.push('Please enter a valid phone number')
        }
        //email 
        if(!this.email) { 
          this.errors.push('Please enter an email address')
        }else if(!this.email.match(emailRegex)) {
          this.errors.push('Please enter a valid email address')
        }
        //message 
        if(!this.message) {
          this.errors.push('Please add a message')
        } 

        if(this.errors) {
          e.preventDefault()
        }
      }, 
     submitForm(e) {   
       console.log('submit form')    
        emailjs.sendForm('service_tjyo04u', 'template_zmypudc', e.target, 'user_cXVYnoDAnK7U0qBsC9viA') 
        //remove text and add the loader  
        .then((result) => {
            console.log('SUCCESS!', result.status, result.text) 
            //add sending class   
            document.getElementById()
            //remove loader 
        }, (error) => {
            console.log('FAILED...', error)  
        }) 
      }
    }
  }
</script>

<style lang="scss" scoped>
@import '../assets/styles/colors';

$noSelect: #cccccc;
$select: #000;

form { 
  width: 50%; 
  margin: 0 auto;
} 

input { 
  width: 100%; 
  padding: .7em; 
  margin-bottom: 1em; 
  border: 3px solid $noSelect; 
  outline: none; 
  transition: border .1s ease-in-out;
  &:focus {
    border: 3px solid $select;
  }
} 

textarea { 
  width: 100%; 
  padding: .7em;
  resize: none; 
  font-family: inherit;
  border: 3px solid $noSelect; 
  outline: none; 
  transition: border .1s ease-in-out;
  &:focus {
    border: 3px solid $select;
  }
} 

button { 
  float: right; 
  padding: .7em 1.5em; 
  margin: 1em 0; 
  border: solid 3px $noSelect; 
  background: none;  
  transition: .15s ease-in-out;
  &:hover {
   border: solid 3px $select;  
   background: $select; 
   color: #fff;
  }
} 

.errors { 
  color: $red; 
  margin: 1em; 
  ul { 
    padding: 0; 
    margin: 0;
  } 
  li { 
    list-style-type: none; 
    margin: 0; 
    padding: 0;
  }
} 

.show { 
  display: block;
} 

.hide {
  display: none;
} 

.send { 
  animation: sendForm 2s ease-out;
} 

@keyframes sendForm { 
  0% {
    transform: scale(0.8);
  } 
  50% {
    transform: translateX(100%); 
  }  
  55% { 
    opacity: 0; 
    transform: translateX(0);
  }  
  70% {
    opacity: .5; 
  }
  100% {
    opacity: 1;
  }
} 

</style>