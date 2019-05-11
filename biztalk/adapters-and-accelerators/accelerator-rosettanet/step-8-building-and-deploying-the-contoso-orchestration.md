---
title: 步骤 8：生成和部署 Contoso 业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, building solutions
- private process tutorial, deploying solutions
ms.assetid: d350b87a-0e4e-4837-ad39-fb5b1fdc1532
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68708976c91d96b3729b1a39776981d9345eb519
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280647"
---
# <a name="step-8-building-and-deploying-the-contoso-orchestration"></a>步骤 8：生成和部署 Contoso 业务流程
在此步骤中，将生成业务流程项目和使用 BizTalk 部署向导部署该网站。 这将程序集添加到配置数据库，并安装在全局程序集缓存 (GAC) 中的程序集。  
  
### <a name="to-assign-a-strong-name-to-your-assembly"></a>若要为您的程序集分配强名称  
  
1.  在解决方案资源管理器中右键单击**PrivateResponder**项目，并单击**属性**。  
  
2.  在 PrivateResponder 属性页对话框中，选择**程序集**在左窗格中。  
  
3.  在右窗格中，向下滚动到**强名称**部分中，单击右侧的字段**程序集密钥文件**，然后单击省略号按钮 (**...**).  
  
4.  找到你的项目文件夹，选择**FabConPriceAvail.snk**文件，，然后单击**打开**。  
  
5.  在右窗格中，选择**False**从**程序集延迟签名**下拉列表中。  
  
6.  单击**确定**以保存所做的更改。  
  
### <a name="to-build-and-deploy-the-orchestration-project"></a>若要生成和部署业务流程项目  
  
1.  在解决方案资源管理器中右键单击**PrivateResponder**项目，并单击**生成**。  
  
    > [!NOTE]
    >  您可以放心地忽略生成过程中出现任何警告。  
  
2.  已成功生成后，再次右键单击项目，然后依次**部署**。  
  
## <a name="see-also"></a>请参阅  
 [步骤 9：启动 Contoso 业务流程](../../adapters-and-accelerators/accelerator-rosettanet/step-9-starting-the-contoso-orchestration.md)