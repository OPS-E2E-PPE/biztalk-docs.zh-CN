---
title: Web 服务发布时的注意事项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, publishing
- Web services, planning
- Web services, schemas
- schemas, Web services
ms.assetid: 3ace0260-a1cb-4e59-a820-36ee7d5cceda
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb9ef5d7dd2e035caaa1981129eae5ac4b51ac71
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014774"
---
# <a name="considerations-when-publishing-web-services"></a>发布 Web Services 时的注意事项
本主题介绍你在发布 Web Services 之前应考虑的信息。  
  
## <a name="publishing-schemas-and-the-include-element"></a>发布架构和 include 元素  
 有几种方案其中所包含的架构**包括**元素不能发布为 Web 服务。 在你完成 BizTalk Web Services 发布向导时，会出现错误。 包含如下这些限制：  
  
- 循环包含 (包含的架构具有**包括**包含架构的元素)  
  
- 无法解析**schemaLocation**属性会导致错误  
  
  有关限制的详细信息包括元素，请参阅"Include 元素绑定支持"，网址[ http://go.microsoft.com/fwlink/?LinkId=62312 ](http://go.microsoft.com/fwlink/?LinkId=62312)。  
  
## <a name="publishing-schemas-and-the-import-element"></a>发布架构和 import 元素  
 BizTalk Web Services 发布向导与 .NET Framework 中包含的 XSD.exe 具有相同的限制。 有关详细信息，请参阅"导入元素绑定支持"网址[ http://go.microsoft.com/fwlink/?LinkId=62311 ](http://go.microsoft.com/fwlink/?LinkId=62311)。  
  
## <a name="publishing-schemas-and-the-redefine-element"></a>发布架构和 redefine 元素  
 BizTalk Web Services 发布向导与 .NET Framework 中包含的 XSD.exe 具有相同的限制。 详细信息，请参阅"Redefine 元素绑定支持"处[ http://go.microsoft.com/fwlink/?LinkId=62313 ](http://go.microsoft.com/fwlink/?LinkId=62313)。  
  
## <a name="publishing-schemas-that-specify-values-for-minoccurs-or-maxoccurs-attributes"></a>发布指定了 minOccurs 或 maxOccurs 属性值的架构  
 如果发布包含的架构**minOccurs**或**maxOccurs**具有特定值的属性，这些值可能是由已发布的 Web 服务公开的架构中不同。 通常，所有 minOccurs 属性被转换为 0 (minOccurs=0) 而 maxOccurs 属性则转换为 1 或 unbounded（maxOccurs=1 或 maxOccurs=unbounded）。  
  
## <a name="publishing-envelope-schemas"></a>发布信封架构  
 如果你有一个要发布为 Web Services 的信封架构，则需要手动修改生成的 Web 项目。  
  
#### <a name="to-modify-the-generated-web-project-for-envelope-schemas"></a>为信封架构修改生成的 Web 项目  
  
1.  打开 <`myWebService`>.asmx.cs 文件。  
  
2.  编辑文件，并更改`bodyTypeAssemblyQualifiedName = <dll.name.version.>`到`bodyTypeAssemblyQualifiedName = null`。  
  
> [!NOTE]
>  如果先前的 .dll 文件仍然在 ASPNET 辅助进程中，你可能需要重置 Internet 信息服务 (IIS)。  
  
## <a name="web-service-and-web-method-attributes"></a>Web Services 和 Web 方法属性  
 BizTalk Web Services 发布向导不允许您自定义在 ASP.NET 中使用的 Web Services 或 Web 方法属性。 某些属性会基于该向导提供的信息自动进行设置。 该向导不使用其他属性。  
  
 修改现有属性或者向 BizTalk Web Services 发布向导生成的 Web Services 添加新属性可能导致该 Web Services 无法正常工作。  
  
 有关 Web 服务和 Web 方法属性的详细信息，请参阅**WebServiceAttribute**并**WebMethodAttribute**的.NET Framework SDK 文档中的类。  
  
## <a name="web-method-required"></a>必需的 Web 方法  
 Web Services 必须具有至少一个 Web 方法。 如果不是至少具有一个 Web 方法，端口类型将不创建其操作。 XLANG/s 不支持没有操作的端口类型。  
  
## <a name="dbcs-character-support"></a>DBCS 字符支持  
 Web Services 不支持 Chinese/Japanese/Korean (CJK) Unified Ideograph Extension A 字符。  
  
## <a name="republishing-web-services-using-the-biztalk-web-services-publishing-wizard"></a>使用 Web Services 发布向导重新发布 Web Services  
 可以使用 BizTalk Web Services 发布向导重新发布已发布的 Web Services。 上**Web**<strong>服务</strong>**项目**页上，可以选择**覆盖**<strong>Web</strong> **服务**选项。  
  
 该向导不存储先前所用的设置。 如果在重新运行向导时更改了设置，使用（调用）已发布的 Web Services 的任何 Web 客户端都可能失败。 你应该更新使用（调用）某个重新发布的 Web Services 的任何客户端的 Web 引用。  
  
## <a name="clients-of-published-web-services-may-not-receive-server-script-timeout-errors"></a>已发布 Web Services 的客户端可能不会收到服务器脚本超时错误。  
 Web 服务使用 Web Services 发布向导中生成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]默认情况下，使用的脚本超时值配置**110**秒。 这是 .NET Framework 的默认值。 **HttpServerUtility.ScriptTimeout**属性。 使用.NET Framework 的 web 客户端配置请求超时值为默认情况下**100**秒。 这是.NET Framework 的默认值**HttpWebRequest.Timeout**属性。  
  
 如果使用 .NET framework 的 Web 客户端调用某个使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Web Services 发布向导生成的 Web Services，客户端可能无法收到服务器脚本超时错误，因为默认情况下会首先发生客户端请求超时。 若要解决该问题，可执行以下操作之一：  
  
-   通过增加的值来提高客户端请求超时值大于服务器脚本超时**HttpWebRequest.Timeout**客户端上的属性。  
  
-   降低服务器脚本超时小于客户端请求超时的值的值**HttpServerUtility.ScriptTimeout**在服务器上的属性。  
  
## <a name="see-also"></a>请参阅  
 [发布 Web 服务](../core/publishing-web-services.md)