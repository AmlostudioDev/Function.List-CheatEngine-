# Function.List (CheatEngine)

![Minion](https://github.com/AmlostudioDev/Function.List-CheatEngine-/blob/master/ImageProof/TutoImage1.png)
![Minion](https://github.com/AmlostudioDev/Function.List-CheatEngine-/blob/master/ImageProof/TutoImage2.png)

**Version: 1.0**
 - Add a System for Check if an Item was in the List
 - Add a System for Add and Item if it wasn't in the List
 - Add a System of parameters

**Tutorial:**<br>
Function.List(Bool Is64BitsProcess, List myList, int myList.Lenght,IntPtr myList.Item)</br>
  - Is64BitsProcess = Needed for the actual index in List "Index+=4 for 32bits", "Index+=8 for 64bits" //0 = 32Bits, 1 = 64Bits
  - myList = Your Allocated List Address 
  - myList.Lenght = Your Lenghts you wan't for your list, It was used for check if List Contains myList.Item and for Add Item if not (Hex value,double it for 64Bits)
  - myList.Item = Your Entity/Structure Address you wan't to Check and Add
  - call Function.List = Call The Function of List

**Example:**<br>
  **[Enable]**</br>
  alloc(newmem,$1000)</br>
  alloc(Job.Recolt.List,14)</br>
  
  newmem:</br> 
  movq xmm0,[eax+28] //Original Code</br>

  //Code needed for the List</br>
  mov [Is64BitsProcess],0</br>
  mov [myList],Job.Recolt.List</br>
  mov [myList.Lenght],14</br>
  mov [myList.Item],eax</br>
  call Function.List</br>
  </br>
  jmp return
