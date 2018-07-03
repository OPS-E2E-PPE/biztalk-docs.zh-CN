---
title: 架构 Validation2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f9d1576-10df-4c5a-9ae0-618f0dd54b4e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8648b1fc098fc303f3afa2fc47733103f30a6f0a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999463"
---
# <a name="schema-validation"></a>架构验证
EDI 接收管道和 EDI 发送管道使用以下架构对消息进行验证：  
  
- **信封验证**： 服务架构`Microsoft.BizTalk.Edi.BaseArtifacts.dll`中 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]  
  
- **事务集验证**： 在架构中的消息架构将存储在[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI  
  
- **确认消息验证**: CONTRL，997 和 TA1 架构中的`Microsoft.BizTalk.Edi.BaseArtifacts.dll`。  
  
  `Microsoft.BizTalk.Edi.BaseArtifacts.dll` 中的架构由安装程序自动部署。 这些架构所示**架构**的节点**BizTalk EDI 应用程序**中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
  若要使用消息架构，您必须通过执行 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI 文件夹中的 MicrosoftEdiXSDTemplates.exe 自解压缩文件，将消息架构安装在服务器的硬盘上，然后将其部署在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 的项目中。  
  
  **架构确定**  
  
  当 EDI 接收管道处理接收消息时，它会通过协议查找和架构发现进程来确定处理该消息时要使用的架构的命名空间。 有关详细信息，请参阅[协议解析、 架构发现和收到的 EDI 消息的授权](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)。  
  
  当 EDI 发送管道创建要发送的消息时，它会使用协议属性填充信封，然后对事务集中的信息进行架构验证。 加载架构之后，发送管道会根据协议属性对架构进行验证（如果未指定任何协议，则根据后备协议进行验证）。 如果架构验证通过，管道会根据该架构对事务集进行验证。  
  
## <a name="see-also"></a>请参阅  
 [EDI 消息验证](../core/edi-message-validation.md)