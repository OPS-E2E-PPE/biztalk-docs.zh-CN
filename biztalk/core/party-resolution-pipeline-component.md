---
title: 方解析管道组件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6ad728ff-4d7c-4ab3-af0e-76006576dce5
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2e1c9b95c84d82dd1d7e2538138bcb9f89b6b8a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971579"
---
# <a name="party-resolution-pipeline-component"></a>参与方解析管道组件

## <a name="overview"></a>概述
参与方解析管道组件用于将发件人证书或发件人安全标识符 (SID) 映射到相应的已配置 BizTalk Server 参与方。  
  
 当参与方解析组件读取传入的消息时，它采用两个消息上下文属性作为输入： **WindowsUser**和**SignatureCertificate**。 **WindowsUser**适配器，或通过自定义管道组件，使用发件人时它可以可靠地派生发件人信息的用户名称填充属性。 **SignatureCertificate**由适配器或客户端身份验证证书的指纹的 MIME/SMIME 解码器管道组件进行填充。  
  
 如果消息已签名，则对入站消息的签名进行验证所用的证书指纹将再用于在配置存储库中查找与该消息关联的参与方。 如果找到参与方，则会将该参与方的 SourcePartyID 作为该消息的创建者置于消息上下文中。  
  
 若要启用参与方解析管道组件以验证 Windows 用户，必须向参与方添加“WindowsUser”别名。 在名称和限定符字段中键入"WindowsUser"并将值设置为用户名称的格式\<域 \ 用户名称\>(例如 SOMEDOMAIN\someuser)。 在独立方案中，用于配置参与方的 WindowsUser 值应与接收适配器设置的值相匹配。  
  
 如果消息到达时这两个标记的属性的参与方解析组件，参与方解析组件首先尝试解析由证书的参与方 (假设**解决方通过证书**属性是设置为**True**)。 如果方得以解决后，为该方 SourcePartyID 放在消息的上下文中作为消息的 OriginatorPID 如果运行管道的主机进程标记为**受信任的身份验证**由管道。 如果无法使用证书完成参与方解析，则该消息的 OriginatorPID 值将标记为“s-1-5-7”（匿名用户的 SID）。 有关 OriginatorPID 属性的详细信息，请参阅[如何安全管道](../core/how-to-secure-pipelines.md)。  

## <a name="resolve-the-party"></a>解析参与方  
 下表显示了参与方解析管道组件如何尝试解析参与方：  
  
|使用 SID|由证书|WindowsUser|SignatureCertificate|结果|  
|------------|--------------------|-----------------|--------------------------|------------|  
|True|False|可用|可用或不可用|解析参与方。|  
|True|False|不可用|可用或不可用|不解析参与方，但将其标记为匿名。|  
|False|True|可用或不可用|可用或不可用|不解析参与方，但将其标记为匿名。|  
|True|True|可用|可用|解析参与方。|  
|True|True|不可用|可用或不可用|不解析参与方，但将其标记为匿名。|  
|False|False|可用或不可用|可用或不可用|不解析参与方，但将其标记为匿名。|  
  
 有关配置参与方解析管道组件的信息，请参阅[如何配置方解析管道组件](../core/how-to-configure-the-party-resolution-pipeline-component.md)。  
  
## <a name="see-also"></a>另请参阅  
-  **消息上下文属性**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]   
-  [管道组件](../core/pipeline-components.md)   
-  [自定义参与方解析（BizTalk Server 示例）](../core/custom-party-resolution-biztalk-server-sample.md)   
-  [进程间的消息验证](../core/authentication-of-messages-between-processes.md)