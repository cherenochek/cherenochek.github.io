# cherenochek.github.io
<!-- SAPE RTB JS -->
<script
    async="async"
    src="//cdn-rtb.sape.ru/rtb-b/js/038/2/121038.js"
    type="text/javascript">
</script>
<!-- SAPE RTB END -->
<html xml:lang="en" lang="en" >
<head>
<body>
<div id="text">
<h1 class="text-center">Team 1</h1>
<div id="text">средний процент побед на героях</div>
<input type="number"  class="player_1" value="" >
<input type="number"  class="player_2" value="" >
<input type="number"  class="player_3" value="" >
<input type="number"  class="player_4" value="" >
<input type="number"  class="player_5" value="" >
    
<div id="text">средний УСП игроков</div>
<input type="number"  class="ysp_1" value="" >
<input type="number"  class="ysp_2" value="" >
<input type="number"  class="ysp_3" value="" >
<input type="number"  class="ysp_4" value="" >
<input type="number"  class="ysp_5" value="" >
      
<div id="text">количество игр на героях</div>
<input type="number"  class="match_1" value="" >
<input type="number"  class="match_2" value="" >
<input type="number"  class="match_3" value="" >
<input type="number"  class="match_4" value="" >
<input type="number"  class="match_5" value="" >
       
<h1 class="text-center">Team 2</h1>
<div id="text">средний процент побед на героях</div>
<input type="number"  class="player2_1" value="" >
<input type="number"  class="player2_2" value="" >
<input type="number"  class="player2_3" value="" >
<input type="number"  class="player2_4" value="" >
<input type="number"  class="player2_5" value="" >
   
<div id="text">средний УСП игроков</div>
<input type="number"  class="ysp2_1" value="" >
<input type="number"  class="ysp2_2" value="" >
<input type="number"  class="ysp2_3" value="" >
<input type="number"  class="ysp2_4" value="" >
<input type="number"  class="ysp2_5" value="" >
   
   
<div id="text">количество игр на героях</div>
<input type="number"  class="match2_1" value="" >
<input type="number"  class="match2_2" value="" >
<input type="number"  class="match2_3" value="" >
<input type="number"  class="match2_4" value="" >
<input type="number"  class="match2_5" value="" >
   
<button>predict</button> 
  
<div class="out">predict action : </div>
   
</div>
    <script src="http://unpkg.com/brain.js"></script>
    <script type="text/javascript" >
//начальная расстановка в шахматах

// Параметры для инициализации ИНС
const config = {
    binaryThresh: 0.5,
    hiddenLayers: [10], // Количество скрытых слоев
    activation: 'sigmoid', // Функция активации
    log: true // Логирование результатов обучения
};
           // {input: [,,,,], output: [1]},
   // {input: [,,,,], output: [0]},

// Создаем ИНС с параметрами в переменной config
const net_heroes = new brain.NeuralNetwork(config);
const net_ysp = new brain.NeuralNetwork(config);
const net_match = new brain.NeuralNetwork(config);        

        
net_match.train([
    {input: [110,17,66,159,16], output: [1]},
    {input: [28,173,72,67,59], output: [0]},
           
    {input: [11,33,16,29,24], output: [1]},
    {input: [110,21,24,42,46], output: [0]},
    
    {input: [40,47,6,20,61], output: [1]},
    {input: [28,12,36,78,85], output: [0]},
    
    {input: [124,37,1,45,6], output: [1]},
    {input: [2,39,38,23,60], output: [0]},
    
    {input: [40,23,12,40,26], output: [1]},
    {input: [62,42,37,46,29], output: [0]},
    
        {input: [9,248,14,45,54], output: [1]},
    {input: [29,49,11,33,5], output: [0]},
    
    {input: [29,11,16,33,5], output: [1]},
{input: [12,248,14,10,54], output: [0]},

    

         ]);
        
        
net_heroes.train([
    {input: [68.18,58.82,77.27,60.38,75.00], output: [1]},
    {input: [46.43,57.80,58.33,49.25,64.41], output: [0]},
    
    {input: [63.64,66.67,56.25,48.28,79.17], output: [1]},
    {input: [68.18,66.67,58.33,64.29,71.74], output: [0]},
    
    {input: [77.50,63.83,50.00,60.00,65.57], output: [1]},
    {input: [64.29,41.67,58.33,52.56,70.59], output: [0]},
    
    {input: [66.94,72.97,100.00,68.89,83.33], output: [1]},
    {input: [50.00,61.54,52.63,60.87,73.33], output: [0]},
    
    {input: [77.50,65.22,75.00,62.50,73.08], output: [1]},
    {input: [67.74,64.29,59.46,76.09,58.62], output: [0]},
    
        {input: [88.89,65.32,50.00,68.89,55.56], output: [1]},
    {input: [51.72,75.51,36.36,51.52,60.00], output: [0]},
    
    {input: [51.72,36.36,62.50,51.52,40.00], output: [1]},
{input: [66.67,65.32,50.00,50.00,55.56], output: [0]},
    
         ]);

        
net_ysp.train([
    {input: [5.65,2.98,7.82,4.38,3.85], output: [1]},
    {input: [4.23,2.40,3.80,1.74,7.35], output: [0]},
           
    {input: [4.30,3.10,3.89,4.50,12.97], output: [1]},
    {input: [5.65,2.75,3.97,6.44,4.00], output: [0]},
    
    {input: [5.85,4.96,10.45,2.55,3.24], output: [1]},
    {input: [5.58,2.18,5.03,3.65,2.55], output: [0]},
    
    {input: [3.33,4.12,12.00,3.21,9.55], output: [1]},
    {input: [1.61,3.07,4.11,3.98,4.69], output: [0]},
    
    {input: [5.85,3.86,8.92,3.94,2.57], output: [1]},
    {input: [2.47,6.44,5.79,4.62,4.65], output: [0]},
    
        {input: [3.62,5.02,3.60,3.21,4.59], output: [1]},
    {input: [1.96,4.38,2.47,2.13,3.80], output: [0]},
    
    {input: [1.96,2.47,4.14,2.13,3.40], output: [1]},
{input: [3.70,5.02,3.60,2.56,4.59], output: [0]},

         ]);
        

