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
ms.openlocfilehash: 82674b175ad1c408b6ddb9f7823427a550288e96
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999294"
---
# <a name="generating-an-instance-edi"></a>生成实例 (EDI)
在设计阶段，可以从 EDI 架构生成消息实例。 为此，您可以使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境中的 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] XML 工具扩展。  
  
 可以生成完整的批交换（带有交换和组标头）或者事务集（没有交换和组标头）。 如果执行生成完整交换的操作，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将生成具有一个交换标头的文件，并且为每个架构生成一个组，为每个架构的每个组生成三个相同的事务集。 如果执行生成事务集的操作，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将生成具有单个事务集的文件。  
  
 要生成一个完整的批交换，可对批架构执行生成实例命令。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将检测项目中的消息架构，并且将自动包括这些架构的事务集。  
  
 要生成单个事务集，可以对消息架构执行生成实例命令。 在此情况下，不需要将批架构添加到项目中。 但是，生成的实例将不包括交换或组标头，因此，您必须手动添加以获得能够工作的 EDI 交换。  
  
 在生成实例时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会显示一个对话框，可在其中指定该实例中使用的配置，包括分隔符和语法标识符。  
  
## <a name="prerequisites"></a>必要條件  
 你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  
  
### <a name="to-generate-an-instance-of-a-batched-interchange"></a>若要生成的批处理交换实例  
  
1. 在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，打开一个项目。 在解决方案资源管理器中，针对要在消息实例中包括的每种类型的事务集向项目添加消息架构。 添加的项目到编码类型的批架构： Edifact_BatchSchema.xsd 或 X12_BatchSchema.xsd。  
  
   > [!NOTE]
   >  批处理架构位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI 文件夹中。  
   > 
   > [!NOTE]
   >  您不需要生成项目来生成实例。  
  
2. 右键单击解决方案资源管理器中的批架构，然后单击**属性**。  
  
3. 在中**属性**窗口中，将**生成实例输出类型**到**本机**或者**XML**。 选择**本机**会提示将生成具有.txt 扩展名的平面文件。 选择**XML**会提示将生成的 XML 文件。  
  
4. 有关**输出实例文件名**、 输入的名称或浏览到的文件和选择的文件。  
  
   > [!NOTE]
   >  如果没有为输出实例文件名输入一个值，系统将为您选择一个文件名。 该文件名将显示在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 的“输出”窗口中。  
   > 
   > [!NOTE]
   >  如果选择了某个现有文件，将使用此操作生成的内容替换现有文件的内容。  
  
5. 右键单击批架构，然后单击**生成实例**。  
  
6. 在中**EDI 实例属性**对话框中，选择分隔符、 标识符和其他配置选项以使用在该实例中，然后单击**确定**。  
  
7. 验证操作起作用**输出**窗口。  
  
8. 若要查看该文件，请按**控制**并单击中的链接**输出**窗口。 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 在 BizTalk 编辑器窗口中将显示该文件的内容。  
  
   > [!NOTE]
   >  在生成一个包含 837I、 837 D 或 837p 的实例时，GS08 的值将错误地设置为 00401。 有关详细信息，请参阅[的已知问题与 EDI 解决方案一起使用的 XML 工具](../core/known-issues-with-xml-tools-used-with-edi-solutions.md)。  
  
### <a name="to-generate-an-instance-of-a-transaction-set"></a>若要生成事务集的实例  
  
1. 在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，打开一个项目。 添加要为其生成实例的事务集类型的架构。  
  
   > [!NOTE]
   >  无需将批架构添加到项目即可生成事务集的实例。  
  
   > [!NOTE]
   >  您不需要生成项目来生成实例。  
  
2. 右键单击解决方案资源管理器中的消息架构，然后单击**属性**。  
  
3. 在属性窗口中设置**生成实例输出类型**到**本机**或**XML**。 选择**本机**会提示将生成具有.txt 扩展名的平面文件。 选择**XML**会提示将生成的 XML 文件。  
  
4. 有关**输出实例文件名**、 输入的名称或浏览到的文件和选择的文件。  
  
   > [!NOTE]
   >  如果没有为输出实例文件名输入一个值，系统将为您选择一个文件名。 该文件名将显示在**输出**窗口中的[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
   > 
   > [!NOTE]
   >  如果选择了某个现有文件，将使用此操作生成的内容替换现有文件的内容。  
  
5. 右键单击消息架构，然后单击**生成实例**。  
  
6. 在中**EDI 实例属性**对话框中，选择的配置选项，您想要，然后单击**确定**。  
  
7. 验证是否在一条消息**输出**窗口中，该值指示操作成功。  
  
8. 若要查看该文件，请按**控制**并单击输出窗口中的链接。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 在 BizTalk 编辑器窗口中将显示该文件的内容。  
  
9. 若要生成可工作的 EDI 消息，请在文本编辑器中将交换和组标头添加到消息中。  
  
## <a name="see-also"></a>请参阅  
 [通过使用设计时 XML 工具](../core/using-design-time-xml-tools.md)   
 [验证实例 (EDI)](../core/validating-an-instance-edi.md)