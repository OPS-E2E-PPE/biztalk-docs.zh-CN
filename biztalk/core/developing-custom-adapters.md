---
title: "开发自定义适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 44765fbb-b24d-43b6-a40c-d28e319b90a5
caps.latest.revision: "29"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c13aba7e378d67523ec755837ac65b26989730a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="developing-custom-adapters"></a>开发自定义适配器
若要与外部系统、 应用程序和实体交换消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用适配器的概念。 适配器是 COM 或[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]传输企业最终的消息的组件。 通过使用各种通信协议 （如文件系统、 数据库和自定义业务应用程序） 的点。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供本机支持各种协议的适配器。 其中包括：  
  
-   支持从文件位置发送和接收消息的文件适配器  
  
-   用于 EDI、FTP、HTTP、MSMQ、SMTP、POP3 和 SOAP 协议的适配器  
  
-   为适配器[!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)]  
  
 在某些情况下[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可能需要传输特定的自定义应用程序的消息或使用为其本机适配器不存在的协议。 第三方公司编写了支持其他协议的适配器。 您可能要在决定编写某一自定义适配器前确定是否存在可用于您的协议的适配器。 有关适配器和关联的供应商的列表，请参阅[http://go.microsoft.com/fwlink/?LinkId=47140](http://go.microsoft.com/fwlink/?LinkId=47140)。 如果您无法找到支持您的通信要求的适配器，则可以开发自定义适配器。  
  
 编写自定义适配器可能颇具挑战性。 为了简化此过程，Microsoft 开发了称作适配器框架的基础框架。 你可以为你的开发以及适配器源中的代码示例将用作基础此框架[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SDK。  
  
 本部分中的以下主题提供自定义适配器的开发技巧和建议。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [什么是适配器 Framework？](../core/what-is-the-adapter-framework.md)  
  
-   [BizTalk Server 如何实例化适配器](../core/how-biztalk-server-instantiates-an-adapter.md)  
  
-   [消息批](../core/message-batches.md)  
  
-   [事务性消息批](../core/transactional-message-batches.md)  
  
-   [开发接收适配器](../core/developing-a-receive-adapter.md)  
  
-   [开发发送适配器](../core/developing-a-send-adapter.md)  
  
-   [实例化隔离的适配器](../core/instantiating-isolated-adapters.md)  
  
-   [适配器设计问题](../core/adapter-design-issues.md)  
  
-   [适配器如何处理大消息](../core/how-adapters-handle-large-messages.md)  
  
-   [如何处理适配器故障影响](../core/how-to-handle-adapter-failures.md)  
  
-   [如何终止适配器](../core/how-to-terminate-an-adapter.md)  
  
-   [如何设计的高性能适配器](../core/how-to-design-a-performant-adapter.md)  
  
-   [如何部署自定义适配器](../core/how-to-deploy-a-custom-adapter.md)  
  
-   [如何测试和调试适配器](../core/how-to-test-and-debug-an-adapter.md)  
  
-   [如何将适配器元数据添加到 BizTalk 项目](../core/how-to-add-adapter-metadata-to-a-biztalk-project.md)  
  
-   [适配器本地化问题](../core/adapter-localization-issues.md)  
  
-   [设计你的适配器的提示](../core/tips-for-designing-your-adapter.md)  
  
-   [适配器设计时配置](../core/adapter-design-time-configuration.md)  
  
## <a name="see-also"></a>另请参阅  
 [开发自定义组件](../core/developing-custom-components.md)