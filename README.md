# Function.List (CheatEngine)

Version : 1.0
 - Add a System for Check if an Item was in the List
 - Add a System for Add and Item if it wasn't in the List
 - Add a System of parameters

Function.List(Bool Is64BitsProcess, List myList, int myList.Lenght,IntPtr myList.Item)

Example : 
  eax = Base Address of Entity or whatever structure
  Is64BitsProcess = Needed for the actual index in List "Index+=4 for 32bits", "Index+=8 for 64bits" //0 = 32Bits, 1 = 64Bits
  myList = Your Allocated List Address 
  myList.Lenght = Your Lenghts you wan't for your list, It was used for check if List Contains myList.Item and for Add Item if not (Hex value,double it for 64Bits)  
  myList.Item = Your Entity/Structure Address you wan't to Check and Add
  call Function.List = Call The Function of List

  [Enable]
  alloc(newmem,$1000)
  alloc(Job.Recolt.List,14)
  
  newmem: 
  movq xmm0,[eax+28] //Original Code

  //Code needed for the List
  mov [Is64BitsProcess],0
  mov [myList],Job.Recolt.List
  mov [myList.Lenght],18
  mov [myList.Item],eax
  call Function.List

  jmp return
