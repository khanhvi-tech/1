
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculator</title>
    <style>
        .container{
            background-image: url(https://preview.redd.it/em4dp1r9qxx41.jpg?width=960&crop=smart&auto=webp&s=1937e598bc3673b4da3d31b859c3c4c7ea8176a6);
            height: 650px;
            width: 1300px;
            background-position: center;
            background-repeat: no-repeat;
            background-size: cover;
            display: flex;
            align-items: center;
            position: fixed;


           
        }
        .container2{
            background-image: url(https://thumbs.dreamstime.com/b/plane-trek-sky-vector-vertical-landscape-clouds-cartoon-anime-style-background-design-171922501.jpg);
            background-position: center;
            background-size: cover;
            width: 400px;
            height: 570px;
            border: black;
            border: 10px solid  darkcyan;
            margin: 0px 420px;
            display: flex;
            justify-content: center;
            align-items: flex-end;
            border-radius: 5%;
            }
        .Number{
            display: flex;
            position: absolute;
        }
        .NumAndSym1,.NumAndSym2, .NumAndSym3, .NumAndSym4, .NumAndSym5{
            display: flex;
            flex-direction: column;
            margin: 5px;
        }
        
        #inputwindow{
            background-size: cover;
            border: 10px solid  cadetblue;
            height: 150px;
            width: 350px;
            margin-bottom: 380px;
            margin-left: 10px;
            margin-right: 10px;
            background-color: #DFF1EA;
            border-radius: 5%;
            color: cadetblue;
            display: flex;
            justify-content: right;
            font-size: 110px;
            word-break: break-word;
            overflow: scroll;
            text-overflow: ellipsis;
            display: -webkit-box;
            -webkit-line-clamp: 1; /* number of lines to show */
            -webkit-box-orient: horizontal;

            }
        .NumAndSym4{
            display: flex;
            justify-content: flex-end;
        }
        .NumAndSym5{
            display: flex;
            justify-content: flex-end;
            
        }
        button{
            height: 60px;
            width:60px;
            border-radius: 30%;
            margin-top:10px;
            margin-bottom: 10px;
            background-color: cadetblue;
            color: cornsilk;
            font-size: 30px;
            font-weight: bolder;
        }
        .ohshiet{
            background-color: #F0F0F0;
            color:cadetblue;
        }
        .ohshiet2{
            background-color: crimson;
            color: #F99584;
        }
        .ohshiet3{
            background-color: #73DFD2 ;
        }
        .button4{
            height: 140px;
            border-radius: 15%;
            background-color: grey;
            
        }
        .button4:hover{
            color: cadetblue;
            background-color: #F0F0F0;
        }

        button:hover{
            color: white;
            background-color: grey;

        }
        .animu{
            background-color: #73DFD2 ;
        }
        
        


    </style>
</head>
<body>
<div class="container">
    <div class="container2">
        
        <div id="inputwindow"></div>
        <div class="Number">
            <div class="NumAndSym1">
                <button class="ohshiet" onclick="display(7)">7</button>
                <button class="ohshiet" onclick="display(4)">4</button>
                <button class="ohshiet" onclick="display(1)">1</button>
                <button class="ohshiet2" onclick="clr()">C</button>
            </div>
            <div class="NumAndSym2">
                <button class="ohshiet" onclick="display(8)">8</button>
                <button class="ohshiet" onclick="display(5)">5</button>
                <button class="ohshiet" onclick="display(2)">2</button>
                <button class="ohshiet" onclick="display(0)">0</button>
            </div>
            <div class="NumAndSym3">
                <button class="ohshiet" onclick="display(9)">9</button>
                <button class="ohshiet" onclick="display(6)">6</button>
                <button class="ohshiet" onclick="display(3)">3</button>
                <button class="ohshiet" onclick="display('.')">.</button>
            </div>
            <div class="NumAndSym4">
                <button class="ohshiet3" onclick="clr2()"> <- </button>
                <button onclick="setOperation('*')">x</button>
                <button onclick="setOperation('-')">-</button>
                <button onclick="setOperation('+')">+</button>
            </div>
            <div class="NumAndSym5">
                <button class="animu">Ø</button>
                <button onclick="setOperation('/')">/</button>
                <button class="button4" onclick="solve()">=</button>
            </div>
        </div>
    </div>
</div>

    <script>


            let sodauTien;
            let sothuHai;
            let toantu="";
            let display = function (n) {
                let result = document.getElementById("inputwindow");
                if (result.innerHTML === "+" ||result.innerHTML === "*" ||result.innerHTML === "-"|| result.innerHTML === "/"){
                result.innerHTML = ""}
                result.innerHTML += n;
                }

            let setOperation = function (n) {
                let result = document.getElementById("inputwindow");
                sodauTien = result.innerHTML;
                result.innerHTML = n; 
                // n là tên toán tử
                toantu = n

                
            }

            let solve = function (n){
                let result = document.getElementById("inputwindow");
                sothuHai = result.innerHTML;
                let Ketqua = 0;
                sodauTien = parseFloat(sodauTien);
                sothuHai = parseFloat(sothuHai);
                if (toantu==="+"){
                    Ketqua=sodauTien + sothuHai;
                }
                if (toantu==="-"){
                    Ketqua=sodauTien - sothuHai;
                }
                if (toantu==="*"){
                    Ketqua=sodauTien * sothuHai;
                }
                if (toantu==="/"){
                    Ketqua=sodauTien / sothuHai;
                }
                result.innerHTML = Ketqua;
                
            }
             let clr = function(){
                 document.getElementById("inputwindow").innerHTML = ""
             }

            let clr2 = function(){
                
            let result  = document.getElementById('inputwindow').innerHTML;
            document.getElementById('inputwindow').innerHTML = result.substring(0,result.length -1);
            }

             
       
    </script>
</body>
</html>
