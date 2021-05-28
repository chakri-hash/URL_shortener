<script>
import Navbar from "$lib/components/Navbar.svelte";
import axios from 'axios'
let url = '';
let shorturl = 'http://trim-url.vercel.app/'
async function sendReq () {
    const response = await axios.post('https://url-shortener-manitej66.azurewebsites.net/api/shorten?code=USDsXCIeE0UKKJTi9pMWHTyQOFWIu2zAOmWmzcAW7PorrkqDeOcnHQ==',{
    "url": url})
    shorturl = shorturl + response.data.shortUrl

}

</script>
<Navbar/>

<div class="main">
<img src="https://www.pngrepo.com/png/149836/512/scissors.png" alt="sessiors image">
<div class="inmain"><h1>URL shortener</h1></div>
<div class="box">

    <input bind:value={url} type= "text" placeholder="enter url to be shorten"/> 
    <button on:click={sendReq}>enter</button>

</div>
<div class="inmain2"><h2>👉  {shorturl}</h2></div>
</div>

<style>
   .inmain{  
       margin-top: 12%; 
        margin-bottom: -14%;
        margin-left: 10px;        
        text-align: center;
        color: white;
    }
    input{
        padding: 20px;
        width: 50%;
        font-size: 20px;
        padding-top: 10px; 
        padding-bottom: 10px;
        border-radius: 10px;

    }
    button{
      
        font-weight: bold;
            padding: 15px;
            padding-left: 20px;
            padding-right: 20px;
           padding-top: 10px; 
            padding-bottom: 10px;
            text-align: center;
            border-radius: 10px;
    }
    .box{
        display: flex;
        justify-content: center;
        align-items: center;
        margin-top: 200px;
    }
    img{
        height: 80px;
        align-items: center;
        margin-top: 2%; 
        margin-bottom: -12%;
        margin-left: 47.5%; 
    }
  
    h1{
        align-items: center;
    }
    .inmain2{
        margin-left: 10px;        
        text-align: center;
        color: white;


    }
   
    @media all and (min-width: 783px) and (max-width: 1028px) {
}
   
</style>