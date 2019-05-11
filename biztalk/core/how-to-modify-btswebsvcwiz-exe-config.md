---
title: 如何修改 BTSWebSvcWiz.exe.config |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, code samples
- Web services, debugging
ms.assetid: 8466e460-faa9-45ea-9586-19174858d194
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fc89d7a0e4201ae3bbff36c636a27c78b2b36b9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384621"
---
# <a name="how-to-modify-btswebsvcwizexeconfig"></a><span data-ttu-id="fb73f-102">如何修改 BTSWebSvcWiz.exe.config</span><span class="sxs-lookup"><span data-stu-id="fb73f-102">How to Modify BTSWebSvcWiz.exe.config</span></span>
<span data-ttu-id="fb73f-103">可以启用跟踪来调试 BizTalk Web Services 发布向导通过取消注释\<添加\>BTSWebSvcWiz.exe.config 文件中的节点。</span><span class="sxs-lookup"><span data-stu-id="fb73f-103">You can enable tracing to debug the BizTalk Web Services Publishing Wizard by uncommenting the \<add\> node in the BTSWebSvcWiz.exe.config file.</span></span> <span data-ttu-id="fb73f-104">如果跟踪侦听器节点未被注释掉并*initializeData*参数进行更改，BizTalk Server 跟踪文件将输出写入到当前目录。</span><span class="sxs-lookup"><span data-stu-id="fb73f-104">If the trace listener node is uncommented and the *initializeData* parameter is unchanged, BizTalk Server writes the trace file output to the current directory.</span></span> <span data-ttu-id="fb73f-105">或者，设置跟踪级别**ApplicationTraceSwitch**并设置跟踪文件的路径名称。</span><span class="sxs-lookup"><span data-stu-id="fb73f-105">Alternatively, you can set the trace level of **ApplicationTraceSwitch** and set the path name of the trace file.</span></span>  
  
 <span data-ttu-id="fb73f-106">BTSWebSvcWiz.exe.config 位于与 BTSWebSvcWiz.exe 文件通常是相同的目录中[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fb73f-106">BTSWebSvcWiz.exe.config is located in the same directory as the BTSWebSvcWiz.exe file, which is usually [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span></span>  
  
 <span data-ttu-id="fb73f-107">以下是取消注释的示例\<添加\>BTSWebSvcWiz.exe.config 文件中的节点：</span><span class="sxs-lookup"><span data-stu-id="fb73f-107">The following is an example of an uncommented \<add\> node in BTSWebSvcWiz.exe.config file:</span></span>  
  
```  
<system.diagnostics>  
  <switches>  
    <!-- TraceLevel 0=Off, 1=Error, 2=Warning, 3=Info, 4=Verbose -->  
    <add name="ApplicationTraceSwitch" value="4" />  
  </switches>  
  <trace autoflush="true" indentsize="4">  
    <listeners>  
      <!--add name="Trace"  
       type="System.Diagnostics.TextWriterTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
       initializeData="BTSWebSvcWiz.trace.log" /-->  
    </listeners>  
  </trace>  
</system.diagnostics>  
```  
  
 <span data-ttu-id="fb73f-108">此跟踪功能使用.NET Framework 中的 Trace 类。</span><span class="sxs-lookup"><span data-stu-id="fb73f-108">This tracing feature uses the Trace class in the .NET Framework.</span></span> <span data-ttu-id="fb73f-109">有关 Trace 类的详细信息，请参阅 Microsoft MSDN 网站上的[ http://go.microsoft.com/fwlink/?LinkId=67886 ](http://go.microsoft.com/fwlink/?LinkId=67886)。</span><span class="sxs-lookup"><span data-stu-id="fb73f-109">For more information about the Trace class, see the Microsoft MSDN Web site at [http://go.microsoft.com/fwlink/?LinkId=67886](http://go.microsoft.com/fwlink/?LinkId=67886).</span></span>  
  
 <span data-ttu-id="fb73f-110">璝惠**TextWriterTraceListener**，请参阅中的"TextWriterTraceListener，"[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]在帮助集合[ http://go.microsoft.com/fwlink/?LinkId=62267 ](http://go.microsoft.com/fwlink/?LinkId=62267)。</span><span class="sxs-lookup"><span data-stu-id="fb73f-110">For information about **TextWriterTraceListener**, see "TextWriterTraceListener" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Help Collection at [http://go.microsoft.com/fwlink/?LinkId=62267](http://go.microsoft.com/fwlink/?LinkId=62267).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb73f-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="fb73f-111">See Also</span></span>  
 [<span data-ttu-id="fb73f-112">调试已发布的 Web 服务</span><span class="sxs-lookup"><span data-stu-id="fb73f-112">Debugging Published Web Services</span></span>](../core/debugging-published-web-services.md)