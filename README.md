#include<iostream>
#include<string.h>
#include<iomanip>
using namespace std;
struct nhanvien
{
	int mnv;
	string hoten,gioitinh,phongban,thidua;
    double ngaycong,luong,phucap,thuclinh;
};
nhanvien nv [100];

void nhap(nhanvien nv[],int n)
{
	for (int i=0;i<n;i++)
	{
		cout<<"\nNhan vien thu: "<<i+1<<""<<endl;
		cout<<"Ma nhan vien "<<i+1<<":";cin>>nv[i].mnv;
		fflush(stdin);
		cout<<"Ho ten nhan vien: ";getline(std::cin,nv[i].hoten);
		cout<<"Gioi tinh(Nam/Nu): ";getline(std::cin,nv[i].gioitinh);
		fflush(stdin);
		cout<<"Ngay cong: ";cin>>nv[i].ngaycong;
		cout<<"Phong ban: ";cin>>nv[i].phongban;
		cout<<"Luong: ";cin>>nv[i].luong;
		cout<<"Phu cap: ";cin>>nv[i].phucap;
		cout<<"Thi dua: ";cin>>nv[i].thidua;
		nv[i].thuclinh=(nv[i].luong+nv[i].phucap);
		cout<<"Thuc linh la: "<<nv[i].thuclinh<<endl;
		
			
	}
}
void xuat(nhanvien nv[],int n)
{
	cout<<"\nMa nhan vien";
	cout<<setw(20)<<"Hotennhanvien"<<setw(10)<<"Gioitinh";
	cout<<setw(10)<<"Ngaycong"<<setw(10)<<"Phongban";
	cout<<setw(10)<<"Luong"<<setw(10)<<"Phucap";
	cout<<setw(10)<<"Thidua"<<setw(10)<<"Thuclinh";
	for(int i=0;i<n;i++)
	{
		cout<<""<<setw(9)<<nv[i].mnv<<setw(20)<<nv[i].hoten;
		cout<<""<<setw(15)<<nv[i].gioitinh<<setw(12)<<nv[i].ngaycong;
		cout<<""<<setw(12)<<nv[i].phongban<<setw(10)<<nv[i].luong;
		cout<<""<<setw(10)<<nv[i].phucap<<setw(10)<<nv[i].thidua<<setw(10)<<nv[i].thuclinh<<endl;
	}
}

void Thidua(nhanvien nv[],int n)
{
	for(int i=0;i<n;i++)
	{
		if(nv[i].ngaycong>=26)
		{
			cout<<setw(10)<<nv[i].thidua<<" :Ngay cong >= 26 Loai =>> Xuat Sac. "<<endl;
		}
	else if(nv[i].ngaycong>=23)
	{
		cout<<setw(10)<<nv[i].thidua<<" :Ngaycong >= 23 Loai =>> Tot."<<endl;
	}
	else if(nv[i].ngaycong<23)
	{
		cout<<setw(10)<<nv[i].thidua<<" :Ngaycong < 23 =>> Khong Dat."<<endl;
	}
	}
}

void phucapMinMax(nhanvien nv[],int n)
{
	float min=nv[0].phucap;
	float max=nv[0].phucap;
	
        for(int i=0;i<n;i++)
		{
			if(nv[i].phucap<min)
			{
				if(nv[i].phucap<min)
				{
				 min=nv[i].phucap;
		        }
			}
	}
	cout<<"\n Phu cap thap nhat: "<<min<<endl;
	for(int i=0;i<n;i++)
	{
			if (nv[i].phucap>max)
			{
			    max=nv[i].phucap;	
			}
		}
		cout<<"\n Phu cap cao nhat: "<<max<<endl;			
       	
}

void luongmax(nhanvien nv[],int n)
{
	float max=0;
	for(int i=0;i<n;i++)
	{
		if(nv[i].luong>max)
		{
			max=nv[i].luong;
		}
	}
	cout<<"\n  Nhan vien co luong cao nhat: "<<max<<endl;
}


