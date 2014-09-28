AT?
             CODAN 3212 HF MODEM HELP MENU
             Copyright (C) 2008 Codan Limited
             
       * indicates default setting
       
A      Answer incoming call
         1* Answer call
         2  Reject call if sender unit > 0
         3  Reject call
         H  As above
B      Telephone compatibility mode
         0* Disabled
         1  Enabled
D      Dial number to initiate call
         D               start a broadcast call
         D<addr>         call station at <addr>
         D<addr>!<chan>  call address using specified channel
         D<addr>00       make a group call
         DS=<n>          call address stored in AT&Z<n>
         DL              call previous address  
E      Command Echo
         0  Off
         1* On
F      Full/half duplex when connected, also known as Local Data Echo
       (applies only if the telephone compatibility mode is enabled)
         0* Disabled
         1  Enabled
H      Hang up
         0  Disconnect & discard unsent data     
         1  Ignore incoming calls
         2  Disconnect when all data sent
         3  Disconnect without informing remote end
I      Information about modem
         0* Hardware & Firmware revision numbers
         1  Equipment name
         2  Copyright notice
         3  Assembly number
         4  Firmware distribution number
         5  Serial number
         9  Plug and Play response
L      Full/half duplex when connected, also known as Local Data Echo
       (applies only if the telephone compatibility mode is disabled)
         0* Disabled
         1  Enabled
O      Online mode - return to connect state
         0* Keep connection going
         1  Disconnect when no more queued data
         H  As above
Q      Result code suppression control
         0* Disabled (no suppression)
         1  Enabled
R      Remote Data Echo                                                     
         0* Disabled
         1  Enabled
S0     Auto Answer (duplicates AT&A=n)
         0* Off
         1  On, Answer all calls
         2  On, Reject if sender unit > 0
         3  On, Reject all calls
S20?   Total bits received for current link
S22?   Total bits sent for current link
S39?   Link connect time in seconds
S40?   Frequency offset of last link in Hz
S41?   Number of correct bits received per error bit
S44?   Unit address of sending station
S45?   Channel connected on if known
V      Verbose responses
         0  Numeric codes
         1* Text messages
W      Warning and information messages
         0* No messages
         1  Explain error codes
         2  Show connect info
         3  Both items 1 & 2
Z      Modem reset                                                          
         0* Reload modem settings from non-volatile memory (soft reset)
         1  Perform full modem reset (hard reset)
%B     Fixed baud rate selection for COMMERCIAL4539/STANAG5066 mode
         1    75 bps   2    150 bps
         3   300 bps   4    600 bps
         5  1200 bps   6   2400 bps
         7  3600 bps   8   4800 bps
         9  6000 bps   10* 7200 bps
%C     Compression
         0  Disabled
         1  (Reserved)
         2* Enabled
%D     Dynamic Rate Control settings for COMMERCIAL4539/STANAG5066 mode
         <en>,<low>,<high>,<init>,<intr>
           en: select fixed or dynamic rate control
               0  Disable DRC
               1* Enable DRC
           low: low rate bound for dynamic control
               1*   75 bps    2   150 bps
               3   300 bps    4   600 bps
               5  1200 bps    6  2400 bps
               7  3600 bps    8  4800 bps
               9  6000 bps   10  7200 bps                                   
           high: high rate bound for dynamic control
               Same rates set as for low rate bound, default is
               10* 7200 bps
           init: initial rate selection
               Same rates set as for low rate bound, plus a special value - 
               zero, which ties the initial rate selection to the LQA report
               received from the transceiver. Default is
               6* 2400 bps
           intr: initial interleaving length for automatic selection
               1* Short
               2  Medium (allowed only for high initial rates: 2400 to 7200 bps)
               3  Long
%F     Asynchronous data port framing and parity selection
         <frm>,<par>
           frm: data port framing
               1  8N2     8 data bits, no parity, 2 stop bits
               2  8O1/8E1 8 data bits, 1 parity bit, 1 stop bit
               3* 8N1     8 data bits, no parity, 1 stop bit
               4  7N2     7 data bits, no parity, 2 stop bits
               5  7O1/7E1 7 data bits, 1 parity bit, 1 stop bit
               6  7N1     7 data bits, no parity, 1 stop bit
           par: data port parity
               0* Odd                                                       
               1  Even
