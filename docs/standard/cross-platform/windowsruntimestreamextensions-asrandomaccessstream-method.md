---
title: Metodo WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream)
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
api_name:
- System.IO.WindowsRuntimeStreamExtensions.AsRandomAccessStream
api_location:
- System.Runtime.WindowsRuntime.dll
ms.assetid: dcc72283-caed-49ee-b45d-ccaf94e97129
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 16f878abc11589fe62f78d941b367d82d7b49e1c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="windowsruntimestreamextensionsasrandomaccessstreamsystemiostream-method"></a>Metodo WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream)
[Supportato in .NET Framework 4.5.1 e versioni successive]  
  
 Converte il flusso specificato in un flusso di accesso casuale.  
  
 **Namespace:** <xref:System.IO?displayProperty=nameWithType>  
 **Assembly:** System.Runtime.WindowsRuntime (in System.Runtime.WindowsRuntime.dll)  
  
## <a name="syntax"></a>Sintassi  
  
```csharp  
[CLSCompliantAttribute(false)]  
public static  IRandomAccessStream AsRandomAccessStream(Stream stream)  
```  
  
```vb  
'Declaration  
<ExtensionAttribute> _  
<CLSCompliantAttribute(False)> _  
Public Shared Function AsRandomAccessStream ( _  
        stream As Stream) As IRandomAccessStream  
```  
  
#### <a name="parameters"></a>Parametri  
 `stream`  
  
 Tipo: <xref:System.IO.Stream?displayProperty=nameWithType>  
Flusso da convertire.  
  
## <a name="return-value"></a>Valore restituito  
 Tipo: [Windows.Storage.Streams.RandomAccessStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.randomaccessstream.aspx)  
Oggetto [!INCLUDE[wrt](../../../includes/wrt-md.md)] flusso ad accesso casuale, che rappresenta il flusso convertito.  
  
## <a name="exceptions"></a>Eccezioni  
  
|Eccezione|Condizione|  
|---------------|---------------|  
|<xref:System.NotSupportedException>|Il flusso da convertire non supporta la ricerca.|  
  
## <a name="remarks"></a>Note  
 Questo metodo di estensione è disponibile solo quando si sviluppano applicazioni Windows Store. Questo metodo fornisce un modo conveniente per lavorare con i flussi nelle applicazioni Windows Store. Il flusso .NET Framework da convertire deve supportare la ricerca. Per altre informazioni, vedere il metodo <xref:System.IO.Stream.Seek%2A?displayProperty=nameWithType>.  
  
> [!IMPORTANT]
>  Questa API è supportata in .NET Framework 4.5.1 e nelle versioni successive, ma non nella versione 4.5.  
  
## <a name="version-information"></a>Informazioni sulla versione  
 **.NET per applicazioni Windows Store**  
  
 Supportato in: Windows 8.1  
  
## <a name="see-also"></a>Vedere anche  
 <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions>--> `System.IO.WindowsRuntimeStreamExtensions`  
 [Procedura: Eseguire la conversione tra flussi di .NET Framework e flussi di Windows Runtime](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)
