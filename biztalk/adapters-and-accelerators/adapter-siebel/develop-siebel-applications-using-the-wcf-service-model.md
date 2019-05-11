---
title: 开发 Siebel 应用程序使用 WCF 服务模型 |Microsoft Docs
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
ms.openlocfilehash: eb741b6a40f5489aded365c9f3ffe91bf12ba6da
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371706"
---
# <a name="develop-siebel-applications-using-the-wcf-service-model"></a>开发 Siebel 应用程序使用 WCF 服务模型
[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] 提供了编程模型调用 WCF 服务模型，该部分，可以帮助解决的一些其他编程模型限制 — WCF 通道模型。  
  
 最低级别[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]显示在其中客户端调用服务上的操作由客户端和服务终结点之间建立的通道通过交换 SOAP 消息的 WCF 通道模型。 WCF 通道模型公开的数据类型和方法，使你能够直接在 WCF 通道体系结构上运行。 WCF 通道模型为您提供直接控制对您创建的 SOAP 消息的内容和方式这两个应用程序和[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]使用它们。 但是，创建格式正确的 SOAP 消息在通道上发送和验证返回的答复消息可以是详细、 更严格的任务。  
  
 WCF 服务模型，但是，需要使用的代理类来调用目标服务上的操作，或若要从客户端接收操作。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel 系统公开为 WCF 服务可在其调用操作。  
  
- 用于目标服务调用操作的代理类调用 WCF 客户端类。 此类模型由服务公开为强类型化参数使用的.NET 方法的操作。 通过使用 WCF 服务模型，可以调用公开的操作[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]为 WCF 客户端上的.NET 方法。 有关 WCF 客户端的详细信息，请参阅[WCF 客户端概述](https://msdn.microsoft.com/library/ms735103.aspx)。   
  
  使用工具来生成 WCF 客户端类和关联的服务元数据中的帮助器代码的[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]公开。 您可以使用以下工具：  
  
- ServiceModel Metadata Utility Tool (svcutil.exe)，其中附带了 WCF  
  
- [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，附带的 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]  
  
  [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]与集成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]设计体验并提供标准的 Microsoft Windows 接口提供了功能强大的浏览和搜索功能对由适配器公开的操作。 有关如何生成 WCF 客户端的详细信息，请参阅[生成 WCF 客户端或 WCF 服务协定为 Siebel 解决方案项目](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)  
  
## <a name="why-choose-the-wcf-service-model-or-the-wcf-channel-model"></a>为什么选择 WCF 服务模型或 WCF 通道模型？  
 因为它提供的是.NET 程序员所熟悉的基础 SOAP 消息交换的复杂性隐藏通过通道模型时，WCF 服务模型通常是最佳选择开发的编程解决方案[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。 但是，有的方案中的 WCF 通道模型可能更好的选择。 例如，序列化和反序列化的 XML 表示形式中的 SOAP 消息的对象和用来表示它们的 WCF 服务模型中的.NET 类型之间涉及到读取到内存中的整个消息。  
  
 WCF 通道模型提供的 XML 节点级别上的所有操作流式处理支持。 在流中节点级别，只能将 XML 消息的每个节点是一次保存在内存中。 对于某些操作，例如，如果您正在执行查询返回大型结果集的 WCF 通道模型可能更好的选择为应用程序。 有关使用 WCF 通道模型的详细信息，请参阅[开发 Siebel 应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-channel-model3.md)。  
  
 在本部分中的主题包含信息、 步骤和示例来帮助你创建和使用 WCF 服务模型开发应用程序使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用 Siebel 适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-siebel/overview-of-the-wcf-service-model-with-the-siebel-adapter.md)  
  
-   [元数据和具有 Siebel 的 WCF 服务模型](../../adapters-and-accelerators/adapter-siebel/metadata-and-the-wcf-service-model-with-siebel.md)  
  
-   [生成 WCF 客户端或 WCF 服务协定为 Siebel 解决方案项目](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)  
  
-   [为 Siebel 系统配置 WCF 客户端](../../adapters-and-accelerators/adapter-siebel/configure-a-wcf-client-for-a-siebel-system.md)  
  
-   [使用 Siebel 适配器使用 WCF 服务模型运行业务组件上的操作](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-with-the-siebel-adapter-using-wcf-service.md)  
  
-   [使用 Siebel 适配器使用 WCF 服务模型运行在包含 MVG 字段的业务组件上的操作](../../adapters-and-accelerators/adapter-siebel/work-with-mvp-fields-using-the-siebel-adapter-and-the-wcf-service-model.md)  
  
-   [使用 Siebel 适配器使用 WCF 服务模型中调用业务服务方法](../../adapters-and-accelerators/adapter-siebel/run-business-service-methods-with-the-siebel-adapter-using-a-wcf-service.md)  
  
## <a name="see-also"></a>请参阅  
[开发 Siebel 应用程序](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)