---
title: 从 XML 文件导入协议属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c8bf5268-1742-47da-b42f-6472706a9bff
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cafd590f4f5936c1d12614e7a2021bc5427d49d0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969142"
---
# <a name="importing-agreement-properties-from-an-xml-file"></a>从 XML 文件导入协议属性
本部分介绍如何从 XML 模板文件中导入协议属性。  
  
## <a name="prerequisites"></a>必要條件  
 以下为执行本主题中的过程的前提条件：  
  
- 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
- 你必须导出协议到 XML 模板文件，如中所述[导出到 XML 文件的协议属性](../core/exporting-agreement-properties-to-an-xml-file.md)。  
  
### <a name="to-import-agreement-properties-from-an-xml-file"></a>从 XML 文件导入协议属性  
  
1.  在 BizTalk Server 管理控制台中，单击**参与方**节点下的**BizTalk Server 管理**并**BizTalk 组**节点。 在中**参与方和业务配置文件**页上，创建一个协议中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。  
  
2.  在中**协议属性**对话框中，单击**从模板加载**。  
  
    > [!NOTE]
    >  **从模板加载**选择协议的协议后才启用按钮。 在指定标准时，您也在隐式声明您只能导入同一编码标准的协议。  
  
3.  在中**开放**对话框中，浏览到 XML 模板文件的位置，选择的文件，然后单击**打开**。  
  
4.  在中**创建模板**框中，单击**确定**。  
  
## <a name="see-also"></a>请参阅  
 [重用其他协议的属性](../core/reusing-properties-from-another-agreement.md)   
 [将协议属性导出为 XML 文件](../core/exporting-agreement-properties-to-an-xml-file.md)