---
title: "实现 FRR 否认处理程序示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 80fa5fb7-6864-4923-b641-e76d2b95d923
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a91c0303c9abdf6b1d8c434869445f3c84348935
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="implementing-the-frr-nak-handler-sample"></a>实现 FRR 否认处理程序示例
若要实现示例 FRR 否认自定义处理程序，将示例项目添加到你的解决方案、 生成和部署项目、 绑定和启动业务流程，然后停止并重新启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  
  
### <a name="to-implement-the-frr-nak-custom-handler"></a>若要实现 FRR 否认自定义处理程序  
  
1.  在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，打开你的解决方案。 在解决方案资源管理器，右键单击该解决方案，指向**添加**，然后单击**现有项目**。  
  
2.  在**添加现有项目**对话框中，移动到*\<驱动器\>*: files\microsoft BizTalk Accelerator for SWIFT\SDK\Samples\FrrHandler。 选择**RepairSWIFTRejectedMessage.btproj**，然后单击**打开**。  
  
3.  生成密钥并将密钥分配到项目。  
  
4.  生成和部署 RepairSWIFTRejectedMessage.btproj 项目。  
  
5.  在 BizTalk 资源管理器中，展开**BizTalk 配置数据库**，  **\<*服务器名称*\>，BizTalkMgmtDb.dbo**，和**业务流程**，右键单击**RepairSWIFTRejectedMessage.Orchestration_1**，然后单击**绑定**。  
  
6.  在**端口绑定属性**对话框中，选择你的主机，如 BizTalkServerApplication，，然后单击**确定**。  
  
7.  在 BizTalk 资源管理器中，右键单击**RepairSWIFTRejectedMessage.Orchestration_1**，然后单击**启动**。  
  
8.  在**Express 启动**对话框中，单击**确定**。  
  
9. 单击 **“启动”**，再单击 **“运行”**。 输入**services.msc**，然后单击**确定**。 右键单击**BizTalk 服务**，然后单击**重新启动**。