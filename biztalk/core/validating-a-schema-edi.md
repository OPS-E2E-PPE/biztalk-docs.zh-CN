---
title: 验证架构 (EDI) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6175460-2dcf-4fef-b770-02f0a058bf93
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12f54b77420a9e03e701c5e154bba681b46c166c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997510"
---
# <a name="validating-a-schema-edi"></a>验证架构 (EDI)
可以在设计时验证 EDI 架构。 为此，您可以使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境中的 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] XML 工具扩展。 验证架构操作会根据 EDI 规则来验证架构。 无需指定输入消息实例即可验证架构。  
  
## <a name="prerequisites"></a>必要條件  
 你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  
  
### <a name="to-validate-a-schema"></a>若要验证架构  
  
1. 在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，打开一个项目。 向解决方案资源管理器中的此项目添加您要验证的消息架构。  
  
   > [!NOTE]
   >  消息架构位于下的相应子文件夹[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI 文件夹。 有关安装架构文件的信息，请参阅[如何安装 EDI 架构文件](http://msdn.microsoft.com/library/787f45d9-d95d-40f4-a4ac-0a0e711f7550)。  
   > 
   > [!NOTE]
   >  无需生成此项目即可验证架构。  
  
2. 右键单击解决方案资源管理器中的架构，然后单击**验证架构**。  
  
3. 检查“输出”窗口中是否有指示操作已成功的消息。  
  
## <a name="see-also"></a>请参阅  
 [通过使用设计时 XML 工具](../core/using-design-time-xml-tools.md)