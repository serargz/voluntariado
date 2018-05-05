Abre https://www.khanacademy.org/computer-programming/new/pjs y pega el código abajo:

```
noStroke();
background(0,0,0);

var star = function(x, y) {
    fill(255, 0, 0);
    triangle(x-10, y+15, x, y, x+10, y+15);
    triangle(x-10, y+5, x, y+20, x+10, y+5);
};

var superStar = function(x, y) {
    fill(255, 255, 0);
    triangle(x-15, y+20, x, y, x+15, y+20);
    triangle(x-15, y+7, x, y+27, x+15, y+7);
    star(x, y+3);
};

var calcularDireccion = function(x, direccionActual) {
    if((direccionActual > 0 && x >= 400) || (direccionActual < 0 && x <= 0)) {
        return -direccionActual;
    }

    return direccionActual;
};

var calcularDireccionBolaX = function(x, y, direccionActual) {
    if(y >= 385 && y <= 390 && x > mouseX && x < mouseX + 40) {
        if(x < mouseX + 10) {
            return -4;
        }
        if(x < mouseX + 20) {
            return -2;
        }
        if(x < mouseX + 30) {
            return 2;
        }
        return 4;
    }

    if((direccionActual > 0 && x >= 400) || (direccionActual < 0 && x <= 0)) {
        return -direccionActual;
    }

    return direccionActual;
};

var calcularDireccionBolaY = function(x, y, direccionActual) {
    if(direccionActual > 0) {
        if(y >= 385 && y <= 390 && x > mouseX && x < mouseX + 40) {
            return -4;
        }
    }

    if(direccionActual < 0 && y <= 0) {
        return 4;
    }

    return direccionActual;
};

superStar(300, 300);
superStar(100, 250);

var star1_x = random(0, 400);
var star2_x = random(0, 400);
var star3_x = random(0, 400);

var star1_direccion = 1;
var star2_direccion = -2;
var star3_direccion = -3;

var mostrarStar1 = true;
var mostrarStar2 = true;
var mostrarStar3 = true;

var bolaX = random(0, 400);
var bolaY = 0;
var bolaDireccionX = 4;
var bolaDireccionY = 4;

var fin = false;

draw = function() {

    // Es el fin del juego?
    if(fin){
        fill(255, 255, 255);
        textSize(30);
        text("Perdiste!", 140, 200);
        return;
    }

    background(0,0,0);

    superStar(star1_x, 20);
    superStar(star2_x, 50);
    superStar(star3_x, 80);

    star1_direccion = calcularDireccion(star1_x, star1_direccion);
    star2_direccion = calcularDireccion(star2_x, star2_direccion);
    star3_direccion = calcularDireccion(star3_x, star3_direccion);

    star1_x += star1_direccion;
    star2_x += star2_direccion;
    star3_x += star3_direccion;

    // TODO: Calcular colisiones

    // Dibujar bola
    rect(mouseX, 390, 40, 5);
    fill(255, 255, 255);
    ellipse(bolaX, bolaY, 10, 10);

    bolaDireccionX = calcularDireccionBolaX(bolaX, bolaY, bolaDireccionX);
    bolaDireccionY = calcularDireccionBolaY(bolaX, bolaY, bolaDireccionY);

    bolaX += bolaDireccionX;
    bolaY += bolaDireccionY;

    if(bolaY > 400) {
        fin = true;
    }
};
```