%H     Chat mode for outgoing STANAG5066 links
       Reduces round trip-time at the expense of permanent HF channel occupation
         0* Disabled
         1  Enabled
%L     Fixed interleaver length selection for COMMERCIAL4539/STANAG5066 mode
         1* Short
         2  Medium
         3  Long
%M     Connection method selection
         0* CLE (Codan 3012 compatible)
         1  COMMERCIAL4539/STANAG5066
%N     ALE network name selection
       If not empty, then ALE addresses have the form:
         "<addr>@<ALE network name>"
         "ASCII string", default = ""
%R     Asynchronous data port rate selection
         0* Autobauding
         1      75 bps   2      150 bps
         3     300 bps   4      600 bps
         5    1200 bps   6     2400 bps
         7    4800 bps   8     9600 bps
         9   19200 bps   10   38400 bps                                     
         11  57600 bps   12  115200 bps
%T     Transceiver audio interface settings
         <audioLevel>,<minAlcTime>,<hangUpTime>
           audioLevel: audio output level in dBm, -30 to 10
           minAlcTime: minimum ALC circuit training time in ms, 10 to 10000
           hangUpTime: delay between the end of transmission 
                       and PTT deassertion in ms, 10..250
&A     Auto answer parameter (duplicates ATS0)
         0* Off
         1  On, Answer all calls
         2  On, Reject if sender unit > 0
         3  On, Reject all calls
&C     Channel selection command (applies only if CLE is selected for 
       the connection method)
         0*                     Cancel channel control
         <ch>                   Select channel 1-9999 now
         <ch1>,<ch2>,...,<ch5>  List for next call
&D     DTR behaviour assuming ON-to-OFF transition
         0* Ignored
         1  Modem assumes command state
         2  Modem hangs up and disables auto answer
         3  Modem performs reset
         4  Modem hangs up or if OFF-to-ON transition,                      
            calls number stored in &Z0
&E     Escape character
         0 to 255, default = 43 i.e. '+'
&F     Factory default all modem settings
&I     Identification code (<addr>) for modem
         1 to 999999, default derived from MAC address
&K     Handshaking behaviour
         0  None
         1  Not defined
         2  Not defined
         3* Hardware using RTS/CTS
&M     Modulation method (applies when AT%M=0)
         0  4 channels QPSK, not secure
         1  8 channels QPSK, not secure
         2  12 channels QPSK, not secure
         3  16 channels QPSK, not secure
         4  16 channels QPSK, secure
         5  16 channels QPSK, secure, interactive
         6* COMMERCIAL4539 waveform
&R?    Remote identification code (<addr>) for last call
&S?    Serial number of modem
&T     Test mode
         3  Digital loopback                                                
         4  Audio loopback
         6* Normal operation
&U     Set unit number sub-address
         0* to 15; 16 to 31 reserved
&V     View all settings
&W     Write all settings to non-volatile memory
&Z0    Stored destination address
         1 to 999999
         To clear, use AT&Z0=
&Z1    As for &Z0
&Z2    As for &Z0
&Z3    As for &Z0
*B?    Type of link for last connection
         0  Selective
         1  Group broadcast
         2  Global broadcast
*I     IP/Ethernet interface settings
         <dhcpEn>,"<ipAddr>","<netmask>","<gateway>"
         *0,"192.168.3.212","255.255.255.0","192.168.3.1"
           dhcpEn:  IP settings allocation method
               0* Do not use DHCP (static IP allocation)
               1  Use DHCP to configure ethernet interface
           ipAddr:  IP address of modem                                     
           netmask: IP subnet mask
           gateway: IP address of gateway
*M?    Show MAC address of modem
*P     Base port number selection  <1 to 65535>
        *50000
         Data Port = base port + 0
         Service Port = base port + 1
?      Help on commands - specify letters to search (e.g. at?&I)