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
# <a name="how-to-modify-btswebsvcwizexeconfig"></a>如何修改 BTSWebSvcWiz.exe.config
可以启用跟踪来调试 BizTalk Web Services 发布向导通过取消注释\<添加\>BTSWebSvcWiz.exe.config 文件中的节点。 如果跟踪侦听器节点未被注释掉并*initializeData*参数进行更改，BizTalk Server 跟踪文件将输出写入到当前目录。 或者，设置跟踪级别**ApplicationTraceSwitch**并设置跟踪文件的路径名称。  
  
 BTSWebSvcWiz.exe.config 位于与 BTSWebSvcWiz.exe 文件通常是相同的目录中[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]。  
  
 以下是取消注释的示例\<添加\>BTSWebSvcWiz.exe.config 文件中的节点：  
  
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
  
 此跟踪功能使用.NET Framework 中的 Trace 类。 有关 Trace 类的详细信息，请参阅 Microsoft MSDN 网站上的[ http://go.microsoft.com/fwlink/?LinkId=67886 ](http://go.microsoft.com/fwlink/?LinkId=67886)。  
  
 璝惠**TextWriterTraceListener**，请参阅中的"TextWriterTraceListener，"[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]在帮助集合[ http://go.microsoft.com/fwlink/?LinkId=62267 ](http://go.microsoft.com/fwlink/?LinkId=62267)。  
  
## <a name="see-also"></a>请参阅  
 [调试已发布的 Web 服务](../core/debugging-published-web-services.md)