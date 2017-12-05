---
title: "SchemaValidator |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- troubleshooting, SchemaValidator utility
- validating, SchemaValidator utility
- SchemaValidator utility
- schemas, SchemaValidator utility
ms.assetid: 3bd61a03-d81e-4fd1-802c-f801000002d7
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9e3921b8bf83e3e7e775efef77a029bfda2e7e9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="schemavalidator"></a>SchemaValidator
使用 SchemaValidator 实用工具可以排除消息实例中的故障。 如果所收到的消息验证失败，则可以运行 SchemaValidator 实用工具来确定失败的根源。  
  
 如果你使用的是包含架构 .dll 文件的程序集并且没有架构 .xsd 文件，则可以使用此实用工具。 通过 SchemaValidator 实用工具，可以使用架构 .dll 文件进行验证。  
  
## <a name="location-in-sdk"></a>在 SDK 中的位置  
 \<*驱动器*\>files\microsoft BizTalk\<版本\>RosettaNet\SDK\SchemaValidator 快捷键  
  
## <a name="building-and-running-schemavalidator"></a>生成和运行 SchemaValidator  
  
#### <a name="to-build-the-schemavalidator-utility"></a>生成 SchemaValidator 实用工具  
  
1.  打开命令提示符。  
  
2.  将移动到\<*驱动器*\>files\microsoft BizTalk\<版本\>RosettaNet\SDK\SchemaValidator 快捷键。  
  
3.  在命令提示符处，键入**sn-k SchemaValidator.snk**，然后按 ENTER。  
  
4.  启动**Microsoft Visual Studio 2012**。  
  
5.  上**文件**菜单上，指向**打开**，然后单击**打开的解决方案**。  
  
6.  将移动到\<*驱动器*\>files\microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\SchemaValidator，选择**SchemaValidator.sln**，然后单击**打开**。  
  
7.  在解决方案资源管理器，右键单击**SchemaValidator**，然后单击**属性**。  
  
8.  在**MessageInspector 属性**页上，单击**签名**选项卡上，并依次**对程序集签名**复选框。 选择**SchemaValidator.snk**中**选择强名称密钥文件**。  
  
9. 单击**SchemaValidator.cs**。  
  
10. 将相应的消息实例路径键入 `Main` 中原有的以下代码行：  
  
    ```  
    const string xmlInstancePath = @"..\..\Sample3A4.xml";  
    ```  
  
11. 用对 RNPIP 程序集的引用替换 `Main` 中原有的以下代码行，然后选择相应的架构：  
  
    ```  
    _3A4_MS_V02_02_PurchaseOrderRequest BTSSchema = new _3A4_MS_V02_02_PurchaseOrderRequest();  
    ```  
  
12. 右键单击**SchemaValidator**，然后单击**生成**。  
  
13. 修改消息实例到你想要通过删除测试\< \!DOCTYPE...\>标记来指定从 XML 实例的标头的 DTD 文件。  
  
14. 在消息实例的根节点下，添加要对其进行验证的架构的 XML 命名空间。  
  
    > [!NOTE]
    >  准备要由 SchemaValidator 实用工具验证架构的示例，请参阅中的 Sample3A4.xml \<*驱动器*\>files\microsoft BizTalk\<版本\>快捷键有关 RosettaNet\SDK\SchemaValidator。  
  
15. 在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，单击**SchemaValidator.cs**，然后按 CTRL 键和 F5 以运行该实用程序。  
  
## <a name="remarks"></a>注释  
 由于 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK 包含 SchemaValidator 代码，因此可以向该实用工具添加逻辑。 例如，可以将其做成命令行实用工具。  
  
## <a name="see-also"></a>另请参阅  
 [实用工具](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)