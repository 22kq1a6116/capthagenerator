
<!DOCTYPE html>
<html lang="en">
<head>
    <style>
          body{
    display: flex;
    justify-content: center;
    height: 250px;
    border: 4px solid skyblue;
    align-items: center;
  margin-left: auto;
  margin-right: auto;
  margin-top: 200px;
  margin-bottom: 200px;
  flex-direction: column;
    background-color:sienna;
    background-attachment: fixed;
    background-size: cover;
    width: 420px;
    }
div {
  margin-bottom: 10px;
}
button {
  margin-bottom: 5px;
  cursor: pointer;
}
input {
  text-decoration: none;
}
#generated-captcha {
  text-decoration: line-through;
  font-weight: bold;
  text-align: center;
  font-size: 30px;
  font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
  background-color:cadetblue; 
  border-radius: 6px;
  border: none;
  padding: 6px;
  outline: none;
  color: red;
  word-spacing: normal;
  letter-spacing: 5px;
  text-decoration: none;
}

#entered-captcha {
  border: 5px solid white;
  font-family: monospace;
  font-weight: bolder;
  outline: none;
  border-radius: 6px;
  padding: 8px 15px;
  font-size: 12px;
}
button {
  border: none;
  padding: 8px 20px;
  border-radius: 6px;
  font-size: 14px;
  font-family: monospace;
  font-weight: bold;
  outline: none;
  background-color:red;
}

#gen {
  background-color: yellow;
}
.wrappr {
  /* border: 1px solid red; */
  display: flex;
  flex-direction: column;
  /* align-items: center; */
  justify-content: center;
}
captcha{
    text-indent: 1px;
}
.innertext{
    color: black;
}
script{
    color: black;
}
        </style>
   
      
    </head>

    <body onload="generate()">

        <div class="wrapper"></div>
        <h2 id="status" style="color: #ee7e6a;"></h2>
        <div>
            <input type="text" readonly id="generated-captcha">
        </div>
        <div>
            <input type="text" id="entered-captcha" placeholder="Enter the captcha..">
        </div>
        <button type="button" onclick="check()">
            verify
        </button>
        <button type="button" onclick="generate()" id="gen">
            refresh
        </button>
       
    
    </body>

<script>
    let captcha;
let alphabets = "AaBbCcDdEeFfGgHhIiJjKkLlMmNnOoPpQqRrSsTtUuVvWwXxYyZz";
console.log(alphabets.length);
let status = document.getElementById('status');
status.innerText = "Captcha Generator";


 generate = () => {
// console.log(status)
let first = alphabets[Math.floor(Math.random() * alphabets.length)];
let second = Math.floor(Math.random() * 10);
let third = Math.floor(Math.random() * 10);
let fourth = alphabets[Math.floor(Math.random() * alphabets.length)];
let fifth = alphabets[Math.floor(Math.random() * alphabets.length)];
let sixth = Math.floor(Math.random() * 10);
captcha = first.toString() + second.toString() + third.toString() + fourth.toString() + fifth.toString() + sixth.toString();
console.log(captcha);
document.getElementById('generated-captcha').value = captcha;
document.getElementById("entered-captcha").value = '';

}

 check = () => {
// console.log(status)
let userValue = document.getElementById("entered-captcha").value;
console.log(captcha);
console.log(userValue);
if(userValue == captcha){
    status.innerText = "Correct!!"
}else{
    alert("invalid captcha")
}
}
</script>
</body>
</html>
