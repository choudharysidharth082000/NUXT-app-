<template>
<div class="containor">
  
  

  <div v-for="items in list" :key ="items.id" class="resultcontainor">

    
      <div class="imagesection">
        
      <img v-bind:src="`https://avatars.dicebear.com/v2/avataaars/${items.username}.svg?options[mood][]=happy`" alt="">
        

    </div>
    <div  class="infosection">
      <h3>{{items.username}}</h3>
      <p>Email : {{items.email}}</p>
      <p>Phone : {{items.phone}}</p>
      <p>Company : {{items.company.name}} </p>
      <p>Website : {{items.website}}</p>
      <p>Address : {{items.address.suite}} {{items.address.street}} {{items.address.city}}</p>
      <button class="btn btn-success">
        <a :href="items.id">View Profile</a>
      </button>
      

    </div>
   
    
    
    
  </div>

</div>

  
</template>

<script>
import axios from "axios";
export default {
  head()
  {
    return{
      title : 'Users List',
      meta : [
        {
          hid: "description",
          name: "description",
          content: "Users Data List"
        }
      ]
    }
  },
  data()
  {
    return{
      list : undefined

    }
  },
  async created()
  {
    const res = await fetch('https://jsonplaceholder.typicode.com/users');
    const data = await res.json();
    if(res.status != 200){
    alert('Failed to get what you want, got status: ' + res.status);
    return null;
 }
    console.log(data);
    this.list = data;
  }
  // async created()
  // {
  //   const config = {
  //     headers:{
  //       'Accept': 'users'
  //     }
  //   };
  //   try
  //   {
  //     const res = await axios.get('https://jsonplaceholder.typicode.com', config);
  //     console.log(res.data);
      

  //   } catch(err)
  //   {
  //     console.log(err);

  //   }


    



  // }
}

 
</script>

<style>
*
{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  transition: all 0.9s ease in;
  
  
}a
{
  color: white;
  text-decoration: white;
  list-style: none;

}
a:hover
{
  color: white;
  text-decoration: white;
}
button
{
  margin: 10px;
}
.containor 
{
  height: 100%;

  width: 100%;
  background-color: #efefef;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  }
.resultcontainor
{
  margin: 20px;
  width: 70%;
  height: 45%;
  background-color: white;
  display: flex;
  flex-direction: row;
  cursor: pointer;
  
  
}
.resultcontainor:hover
{
  background-color: rgba(255, 255, 255, 0.753);
}
h3
{
  color: black;
  

}
p
{
  font-size: 11px;
}
.infosection
{
  display: flex;
  justify-content: center;
  padding-left: 20px;
  padding-top: 10px;
  
  flex-direction: column;
  
  
  
}

.imagesection 
{
  height: 100%;
  width: 20%;
  
  object-fit: contain;
}
.imagesection img
{
  height: 100%;
  width: 90%;
  
  object-fit: cover;
}
.buttons 
{
  
  width: 20%;
  height: 200px;
  margin-left: 80px;
  display: flex;
  justify-content: flex-end;

  align-items: flex-end;
}
@media screen and (max-width: 360px) {
  *
  {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: Verdana, Geneva, Tahoma, sans-serif;

  }
  h3
  {
    font-size: 1.2rem;


  }
  p
  {
    font-size: 0.5rem;
  }
  .resultcontainor
  {
    padding: 10px;
  }
  .infosection
  {
    padding: 10px;
  }
  
}
</style>