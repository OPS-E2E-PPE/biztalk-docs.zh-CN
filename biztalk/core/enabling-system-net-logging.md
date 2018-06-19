---
title: 启用 System.Net 日志记录 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5eea50b9-1f46-45fc-a327-585adb4583a0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e672f2b9e7ae8b0ef3889493273660c8ef9140c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239933"
---
# <a name="enabling-systemnet-logging"></a>启用 System.Net 日志记录
你可以启用日志记录`System.Net`和`System.Net.Sockets` [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] BTSNtSvc.exe 服务命名空间。 这会导致创建一个详细的日志文件，其中包含的信息可以帮助您找出安装 BizTalk Server 时出现的问题。  
  
> [!NOTE]
>  这是 Microsoft [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] 的一项功能，将在 [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] 或更高版本中生效。  
  
 通过修改的应用程序配置文件启用了跟踪**BTSNtSvc.exe**， **BTSNtSvc.exe.config**。BtsNtSvc.exe 可以在 BizTalk Server 安装路径中找到；如果将 BizTalk Server 安装到默认位置，则 BtsNtSvc.exe 将位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] 目录下。  
  
 若要修改**BTSNtSvc.exe.config**，打开配置文件并将粘贴到下面的代码`<configuration>`使用记事本或你喜爱的文本编辑器的元素。  
  
```  
<system.diagnostics>  
  <sources>  
    <source name="System.Net" switchValue="Verbose">  
      <listeners>  
        <add name="System.Net"/>  
      </listeners>  
    </source>  
    <source name="System.Net.Sockets" switchValue="Verbose">  
      <listeners>  
        <add name="System.Net"/>  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add name="System.Net"  
          type="System Diagnostics.TextWriterTraceListener"  
          initializeData="System.Net..log"/>  
  </sharedListeners>  
  <trace autoflush="true" />  
</system.diagnostics>  
```  
  
 日志文件将写入包含 BTSNtSvc.exe 的相同目录。 如果您已安装到默认位置，它将被写入[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]。  
  
## <a name="see-also"></a>另请参阅  
 [解释网络跟踪](http://go.microsoft.com/fwlink/?LinkId=78679)