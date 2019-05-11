---
title: 用于 PeopleSoft Enterprise 的 BizTalk 适配器的体系结构 |Microsoft Docs
description: 介绍如何接收消息，消息是如何验证，并使用 PeopleSoft 适配器与 BizTalk Server 时，提供了组件接口方法上的信息
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f246e974-a082-430c-ad15-23a5e597738b
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d65bfed5d76d4cb78a476ee56c863247a92a7ae
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528804"
---
# <a name="peoplesoft-enterprise-adapter-architecture"></a>PeopleSoft Enterprise 适配器体系结构
在 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器的基本操作，适配器从 BizTalk Server 接收一条 XML 消息。 它包含在 SOAP 信封的 XML 消息。 用于 PeopleSoft Enterprise 的 BizTalk 适配器将转发到服务器的 SOAP 请求。 适配器与使用 PeopleSoft psjoa 类，它连接到 PeopleSoft 系统通过 Jolt 事务协议的 PeopleSoft 系统进行通信。 PeopleSoft 系统接收请求并执行业务逻辑。 通过一个类似过程发送回复。  
  
 ![](../core/media/psadapter-01-architecture.gif "PSAdapter_01_Architecture")  

  
## <a name="component-interface-methods"></a>组件接口方法  
 提供的 PeopleSoft 组件接口的基本 Api 是低级别在本质上。 客户端需要这些 Api 的多个调用。 例如，若要获得组件接口的实例的属性，客户端需要一个或多个调用来设置项的值和低级别的 Get 方法调用。 然后，它必须发送多个调用以获取的属性。 使用用于 PeopleSoft Enterprise 的 BizTalk 适配器，这样客户端所需执行一次调用来完成相同的结果中提供了一组新的标准方法 （Get、 创建、 查找和更新）。 通过让执行多个代表客户端调用用于 PeopleSoft Enterprise 的 BizTalk 适配器来执行此操作。 有关方法的详细信息，请参阅[附录 a:组件接口方法](../core/appendix-a-component-interface-methods.md)。  
  
 若要创建 PeopleSoft 的架构，用于 PeopleSoft Enterprise 的 BizTalk 适配器会检索 PeopleSoft 组件接口定义或元数据。  
  
 用于 PeopleSoft Enterprise 的 BizTalk 适配器基于发送功能的组件接口，并不需要 PeopleSoft Integration Broker。 组件接口公开为 Web 服务，可以从 BizTalk Server 进行访问。  
  
### <a name="validation"></a>验证  
 当用于 PeopleSoft Enterprise 的 BizTalk 适配器从 BizTalk Server 收到一条 XML 消息时，将执行两个级别的验证：  
  
-   XML 消息必须是有效根据 XML 规范。  
  
-   XML 消息必须与匹配内容所需的特定 Web 服务 （例如，与数据类型的接口）。  
  
> [!NOTE]
>  不会验证对于业务逻辑，这是 PeopleSoft 系统的域，对用于 PeopleSoft Enterprise 的 BizTalk 适配器是透明的。  
  
## <a name="see-also"></a>请参阅  
 [入门](../core/getting-started-with-biztalk-adapter-for-peoplesoft-enterprise.md)   