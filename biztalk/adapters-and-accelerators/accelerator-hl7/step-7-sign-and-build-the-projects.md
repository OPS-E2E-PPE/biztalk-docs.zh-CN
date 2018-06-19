---
title: 步骤 7： 登录和生成项目 |Microsoft 文档
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
ms.openlocfilehash: f62a37da291bdc148369a28149cdfe29ed7fe446
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
ms.locfileid: "25961763"
---
# <a name="step-7-sign-and-build-the-projects"></a>步骤 7： 登录和生成项目
在此步骤中，可以指定一个强名称和生成项目以生成包含你在中创建的资源 （架构） 的程序集[步骤 6： 验证架构](../../adapters-and-accelerators/accelerator-hl7/step-6-validate-the-schemas.md)。 这还可以确保到目前为止完成的工作中没有编译错误。  
  
### <a name="to-sign-the-btahl7-project"></a>若要登录 BTAHL7 项目  
  
1.  在解决方案资源管理器，右键单击**BTAHL7 项目**，然后单击**属性**。  
  
2.  在 BTAHL7 项目属性页对话框中，单击**程序集**。  
  
3.  在右窗格中，向下滚动到**强名称**部分中，单击右侧的字段**程序集密钥文件**，然后单击省略号 （...） 按钮。  
  
4.  在程序集密钥文件对话框中，浏览到 **\<*驱动器*\>: \Tutorial\BTAHL7V22Common\key.snk** (在创建[步骤 3： 分配到一个强名称程序集](../../adapters-and-accelerators/accelerator-hl7/step-3-assign-a-strong-name-to-the-assembly.md))，然后单击**打开**。  
  
5.  单击**确定**以保存更改。  
  
### <a name="to-build-the-btahl7-project"></a>若要生成 BTAHL7 项目  
  
-   在解决方案资源管理器，右键单击**BTAHL7 项目**，然后单击**部署**。 [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]将编译为 DLL 文件的程序集并将其保存在\<*驱动器*\>: \Tutorial\BTAHL7V22Common\Bin\Development 文件夹。  
  
 继续执行[步骤 8： 使用 BizTalk 映射程序创建地图](../../adapters-and-accelerators/accelerator-hl7/step-8-create-a-map-with-biztalk-mapper.md)。  
  
## <a name="see-also"></a>另请参阅  
 [消息充实教程](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)