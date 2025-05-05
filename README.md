# ContrastSwitch
Programs, that will either turn on or turn off High contrast on Windows 10.

This program was created and compiled in AutoHotkey32 v2.0.
There are 2 programs that will either turn on or turn off High contrast. Both of them were signed, but not with verified certificate.

I take NO responsibility for your actions with these programs, use them only with permissions that you have been given.

This is script, that was in AutoHotkey v2.0 before compilation:

 ;vFlags := 0x1 ;on
 vFlags := 0x0 ;off
 vSize := A_PtrSize=8?16:12
 VarSetCapacity(HIGHCONTRAST, vSize, 0)
 NumPut(vSize, &HIGHCONTRAST, 0, "UInt") ;cbSize
 ;HCF_HIGHCONTRASTON := 0x1
 NumPut(vFlags, &HIGHCONTRAST, 4, "UInt") ;dwFlags
 ;SPI_SETHIGHCONTRAST := 0x43
 DllCall("user32\SystemParametersInfo", UInt,0x43, UInt,vSize, Ptr,&HIGHCONTRAST, UInt,0)
 return
