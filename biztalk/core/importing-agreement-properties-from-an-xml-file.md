---
title: "从 XML 文件导入协议属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c8bf5268-1742-47da-b42f-6472706a9bff
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc0bd397e49dcad670bb73e9dff9c164b9d0997a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="importing-agreement-properties-from-an-xml-file"></a>从 XML 文件导入协议属性
本部分介绍如何从 XML 模板文件中导入协议属性。  
  
## <a name="prerequisites"></a>先决条件  
 以下为执行本主题中的过程的前提条件：  
  
-   必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
-   你必须导出协议到 XML 模板文件，如中所述[导出到 XML 文件的协议属性](../core/exporting-agreement-properties-to-an-xml-file.md)。  
  
### <a name="to-import-agreement-properties-from-an-xml-file"></a>从 XML 文件导入协议属性  
  
1.  在 BizTalk Server 管理控制台中，单击**方**节点下的**BizTalk Server 管理**和**BizTalk 组**节点。 在**方和业务配置文件**页上，创建了协议中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。  
  
2.  在**协议属性**对话框中，单击**负载从模板**。  
  
    > [!NOTE]
    >  **负载从模板**仅在选择一种协议的协议后，才启用按钮。 在指定标准时，您也在隐式声明您只能导入同一编码标准的协议。  
  
3.  在**打开**对话框中，浏览到的 XML 模板文件的位置，选择的文件，然后单击**打开**。  
  
4.  在**创建模板**框中，单击**确定**。  
  
## <a name="see-also"></a>另请参阅  
 [重复使用来自另一个协议的属性](../core/reusing-properties-from-another-agreement.md)   
 [将协议属性导出为 XML 文件](../core/exporting-agreement-properties-to-an-xml-file.md)