//Aplikasi sederhana prinsip dasar sistem E money

#include<iostream>
#include<stdlib.h>
#include<string.h>
#include<conio.h>
using namespace std;

void masuk();
void daftar();
void awal();
void isi();
void trf();
void ipul();
void ganti();

class Akun {

	public:
		string uname, nama, pasw;
		int saldo;
		Akun(string Un, string newNama, string newPasw, int newSaldo){
			uname = Un;
			nama = newNama;
			pasw = newPasw;
			saldo = newSaldo;
		}

		string getNama(){
			return nama;
		}

		int getSaldo(){
			return saldo;
		}
		string getPass(){
			return pasw;
		}
};

/*<<------------------------------------- PEMBATAS ------------------------------------->>*/
/*<<------------------------- PENDESKRIPSIAN VARIABEL & OBJEK -------------------------->>*/

char user[12], nam[100], pass[8], pasu[8], no[13], g;
Akun *u= NULL; //objek menyesuaikan akun yang dipakai/login
int m,s;
float i;
string y;

//akun yang tersedia
Akun u1 = Akun ("qirizar","Rizqi Abdul Rafi","jombloku",200000);
Akun u2 = Akun ("arlanmau","Arlan Maulana","baperboy",100000);
Akun u3 = Akun ("","","",0); //slot untuk akun baru saat daftar

/*<<------------------------------------- PEMBATAS ------------------------------------->>*/
/*<<----------------------------------- MAIN PROGRAM ----------------------------------->>*/

main()
{
    system("cls");
    awal:
    cout<<endl;
    cout<<"\t    WELCOME TO SIMPLE E-MONEY"<<endl;
    cout<<"\t Tekan 'Enter' untuk melanjutkan"<<endl;
    getch();
    system("cls");
    cout<<endl;
    cout<<"\t(1) Masuk dengan Akunmu"<<endl;
    cout<<"\t(2) Belum punya akun?"<<endl;
    cout<<"\t(0) Keluar"<<endl;
    cout<<endl;
    ulang:
    cout<<"\tMasukkan pilihanmu: "; cin>>m;

    switch(m)
    {
        case 0: goto akhir;
        case 1: masuk(); break;
        case 2: daftar(); break;
        default:
            cout<<"    !Pilihan tidak tersedia!"<<endl<<endl;
            goto ulang;
    }

    akhir:
    return 0;
}

/*<<------------------------------------- PEMBATAS ------------------------------------->>*/
/*<<------------------------------ LOG IN & DAFTAR AKUN -------------------------------->>*/

void daftar()
{
    system("cls");
    cout<<endl;
    cout<<"\t \tIsi Data berikut"<<endl;
    cout<<endl;
    cout<<"\tUsername: "; cin>>user;
    if(strlen(user)<4||strlen(user)>=13){
        system("cls");
        cout<<endl;
        cout<<"\t Username harus berisi 4-12 karakter";
        getch();
        daftar();
    }
    cin.ignore();
    cout<<"\tNama    : "; cin.getline(nam,100);
    cout<<"\tPassword: "; cin>>pass;
    if(strlen(pass)<4||strlen(pass)>=9){
        system("cls");
        cout<<endl;
        cout<<"\t Password harus berisi 4-8 karakter";
        getch();
        daftar();
    }
    system("cls");
    cout<<endl;
    cout<<"\t Username: "<<user<<endl;
    cout<<"\t Nama    : "<<nam<<endl;
    cout<<"\t Password: "<<pass<<endl;
    cout<<"\n\tApakah data diatas sudah benar (Y/N)?"; cin>>g;
    if(g!='Y'){
        if(g=='N'){
            daftar();
        }else{
            system("cls");
            cout<<"\n\t pilihan tidak terdaftar"<<endl<<"\tGunakan huruf kapital";
            getch();
            daftar();
        }
    }

    u3.uname=user;
    u3.nama=nam;
    u3.pasw=pass;
    u3.saldo+=5000;
    system("cls");
    cout<<endl;
    cout<<"\tSelamat Anda sudah terdaftar di E-Money"<<endl;
    cout<<"\t\tSaldo Awal Anda Rp5000"<<endl;
    getch();
    masuk();
}

