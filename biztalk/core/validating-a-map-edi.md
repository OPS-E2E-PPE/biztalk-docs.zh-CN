---
title: 验证映射 (EDI) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: caf58ecf-ed10-4c13-8d7d-e007b9158b0e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df76eda6ba42d96866cd8d3d8c4904ab2ef14f42
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65250214"
---
# <a name="validating-a-map-edi"></a>验证映射 (EDI)
可以在设计时验证映射。 若要执行此操作，您使用的 XML 工具扩展[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]环境。 此操作将生成包含基础映射和包含扩展对象的文件的 XSLT 的文件。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  
  
### <a name="to-validate-a-map"></a>若要验证映射  
  
1. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开一个项目。 解决方案资源管理器中的项目，添加你想要验证的映射和其输入和输出消息架构。  
  
   > [!NOTE]
   >  消息架构位于下的相应子文件夹[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI 文件夹。 有关安装架构文件的详细信息，请参阅[如何安装 EDI 架构文件](http://msdn.microsoft.com/library/787f45d9-d95d-40f4-a4ac-0a0e711f7550)。  
   > 
   > [!NOTE]
   >  无需生成项目即可验证映射。  
  
2. 右键单击解决方案资源管理器中的映射，然后单击**验证映射**。  
  
3. 验证在输出窗口，指示操作成功的消息。  
  
4. 请注意任何警告，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中发布**输出**窗口。  
  
5. 在中**输出**窗口中，记下名称和输出 XSLT 的路径。 该 XSL 文件都有相同的名称与映射文件，但采用 XSL 扩展名。 可以按 CTRL 并单击链接以在 BizTalk 编辑器中显示 XSL 文件。  
  
6. 在中**输出**窗口中，记下名称和扩展对象 XML 的路径。 可以按 CTRL 并单击链接以在 BizTalk 编辑器中显示 XSL 文件。  
  
## <a name="see-also"></a>请参阅  
 [通过使用设计时 XML 工具](../core/using-design-time-xml-tools.md)