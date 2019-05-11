---
title: 生成实例 (EDI) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 362b9803-4d4a-4d17-9ad6-439ec4c7d8aa
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4eea6263fe104da17cfe9cea7f5cc7da8b08a2be
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345240"
---
# <a name="generating-an-instance-edi"></a>生成实例 (EDI)
在设计时，可以从 EDI 架构生成消息实例。 若要执行此操作，您使用的 XML 工具扩展[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]环境。  
  
 你可以生成完整的批处理的交换 （带有交换和组标头） 或事务集 （没有交换和组标头）。 如果您执行该操作来生成完整交换，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将生成包含一个交换标头，为每个架构的组和每个组的三个相同的事务集的每个架构文件。 如果执行生成事务集的操作[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将生成具有单个事务集的文件。  
  
 若要生成完整的批的交换，请对批架构执行生成实例命令。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将在项目中，检测消息架构，并将自动包括这些架构的事务集。  
  
 若要生成单个事务集，对消息架构执行生成实例命令。 在这种情况下，批架构不必添加到项目。 生成的实例将不包括交换或组的标头，但是，因此将需要手动添加以具有正常工作的 EDI 交换。  
  
 当您生成一个实例，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]显示一个对话框，在其中指定该实例，包括分隔符和语法标识符中使用的配置。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  
  
### <a name="to-generate-an-instance-of-a-batched-interchange"></a>若要生成的批处理交换实例  
  
1. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开一个项目。 将消息架构添加到每种类型的消息实例中所需的事务集的解决方案资源管理器中的项目。 添加的项目到编码类型的批架构： Edifact_BatchSchema.xsd 或 X12_BatchSchema.xsd。  
  
   > [!NOTE]
   >  批处理架构位于[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI 文件夹。  
   > 
   > [!NOTE]
   >  无需生成项目以生成一个实例。  
  
2. 右键单击解决方案资源管理器中的批架构，然后单击**属性**。  
  
3. 在中**属性**窗口中，将**生成实例输出类型**到**本机**或者**XML**。 选择**本机**会提示将生成具有.txt 扩展名的平面文件。 选择**XML**会提示将生成的 XML 文件。  
  
4. 有关**输出实例文件名**、 输入的名称或浏览到的文件和选择的文件。  
  
   > [!NOTE]
   >  如果不为输出实例文件名输入一个值，将为你选择一个。 该文件名将显示在输出窗口中的[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
   > 
   > [!NOTE]
   >  如果选择现有的文件，则现有文件的内容将替换此操作生成的内容。  
  
5. 右键单击批架构，然后单击**生成实例**。  
  
6. 在中**EDI 实例属性**对话框中，选择分隔符、 标识符和其他配置选项以使用在该实例中，然后单击**确定**。  
  
7. 验证操作起作用**输出**窗口。  
  
8. 若要查看该文件，请按**控制**并单击中的链接**输出**窗口。 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 在 BizTalk 编辑器窗口中将显示该文件的内容。  
  
   > [!NOTE]
   >  在生成一个包含 837I、 837 D 或 837p 的实例时，GS08 的值将错误地设置为 00401。 有关详细信息，请参阅[的已知问题与 EDI 解决方案一起使用的 XML 工具](../core/known-issues-with-xml-tools-used-with-edi-solutions.md)。  
  
### <a name="to-generate-an-instance-of-a-transaction-set"></a>若要生成事务集的实例  
  
1. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开一个项目。 添加你想要生成的实例集的事务类型的架构。  
  
   > [!NOTE]
   >  无需将批架构添加到此项目以生成事务集的实例。  
  
   > [!NOTE]
   >  无需生成项目以生成一个实例。  
  
2. 右键单击解决方案资源管理器中的消息架构，然后单击**属性**。  
  
3. 在属性窗口中设置**生成实例输出类型**到**本机**或**XML**。 选择**本机**会提示将生成具有.txt 扩展名的平面文件。 选择**XML**会提示将生成的 XML 文件。  
  
4. 有关**输出实例文件名**、 输入的名称或浏览到的文件和选择的文件。  
  
   > [!NOTE]
   >  如果不为输出实例文件名输入一个值，将为你选择一个。 该文件名将显示在**输出**窗口中的[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
   > 
   > [!NOTE]
   >  如果选择现有的文件，则现有文件的内容将替换此操作生成的内容。  
  
5. 右键单击消息架构，然后单击**生成实例**。  
  
6. 在中**EDI 实例属性**对话框中，选择的配置选项，您想要，然后单击**确定**。  
  
7. 验证是否在一条消息**输出**窗口中，该值指示操作成功。  
  
8. 若要查看该文件，请按**控制**并单击输出窗口中的链接。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 在 BizTalk 编辑器窗口中将显示该文件的内容。  
  
9. 若要使工作的 EDI 消息，将添加到文本编辑器中的消息的交换和组标头。  
  
## <a name="see-also"></a>请参阅  
 [通过使用设计时 XML 工具](../core/using-design-time-xml-tools.md)   
 [验证实例 (EDI)](../core/validating-an-instance-edi.md)