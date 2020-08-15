# Function.List (CheatEngine)

<H1>Version: 1.0</H1>
 - Add a System for Check if an Item was in the List
 - Add a System for Add and Item if it wasn't in the List
 - Add a System of parameters

<H1>Tutorial:</H1><br>
Function.List(Bool Is64BitsProcess, List myList, int myList.Lenght,IntPtr myList.Item)</br>
  - Is64BitsProcess = Needed for the actual index in List "Index+=4 for 32bits", "Index+=8 for 64bits" //0 = 32Bits, 1 = 64Bits
  - myList = Your Allocated List Address 
  - myList.Lenght = Your Lenghts you wan't for your list, It was used for check if List Contains myList.Item and for Add Item if not (Hex value,double it for 64Bits)
  - myList.Item = Your Entity/Structure Address you wan't to Check and Add
  - call Function.List = Call The Function of List

<H1>Example:</H1><br>
  [Enable]</br>
  alloc(newmem,$1000)</br>
  alloc(Job.Recolt.List,14)</br>
  
  newmem:</br> 
  movq xmm0,[eax+28] //Original Code</br>

  //Code needed for the List</br>
  mov [Is64BitsProcess],0</br>
  mov [myList],Job.Recolt.List</br>
  mov [myList.Lenght],18</br>
  mov [myList.Item],eax</br>
  call Function.List</br>
  </br>
  jmp return
