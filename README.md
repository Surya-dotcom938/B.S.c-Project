# B.S.c-Project
Voice based engine starting system
#include<pic.h>
#include"pic_lcd4.h"
#include"pic_adc.h"
#include"pic_serial.h"

#define relay RC0

void Mobile_Init();
void Msg_Send();
void Msg_send1();

void set_receive_timer();

void send_data(unsigned int);
void send_msg();
void ultrasonic();

void msg_send_start();
bit vv=0;
bit rr=0;

unsigned char a[80],m=0,d=0,read=0,rec,act=1,unit=1,gas=0,m,tem,ab[30],mm;
unsigned char mon,dat,hh,min,act_time=0,sec2,ldr;

unsignedint
count1=0,inch1,inch2,inch3,result,tempr,count,dis1,dis2,dis3,dis,load_cell;

unsigned char il,b[15],h,sec,k,c,i,aa,bb,rx[10],k1;

unsigned char m_sec,gg=0,sec1,id=0;

unsigned char curr,reading,limit=1,pf;

void interrupt timer2(void)
{
if(RCIF==1)
{
RCIF=0;

a[m] = RCREG;
m++;
//if(a[0]==
}
 }
void main()
{
int 1_i=0;
ADCON1=0x02;
TRISA=0xFF;
TRISB=0x01;
TRISC=0xC0;
TRISD=0x00;
TRISE=0b111;

Lcd4_Init();
Delay(5000);
PORTB=0xFF;
Serial_Init(9600);
Receive(0);
Lcd4_Display(0x80,"VOICE BASED ENGINE STARTING SYSTEM",16);
Delay(65000);
relay = 1;

Delay(65000):Delay(65000);

Lcd4_Command(0x01);
Delay(65000);
Lcd4_Command(0x0C);

//Msg_Send();
Receiver(1);

while(1)
{
gas = Adc8_Cha(1);
Lcd4_Decimal3(0xc0,gas);
tem = Adc8_Cha(0)-10;
sec++;
Delay(500);

Lcd4_Display(0x80,"T:",2);
Lcd4_Decimal(0x82,tem);
Lcd4_Decimal3(0x89,sec);

if(tem>40 || gas>100)
{
relay = 1;
}
if(m>1)
{
for(int i=0;i<=3;i++)
{
Lcd4_Write(0xc5+i,a[i]);
}
if(a[0]=='o'&& a[1]=='n'{relay=0;}
if(a[0]=='o'&& a[1]=='f'{relay=1;}

m=0;
}


}


}
void send_data(unsigned int jk)
{
Serial_Out(jk%10000/1000+0x30);
Serial_Out(jk%1000/100+0x30);
Serial_Out(jk%100/10+0x30);
Serial_Out(jk%10/1+0x30);
}
