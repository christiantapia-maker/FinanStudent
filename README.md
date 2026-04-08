# FinanStudent
Sistema de control financiero c++
#include<iostream>
using namespace std;

float vivienda=0, alimentacion=0, transporte=0, estudios=0, ocio=0;

float ingresos (){
    float ingr;
    cout<<"Ingrese sus ingresos mensuales: "<<endl;
    cin>>ingr;
    return ingr;
}

void clasigastos(float gast){
    int tipo;

    cout<<"Ingrese el tipo de gasto a registrar"<<endl;
    cout<<"1. vivienda"<<endl;
    cout<<"2. alimentacion"<<endl;
    cout<<"3. transporte"<<endl;
    cout<<"4. estudios"<<endl;
    cout<<"5. ocio"<<endl;

    cin>>tipo;

    switch (tipo){
        case 1:
            vivienda += gast;
            break;
        case 2:
            alimentacion += gast;
            break;
        case 3:
            transporte += gast;
            break;
        case 4:
            estudios += gast;
            break;
        case 5:
            ocio += gast;
            break;
        default:
            cout<<"Tipo de gasto no valido"<<endl;
    }
}

void gastos(){
    float gast;
    string respuesta;

    cout<<"Ingrese el monto del gasto: "<<endl;
    cin>>gast;

    cout<<"¿Desea clasificar el gasto? (si/no): "<<endl;
    cin>>respuesta;

    if(respuesta=="si"){
        clasigastos(gast);
    }else{
        cout<<"Gasto registrado sin clasificacion"<<endl;
    }
}

void visualizacion(){
    cout<<"\n°°°°° ESTADO FINANCIERO °°°°"<<endl;
    cout<<"Vivienda: "<<vivienda<<endl;
    cout<<"Alimentacion: "<<alimentacion<<endl;
    cout<<"Transporte: "<<transporte<<endl;
    cout<<"Estudios: "<<estudios<<endl;
    cout<<"Ocio: "<<ocio<<endl;
}

int main(){
    int opcion;
    float ingreso=0;

    cout<<"| BIENVENIDO A FINSTUDENT-SISTEMA DE CONTROL FINANCIERO |"<<endl;

    cout<<"1. Registro de ingresos"<<endl;
    cout<<"2. Registro de gastos"<<endl;
    cout<<"3. Visualizacion financiera"<<endl;
    cout<<"4. Salir"<<endl;

    cin>>opcion;

    switch(opcion){

        case 1:
            ingreso=ingresos();
            break;

        case 2:
            gastos();
            break;

        case 3:
            visualizacion();
            break;

        case 4:
            cout<<"Gracias por usar el sistema"<<endl;
            break;

        default:
            cout<<"Opcion no valida"<<endl;
    }
}
