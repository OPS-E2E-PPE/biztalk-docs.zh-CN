---
title: "BizTalk Adapter for PeopleSoft 企业体系结构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- validating, XML messages
- architecture
- XML, messages
- XML, validating
ms.assetid: f246e974-a082-430c-ad15-23a5e597738b
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 377e49af3a20302b92a4214959b534c9d0949a93
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="architecture-of-biztalk-adapter-for-peoplesoft-enterprise"></a>PeopleSoft Enterprise 的 BizTalk 适配器的体系结构
在用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器的基本操作过程中，适配器会接收来自 BizTalk Server 的 XML 消息。 它包含 SOAP 信封中的 XML 消息。 PeopleSoft Enterprise 的 BizTalk 适配器会将 SOAP 请求转发给服务器。 适配器使用 PeopleSoft psjoa 类与 PeopleSoft 系统进行通信，通过 Jolt 事务协议连接到 PeopleSoft 系统。 PeopleSoft 系统接收请求，并执行业务逻辑。 通过一个类似过程发送回复。  
  
 ![](../core/media/psadapter-01-architecture.gif "PSAdapter_01_Architecture")  
适配器体系结构  
  
## <a name="peoplesoft-component-interface-methods"></a>PeopleSoft 组件接口方法  
 PeopleSoft 组件接口所提供的基本 API 在性质上是低级的。 客户端要求这些 API 的多次调用。 例如，若要获得组件接口的实例属性，客户端需要一个或多个调用来设置低级别 Get 方法调用后面的项值。 然后，它必须发送多个调用以获取其属性。 使用 PeopleSoft Enterprise 的 BizTalk 适配器，使用此方法提供一组新的标准方法（Get、Create、Find 和 Update），以便需要客户端进行单一调用完成相同结果。 通过代表客户端使 PeopleSoft Enterprise 的 BizTalk 适配器执行多个调用，完成操作。 有关方法的详细信息，请参阅[附录 a： 组件接口方法](../core/appendix-a-component-interface-methods.md)。  
  
 若要创建 PeopleSoft 的架构，则 PeopleSoft Enterprise 的 BizTalk 适配器会检索 PeopleSoft 组件接口定义或元数据。  
  
 PeopleSoft Enterprise 的 BizTalk 适配器是基于“发送”功能的组件接口，并且不需要 PeopleSoft Integration Broker。 组件接口公开为 Web 服务，可以通过 BizTalk Server 进行访问。  
  
### <a name="validation"></a>验证  
 当 PeopleSoft Enterprise 的 BizTalk 适配器接收来自 BizTalk Server 的 XML 消息时，会执行两个级别的验证：  
  
-   根据 XML 规范，XML 消息必须有效。  
  
-   XML 消息必须与特定 Web 服务要求的内容相匹配（例如，接口与数据类型相匹配）。  
  
> [!NOTE]
>  对于业务逻辑（是 PeopleSoft 系统的域，并且对 PeopleSoft Enterprise 的 BizTalk 适配器是透明的）没有验证。  
  
## <a name="see-also"></a>另请参阅  
 [入门](../core/getting-started-with-biztalk-adapter-for-peoplesoft-enterprise.md)   
 [规划和体系结构](../core/planning-and-architecture13.md)