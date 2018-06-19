---
title: 开发 Siebel 应用程序使用 WCF 服务模型 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, developing applications by using
- WCF service model, performing operations
- proxy programming, performing operations
- WCF service model, advantages of using
ms.assetid: df5627b9-c80d-4a75-a20a-a0be119735a2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c14560fb92eb2cca1e55d32e556dec23725a0de6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222525"
---
# <a name="develop-siebel-applications-using-the-wcf-service-model"></a>开发 Siebel 应用程序使用 WCF 服务模型
[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供一个编程模型调用 WCF 服务模型，该部分可帮助解决的一些其他的编程模型的限制 — WCF 通道模型。  
  
 在最低级别，[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]显示在其中客户端调用服务上的操作通过在客户端和服务终结点之间建立信道交换 SOAP 消息的 WCF 通道模型。 WCF 通道模型公开数据类型和方法，您可以直接对 WCF 通道体系结构进行操作。 WCF 通道模型为您提供通过你创建的 SOAP 消息的内容和方式这两个应用程序的直接控制和[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]使用它们。 但是，创建格式正确的 SOAP 消息在通道上发送和验证返回的答复消息可以是详细、 更严格的任务。  
  
 WCF 服务模型，但是，涉及使用代理类来调用针对目标服务的操作或从客户端接收操作。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]作为 WCF 服务可以在其调用操作公开 Siebel 系统。  
  
-   用于调用操作将针对目标服务的代理类调用 WCF 客户端类。 此类模型作为使用强类型参数的.NET 方法由服务公开的操作。 通过使用 WCF 服务模型，你可以调用公开的运算[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]为 WCF 客户端上的.NET 方法。 有关 WCF 客户端的详细信息，请参阅[WCF 客户端概述](https://msdn.microsoft.com/library/ms735103.aspx)。   
  
 使用工具来生成 WCF 客户端类和关联的服务元数据中的帮助器代码，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]公开。 你可以使用以下工具之一：  
  
-   ServiceModel 元数据实用工具 (svcutil.exe)，其中附带 WCF  
  
-   [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，其中附带[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]  
  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]与集成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]设计体验和显示标准的 Microsoft Windows 接口提供了功能强大的浏览和搜索功能公开的适配器操作。 有关如何生成 WCF 客户端的详细信息，请参阅[生成 WCF 客户端或 WCF 服务协定 Siebel 解决方案项目](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)  
  
## <a name="why-choose-the-wcf-service-model-or-the-wcf-channel-model"></a>为什么选择 WCF 服务模型或 WCF 通道模型？  
 因为它提供一种模型，可为.NET 程序员熟悉并通过通道隐藏基础 SOAP 消息交换的复杂性，WCF 服务模型通常是最佳选择，以编程的开发解决方案[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。 但是，有一些的情形，WCF 通道模型可能是更好的选择。 例如，序列化和反序列化的 XML 表示形式在 SOAP 消息的对象和用于表示它们的 WCF 服务模型中的.NET 类型之间会涉及到内存中读取整个消息。  
  
 WCF 通道模型提供对 XML 节点级别上的所有操作流式处理支持。 在节点级流中，仅 XML 消息的每个节点是在任何时候保存在内存中。 对于某些操作，例如，如果您正在执行返回大型结果集的查询的 WCF 通道模型可能更好的选择为你的应用程序。 有关使用 WCF 通道模型的详细信息，请参阅[开发 Siebel 应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-channel-model3.md)。  
  
 本部分中的主题包含信息、 过程和示例来帮助你创建并使用 WCF 服务模型来开发应用程序使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [与 Siebel 适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-siebel/overview-of-the-wcf-service-model-with-the-siebel-adapter.md)  
  
-   [元数据和 Siebel WCF 服务模型](../../adapters-and-accelerators/adapter-siebel/metadata-and-the-wcf-service-model-with-siebel.md)  
  
-   [生成 WCF 客户端或 WCF 服务协定 Siebel 解决方案项目](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)  
  
-   [配置 Siebel 系统的 WCF 客户端](../../adapters-and-accelerators/adapter-siebel/configure-a-wcf-client-for-a-siebel-system.md)  
  
-   [使用 Siebel 适配器使用 WCF 服务模型运行业务组件上的操作](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-with-the-siebel-adapter-using-wcf-service.md)  
  
-   [在上运行操作的业务组件与 MVG 字段与使用 WCF 服务模型和 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/work-with-mvp-fields-using-the-siebel-adapter-and-the-wcf-service-model.md)  
  
-   [与使用 WCF 服务模型和 Siebel 适配器调用业务服务方法](../../adapters-and-accelerators/adapter-siebel/run-business-service-methods-with-the-siebel-adapter-using-a-wcf-service.md)  
  
## <a name="see-also"></a>另请参阅  
[开发 Siebel 应用程序](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)