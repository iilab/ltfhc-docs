
# Demo Model - Lagos/1001


B0: Uses normal HF data modem response codes.
E1: (default) Enables command echo.
L0: (default) Disables local echo of data entered while connected.
X4 V1 Q0 R0 W0  : ????

&A=1 : Enables automatic answering of all calls.

&C=0,0,0,0,0 : Sets up the list of channels to be used by the 3212 during a data call in a Selcall network. Up to five channels may be specified. The maximum length of the command line is 37 characters including
commas.

&D=0 : (default) Ignores DTR input.

&E=43 : (default) Sets the escape sequence character to the specified ASCII value. Default value is 43 (+).

&I=1001 : Sets the local station address (up to 6 digits). The default address is derived from the MAC address of the 3212.

&K=3 : Switches on RTS/CTS (hardware) flow control.

&M=6 : Sets the modulation method - COMMERCIAL4539 waveform

&R=1002 : Displays the address of the remote node that is
currently, or was last connected.

&S=1621774705 : Displays the serial number of the 3212.

&T=6 : 

&U=0 
%B=10 %C=2 %D=1,1,10,6,1 %F=3,0 %H=0 %L=1 %T=-10,30,20 %M=0 %N="" %R=0 
*B=0 *I=0,"192.168.3.212","255.255.255.0","192.168.3.1" *P=50000 
S00=     1 S01=     0 S02=     1 S03=  1002 S04=     0 S05=     0
S06=     0 S07=     0 S08=     0 S09=     0 S10=     0 S11=     0
S12=     0 S13=     0 S14=     0 S15=     0 S16=     0 S17=     0
S18=     0 S19=     0 S20= 26520 S21=    21 S22=  2472 S23=     1
S24=    43 S25=    13 S26=    10 S27=     8 S28=    50 S29=   336
S30=    71 S31=     3 S32=   100 S33=  5066 S34=    41 S35= 18073
S39=  1252 S40=   -10 S41= 26520 S42=    86 S43=     0 S44=     0
S45=  6995 S46=     0 S47=     0 S56=  1001 S58=     6 S60=     0
S61="192.168.3.212"   S62="255.255.255.0"   S63="192.168.3.1"
S64= 50000 S65=     0 S66=    "" S67=   -10 S68=    30 S69=    20
S70=  6995 S71=     0 S72=     0 S73=     0 S74=     0 S75=     0
S76=     0 S82=   208 
&Z0=       &Z1=       &Z2=       &Z3=       
Last dialled = 



AT&V
B0 E1 L0 X4 V1 Q0 R0 W0 
&A=1 &C=0,0,0,0,0 &D=0 &E=43 &I=1001 &K=3 &M=6 &R=1002 &S=1621774705 &T=6 &U=0 
%B=10 %C=2 %D=1,1,10,6,1 %F=3,0 %H=0 %L=1 %T=-10,30,20 %M=0 %N="" %R=0 
*B=0 *I=0,"192.168.3.212","255.255.255.0","192.168.3.1" *P=50000 
S00=     1 S01=     0 S02=     1 S03=  1002 S04=     0 S05=     0
S06=     0 S07=     0 S08=     0 S09=     0 S10=     0 S11=     0
S12=     0 S13=     0 S14=     0 S15=     0 S16=     0 S17=     0
S18=     0 S19=     0 S20= 26520 S21=    21 S22=  2472 S23=     1
S24=    43 S25=    13 S26=    10 S27=     8 S28=    50 S29=   336
S30=    71 S31=     3 S32=   100 S33=  5066 S34=    41 S35= 18073
S39=  1252 S40=   -10 S41= 26520 S42=    86 S43=     0 S44=     0
S45=  6995 S46=     0 S47=     0 S56=  1001 S58=     6 S60=     0
S61="192.168.3.212"   S62="255.255.255.0"   S63="192.168.3.1"
S64= 50000 S65=     0 S66=    "" S67=   -10 S68=    30 S69=    20
S70=  6995 S71=     0 S72=     0 S73=     0 S74=     0 S75=     0
S76=     0 S82=   208 
&Z0=       &Z1=       &Z2=       &Z3=       
Last dialled = 

# Demo Model - Abuja/1002

AT&V
B0 E1 L0 X4 V1 Q0 R0 W0 
&A=1 &C=0,0,0,0,0 &D=0 &E=43 &I=1002 &K=3 &M=6 &R=1001 &S=1621774667 &T=6 &U=0 
%B=10 %C=2 %D=1,1,10,6,1 %F=3,0 %H=0 %L=1 %T=-10,30,20 %M=0 %N="" %R=0 
*B=0 *I=0,"192.168.3.212","255.255.255.0","192.168.3.1" *P=50000 
S00=     1 S01=     0 S02=     1 S03=  1001 S04=     0 S05=     0
S06=     0 S07=     0 S08=     0 S09=     0 S10=     0 S11=     0
S12=     0 S13=     0 S14=     0 S15=     0 S16=     0 S17=     0
S18=     0 S19=     0 S20=     0 S21=     0 S22=     0 S23=     0
S24=    43 S25=    13 S26=    10 S27=     8 S28=    50 S29=   336
S30=    71 S31=     3 S32=   100 S33=  5066 S34=    41 S35= 18073
S39=     0 S40=     0 S41=     0 S42=   100 S43=     0 S44=     0
S45=  6995 S46=     0 S47=     0 S56=  1002 S58=     6 S60=     0
S61="192.168.3.212"   S62="255.255.255.0"   S63="192.168.3.1"
S64= 50000 S65=     0 S66=    "" S67=   -10 S68=    30 S69=    20
S70=  6995 S71=     0 S72=     0 S73=     0 S74=     0 S75=     0
S76=     0 S82=   208 
&Z0=       &Z1=       &Z2=       &Z3=       
Last dialled = 1001