void masuk()
{
    system("cls");
    cout<<endl;
    cout<<"\t \tLOG IN"<<endl;
    cout<<endl;
    cout<<"\tUsername: "; cin>>user;
    if(strlen(user)<4||strlen(user)>=13){
        system("cls");
        cout<<endl;
        cout<<"\t Username harus berisi 4-12 karakter";
        getch();
        masuk();
    }
    cout<<"\tPassword: "; cin>>pass;
    if(strlen(pass)<4||strlen(pass)>=9){
        system("cls");
        cout<<endl;
        cout<<"\t Password harus berisi 4-8 karakter";
        getch();
        masuk();
    }
    cout<<endl;

    if(user==u1.uname){
        if(pass==u1.pasw){
            u=&u1;
            s=1;
            awal();
        } else {
            pilll:
            system("cls");
            cout<<endl;
            cout<<"   Username dan Password tidak terdaftar"<<endl;
            cout<<"        Ingin Mendaftar (Y/N) ? ";
            cin>>g;
            if(g != 'N'){
                if(g == 'Y'){
                    daftar();
                } else {
                    system("cls");
                    cout<<endl;
                    cout<<"\tPilihan tidak tersedia"<<endl<<"\tGunakan huruf kapital";
                    getch();
                    goto pilll;
                }
            } else masuk();
        }
    } else if(user==u2.uname){
        if(pass==u2.pasw){
            u=&u2;
            s=2;
            awal();
        } else goto pilll;
    } else if(user==u3.uname){
        if(pass==u3.pasw){
            u=&u3;
            s=3;
            awal();
        }else goto pilll;
    } else{
        goto pilll;
    }
}

/*<<------------------------------------- PEMBATAS ------------------------------------->>*/
/*<<---------------------------------- SETELAH LOG IN ---------------------------------->>*/

void awal()
{
    system("cls");
    cout<<endl;
    cout<<"\tSelamat datang, "<<u->getNama()<<"!"<<endl;
    getch();
    system("cls");
    cout<<endl;
    cout<<"\tSaldo Anda saat ini Rp "<<u->getSaldo()<<endl<<endl;
    cout<<"\t (1) Isi Saldo"<<endl;
    cout<<"\t (2) Transfer Saldo"<<endl;
    cout<<"\t (3) Beli Pulsa"<<endl;
    cout<<"\t (4) Ganti Password"<<endl;
    cout<<"\t (0) Log Out"<<endl;
    cout<<endl;
    cout<<"\tMasukkan Pilihanmu: "; cin>>m;

    switch(m)
    {
        case 0: main();break;
        case 1: isi();break;
        case 2: trf();break;
        case 3: ipul();break;
        case 4: ganti();break;
        default:
            system("cls");
            cout<<endl;
            cout<<"\tPilihan tidak tersedia";
            getch();
            awal();
    }
}

/*<<------------------------------------- PEMBATAS ------------------------------------->>*/
/*<<----------------------------------- FUNGSI LAIN ------------------------------------>>*/

void isi()
{
    system("cls");
    cout<<endl;
    cout<<"\tNominal Pengisian: Rp"; cin>>m;
    i=m%5000;
    if(i != 0)
    {
        system("cls");
        cout<<endl;
        cout<<"\tNominal pengisian kelipatan Rp5000";
        getch();
        isi();
    }
    system("cls");
    cout<<endl;
    cout<<"\tMasukkan password kamu: "; cin>>y;
    if(y != u->getPass())
    {
        system("cls");
        cout<<endl;
        cout<<"\tPassword Salah";
        getch();
        isi();
    }
    ggg:
    system("cls");
    cout<<endl;
    cout<<"\tApa anda yakin akan melakukan transaksi berikut: "<<endl;
    cout<<"\t  Isi Saldo"<<endl;
    cout<<"\t  Nominal: Rp"<<m<<endl;
    cout<<"\t(Y/N) : ";
    cin>>g;
    if(g != 'Y'){
        if(g == 'N'){
            awal();
        } else {
            system("cls");
            cout<<endl;
            cout<<"Pilihan tidak tersedia"<<endl<<"\tGunakan huruf kapital";
            getch();
            goto ggg;
        }
    }

    system("cls");
    if(s==1) u1.saldo += m;
    else if(s==2) u2.saldo += m;
    else if(s==3) u3.saldo += m;

    cout<<endl;
    cout<<"\tPengisian Saldo sebesar Rp"<<m<<" Berhasil"<<endl;
    getch();
    awal();
}

