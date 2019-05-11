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
ms.openlocfilehash: f74afc7c9b0a10c5050ce13d7ce5ab9c8c13967f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396873"
---
# <a name="schema-validation"></a>架构验证
EDI 接收管道和 EDI 发送管道验证使用以下架构的消息：  
  
- **信封验证**:服务架构`Microsoft.BizTalk.Edi.BaseArtifacts.dll`中 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]  
  
- **事务集验证**:在架构中的消息架构将存储在[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI  
  
- **确认消息验证**:CONTRL，997 和 TA1 架构中的`Microsoft.BizTalk.Edi.BaseArtifacts.dll`。  
  
  中的架构`Microsoft.BizTalk.Edi.BaseArtifacts.dll`由安装程序自动部署。 这些架构所示**架构**的节点**BizTalk EDI 应用程序**中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
  若要使用的消息架构，必须安装在你的服务器的硬盘驱动器上的执行中的 MicrosoftEdiXSDTemplates.exe 自解压缩文件[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI 文件夹中，然后将其部署在你的项目中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
  **架构确定**  
  
  当 EDI 接收管道处理接收消息时，它确定要在通过协议查找和架构发现进程处理该消息中使用的架构的命名空间。 有关详细信息，请参阅[协议解析、 架构发现和收到的 EDI 消息的授权](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)。  
  
  当 EDI 发送管道创建要发送的消息时，它使用协议属性填充信封，然后事务集中执行架构验证的信息。 加载架构之后, 的发送管道验证对协议属性 （或如果已指定不存在的协议的后备协议） 的架构。 如果架构验证通过，管道会验证的事务集根据架构。  
  
## <a name="see-also"></a>请参阅  
 [EDI 消息验证](../core/edi-message-validation.md)