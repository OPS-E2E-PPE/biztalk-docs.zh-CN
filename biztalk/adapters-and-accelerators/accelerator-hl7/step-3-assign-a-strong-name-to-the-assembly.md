---
title: 步骤 3： 对程序集分配强名称 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assemblies
- message enrichment tutorial, strong name assemblies
- strong name assemblies
ms.assetid: 8709e4e1-b428-42af-ba3c-08225c17a9eb
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 591423d04d8551620036e94a6ec780271e04feec
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012622"
---
# <a name="step-3-assign-a-strong-name-to-the-assembly"></a>步骤 3： 对程序集分配强名称
在此步骤中，创建并分配强名称[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]程序集。 强名称的程序集提供多个安全优势和所需部署到全局程序集缓存 (GAC) 中的项目。 强名称通过分配的数字签名和唯一的密钥对保证唯一性的程序集。 这还可通过确保没有人可以生成的程序集的后续版本的程序集的沿袭。 最后，强名称提供可靠的完整性检查以确保自您生成后，未更改的程序集的内容。  
  
### <a name="to-assign-a-strong-name-to-the-assembly"></a>若要对程序集分配强名称  
  
1. 启动**Visual Studio 命令提示符**。  
  
   > [!NOTE]
   >  如果你已创建强名称密钥，则可以重用它。  
  
2. 在命令提示符处，转到<strong>\<*驱动器*\>: \Tutorial\BTAHL7V22Common</strong> (其中\<*驱动器*\>是你安装的驱动器号），然后按**Enter**。  
  
3. 在命令提示符处，键入**sn – k key.snk**，然后按**Enter**。 出现一条消息，指示[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]密钥对写入密钥文件 key.snk。  
  
4. 在解决方案资源管理器中右键单击**BTAHL7V22Common**项目，并单击**属性**。  
  
5. 在 BTAHL7V22Common 属性页对话框中，单击**程序集**。  
  
6. 在右窗格中，向下滚动到**强名称**部分中，单击右侧的字段**程序集密钥文件**，然后单击省略号 （...） 按钮。  
  
7. 在程序集密钥文件对话框中，浏览到 **\<*驱动器*\>: \Tutorial\BTAHL7V22Common\key.snk**，单击**打开**，然后单击**确定**。  
  
8. 在解决方案资源管理器中右键单击**BTAHL7V22Common**，然后单击**部署**。 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] 创建可以从下一个项目引用的程序集。  
  
9. BTAHL7V2XCommon 项目重复步骤 4 到 8。  
  
   请继续执行[步骤 4： 创建架构](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-schemas.md)。  
  
## <a name="see-also"></a>请参阅  
 [消息充实教程](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)