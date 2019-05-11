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
ms.openlocfilehash: fc2a90b0b707b9ab037968f7636d75437a43d1a9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279597"
---
# <a name="validating-a-schema-edi"></a>验证架构 (EDI)
可以在设计时验证 EDI 架构。 若要执行此操作，您使用的 XML 工具扩展[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]环境。 验证架构操作来验证根据 EDI 规则的架构。 无需指定输入的消息实例即可验证架构。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  
  
### <a name="to-validate-a-schema"></a>若要验证架构  
  
1. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开一个项目。 解决方案资源管理器中的项目，添加你想要验证的消息架构。  
  
   > [!NOTE]
   >  消息架构位于下的相应子文件夹[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI 文件夹。 有关安装架构文件的信息，请参阅[如何安装 EDI 架构文件](http://msdn.microsoft.com/library/787f45d9-d95d-40f4-a4ac-0a0e711f7550)。  
   > 
   > [!NOTE]
   >  无需生成项目即可验证架构。  
  
2. 右键单击解决方案资源管理器中的架构，然后单击**验证架构**。  
  
3. 验证在输出窗口，指示操作成功的消息。  
  
## <a name="see-also"></a>请参阅  
 [通过使用设计时 XML 工具](../core/using-design-time-xml-tools.md)