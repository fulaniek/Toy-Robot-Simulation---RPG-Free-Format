# Toy-Robot-Simulation---RPG-Free-Format
Steps to :
Download TOY ROBOT-RPG FREE.zip file
Extract the file
Upload to AS400
COMPILE DISPLAY FILE TOYRD :
===> CRTDSPF   FILE(NIM231/TOYRD) SRCFILE(NIM231/QDDSSRC) SRCMBR(TOYRD) ??REPLACE(*YES)   
COMPILE MODULES TOYR & TOYRBTR: 
1. CRTRPGMOD   MODULE(*CURLIB/TOYRBTR) SRCFILE(*CURLIB/QRPGLESRC) SRCMBR(TOYRBTR) ??ADD(*YES)                                               
2.CRTRPGMOD   MODULE(*CURLIB/TOYR) SRCFILE(*CURLIB/QRPGLESRC) SRCMBR(TOYR) ??ADD(*YES) 
Create Service Program : CRTSRVPGM SRVPGM(*CURLIB/TOYR) MODULE(TOYR) EXPORT(*ALL)
Create Program : CRTPGM PGM(TOYRBTR) MODULE(TOYRBTR) BNDSRVPGM((*CURLIB/TOYR))
Call the proram : CALL *CURLIB/TOYRBTR
