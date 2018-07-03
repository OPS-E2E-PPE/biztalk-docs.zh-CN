---
title: 参与方解析管道组件 |Microsoft Docs
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
ms.openlocfilehash: 20a466c2de29859b6a971fd34540d6a806da9fe1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977078"
---
# <a name="party-resolution-pipeline-component"></a>参与方解析管道组件

## <a name="overview"></a>概述
参与方解析管道组件用于将发件人证书或发件人安全标识符 (SID) 映射到相应的已配置 BizTalk Server 参与方。  

 当参与方解析组件读取传入消息时，它使用两个消息上下文属性作为输入： **WindowsUser**并**SignatureCertificate**。 **WindowsUser**适配器，或通过自定义管道组件，它可以可靠地派生发件人信息的发送程序的用户名填充属性。 **SignatureCertificate**填充由适配器或 MIME/SMIME 解码器管道组件使用的客户端身份验证证书的指纹。  

 如果消息已签名，则对入站消息的签名进行验证所用的证书指纹将再用于在配置存储库中查找与该消息关联的参与方。 如果找到参与方，则会将该参与方的 SourcePartyID 作为该消息的创建者置于消息上下文中。  

 若要启用参与方解析管道组件以验证 Windows 用户，必须向参与方添加“WindowsUser”别名。 在名称和限定符字段中键入"WindowsUser"，并将值设置为中的格式的用户名\<域 \ 用户名\>(例如 SOMEDOMAIN\someuser)。 在独立方案中，用于配置参与方的 WindowsUser 值应与接收适配器设置的值相匹配。  

 如果消息到达具有这两个标记的属性的参与方解析组件，参与方解析组件首先尝试通过证书解析参与方 (假设**通过证书解析参与方**属性设置为 **，则返回 True**)。 如果解析参与方后，该参与方的 SourcePartyID 将放在消息的上下文作为消息的 OriginatorPID 如果运行管道的主机进程标记为**受信任验证**由管道。 如果无法使用证书完成参与方解析，则该消息的 OriginatorPID 值将标记为“s-1-5-7”（匿名用户的 SID）。 有关 OriginatorPID 属性的详细信息，请参阅[如何确保管道](../core/how-to-secure-pipelines.md)。  

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

 有关配置参与方解析管道组件的信息，请参阅[如何配置参与方解析管道组件](../core/how-to-configure-the-party-resolution-pipeline-component.md)。  

## <a name="see-also"></a>请参阅  
- **消息上下文属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]   
- [管道组件](../core/pipeline-components.md)   
- [自定义参与方解析（BizTalk Server 示例）](../core/custom-party-resolution-biztalk-server-sample.md)   
- [进程间的消息验证](../core/authentication-of-messages-between-processes.md)
