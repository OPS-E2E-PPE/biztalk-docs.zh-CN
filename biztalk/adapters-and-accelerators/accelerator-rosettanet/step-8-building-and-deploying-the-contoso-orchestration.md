---
title: "步骤 8： 构建和部署 Contoso 业务流程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- private process tutorial, building solutions
- private process tutorial, deploying solutions
ms.assetid: d350b87a-0e4e-4837-ad39-fb5b1fdc1532
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 706c5ab2b52d30aeedfba7b3e002dc637fcece93
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-8-building-and-deploying-the-contoso-orchestration"></a>步骤 8： 构建和部署 Contoso 业务流程
在此步骤中，您将生成 Orchestration 项目并使用“BizTalk 部署向导”部署该项目。 这会将程序集添加到 Configuration 数据库，并在全局程序集缓存 (GAC) 中安装该程序集。  
  
### <a name="to-assign-a-strong-name-to-your-assembly"></a>指定程序集的强名称  
  
1.  在解决方案资源管理器，右键单击**PrivateResponder**项目，，然后单击**属性**。  
  
2.  在 PrivateResponder 属性页对话框中，选择**程序集**从左窗格。  
  
3.  在右窗格中，向下滚动到**强名称**部分中，单击右侧的字段**程序集密钥文件**，然后单击省略号按钮 (**...**).  
  
4.  找到你的项目文件夹中，选择**FabConPriceAvail.snk**文件，，然后单击**打开**。  
  
5.  在右窗格中，选择**False**从**程序集延迟签名**下拉列表。  
  
6.  单击**确定**以保存所做的更改。  
  
### <a name="to-build-and-deploy-the-orchestration-project"></a>生成和部署业务流程项目  
  
1.  在解决方案资源管理器，右键单击**PrivateResponder**项目，，然后单击**生成**。  
  
    > [!NOTE]
    >  可以放心地忽略在生成过程中出现的任何警告。  
  
2.  已成功生成后，再次右键单击项目，然后单击**部署**。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 9： 启动 Contoso 业务流程](../../adapters-and-accelerators/accelerator-rosettanet/step-9-starting-the-contoso-orchestration.md)