---
title: Errore interno. Impossibile ottenere il nome completo del sistema operativo
ms.date: 07/20/2015
f1_keywords:
- vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
ms.openlocfilehash: f85ca5f7f325cb0dd2b8fc55d3f90f6abdfd4a7c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a>Errore interno. Impossibile ottenere il nome completo del sistema operativo
Errore interno. Impossibile ottenere il nome completo del sistema operativo. WMI potrebbe non essere presente sul computer in uso.  
  
 Una chiamata alla proprietà `My.Computer.Info.OSFullName` non è riuscita. L'errore può derivare dal fatto che Strumentazione gestione Windows (WMI) non è installato nel computer corrente.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Aggiungere un blocco `Try...Catch` nella chiamata alla proprietà `My.Computer.Info.OSFullName` .  
  
2.  Per ulteriori informazioni su WMI e su come installarlo, passare a e cercare "Windows Management Instrumentation Core".  
  
## <a name="see-also"></a>Vedere anche  
 [My.Computer.Info.OSFullName](xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName)  
 [Eccezioni e gestione degli errori in Visual Basic](http://msdn.microsoft.com/library/3e351e73-cf23-40ab-8b60-05794160529e)  
 [Istruzione Try...Catch...Finally](../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
