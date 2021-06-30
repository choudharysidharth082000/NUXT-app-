<template>
<div class="containor">
    
    <div class="resultcontainor">
        <div class="imagecontainor">
            <img v-bind:src="`https://avatars.dicebear.com/v2/avataaars/${this.list.username}.svg?options[mood][]=happy`" alt="">

        </div>
        <div class="infocontainor">
            <h4>{{this.list.username}}</h4>
            <fa icon="envelope" /> 
            <p> {{this.list.email}}</p>
            <p>{{this.list.phone}}</p>
            <p>{{this.list.website}}</p>
            

        </div>

    </div>



    
</div>
    
</template>
<script>
export default {
    data()
    {
        return {
            list : { }, 
        }
    },
    async created()
    {
        const res = await fetch(`https://jsonplaceholder.typicode.com/users/${this.$route.params.id}`);
        const data = await res.json();

        console.log(data);
        if(res.status != 200){
        alert('Failed to get what you want, got status: ' + res.status);
        return null;
        }
        this.list = data;
        


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
    transition: 0.5s ease;
}
.containor{
    width: 100%;
    height: 100vh;
    background-color: white;
    display: flex;
    justify-content: center;
    align-items: center;
}
.resultcontainor
{
    height: 400px;
    width: 300px;
    display: flex;
flex-direction: column;
    background-color: #efefef;
    border: 0.2px solid rgba(0, 0, 0, 0.034);
    cursor: 
    pointer;
}
.resultcontainor:hover .infocontainor
{
      background-color: #f7f3f3;

      

}

.resultcontainor:hover
{
    background-color: white;
    
}
h4 
{
    margin-bottom: 20px;
    font-size: 1.6rem;
}
.imagecontainor
{
    height: 200px;
    width: 100%;

}
.imagecontainor img 
{
    height : 200px;
    width: 100%;

    object-fit: contain;
}
.infocontainor
{
    padding: 20px;
    height: 200px;
    width: 100%;
    background-color: white;
    
}

 </style>