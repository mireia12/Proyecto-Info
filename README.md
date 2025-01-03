#include<fstream>
#include<vector>
#include<math.h>

using namespace std ;


// DANI

struct DadesConsum {
    string sexe, edat, nivell_ingressos, consum_tabac;
    double total;
};

// ÁLVARO

struct DadesEstudi{
string Sexo, edad, Nivel, Indicador;
float Porcentaje;
};

// MIREIA

struct DadesComunitat{
string sexo, comunitat, exposicio_tabac;
float total_consumicio;
};


// VOID LECTURA FICHERO DANI

vector<DadesConsum> lector_consum(const string& fitxer_dani_FI) {
    vector<DadesConsum> dades;
    ifstream fitxer(fitxer_dani_FI.txt);
    string p1;
    DadesConsum D;

    getline(fitxer, p1); // Prelectura per eliminar la capcalera

    while (fitxer >> D.sexe >> D.edat >> D.nivell_ingressos >> D.consum_tabac >> D.total) {
        if (D.edat != "TOTAL" && D.nivell_ingressos != "TOTAL" && D.consum_tabac != "TOTAL") {
            dades.push_back(D);
        }
    }

    return dades;
}


//VOID LECTURA FICHERO ALVARO

vector<DadesEstudi> lector_consum(const string& INFO_AMR) {
    vector<DadesEstudi> dades_AMR;
    ifstream CinF(INFO_AMR);
    string titol;
    DadesEstudi DE;

    getline(CinF, titol); // Prelectura per eliminar la capcalera

    while (CinF >> DE.Sexo >> DE.edad >> DE.Nivel >> DE.Indicador >> DE.Porcentaje) {
        if (DE.edad != "TOTAL" && DE.Nivel != "TOTAL" && DE.Indicador != "TOTAL") {
           dades_AMR.push_back(DE);
        }
    }

    return dades_AMR;
}
//VOID LECTURA FICHERO MIREIA

vector<DadesComunitat> lector_consum (const string& Info_Mireia) {
    vector<DadesComunitat> dades_Mireia;
    ifstream fichero(Info_Mireia);
    string p3;
    DadesComunitat DC;

    getline(fichero, p3);
    while (fichero >> DC.sexo >> DC.comunitat >> DC.exposicio_tabac >> DC.total_consumicio) {
        if (DC.comunitat != "TOTAL" && DC.exposicio_tabac != "TOTAL") {
           dades_Mireia.push_back(DC);
        }
    }

    return dades_Mireia;
}
