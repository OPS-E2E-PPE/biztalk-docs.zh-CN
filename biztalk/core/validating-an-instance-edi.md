---
title: 验证实例 (EDI) |Microsoft Docs
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
ms.openlocfilehash: 966c0323619985766eb39611c25fe813588b4082
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394047"
---
# <a name="validating-an-instance-edi"></a>验证实例 (EDI)
您可以在设计时验证针对其 EDI 架构实例。 若要执行此操作，您使用的 XML 工具扩展[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]环境。 验证的实例可以是单个事务集 （没有交换和组标头）、 是将单个事务集 （带有交换和组标头），包含的交换或具有多个事务集 （具有完整的批的交换交换和组标头）。  
  
> [!NOTE]
>  不支持验证 xml 保留交换。 但是，支持的保留的交换的 EDI 验证。  
  
 验证实例操作的执行 EDI 和 XSD 验证。  
  
 当验证实例，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]显示一个对话框，在其中指定要验证该实例，包括分隔符和语法标识符中的配置。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  
  
### <a name="to-validate-an-instance-against-its-schema"></a>若要验证针对其架构实例  
  
1. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开一个项目。  
  
2. 在解决方案资源管理器，向项目添加所需的消息实例的所有架构。  
  
   1. 如果您要验证单个事务集没有交换和组标头，添加该事务集的文档架构。  
  
   2. 如果验证的是包含单个事务集的交换，将添加到项目的事务的架构和消息使用的编码类型的批架构 (Edifact_BatchSchema.xsd 或 X12_BatchSchema.xsd 中的[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI)。  
  
      > [!NOTE]
      >  所需的批架构验证信封的实例。 如果您打算使用仅在消息架构，将不验证信封。  
  
   3. 如果您要验证包含多个事务集的批处理的交换，将添加到项目的架构中消息实例，并使用消息的编码类型的批架构的每个事务集组 (任一 Edifact_BatchSchema.xsd 或中的 X12_BatchSchema.xsd [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI)。  
  
      > [!NOTE]
      >  如果已自定义服务架构，必须文档 （事务集） 架构除了包括自定义服务架构在 BizTalk 项目中，并且如有必要，批架构。  
  
      > [!NOTE]
      >  无需生成项目以验证实例。  
  
3. 在解决方案资源管理器中显示架构的属性页，如下所示：  
  
   1.  如果您要验证单个事务集，右键单击该事务集，该文档架构，然后单击**属性**。  
  
   2.  如果您要验证是包含单个事务集的交换或包含多个事务集的批处理的交换，右键单击批架构 （Edifact_BatchSchema.xsd 或 X12_BatchSchema.xsd 架构），然后单击**属性**.  
  
4. 在此架构中，属性窗口中的**输入实例文件名**输入名称和你想要验证，或浏览到该文件，选择它，，然后单击消息实例路径**确定**。  
  
5. 有关**验证实例输入类型**，输入要进行验证的文件类型：**本机**EDI 文件或**XML**的 XML 文件。  
  
   > [!NOTE]
   >  不支持验证 xml 保留交换。 如果您选择的 XML**验证实例输入类型**属性验证保留的交换时，该操作将失败，并且不会返回。 但是，如果您选择**本机**有关**验证实例输入类型**时验证保留的交换，操作将成功。  
  
6. 右键单击消息架构 （Edifact_BatchSchema.xsd 或 X12_BatchSchema.xsd 如果验证是包含单个事务集的交换或批处理的交换），然后单击**验证实例**。  
  
7. 在中**EDI 实例属性**对话框框中，执行以下操作：  
  
   1.  如果实例应使用重复分隔符，则选择**重复分隔符**。  
  
   2.  如果实例应使用尾部分隔符，则选择**是**有关**使用尾部分隔符**。  
  
   3.  如果实例应使用字符集以外**基本**，选择**扩展**或**Unicode**中**语法标识符**。  
  
   4.  单击“确定” 。  
  
       > [!NOTE]
       >  **EDI 实例属性**可能会出现第二次后单击了对话框**确定**。 如果是这样，请单击**确定**试。  
  
       > [!NOTE]
       >  **EDI 实例属性**对话框将填充与针对同一登录的用户运行的最后一个验证实例操作中使用的相同值。  
  
8. 验证是否在一条消息**输出**窗口中，该值指示操作成功。  
  
## <a name="see-also"></a>请参阅  
 [通过使用设计时 XML 工具](../core/using-design-time-xml-tools.md)   
 [生成实例 (EDI)](../core/generating-an-instance-edi.md)