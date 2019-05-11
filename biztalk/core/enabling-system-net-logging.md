---
title: 启用 System.Net 日志记录 |Microsoft Docs
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
ms.openlocfilehash: b7044d1455905c45995a3096b7ec3cc6c153adb3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349626"
---
# <a name="enabling-systemnet-logging"></a><span data-ttu-id="4c049-102">启用 System.Net 日志记录</span><span class="sxs-lookup"><span data-stu-id="4c049-102">Enabling System.Net Logging</span></span>
<span data-ttu-id="4c049-103">可以启用日志记录`System.Net`并`System.Net.Sockets` [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] BTSNtSvc.exe 服务命名空间。</span><span class="sxs-lookup"><span data-stu-id="4c049-103">You can enable logging for the `System.Net` and `System.Net.Sockets`[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] namespace for the BTSNtSvc.exe service.</span></span> <span data-ttu-id="4c049-104">这会导致要创建包含的信息来帮助你识别您的 BizTalk Server 安装的问题的详细的日志文件。</span><span class="sxs-lookup"><span data-stu-id="4c049-104">This will cause a detailed log file to be created containing information that may help you identify issues with your BizTalk Server installation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4c049-105">这是 Microsoft 的一项功能[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]，并且[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]或更高版本。</span><span class="sxs-lookup"><span data-stu-id="4c049-105">This is a feature of the Microsoft [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] and will work in [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] or later.</span></span>  
  
 <span data-ttu-id="4c049-106">通过修改的应用程序配置文件启用了跟踪**BTSNtSvc.exe**， **BTSNtSvc.exe.config**。可在 BizTalk Server 安装路径;如果在默认位置安装 BizTalk Server，则 BtsNtSvc.exe 将在目录中[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4c049-106">Tracing is enabled by modifying the application configuration file for **BTSNtSvc.exe**,  **BTSNtSvc.exe.config**. It can be found in the BizTalk Server installation path; if you installed BizTalk Server to the default location, BtsNtSvc.exe will be in the directory [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span></span>  
  
 <span data-ttu-id="4c049-107">若要修改**BTSNtSvc.exe.config**，打开配置文件并粘贴到下面的代码`<configuration>`元素使用记事本或你最喜欢的文本编辑器。</span><span class="sxs-lookup"><span data-stu-id="4c049-107">To modify **BTSNtSvc.exe.config**, open the configuration file and paste the code below into the `<configuration>` element using Notepad or your favorite text editor.</span></span>  
  
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
  
 <span data-ttu-id="4c049-108">日志文件将写入到 BTSNtSvc.exe 所在的相同目录中。</span><span class="sxs-lookup"><span data-stu-id="4c049-108">The log file will be written to the same directory that contains BTSNtSvc.exe.</span></span> <span data-ttu-id="4c049-109">如果已安装到默认位置，它将写入[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4c049-109">If you installed to the default location, it will be written to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c049-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="4c049-110">See Also</span></span>  
 [<span data-ttu-id="4c049-111">解释网络跟踪</span><span class="sxs-lookup"><span data-stu-id="4c049-111">Interpreting Network Tracing</span></span>](http://go.microsoft.com/fwlink/?LinkId=78679)