void trf()
{
    system("cls");
    cout<<endl;
    cout<<"\tNominal yang akan ditransfer: Rp"; cin>>m;
    i=(m%5000);
    if(i != 0)
    {
        system("cls");
        cout<<endl;
        cout<<"\tNominal transfer kelipatan Rp5000";
        getch();
        trf();
    }

    system("cls");
    cout<<endl;
    cout<<"\tUsername akun yang akan ditransfer: "; cin>>user;
    if(user == u1.uname){
    } else if(user == u2.uname){
    } else if(user == u3.uname){
    } else {
        system("cls");
        cout<<endl;
        cout<<"\tUsername tidak terdaftar";
        getch();
        trf();
    }

    system("cls");
    cout<<endl;
    cout<<"\tMasukkan password kamu: "; cin>>y;
    if(y != u->getPass())
    {
        system("cls");
        cout<<endl;
        cout<<"\tPassword Salah";
        getch();
        isi();
    }
    ttt:
    system("cls");
    cout<<endl;
    cout<<"\tApa anda yakin akan melakukan transaksi berikut: "<<endl;
    cout<<"\t  Tranfer saldo"<<endl;
    cout<<"\t  Nominal: Rp"<<m<<endl;
    cout<<"\t  Kepada : ";
    if(user == u1.uname) cout<<u1.nama<<endl;
    if(user == u2.uname) cout<<u2.nama<<endl;
    if(user == u3.uname) cout<<u3.nama<<endl;
    cout<<"\t(Y/N) : ";
    cin>>g;
    if(g != 'Y'){
        if(g == 'N') trf();
        else {
            system("cls");
            cout<<"\n\tPilihan tidak tersedia"<<endl<<"\tGunakan huruf kapital";
            getch();
            goto ttt;
        }
    system("cls");
        u1.saldo += m;
    } else if(user != u2.uname){
        u2.saldo += m;
    } else if(user != u3.uname){
        u3.saldo += m;
    }
    if(s=1) u1.saldo-=m;
    else if(s=2) u2.saldo-=m;
    else if(s=3) u3.saldo-=m;

    cout<<endl;
    cout<<"\tTransfer Berhasil"<<endl;
    cout<<"\tSisa saldo anda Rp "<<u->getSaldo();
    getch();
    awal();

}

void ipul()
{
    system("cls");
    cout<<"\n\tMasukkan nominal pulsa: Rp"; cin>>m;
    i=m%5000;
    if(i != 0)
    {
        system("cls");
        cout<<endl;
        cout<<"\tNominal pengisian kelipatan Rp5000";
        getch();
        ipul();
    }
    system("cls");
    cout<<"\n\tMasukkan nomor yang akan diisi: "; cin>>no;
    if (strlen(no)<11||strlen(no)>=13){
        system("cls");
        cout<<"\n\tMasukkan nomor telpon dengan benar";
        getch();
        ipul();
    }
    system("cls");
    cout<<endl;
    cout<<"\tMasukkan password kamu: "; cin>>y;
    if(y != u->getPass())
    {
        system("cls");
        cout<<endl;
        cout<<"\tPassword Salah";
        getch();
        ipul();
    }

    jjj:
    system("cls");
    cout<<endl;
    cout<<"\tApa anda yakin akan melakukan transaksi berikut: "<<endl;
    cout<<"\t  Isi Pulsa"<<endl;
    cout<<"\t  Nominal: Rp"<<m<<endl;
    cout<<"\t  Nomor  : "<<no<<endl;
    i=m+1000;
    cout<<"\t  Harga  : Rp"<<i;
    cout<<"\n\t(Y/N) : ";
    cin>>g;
    if(g != 'Y'){
        if(g == 'N'){
            awal();
        } else {
            system("cls");
            cout<<endl;
            cout<<"Pilihan tidak tersedia";
            getch();
            goto jjj;
        }
    }

    system("cls");
    if(s=1) u1.saldo-=i;
    else if(s=2) u2.saldo-=i;
    else if(s=3) u3.saldo-=i;
    cout<<"\n\t Pengisian pulsa sebesar Rp"<<m<<" Berhasil"<<endl;
    cout<<"\t  Sisa saldo anda saat ini Rp"<<u->getSaldo();
    getch();
    awal();
}

void ganti()
{
    system("cls");
    cout<<"\n\tmasukkan password saat ini: "; cin>>pass;
    if(pass!=(u->getPass())){
        system("cls");
        cout<<"\n\tPassword Salah";
        getch();
        ganti();
    }
    system("cls");
    cin.ignore();
    cout<<"\n\tmasukkan password baru: "; cin.getline(pass,8);
    if(strlen(pass)<4||strlen(pass)>=9){
        system("cls");
        cout<<endl;
        cout<<"\t Password harus berisi 4-8 karakter";
        getch();
        ganti();
    }
    mmm:
    system("cls");
    cout<<endl;
    cout<<"\tApa anda yakin ingin mengganti password (Y/N) ? ";
    cin>>g;
    if(g != 'Y'){
        if(g == 'N'){
            awal();
        } else {
            system("cls");
            cout<<endl;
            cout<<"Pilihan tidak tersedia"<<endl<<"\tGunakan huruf kapital";
            getch();
            goto mmm;
        }
    }

    if(s=1) u1.pasw=pass;
    else if(s=2) u2.pasw=pass;
    else if(s=3) u3.pasw=pass;
    system("cls");
    cout<<"\n\tGanti password berhasil";
    getch();
    awal();
}

