# JS-CLOCK
<!DOCTYPE html>
<html lang="en">
<head>
     <meta charset="utf-8">
    <title>Dee's Clock</title>
</head>
<body>
   <div class="clock">
       <div class="clock-face">
           <div class="hand hour-hand"></div>
           <div class="hand min-hand"></div>
           <div class="hand sec-hand"></div>
       </div>
   </div>


   <style>
       html {
           background:#018DED url(https://unsplash.it/1500/1000?image=881&blur=5);;
           background-size: cover;
           font-family:'Franklin Gothic Medium';
           text-align: center;
           font-size: 10px;
       }

       body {
           margin: 0;
           font-size: 2rem;
           display: flex;
           flex: 1;
           min-height: 100vh;
           align-items: center;
     
       }

       .clock {
           width: 30rem;
           height: 30rem;
           border: 20px solid white;
           border-radius: 50%;
           margin: 50px auto;
           position: relative;
           padding: 2rem;
           box-shadow: 0 0 0 4px rgba(0,0,0,0.1),
           inset 0 0 0 3px #EFEFEF, inset 0 0 10px black, 0 0 10px rgba(0,0,0,0.2);
       }

       .clock-face {
           position: relative;
           width: 100%;
           height: 100%;
           transform: translateY(-3px);
       }

       .hand {
           width: 50%;
           height: 6px;
           background: black;
           position: absolute;
           top: 50%;
           transform-origin: 100%;
           transform: rotate(90deg);
           transition: all 0.05sec;
           transition-timing-function: cubic-bezier(0.1,2.7,0.58,1);
           
       }
   </style>

   <script>
     const secondHand = document.querySelector('.second-hand');
     const minsHand = document.querySelector('.min-hand');
     const hourHand = document.querySelector('.hour-hand');
     
     
     function setDate(){
         const now = new Date();

         const seconds = now.getSeconds();
         const secondsDegrees = ((seconds / 60) * 360)+ 90;
         secondHand.style.transform = 'rotate(${secondsDegrees}deg)';

         const min = now.getMinutes();
         const minsDegrees = ((seconds / 60) * 360) + 90;
         minHand.style.transform = 'rotate(${minsDegrees}deg)';

         const hour = now.getHours();
         const hourDegrees = ((min / 12) * 360) + 90;
         hourHand.style.transform = 'rotate(${hourDegrees}deg)';

     
     
     }   


     setInterval(setDate,1000);

     setDate();

   </script>
    


</body>
</html>
