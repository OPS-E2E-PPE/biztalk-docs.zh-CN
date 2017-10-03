---
title: "如何配置参与方解析管道组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- authenticating, Partner Management
- Party Resolution [pipeline component], configuring
- Partner Management, authenticating
- pipeline components, Party Resolution
ms.assetid: 0ebd30f7-3a6b-4457-8e30-80bf81fbd28d
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0c78792cd7c61ed1297954625fbd7da5aedfa04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-party-resolution-pipeline-component"></a>如何配置参与方解析管道组件
参与方解析管道组件用于将客户端的用户安全 ID 和证书主题映射到 BizTalk Server 参与方。 该映射用于加强对向 BizTalk Server 发送消息的参与方的验证。 有关合作伙伴管理的详细信息，请参阅[如何创建协议](http://msdn.microsoft.com/library/f8608cf7-8ac5-4f02-805e-5a0bdf19ca8c)。  
  
> [!NOTE]
>  若要启用参与方解析管道组件以验证 Windows 用户，您必须向参与方添加 WindowsUser 别名。 有关详细信息，请参阅[方解析管道组件](../core/party-resolution-pipeline-component.md)。  
  
### <a name="to-configure-the-properties-for-the-party-resolution-pipeline-component"></a>配置参与方解析管道组件的属性  
  
1.  将参与方解析管道组件拖至接收管道的“解析参与方”阶段中。  
  
2.  在属性窗口中，在**管道组件属性**部分中，执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**解析由证书的参与方**|设置为**True**如果你想要启用基于来自其中接收的消息的参与方的签名证书的指纹的参与方解析。<br /><br /> 默认值： **True**|  
    |**SID 解析参与方**|设置为**True**如果你想要启用基于发件人帐户的安全标识符 (SID) 的参与方解析。<br /><br /> 如果这两个属性都设置为**True**、**解决方通过证书**属性优先于**通过 SID 解析方**属性，这意味着，如果这两个证书，并且该 SID 的可用，使用证书使用者。 如果无法通过证书使用者解析当事方，该组件不会回退**通过 SID 解析方**属性，且默认值 (s-1-5-7) 标为**BTS。SourcePartyID**。<br /><br /> 默认值： **True**|  
  
> [!NOTE]
>  如果你使用的 BizTalk 消息队列的适配器和想要解析的参与方基于用户名称，将设置**解决方通过证书**到**False**和**通过 SID 解析方**到**True**。  
  
## <a name="see-also"></a>另请参阅  
 [参与方解析管道组件](../core/party-resolution-pipeline-component.md)   
 [配置本机管道组件](../core/configuring-native-pipeline-components.md)   
 [自定义参与方解析 （BizTalk Server 示例）](../core/custom-party-resolution-biztalk-server-sample.md)