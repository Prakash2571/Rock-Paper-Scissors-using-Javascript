# Rock-Paper-Scissors-using-Javascript
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rock paper scissors</title>
    <style>
      body{
        background-color: black;
      }
      .icon{
        height:50px;
       
      }
      .ss{
        color:white;
        
        font-size: 2.5rem;
      }

      .tag{
        color:blue;
        font-size: 3rem;
        background-color: transparent;
        border:3px solid white;
        border-radius:50% ;
        height:120px;
        width:120px;
      }

      .allreset{
        font-size: 2rem;
        background-color: white;
        
      }
      
       
    
      .result{
        color:white;
        font-size: 2.5rem;
      }
    </style>
</head>
<body>
    <p class="ss">Rock Paper Scissors</p>
    <button class="ro tag"><img src="./images/rock-emoji.png" class="icon"></button>
    <button class="pa tag"><img src="./images/paper-emoji.png" class="icon"></button>
    <button class="si tag"><img src="./images/scissors-emoji.png" class="icon"></button><br><br>
    <button class="res allreset">Reset</button>
    <button class="auto allreset">Auto Play</button>
    <p class="result"></p>


    <script>

        let s=" ";
        let wins=0;
        let losses=0;
        let ties=0;
        
        
   
    
        
        document.querySelector(".ro").addEventListener("click",function(){
            s= "./images/rock-emoji.png";
       


           compturn();
        });
        document.querySelector(".pa").addEventListener("click",function(){
             s="./images/paper-emoji.png";
            compturn();
        });

        
        document.querySelector(".si").addEventListener("click",function(){
             s="./images/scissors-emoji.png";
            compturn();
        });

        document.querySelector(".res").addEventListener("click",function(){
         wins=0;
          losses=0;
          ties=0;
          
          document.querySelector(".result").innerHTML=`Score Reset ! wins=${wins},losses=${losses},ties=${ties}`;
          
        });

      
         
        
         




        function compturn(){

          let r=Math.ceil(Math.random()*3);
             let ct ="";


         if(r==1)
        {  
            ct="./images/rock-emoji.png";


        }
        else if(r==2)
        {
             ct="./images/paper-emoji.png";
        }
        else{
             ct="./images/scissors-emoji.png";
        }
         
     
            let fs="";
      if(s==ct)
      {
       fs="Draw !"
      }
      else if(s=="./images/paper-emoji.png" && ct=="./images/rock-emoji.png"){
        fs="You Win !"
      }
      else if(s=="./images/paper-emoji.png" && ct=="./images/scissors-emoji.png")
      {
        fs="You Loose !";
      }
      else if(s=="./images/rock-emoji.png" && ct=="./images/paper-emoji.png")
      {
        fs="You Loose !";
      }
      else if(s=="./images/rock-emoji.png" && ct=="./images/scissors-emoji.png")
      {
         fs="You Win !"
      }
      else if(s=="./images/scissors-emoji.png" && ct=="./images/rock-emoji.png")
      {
        fs="You Loose !"; 
      }
      else if(s=="./images/scissors-emoji.png" && ct=="./images/paper-emoji.png")
      {
          fs="You Win !"
      }


      if(fs=="You Win !")
      {
        wins=wins+1;
      }
      else if(fs=="You Loose !")
      {
        losses=losses+1;
      }
      else if(fs=="Draw !")
      {
        ties=ties+1;
      }
    
    
      
      document.querySelector(".result").innerHTML=`you chose <img src="${s}" class="icon"> and computer chose <img src="${ct}" class="icon"> ${fs} <br>
      score:wins=${wins},looses=${losses},ties=${ties}`;                                              
    }
        
     
       
    </script>
    
</body>
</html>
