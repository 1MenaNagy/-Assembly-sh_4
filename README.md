# -Assembly-sh_4_P1
.586
.Model Flat
Include io.h
.STACK 4094
  .DATA
  num DWORD 3 ,1 ,2                   
 PstrX BYTE "please enter X ",0
 PstrY BYTE "please enter Y ",0
 PstrZ BYTE "please enter Z ",0
 PstrR BYTE "the result ",0
 Re BYTE "the Result of-(x+y-2z+1):-( "
   RE1 BYTE"            +" 
   RE2 BYTE"            - 2 * " 
   RE3 BYTE"            + 1  ) =  " 
   RE4 BYTE"            ",0 ; 25
 temp BYTE   40 DUP (?),0
 X DWORD  ? 
 Y DWORD ?
 Z DWORD ?
 tem DWORD ?

 .CODE
 MainProc PROC

                input PstrX,temp,40
				atod temp
			
				mov X,eax
					dtoa [RE1] ,X

				 input PstrY,temp,40
				atod temp
				mov Y,eax
					dtoa [RE2]  ,Y
				 input PstrZ,temp,40
				atod temp
				mov Z,eax
				dtoa [RE3]  ,Z

				mov eax ,X
				add eax , Y
				mov tem,eax
				

				mov eax , Z
				add eax ,Z
				neg eax
				add eax ,tem
				inc eax
				neg eax


				dtoa [Re4],eax
				output [PstrR],Re
				mov eax,0
				ret

 MainProc ENDP
 END
