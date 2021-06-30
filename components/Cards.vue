<template>
    <div class="resultcontainor">
        

    
      <div class="imagesection">
        
      <img v-bind:src="`https://avatars.dicebear.com/v2/avataaars/Bret.svg?options[mood][]=happy`" alt="">
        

    </div>
    <div  class="infosection">
      <h3>Sidharth Choudhary</h3>
      <p>Email : choudharysidharth082000@gmail.com</p>
      <p>Phone : 8448605993</p>
      <p>Company : Premier Dies and Polishing </p>
      <p>Website : time.plot.com</p>
      <p>Address : B-2 477 fourth floor Glorious Apartment Lok Nayak Puram Bakkarwala New Delhi</p>
      
    
      

    </div>
   
    
    
    
  </div>

</template>
<script>
export default {
    name: 'Cards',
    props:
    {

    }
    

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
  
  
}
.resultcontainor

{
    height: 250px;
    width: 750px;
    background-color: #efefef;
    display: flex;
    justify-content: center;
    align-content: center;
    flex-direction: row;
}
.imagesection
{
    width: 30%;
    height: 100%;


}
.imagesection img
{
    object-fit: contain;
    width: 100%;
    height: 100%;
}
.infosection
{
    width: 70%;
    height: 100%;

    padding: 20px;
}
h3
{
    font-size: 1.7rem;
}

p
{
    font-size: 0.7rem;
}
</style>