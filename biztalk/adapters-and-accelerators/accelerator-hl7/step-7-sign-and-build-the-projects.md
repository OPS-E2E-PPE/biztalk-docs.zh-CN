---
title: 步骤 7：登录和生成项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, projects
- projects, building
- projects, signing
ms.assetid: b66e4dc1-4ec6-4ec0-a69a-419b116b19c1
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2912ceb1128a1f9a51acdbda6743b687128bd38
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65287891"
---
# <a name="step-7-sign-and-build-the-projects"></a>步骤 7：登录和生成项目
在此步骤中，指定一个强名称和生成项目以生成包含你在中创建的资源 （架构） 的程序集[步骤 6:验证架构](../../adapters-and-accelerators/accelerator-hl7/step-6-validate-the-schemas.md)。 这还可确保到目前为止完成的工作中没有任何编译错误。  
  
### <a name="to-sign-the-btahl7-project"></a>若要登录 BTAHL7 项目  
  
1.  在解决方案资源管理器中右键单击**BTAHL7 项目**，然后单击**属性**。  
  
2.  在 BTAHL7 项目属性页对话框中，单击**程序集**。  
  
3.  在右窗格中，向下滚动到**强名称**部分中，单击右侧的字段**程序集密钥文件**，然后单击省略号 （...） 按钮。  
  
4.  在程序集密钥文件对话框中，浏览到 **\<*驱动器*\>: \Tutorial\BTAHL7V22Common\key.snk** (在创建[步骤 3:对程序集分配强名称](../../adapters-and-accelerators/accelerator-hl7/step-3-assign-a-strong-name-to-the-assembly.md))，然后单击**打开**。  
  
5.  单击**确定**以保存更改。  
  
### <a name="to-build-the-btahl7-project"></a>若要生成 BTAHL7 项目  
  
- 在解决方案资源管理器中右键单击**BTAHL7 项目**，然后单击**部署**。 [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)] 编译到 DLL 文件的程序集，并将其保存在\<*驱动器*\>: \Tutorial\BTAHL7V22Common\Bin\Development 文件夹。  
  
  请继续执行[步骤 8:与 BizTalk 映射器创建映射](../../adapters-and-accelerators/accelerator-hl7/step-8-create-a-map-with-biztalk-mapper.md)。  
  
## <a name="see-also"></a>请参阅  
 [消息充实教程](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)