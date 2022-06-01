# Digital-Clock

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Digital Clock</title>
</head>
<style>
    
    *{
        background-color: gainsboro;
    }
    #Clock{
        font-size: 175px;
        background-color: black;
        color: red;
        width: 950px;
        margin-left: 200px;
        margin-top: 20px;
        text-align: center;
        border: 20px solid blue;
        border-radius: 20px;
    }
    h1{
        text-align: center;
        width: 200px;
        border: 20px solid black;
        margin-left: 550px;
        margin-top: 200px;
        border-radius: 20px;
    }
</style>
<link rel="favicon" href="favicon.png">
<body>
    <h1>Digital Clock</h1>
    <div id="Clock">hh:mm:ss</div>
    
    <script>
        setInterval(showTime,1000);
        function showTime(){
            let time = new Date();
            let hh = time.getHours();
            let mm = time.getMinutes();
            let ss = time.getSeconds();
            let am_pm = "AM";

            if (hh>12){
                hh -= 12; 
                am_pm= "PM";
            }
            if (hh==0){
                hh = 12;
                am_pm = "AM";
            }

            if (hh<10){
               hh = "0"+hh;
            }
            if (mm<10){
                mm= "0"+mm;
            }
            if (ss<10){
                ss= "0"+ss;
            }

            let currentTime = hh+":"+mm+":"+ss+" "+am_pm;
            document.getElementById("Clock").innerHTML = currentTime;

        }
        showTime();
    </script>
</body>
</html>
