<template>
    <div >
        
         <h2>Login</h2>
         <p>
           Username
         <input type="username" v-model="text" class="rounded border border-link">
         </p>
         <p>
           Email Id
         <input type="email ID" v-model="email" class="rounded border border-link">
         </p>
         <p>
           Password
         <input type="password" v-model="password" class="rounded border border-link" />
         </p>

         <button type="button" v-on:click="buttonClick">Sign In</button>

      
         <h2>Sign In</h2>
         <p>
           Email Id
         <input type="email ID" v-model="email" class="rounded border border-link">
         </p>
         <p>
           password
         <input type="password" v-model="password" class="rounded border border-link" />
         </p>
         <p>
           
         <a href="#">Forgot your password?</a>
         </p>
    
         <button type="button" v-on:click="buttonClick">Sign Up</button>
    
    
    </div>
</template>

<script>
export default {
  data: () =>{
    return{
      signUp: false
    }
  },

 methods:{
        SignIn() {
          if(this.input.email!= "joby23@gmail.com" && this.input.password != "110727" ) {     
            if(this.input.email == this.$parent.mockAccount.email && this.input.password == this.$parent.mockAccount.password) {
              this.$emit("authenticated", true);    
              this.$router.replace({ name: "secure"});
            } else {
              console.log("The email and / or password is incorrect");
            }
         } else {
           console.log("A email and password must be present");
         }
           this.$router.push({name:'Sign In'})
       },
       buttonClick: function(){ 
         alert('Hey! I am here');

       }       
   }
}


</script>

<style scoped>
h2 {
  text-align: center;
}

p{
  text-align: center;
}

button{
  width: 7%;
  margin-left: 50%;
  margin-right: 50%
}

h3 {
  margin: 40px 0 0;
}
a {
  color: #42b983;
}

button{
  background-color: whitesmoke;

}

</style>
