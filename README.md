# Meghitung-gaji-karyawan


        #include<iostream>
        #include <cstdlib>
        #include <cstring>
        using namespace std;

        int kata;
        char val [100];

        int validasi()
        {
            do

            {
                kata=0;
                cin>>val;
                for(int i=0; i<strlen(val); i++)
                {
                    if(isdigit(val[i])==0)
                        kata++;
                }
                if(kata !=0)
                    cout<<"\t\tInput salah !\n"<<endl;

            }
         while(kata!=0);
            return 0;
        }


        class pegawai {
         public :
          int nip;
          char nama[30];
         private:
          int x;
         public:
          int b;
          void assign(int a);
          int waktunormal() {
              return 8*5000;
          }
          int waktulembur() {
              b=x-8;
           return b*(10*5000);
          }
        };

        //Prototipe fungtion
        void pegawai::assign(int a)
        {
            x=a;
        }

        int main()

        {
         cout<<"\n|=======================================================|";
         cout<<"\n|================= ALIF MUSTAFANAH =====================|";
         cout<<"\n|===================== PROGRAM =========================|";
         cout<<"\n|============== MENGHITUNG GAJI KARYAWAN ===============|";
         cout<<"\n|=======================================================|\n";

         int jam, hasil;
         pegawai pgw;
         cout<<"\n____________________________________\n";
         cout<<"Masukkan nama : ";
         cin.getline(pgw.nama,23);
         cout<<"Masukkan nip  : ";
         validasi(); pgw.nip=atoi(val);

         balik:
         cout<<"Masukkan jumlah jam kerja : ";
         validasi(); jam=atoi(val);
         pgw.assign(jam);
         if (jam==8)
          hasil=pgw.waktunormal();
         else if (jam>8)
          hasil=pgw.waktulembur()+pgw.waktunormal();
         else {
          cout<<"Jumlah jam kerja minimal adalah 8 jam "<<endl;
          goto balik;
         }

         cout<<"\n____________________________________\n";
         cout<<"NIP  : "<<pgw.nip<<endl;
         cout<<"Nama : "<<pgw.nama<<endl;
         cout<<"Jumlah jam kerja "<<jam<<" jam "<<endl;
         cout<<"Total upah : "<<hasil;
          cout<<"\n____________________________________\n";
          cout<<"\n|===================== TERIMAKASIH =====================|";
          cout<<"\n|================ PRESS ENTER TO EXIT ==================|";

         return 0;

        }