// На этом этапе у нас уже есть отлично тренерованная ИНС, которую уже можно использовать



        
        
let predict_button = document.querySelector('button')
         
let player_1 = document.querySelector('.player_1')
let player_2 = document.querySelector('.player_2')
let player_3 = document.querySelector('.player_3')        
let player_4 = document.querySelector('.player_4')
let player_5 = document.querySelector('.player_5')

let ysp_1 = document.querySelector('.ysp_1')
let ysp_2 = document.querySelector('.ysp_2')
let ysp_3 = document.querySelector('.ysp_3')        
let ysp_4 = document.querySelector('.ysp_4')
let ysp_5 = document.querySelector('.ysp_5')

let match_1 = document.querySelector('.match_1')
let match_2 = document.querySelector('.match_2')
let match_3 = document.querySelector('.match_3')        
let match_4 = document.querySelector('.match_4')
let match_5 = document.querySelector('.match_5')


let player2_1 = document.querySelector('.player2_1')
let player2_2 = document.querySelector('.player2_2')
let player2_3 = document.querySelector('.player2_3')        
let player2_4 = document.querySelector('.player2_4')
let player2_5 = document.querySelector('.player2_5')

let ysp2_1 = document.querySelector('.ysp2_1')
let ysp2_2 = document.querySelector('.ysp2_2')
let ysp2_3 = document.querySelector('.ysp2_3')        
let ysp2_4 = document.querySelector('.ysp2_4')
let ysp2_5 = document.querySelector('.ysp2_5')

let match2_1 = document.querySelector('.match2_1')
let match2_2 = document.querySelector('.match2_2')
let match2_3 = document.querySelector('.match2_3')        
let match2_4 = document.querySelector('.match2_4')
let match2_5 = document.querySelector('.match2_5')


let div_out = document.querySelector('.out')




predict_button.onclick = function (){
div_out.innerHTML = "predict action : "

    let p1 = player_1.value
   let p2 = player_2.value
   let p3 = player_3.value
   let p4 =player_4.value
   let p5 =player_5.value
   
   let ysp1 = ysp_1.value
   let ysp2 = ysp_2.value
   let ysp3 = ysp_3.value
   let ysp4 =ysp_4.value
   let ysp5 =ysp_5.value
   
   let match1 = match_1.value
   let match2 = match_2.value
   let match3 = match_3.value
   let match4 =match_4.value
   let match5 =match_5.value
   
   
   
   let p21 = player2_1.value
   let p22 = player2_2.value
   let p23 = player2_3.value
   let p24 =player2_4.value
   let p25 =player2_5.value
   
   let ysp21 = ysp2_1.value
   let ysp22 = ysp2_2.value
   let ysp23 = ysp2_3.value
   let ysp24 =ysp2_4.value
   let ysp25 =ysp2_5.value
   
   let match21 = match2_1.value
   let match22 = match2_2.value
   let match23 = match2_3.value
   let match24 =match2_4.value
   let match25 =match2_5.value
   
let heroes1= [p1,p2,p3,p4,p5]
let ysp11_1= [ysp1,ysp2,ysp3,ysp4,ysp5]
let match11_1= [match1,match2,match3,match4,match5]

    
let heroes2=[p21,p22,p23,p24,p25]
let ysp22_2=[ysp21,ysp22,ysp23,ysp24,ysp25]
let match22_2=[match21,match22,match23,match24,match25]


let out_h1=net_heroes.run(heroes1)
let out_ysp1 = net_ysp.run(ysp11_1)
let out_match1=net_match.run(match11_1)


let out_h2=net_heroes.run(heroes2)
let out_ysp2 = net_ysp.run(ysp22_2)
let out_match2=net_match.run(match22_2)

let output
let output_2
output = parseFloat(out_h1) + parseFloat(out_ysp1) + parseFloat(out_match1)
output_2 =  parseFloat(out_h2)+ parseFloat(out_ysp2) + parseFloat(out_match2)
       //  document.write("<pre>next  predictions:\n <\/pre>");
        
            div_out.innerHTML +='Team_1: '+ Math.round(output) +"<pre>\n <\/pre>"+'Team_2: '+ Math.round(output_2)+"<pre>\n <\/pre>"

    div_out.innerHTML +='Team_1: '+ output +"<pre>\n <\/pre>"+'Team_2: '+ output_2
            //document.write("\t")
            
             div_out.innerHTML +=("<pre>\n <\/pre>")
    if(output ==output_2){
        div_out.innerHTML +='the first and second teams have the same chances'
        div_out.innerHTML +=("<pre>\n <\/pre>")
        div_out.innerHTML +='у первой и второй команд одинаковые шансы'
            }else
            if(output >output_2){
           div_out.innerHTML +='Team_1 WIN'
           }else{
              div_out.innerHTML +='Team_2 WIN' 
           }
        
    
}
        
        
        

        // Выводим информацию о работе в консоль. Это будет числов в диапазоне от 0 до 1. Не забываем что ИНС не может давать 100% правильный результат, поэтому мы получим число с плавающей запятой. Если число > .5, то это ближе к 1, если < .5, то это ближе к 0. Для нормализации ответа округлим его при помощи фукнции Math.round(...)

    </script>    
        
    </body>
</head>
</html>
