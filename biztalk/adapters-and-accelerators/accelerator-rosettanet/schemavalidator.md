---
title: SchemaValidator |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting, SchemaValidator utility
- validating, SchemaValidator utility
- SchemaValidator utility
- schemas, SchemaValidator utility
ms.assetid: 3bd61a03-d81e-4fd1-802c-f801000002d7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2be96f3d87cb0744ca4e823942f7265bf6b3fa3e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281974"
---
# <a name="schemavalidator"></a>SchemaValidator
使用 SchemaValidator 实用工具来排除与消息实例。 如果你收到一条消息，未通过验证，可以运行 SchemaValidator 实用工具来确定失败的原因。  
  
 如果您使用的包含架构.dll 文件，程序集使用此实用程序和没有架构.xsd 文件。 SchemaValidator 实用工具，可以使用架构.dll 文件进行验证。  
  
## <a name="location-in-sdk"></a>在 SDK 中的位置  
 \<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\SchemaValidator  
  
## <a name="building-and-running-schemavalidator"></a>生成和运行 SchemaValidator  
  
#### <a name="to-build-the-schemavalidator-utility"></a>生成 SchemaValidator 实用工具  
  
1. 打开命令提示符。  
  
2. 将移动到\<*驱动器*\>\Program 文件 (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\SchemaValidator。  
  
3. 在命令提示符处，键入**sn-k SchemaValidator.snk**，然后按 ENTER。  
  
4. 启动**Microsoft Visual Studio 2012**。  
  
5. 上**文件**菜单，依次指向**打开**，然后单击**打开的解决方案**。  
  
6. 将移动到\<*驱动器*\>\Program 文件 (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\SchemaValidator，选择**SchemaValidator.sln**，然后单击**打开**。  
  
7. 在解决方案资源管理器中右键单击**SchemaValidator**，然后单击**属性**。  
  
8. 在中**MessageInspector 属性**页上，单击**签名**选项卡，然后依次**程序集签名**复选框。 选择**SchemaValidator.snk**中**选择一个强名称密钥文件**。  
  
9. 单击**SchemaValidator.cs**。  
  
10. 在代码中原有的以下行中键入相应的消息实例路径`Main`:  
  
    ```  
    const string xmlInstancePath = @"..\..\Sample3A4.xml";  
    ```  
  
11. 替换原有的以下行中的代码`Main`到 Rnpip 程序集，然后选择相应的架构的引用：  
  
    ```  
    _3A4_MS_V02_02_PurchaseOrderRequest BTSSchema = new _3A4_MS_V02_02_PurchaseOrderRequest();  
    ```  
  
12. 右键单击**SchemaValidator**，然后单击**生成**。  
  
13. 修改消息实例到你想要通过删除测试\< \!DOCTYPE...\>标记来指定从 XML 实例的标头的 DTD 文件。  
  
14. 在消息实例的根节点，添加对其进行验证的架构的 XML 命名空间。  
  
    > [!NOTE]
    >  准备好可由 SchemaValidator 实用工具进行验证的架构的示例，请参阅中的 Sample3A4.xml \<*驱动器*\>\Program 文件 (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\SchemaValidator。  
  
15. 在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，单击**SchemaValidator.cs**，然后按 CTRL 和 F5 以运行此实用工具。  
  
## <a name="remarks"></a>备注  
 因为[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]SDK 包含 SchemaValidator 代码，可以将逻辑添加到该实用工具。 例如，您可以使其提供一个命令行实用工具。  
  
## <a name="see-also"></a>请参阅  
 [实用工具](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)
