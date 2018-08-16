# Laboratorio-1

#include <iostream>
#include <math.h>

using namespace std;

#define pi 3.1416

float ALPHA = 1.24;
float x, y, vx, vy;


void calcParabolico(void);
void print_results(void);
void otros_calculos(void);

int main()
{
    
    unsigned short int des = 5;
    int lib_func1();
   int var = 100;

    var += des;

    //Calculando los parametros en la Tierra con g = 9.8 m/s*s
    calcParabolico();
    print_results();

    //Calculando los parametros en la Luna con g = 1.62 m/s*s
    calcParabolico();
    print_results();
    
    otros_calculos();


    return 0;
}

void calcParabolico(void)
{
    const float g = 9.8;
    float vx0=5, vy0=8, x, y, vx, vy, t=3, y0 ;
    float v0=7;

    vx0 = v0 * cos(ALPHA);
    vy0 = v0 * sin(ALPHA);

    vx = vx0;
    vy = vy0-g*t;

    x = vx*t;
    y = y0+vy0*t-(g*pow(t,2)/2);
}

void print_results(void)
{
    std::cout<<"Los resultados del calculo parabolico son: "<<std::endl;
    std::cout<<"Velocidad en x: "<<vx<<", ";
    std::cout<<"Velocidad en y: "<<vy<<", ";
    std::cout<<"Posicion en x: "<<x<<", ";
    std::cout<<"Posicion en y: "<<y<<std::endl;
}

void otros_calculos(void)
{
    /* Serie simple (1/[(x^2) + (x+1)]) para x entre 1 y 199*/
    for(int x=1; x<200; x++){
        
        static float cuenta=0;
        cuenta= 1/(pow (x,2)+(x+1));
        
        cout<<"el numero es:"<<cuenta<<"\n";
        
    }
        

    /* Volumen de la esfera */
      
      float radio=3;
      
      double vol=0;
      
      vol= (4/3)*pi*pow(radio,3);
      
      cout<<"el volumen de la esfera es "<<vol<<"\n";
      
      
      
    /* Raices de la ecuacion (3*x^2) + (5*x) + 8  = 0 */
      //
      

float raizneg=0;
float raizpos=0;

raizpos= (-5+sqrt(pow(5,2)-4*3*8))/6;

raizneg= (-5-sqrt(pow(5,2)-4*3*8))/6;

cout<<"el primer resultado de la ecuacion es "<<raizpos<<"\n";
cout<<"el segundo resultado de la ecuacion es "<<raizneg<<"\n";

   
   
   
    /* Impedancia tipica de una linea de transmision
     * Z0 = [(R+wL)/(G+wC)]^(1/2)
     * w = frecuencia angular = 2*pi*f, f = 10kHz */
        //Agregue aqui la formula
        
     float R=1000, L=0.00003, G=3, C=0.000001, Z, W; 
     
     W= 2*pi*10000;
     
     Z= sqrt((R+W*L)/(G+W*C));
     
    cout<<"la impedancia tipica de la linea de transmision es "<<Z<<"\n";
     
        
        
        

    /* Constante de fase de una fibra optica
     * B = {[((a^2)-(b^2))*c+(b^2)]^(1/2)}*betacero
     * betacero = w*(mu*epsi)^(1/2)
     * w = frecuencia angular = 2*pi*f, f = 5GHz
     * mu = 0.00000125664
     * epsi = 0.00000000000088542  */
     
     
     double mu = 0.00000125664, epsi = 0.00000000000088542;
     float betacero, fa, B, a=3, b=3, c=4;
     
     fa= 2*pi*5000000;
     
     betacero= fa*sqrt(mu*epsi);
     
     B=pow((pow(a,2)-pow(b,2))*C+pow(b,2),1/2)*betacero;
     
     cout<<"la constante de fase es "<<B<<"\n";
     
     
     

}  
