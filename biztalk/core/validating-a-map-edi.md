---
title: "验证映射 (EDI) |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: caf58ecf-ed10-4c13-8d7d-e007b9158b0e
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 028a152be285bb79f3cd0899b2143e99ef2b6042
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="validating-a-map-edi"></a>验证映射 (EDI)
您可以在设计时验证映射。 若要执行此操作，你使用的 XML 工具扩展[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]环境。 此操作将生成两个文件，一个包含映射的基础 XSLT，另一个包含扩展对象。  
  
## <a name="prerequisites"></a>先决条件  
 你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  
  
### <a name="to-validate-a-map"></a>若要验证映射  
  
1.  在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，打开一个项目。 对于解决方案资源管理器中的项目，请添加要验证的映射及其输入和输出消息架构。  
  
    > [!NOTE]
    >  消息架构下的相应子文件夹位于[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI 文件夹。 有关安装的架构文件的详细信息，请参阅[如何安装 EDI 架构文件](http://msdn.microsoft.com/library/787f45d9-d95d-40f4-a4ac-0a0e711f7550)。  
  
    > [!NOTE]
    >  您不需要生成项目即可验证映射。  
  
2.  右键单击解决方案资源管理器中的映射，然后单击**验证映射**。  
  
3.  检查“输出”窗口中是否有指示操作已成功的消息。  
  
4.  请注意任何警告，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中已投递**输出**窗口。  
  
5.  在**输出**窗口中，记下名称和输出 XSLT 的路径。 该 XSL 文件的指定名称与映射文件的名称相同，但采用 XSL 扩展名。 您可以按住 Ctrl 键并单击链接，以便在 BizTalk 编辑器中显示 XSL 文件。  
  
6.  在**输出**窗口中，记下名称和路径的扩展对象 XML。 您可以按住 Ctrl 键并单击链接，以便在 BizTalk 编辑器中显示 XSL 文件。  
  
## <a name="see-also"></a>另请参阅  
 [通过使用设计时 XML 工具](../core/using-design-time-xml-tools.md)