void sapxep(nhanvien nv[],int n)
{
	nhanvien tg;
	for(int i=0;i<n-1;i++)
	{
		for(int j=i=1;j<n;j++)
		{
			if(nv[i].phucap>nv[j].phucap)
			{
				tg = nv[i];
				nv[i] = nv[j];
				nv[j] = tg;
				
			}
		}
	}
	cout<<"\nSau khi sap xep la: ";
	for(int i=0;i<n;i++)
	{
	cout<<"\nManhanvien";
	cout<<setw(20)<<"Hotenhanvien"<<setw(10)<<"Gioitinh";
	cout<<setw(10)<<"Ngaycoong"<<setw(10)<<"Phongban";
	cout<<setw(10)<<"Luong"<<setw(10)<<"Phucap";
	cout<<setw(10)<<"Thidua"<<setw(10)<<"Thuclinh";
	cout<<""<<setw(9)<<nv[i].mnv<<setw(20)<<nv[i].hoten;
	cout<<""<<setw(15)<<nv[i].gioitinh<<setw(12)<<nv[i].ngaycong;
	cout<<""<<setw(12)<<nv[i].phongban<<setw(10)<<nv[i].luong;
	cout<<""<<setw(10)<<nv[i].phucap<<setw(10)<<nv[i].thidua<<setw(10)<<nv[i].thuclinh<<endl;
	}
}

void Search(nhanvien nv[],int n)
{
	int z;
	cout<<"\nMa nhan vien can tim: ";cin>>z;
	for(int i=0;i<n;i++)
	{
		if(nv[i].mnv==z)
		{
	cout<<""<<setw(9)<<nv[i].mnv<<setw(20)<<nv[i].hoten;
	cout<<""<<setw(15)<<nv[i].gioitinh<<setw(12)<<nv[i].ngaycong;
	cout<<""<<setw(12)<<nv[i].phongban<<setw(10)<<nv[i].luong;
	cout<<""<<setw(10)<<nv[i].phucap<<setw(10)<<nv[i].thidua<<setw(10)<<nv[i].thuclinh<<endl;	
		}
	}
}

int main()
{
	int option,n;
	cout<<"Nhap so luong nhan vien: ";cin>>n;
	while(n>0)
	{
	    cout<<"\tCHUONG TRINH QUAN LY NHAN  VIEN.\t"<<endl;;
	    cout<<"========================MENU========================\n";
	    cout<<"==                                                ==\n";
	    cout<<"==        1.Nhap thong tin nhan vien.             ==\n";
	    cout<<"==        2.In ra danh sach nhan vien.            ==\n";
	    cout<<"==        3.Xep loai nhan vien.                   ==\n";
	    cout<<"==        4.Danh sach phu cap Max,Min.            ==\n";
	    cout<<"==        5.Sap xep nhan vien.                    ==\n";
	    cout<<"==        6.Tim kiem nhan vien khi nhap MSV       ==\n";
	    cout<<"==        7.Exit                                  ==\n";
	    cout<<"====================================================\n";
	    cout<<"Hay nhap tuy chon cua ban: ";
	    cin>>option;
	    switch(option)
	    {
	    	case 1:
	    		cout<<"Moi ban nhap thong tin nhan vien:\n";
	    		nhap(nv,n);
	    		cout<<"Bam phim bat ky de tiep tuc\n";
	    		system("pause");
	    		break;
	    	case 2:
	    		if(n>0)
	    		cout<<"Danh sach nhan vien la:\n";
	    		xuat(nv,n);
	    		cout<<"Bam phim bat ky de tiep tuc\n";
	    		system("pause");
	    		break;
	    	case 3:
	    		if(n>0)
	    		cout<<"Xep loai nhan vien:\n";
	    		Thidua(nv,n);
	    		cout<<"Bam phim bat ky de tiep tuc\n";
	    		system("pause");
	    		break;
	    	case 4:
	    		if(n>0)
	    		cout<<"Danh sach phu cap MaxMin:\n";
	    		phucapMinMax(nv,n);
	    		cout<<"Bam phim bat ky de tiep tuc\n";
	    		system("pause");
	    		break;
	    	case 5:
	    		if(n>0)
	    		cout<<"Sap xep nhan vien:\n";
	    		sapxep(nv,n);
	    		cout<<"Bam phim bat ky de tiep tuc\n";
	    		system("pause");
	    		break;
	    	case 6:
	    		if(n>0)
	    		Search(nv,n);
	    		cout<<"Bam phim bat ky de tiep tuc\n";
	    		system("pause");
	    		break;	
		    }
	    }   
}
