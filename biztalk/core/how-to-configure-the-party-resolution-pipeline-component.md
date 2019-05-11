---
title: 如何配置参与方解析管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- authenticating, Partner Management
- Party Resolution [pipeline component], configuring
- Partner Management, authenticating
- pipeline components, Party Resolution
ms.assetid: 0ebd30f7-3a6b-4457-8e30-80bf81fbd28d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9c5c56dbb5ae5c74bfefca9554d20c3f4f10afc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340766"
---
# <a name="how-to-configure-the-party-resolution-pipeline-component"></a>如何配置参与方解析管道组件
参与方解析管道组件用于将用户安全 ID 和客户端证书使用者映射到 BizTalk Server 参与方。 若要强制实施的参与方将消息发送到 BizTalk Server 的身份验证，使用的映射。 有关合作伙伴管理的详细信息，请参阅[如何创建协议](http://msdn.microsoft.com/library/f8608cf7-8ac5-4f02-805e-5a0bdf19ca8c)。  
  
> [!NOTE]
>  若要启用参与方解析管道组件以验证 Windows 用户，必须向参与方添加 WindowsUser 别名。 有关详细信息，请参阅[参与方解析管道组件](../core/party-resolution-pipeline-component.md)。  
  
### <a name="to-configure-the-properties-for-the-party-resolution-pipeline-component"></a>若要配置参与方解析管道组件的属性  
  
1.  将参与方解析管道组件拖至接收管道解析参与方阶段。  
  
2.  在属性窗口中**管道组件属性**部分中，执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**证书解析参与方**|设置为 **，则返回 True**如果你想要启用根据从其接收消息的参与方的签名证书的指纹的参与方解析。<br /><br /> 默认值：**True**|  
    |**SID 解析参与方**|设置为 **，则返回 True**如果你想要启用根据发件人帐户的安全标识符 (SID) 的参与方解析。<br /><br /> 如果这两个属性都设置为 **，则返回 True**，则**通过证书解析参与方**属性优先于**通过 SID 解析参与方**属性; 也就是说，如果两个证书和 SID 均可用，则使用证书使用者。 如果使用证书主题无法解析参与方，该组件不会回退**通过 SID 解析参与方**属性和默认值 (s-1-5-7) 标记为**BTS。SourcePartyID**。<br /><br /> 默认值：**True**|  
  
> [!NOTE]
>  如果使用了 BizTalk 消息队列适配器并且想要解析的参与方基于用户名称，则设置**通过证书解析参与方**到**False**并**通过 SID 解析参与方**到 **，则返回 true**。  
  
## <a name="see-also"></a>请参阅  
 [参与方解析管道组件](../core/party-resolution-pipeline-component.md)   
 [配置本地管道组件](../core/configuring-native-pipeline-components.md)   
 [自定义参与方解析（BizTalk Server 示例）](../core/custom-party-resolution-biztalk-server-sample.md)