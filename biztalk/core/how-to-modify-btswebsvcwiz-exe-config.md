---
title: "如何修改 BTSWebSvcWiz.exe.config |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web services, code samples
- Web services, debugging
ms.assetid: 8466e460-faa9-45ea-9586-19174858d194
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1686932099baa98f36af9ef8a2ca384f7f27a0ce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-modify-btswebsvcwizexeconfig"></a><span data-ttu-id="2e7f8-102">如何修改 BTSWebSvcWiz.exe.config</span><span class="sxs-lookup"><span data-stu-id="2e7f8-102">How to Modify BTSWebSvcWiz.exe.config</span></span>
<span data-ttu-id="2e7f8-103">你可以启用跟踪来调试 BizTalk Web 服务发布向导通过对取消注释\<添加 > BTSWebSvcWiz.exe.config 文件中的节点。</span><span class="sxs-lookup"><span data-stu-id="2e7f8-103">You can enable tracing to debug the BizTalk Web Services Publishing Wizard by uncommenting the \<add> node in the BTSWebSvcWiz.exe.config file.</span></span> <span data-ttu-id="2e7f8-104">如果跟踪侦听器节点是取消注释和*initializeData*参数不变，BizTalk Server 到当前目录中写入输出的跟踪文件。</span><span class="sxs-lookup"><span data-stu-id="2e7f8-104">If the trace listener node is uncommented and the *initializeData* parameter is unchanged, BizTalk Server writes the trace file output to the current directory.</span></span> <span data-ttu-id="2e7f8-105">或者，设置跟踪级别的**ApplicationTraceSwitch**并设置跟踪文件的路径名称。</span><span class="sxs-lookup"><span data-stu-id="2e7f8-105">Alternatively, you can set the trace level of **ApplicationTraceSwitch** and set the path name of the trace file.</span></span>  
  
 <span data-ttu-id="2e7f8-106">BTSWebSvcWiz.exe.config 位于与 BTSWebSvcWiz.exe 文件所在相同的目录中，通常是 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2e7f8-106">BTSWebSvcWiz.exe.config is located in the same directory as the BTSWebSvcWiz.exe file, which is usually [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span></span>  
  
 <span data-ttu-id="2e7f8-107">以下是一种取消注释的\<添加 > BTSWebSvcWiz.exe.config 文件中的节点：</span><span class="sxs-lookup"><span data-stu-id="2e7f8-107">The following is an example of an uncommented \<add> node in BTSWebSvcWiz.exe.config file:</span></span>  
  
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
  
 <span data-ttu-id="2e7f8-108">此跟踪功能使用 .NET Framework 中的 Trace 类。</span><span class="sxs-lookup"><span data-stu-id="2e7f8-108">This tracing feature uses the Trace class in the .NET Framework.</span></span> <span data-ttu-id="2e7f8-109">有关跟踪类的详细信息，请参阅 Microsoft MSDN 网站在[http://go.microsoft.com/fwlink/?LinkId=67886](http://go.microsoft.com/fwlink/?LinkId=67886)。</span><span class="sxs-lookup"><span data-stu-id="2e7f8-109">For more information about the Trace class, see the Microsoft MSDN Web site at [http://go.microsoft.com/fwlink/?LinkId=67886](http://go.microsoft.com/fwlink/?LinkId=67886).</span></span>  
  
 <span data-ttu-id="2e7f8-110">璝惠**TextWriterTraceListener**，请参阅中的"TextWriterTraceListener"[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]在帮助集合[http://go.microsoft.com/fwlink/?LinkId=62267](http://go.microsoft.com/fwlink/?LinkId=62267)。</span><span class="sxs-lookup"><span data-stu-id="2e7f8-110">For information about **TextWriterTraceListener**, see "TextWriterTraceListener" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Help Collection at [http://go.microsoft.com/fwlink/?LinkId=62267](http://go.microsoft.com/fwlink/?LinkId=62267).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e7f8-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e7f8-111">See Also</span></span>  
 [<span data-ttu-id="2e7f8-112">调试已发布的 Web 服务</span><span class="sxs-lookup"><span data-stu-id="2e7f8-112">Debugging Published Web Services</span></span>](../core/debugging-published-web-services.md)