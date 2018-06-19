---
title: 验证实例 (EDI) |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e0fe4e87-5ab4-41e4-8ceb-8f6cf40cae0b
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cceea8afe67f7e69b3ee842198d9a5373a972d04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288909"
---
# <a name="validating-an-instance-edi"></a>验证实例 (EDI)
你可以在设计时验证对照其 EDI 架构实例。 为此，您可以使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境中的 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] XML 工具扩展。 你验证该实例可以使用单个事务集 （具有交换和组标题） 的交换或使用多个事务集 （具有完成批处理的交换单个事务设置 （而无需交换和组标头）交换标题和组标题）。  
  
> [!NOTE]
>  不支持验证的 XML 保留交换。 但是，支持的保留交换 EDI 验证。  
  
 验证实例操作执行 EDI 和 XSD 验证。  
  
 在验证实例时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会显示一个对话框，可在其中指定该实例中要验证的配置，包括分隔符和语法标识符。  
  
## <a name="prerequisites"></a>先决条件  
 你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  
  
### <a name="to-validate-an-instance-against-its-schema"></a>若要验证对照其架构实例  
  
1.  在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，打开一个项目。  
  
2.  在解决方案资源管理器向项目中添加所需的消息实例的所有架构。  
  
    1.  如果您要验证设置而无需交换和组标头单个事务，将添加为该事务集的文档架构。  
  
    2.  如果验证的是包含一个事务集的交换，则向项目添加该事务的架构和消息使用的编码类型的批架构（即 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] XSD_Schema\EDI 中的 Edifact_BatchSchema.xsd 或 X12_BatchSchema.xsd）。  
  
        > [!NOTE]
        >  要验证的信封中实例，需使用批处理架构。 如果你是使用仅的消息架构，将不验证信封。  
  
    3.  如果验证的是包含多个事务集的批处理交换，则向项目添加消息实例中各事务集组的架构和消息使用的编码类型的批架构（即 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] XSD_Schema\EDI 中的 Edifact_BatchSchema.xsd 或 X12_BatchSchema.xsd）。  
  
        > [!NOTE]
        >  如果你已自定义服务架构，你将必须包括在 BizTalk 项目中，自定义服务架构此外到的文档 （事务集） 架构和必要时，批处理架构。  
  
        > [!NOTE]
        >  无需生成项目，以验证实例。  
  
3.  在解决方案资源管理器，显示架构的属性页，如下所示：  
  
    1.  如果您要验证单个事务集，右键单击该组事务的文档架构，然后单击**属性**。  
  
    2.  如果您要验证使用单个事务集的交换或使用多个事务集批处理的交换，右键单击批处理架构 （Edifact_BatchSchema.xsd 或 X12_BatchSchema.xsd 架构），然后单击**属性**.  
  
4.  对于架构，属性窗口中为**输入实例 Filename**输入的名称和你想要验证，或浏览到文件，选择它，，然后单击消息实例的路径**确定**。  
  
5.  有关**验证实例输入类型**，输入要将验证的文件类型：**本机**EDI 文件或**XML**有关 XML 文件。  
  
    > [!NOTE]
    >  不支持验证的 XML 保留交换。 如果你选择 XML for**验证实例输入类型**属性验证保留的交换时，操作将失败，并且将返回任何内容。 但是，如果你选择**本机**为**验证实例输入类型**时验证保留的交换，操作将成功。  
  
6.  右键单击消息架构 （Edifact_BatchSchema.xsd 或 X12_BatchSchema.xsd 如果验证使用单个事务集的交换或批处理的交换），然后单击**验证实例**。  
  
7.  在**EDI 实例属性**对话框框中，执行以下操作：  
  
    1.  如果你的实例应使用重复分隔符，则选择**重复分隔符**。  
  
    2.  如果你的实例应使用尾随分隔符，则选择**是**为**尾随分隔符的使用**。  
  
    3.  如果你的实例应使用的字符集以外**基本**，选择**扩展**或**Unicode**中**语法标识符**。  
  
    4.  单击 **“确定”**。  
  
        > [!NOTE]
        >  **EDI 实例属性**可能会出现第二次后单击了对话框**确定**。 如果是这样，则单击**确定**试。  
  
        > [!NOTE]
        >  **EDI 实例属性**对话框中将使用相同的值已运行的最后一个验证实例操作中使用的同一个登录的用户进行填充。  
  
8.  验证是否有一条消息采用**输出**窗口，该值指示该操作成功。  
  
## <a name="see-also"></a>另请参阅  
 [通过使用设计时 XML 工具](../core/using-design-time-xml-tools.md)   
 [生成实例 (EDI)](../core/generating-an-instance-edi.md)