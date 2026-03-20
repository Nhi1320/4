#include <iostream>
using namespace std;

bool NamNhuan(int Nam)
{
    if (Nam % 400 == 0 || Nam % 4 == 0 && Nam % 100 != 0) return true;
    return false;
}

int NgayTrongThang(int Thang, int Nam)
{
    switch(Thang)
    {
    case 1: case 3: case 5: case 7: case 8: case 10:case 12:
        return 31;
        break;

    case 2:
        return NamNhuan(Nam) ? 29 : 28;
        break;

    case 4: case 6: case 9: case 11:
        return 30;
        break;

    default: return 0;
    }
}

bool KiemTraHopLe(int Ngay, int Thang, int Nam)
{
    if (Thang <1 || Thang >12) return false;
        return 1;
    return 0;
}


void NgayKeTiep(int Ngay,int Thang,int Nam)
{
    if(KiemTraHopLe(Ngay,Thang,Nam)==0) return;
    if(Ngay == NgayTrongThang(Thang,Nam))
 {
     if(Thang==12)
     {
         Nam++;
         cout<<"1"<<'/'<<"1"<<'/'<<Nam<<endl;
     }

     else
     {
         Thang ++;
        cout << "1" << "/" << Thang << "/" << Nam << endl;
     }
 }
 else if(Ngay<NgayTrongThang(Thang,Nam))
 {
     Ngay++;
     cout<<Ngay<<'/'<<Thang<<'/'<<Nam<<endl;
 }
 else
 {
     cout<< "Ngay khong hop le. "<<endl;
 }
}

int main()
{
    int Ngay, Thang, Nam;
    cout<< "Nhap ngay: "<<endl;
    cin>> Ngay;
    cout<< "Nhap thang: "<<endl;
    cin>> Thang;
    cout<< "Nhap nam: "<<endl;
    cin>> Nam;

    cout<< "Ngay ke tiep la: " << endl;
    NgayKeTiep(Ngay,Thang,Nam)
;
    return 0;
}
