# clase-empleado-materia
clase materia
//jose javier gonzalez martinez, seminario estructura de datos, seccion D14
#include<iostream>
#include<stdlib.h>
using namespace std;


class materia{
    private:
        int claveClase;
        string nombre;
        string profesorTit;
        string libroTexto;
    public:
        materia (int clave,string nom,string prof,string libt);
        void imprime();
        void cambiaClave();
        void cambiaProfe();
};

materia::materia(int clave,string nom,string prof,string libt){
    claveClase =clave;
    nombre=nom;
    profesorTit=prof;
    libroTexto=libt;
}

void materia::imprime(){
    cout<<"clave: "<<claveClase<<" materia: "<<nombre<<" profesor: "<<profesorTit<<" libro: "<<libroTexto<<endl;
}

void materia::cambiaClave(){
    cout<<"cual es la nueva clave? "<<endl;
    cin>>claveClase;
}

void materia::cambiaProfe(){
    cout<<"cual es el nuevo profesor? "<<endl;
    getline(cin,profesorTit);
}

int main(){
    int opc,c=1;
    materia clase(42556,"programacion","Ortiz Pimentel, Belen Anabett","introduccion a los algoritmos");
    cout<<"que opcion desea realizar"<<endl;
    cout<<"1.- imprimir datos"<<endl<<"2.- cambiar clave de materia"<<endl<<"3.- cambiar nombre del profesor"<<endl;
    cout<<"4.- salir"<<endl;
    cin>>opc;
    while(c=1){
    switch(opc){
    case(1):
        system("cls");
        clase.imprime();
        break;
    case(2):
        system("cls");
        clase.cambiaClave();
        clase.imprime();
        break;
    case(3):
        system("cls");
        clase.cambiaProfe();
        clase.imprime();
        break;
    case(4):
        system("cls");
        c=0;
        break;
    default:
        cout<<"opcion no valida"<<endl;
        break;
    }
    break;
}
}



clase empleado

//jose javier gonzalez martinez, seminario estructura de datos, seccion D14
#include <iostream>
#include <stdlib.h>
using namespace std;

class empleado{
    private:
        string Nombre;
        string domicilio;
        int ClaveEmpleado;
        string reportaA;
        float sueldo;
    public:
        empleado (string nom,string dom,int CE,float su);
        void imprime();
        void cambiadom();
        void cambiareportaA();
        void actualsueldo();
};
empleado::empleado(string nom,string dom,int CE,float su){
    Nombre = nom;
    domicilio= dom;
    ClaveEmpleado= CE;
    sueldo= su;
}

void empleado::imprime(){
    system("cls");
    cout<<"empleado: "<<Nombre<<", domicilio: "<<domicilio<<", clave de empleado: "<<ClaveEmpleado<<", sueldo: "<<sueldo<<endl;
}
void empleado::cambiadom(){
    system("cls");
    cout<<"cual es el nuevo domicilio?"<<endl;
    cin>>domicilio;
}
void empleado::actualsueldo(){
    int sal;
    system("cls");
    cout<<"en que porcentaje quiere cambier el salario?"<<endl;
    cin>>sal;
    sueldo=sueldo+(sueldo*sal/100);
}
void empleado::cambiareportaA(){
    cout<<"cual es el nombre del nuevo empleado?"<<endl;
    cin>>Nombre;

}


int main(){
    empleado jefeplanta("alejandro","lopez mateos 1365",12297,3985.57);
    empleado jefepersonal("ramon","rio tiber 234",45562,6546.82);
    int opc,c;
    cout<<"que operacion desea realizar?"<<endl;
    cout<<"1.- cambiar domicilio"<<endl<<"2.- actualizar sueldo"<<endl<<"3.- imprimir datos"<<endl<<"4.- cambiar nombre"<<endl;
    cout<<"codigo jefe planta: 12297"<<endl<<"codigo jefe personal: 45562"<<endl;
    cin>>opc;
    switch (opc){
    case(1):
        system("cls");
    cout<<"de cual empleado quere cambiar el domicilio?"<<endl;
    cin>>c;
    if (c=12297){
        system("cls");
        jefeplanta.cambiadom();
        jefeplanta.imprime();
    }
    if(c=45562){
        system("cls");
        jefepersonal.cambiadom();
        jefepersonal.imprime();
    }
    else{
        system("cls");
        cout<<"el empleado no existe"<<endl;
    }
        break;
    case(2):
        system("cls");
        cout<<"de cual empleado quiere cambier el salario"<<endl;
        cin>>c;
        if(c=12297){
                system("cls");
            jefeplanta.actualsueldo();
            jefeplanta.imprime();
        }
        if(c=45562){
            system("cls");
            jefepersonal.actualsueldo();
            jefepersonal.imprime();
        }
        else{
            system("cls");
            cout<<"el empleado no existe";
    }
        break;
    case(3):
        system("CLS");
            cout<<"que empleado desea ver?"<<endl;
        cin>>c;
        if(c=12297){
            jefeplanta.imprime();
        }
        if(c=45562){
            jefepersonal.imprime();
        }
        else{
            system("cls");
            cout<<"el empleado no existe";
    }
        break;
    case(4):
        system("cls");
    cout<<"de cual empleado quiere cambiar el nombre?"<<endl;
    int c;
    if (c=12297){
        jefeplanta.cambiareportaA();
        jefeplanta.imprime();
    }
    if (c=45562){
        jefepersonal.cambiareportaA();
        jefepersonal.imprime();
    }
    else{
        system("cls");
        cout<<"el empleado no existe"<<endl;
    }
        break;
    default:
        system("cls");
        cout<<"opcion invalida";
        break;
    }
    return 0;
}

