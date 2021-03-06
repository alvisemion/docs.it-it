---
title: Passaggio di strutture
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- platform invoke, calling unmanaged functions
ms.assetid: 9b92ac73-32b7-4e1b-862e-6d8d950cf169
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3764916263f6f88615d61badaf2c32807bcc09b8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="passing-structures"></a>Passaggio di strutture
Molte funzioni non gestite prevedono il passaggio, come parametro della funzione, di membri di strutture (tipi definiti dall'utente in Visual Basic) o membri di classi definiti nel codice gestito. Quando si passano strutture o classi al codice non gestito mediante platform invoke, è necessario fornire informazioni aggiuntive per mantenere il layout e l'allineamento originali. In questo argomento viene presentato l'attributo <xref:System.Runtime.InteropServices.StructLayoutAttribute>, usato per definire i tipi formattati. Per le classi e le strutture gestite, è possibile selezionare tra diversi comportamenti di layout prevedibili forniti dall'enumerazione **LayoutKind**.  
  
 Un aspetto fondamentale per i concetti presentati in questo argomento è l'importante differenza esistente tra i tipi di strutture e classi. Le strutture sono tipi valore e le classi sono tipi riferimento. Le classi forniscono sempre almeno un livello di riferimento indiretto di memoria (un puntatore a un valore). Questa differenza è importante perché le funzioni non gestite spesso richiedono riferimenti indiretti, come illustrato dalle firme nella prima colonna della tabella seguente. La struttura gestita e le dichiarazioni di classe nelle colonne rimanenti mostrano il grado di cui è possibile modificare il livello di riferimento indiretto nella dichiarazione. Le dichiarazioni sono disponibili sia per Visual Basic che per Visual C#.  
  
|Firma non gestita|Dichiarazione gestita: <br />nessun riferimento indiretto<br />`Structure MyType`<br />`struct MyType;`|Dichiarazione gestita: <br />un livello di riferimento indiretto<br />`Class MyType`<br />`class MyType;`|  
|-------------------------|---------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|  
|`DoWork(MyType x);`<br /><br /> Richiede zero livelli di riferimento indiretto.|`DoWork(ByVal x As MyType)` <br /> `DoWork(MyType x)`<br /><br /> Non aggiunge alcun livello di riferimento indiretto.|Non possibile perché esiste già un livello di riferimento indiretto.|  
|`DoWork(MyType* x);`<br /><br /> Richiede un livello di riferimento indiretto.|`DoWork(ByRef x As MyType)` <br /> `DoWork(ref MyType x)`<br /><br /> Aggiunge un livello di riferimento indiretto.|`DoWork(ByVal x As MyType)` <br /> `DoWork(MyType x)`<br /><br /> Non aggiunge alcun livello di riferimento indiretto.|  
|`DoWork(MyType** x);`<br /><br /> Richiede due livelli di riferimento indiretto.|Impossibile perché non è possibile usare **ByRef** **ByRef** o `ref` `ref`.|`DoWork(ByRef x As MyType)` <br /> `DoWork(ref MyType x)`<br /><br /> Aggiunge un livello di riferimento indiretto.|  
  
 La tabella descrive le linee guida seguenti per le dichiarazioni di platform invoke:  
  
-   Usare una struttura passata per valore quando la funzione non gestita non richiede alcun riferimento indiretto.  
  
-   Usare una struttura passata per riferimento o una classe passata per valore quando la funzione non gestita richiede un livello di riferimento indiretto.  
  
-   Usare una classe passata per riferimento quando la funzione non gestita richiede due livelli di riferimento indiretto.  
  
## <a name="declaring-and-passing-structures"></a>Dichiarazione e passaggio di strutture  
 L'esempio seguente mostra come definire le strutture `Point` e `Rect` nel codice gestito e passare i tipi come parametro alla funzione **PtInRect** nel file User32.dll. **PtInRect** include la firma non gestita seguente:  
  
```  
BOOL PtInRect(const RECT *lprc, POINT pt);  
```  
  
 Si noti che è necessario passare la struttura Rect per riferimento, perché la funzione si aspetta un puntatore a un tipo RECT.  
  
```vb  
Imports System.Runtime.InteropServices  
  
<StructLayout(LayoutKind.Sequential)> Public Structure Point  
    Public x As Integer  
    Public y As Integer  
End Structure  
  
Public Structure <StructLayout(LayoutKind.Explicit)> Rect  
    <FieldOffset(0)> Public left As Integer  
    <FieldOffset(4)> Public top As Integer  
    <FieldOffset(8)> Public right As Integer  
    <FieldOffset(12)> Public bottom As Integer  
End Structure  
  
Class Win32API      
    Declare Auto Function PtInRect Lib "user32.dll" _  
    (ByRef r As Rect, p As Point) As Boolean  
End Class  
```  
  
```csharp  
using System.Runtime.InteropServices;  
  
[StructLayout(LayoutKind.Sequential)]  
public struct Point {  
    public int x;  
    public int y;  
}     
  
[StructLayout(LayoutKind.Explicit)]  
public struct Rect {  
    [FieldOffset(0)] public int left;  
    [FieldOffset(4)] public int top;  
    [FieldOffset(8)] public int right;  
    [FieldOffset(12)] public int bottom;  
}     
  
class Win32API {  
    [DllImport("User32.dll")]  
    public static extern bool PtInRect(ref Rect r, Point p);  
}  
```  
  
## <a name="declaring-and-passing-classes"></a>Dichiarazione e passaggio di classi  
 È possibile passare i membri di una classe a una funzione DLL non gestita, a condizione che la classe abbia un layout di membri fisso. L'esempio seguente dimostra come passare membri alla classe `MySystemTime`, definiti in ordine sequenziale, a **GetSystemTime** nel file User32.dll. **GetSystemTime** include la firma non gestita seguente:  
  
```  
void GetSystemTime(SYSTEMTIME* SystemTime);  
```  
  
 Diversamente dai tipi valore, le classi hanno sempre almeno un livello di riferimento indiretto.  
  
```vb  
Imports System  
Imports System.Runtime.InteropServices  
Imports Microsoft.VisualBasic  
  
<StructLayout(LayoutKind.Sequential)> Public Class MySystemTime  
    Public wYear As Short  
    Public wMonth As Short  
    Public wDayOfWeek As Short   
    Public wDay As Short  
    Public wHour As Short  
    Public wMinute As Short  
    Public wSecond As Short  
    Public wMiliseconds As Short  
End Class  
  
Public Class Win32  
    Declare Auto Sub GetSystemTime Lib "Kernel32.dll"(sysTime _  
        As MySystemTime)  
    Declare Auto Function MessageBox Lib "User32.dll"(hWnd As IntPtr, _  
        txt As String, caption As String, Typ As Integer) As Integer  
End Class  
  
Public Class TestPlatformInvoke      
    Public Shared Sub Main()  
        Dim sysTime As New MySystemTime()  
        Win32.GetSystemTime(sysTime)  
  
        Dim dt As String  
        dt = "System time is:" & ControlChars.CrLf & _  
              "Year: " & sysTime.wYear & _  
              ControlChars.CrLf & "Month: " & sysTime.wMonth & _  
              ControlChars.CrLf & "DayOfWeek: " & sysTime.wDayOfWeek & _  
              ControlChars.CrLf & "Day: " & sysTime.wDay  
        Win32.MessageBox(IntPtr.Zero, dt, "Platform Invoke Sample", 0)        
    End Sub  
End Class  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
public class MySystemTime {  
    public ushort wYear;   
    public ushort wMonth;  
    public ushort wDayOfWeek;   
    public ushort wDay;   
    public ushort wHour;   
    public ushort wMinute;   
    public ushort wSecond;   
    public ushort wMilliseconds;   
}  
class Win32API {  
    [DllImport("Kernel32.dll")]  
    public static extern void GetSystemTime(MySystemTime st);  
  
    [DllImport("user32.dll", CharSet=CharSet.Auto)]  
     public static extern int MessageBox(IntPtr hWnd,  
         string text, string caption, int options);  
}  
  
public class TestPlatformInvoke  
{  
    public static void Main()  
    {  
        MySystemTime sysTime = new MySystemTime();  
        Win32API.GetSystemTime(sysTime);  
  
        string dt;  
        dt = "System time is: \n" +  
              "Year: " + sysTime.wYear + "\n" +  
              "Month: " + sysTime.wMonth + "\n" +  
              "DayOfWeek: " + sysTime.wDayOfWeek + "\n" +  
              "Day: " + sysTime.wDay;  
        Win32API.MessageBox(IntPtr.Zero, dt, "Platform Invoke Sample", 0);  
    }  
}  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Chiamata a una funzione di DLL](../../../docs/framework/interop/calling-a-dll-function.md)  
 <xref:System.Runtime.InteropServices.StructLayoutAttribute>  
 <xref:System.Runtime.InteropServices.StructLayoutAttribute>  
 <xref:System.Runtime.InteropServices.FieldOffsetAttribute>
