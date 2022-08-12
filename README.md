# jogo-da-memoria
jogo da memória educativo sobre matemática 
var cartasValor = ['2x3', '5x8','6x9', '6', '8x8', '40', '64','4x8', '54', '32'];
var cartasX = [];
var cartasY = [];
var quantidadeCartas = 10;
var cartaAltura = 150;
var cartaLargura = 90;
var viradas = [];

var contagemTempo = false;
var contTempo = 0;


function setup() {
  createCanvas(600, 450);
  frameRate(900);
  
  incY = 200;
  incX = 100;
  
  xi = 50;
  yi = 40;
  
    for (i = 0; i < quantidadeCartas; i++ ){
    cartasX[i] = xi;
    cartasY[i] = yi;
    xi = xi + incX;
    if ( xi > 500){ 
     yi = yi + incY;
     xi = 50;
   }
  
   viradas[i] = false;
  }
  console.log(viradas);
}

function desviraCartas(){
  for ( i = 0; i < quantidadeCartas; i++){ 
    viradas[i] = false;
  }
}

function draw() {
  background(0);
  textSize (50);
  
  for (i=0; i < quantidadeCartas; i++ ){ 
    rect(cartasX[i], cartasY[i], cartaLargura, cartaAltura )
    if ( viradas[i] ){ 
      text(cartasValor[i], cartasX[i] + 10, cartasY[i] + 40 ) 
    }
  }
  console.log(viradas)
  
  if ( contagemTempo ){ 
    contTempo++;
    // conta dois segundos 
    if ( contTempo > 90 ){
        contagemTempo = false;
        desviraCartas(2);
        contTempo = 0;
    } 
    
  }
  
}

function mouseClicked(){
  for (i=0; i < quantidadeCartas; i++ ){ 
   if ( mouseX > cartasX[i] && mouseX < cartasX[i] + cartaLargura    && mouseY > cartasY[i] && mouseY < cartasY[i] + cartaAltura ){
  viradas[i] = ! viradas[i] ;
     contagemTempo 
    }
  } 
}
[jogo-da-memoria-main.zip](https://github.com/maxeduardo987/jogo-da-memoria/files/9330145/jogo-da-memoria-main.zip)
