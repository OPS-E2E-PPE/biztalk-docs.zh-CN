---
title: 实现 FRR NAK 处理程序示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 80fa5fb7-6864-4923-b641-e76d2b95d923
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42885d6c487c6f088bfab113891ec5425d3fc82e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990278"
---
# <a name="implementing-the-frr-nak-handler-sample"></a>实现 FRR NAK 处理程序示例
若要实现示例 FRR NAK 自定义处理程序、 将示例项目添加到你的解决方案、 生成和部署项目、 绑定和启动业务流程，然后停止并重新启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  

### <a name="to-implement-the-frr-nak-custom-handler"></a>若要实现 FRR NAK 自定义处理程序  

1. 在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，打开你的解决方案。 在解决方案资源管理器中右键单击解决方案，指向**外**，然后单击**现有项目**。  

2. 在中**添加现有项目**对话框中，转到*\<驱动器\>*: \Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Samples\FrrHandler。 选择**RepairSWIFTRejectedMessage.btproj**，然后单击**打开**。  

3. 生成密钥并将该密钥分配到项目。  

4. 生成和部署 RepairSWIFTRejectedMessage.btproj 项目。  

5. 在 BizTalk 浏览器中，展开**BizTalk 配置数据库**，  **\<*服务器名称*\>，BizTalkMgmtDb.dbo**，和**业务流程**，右键单击**RepairSWIFTRejectedMessage.Orchestration_1**，然后单击**绑定**。  

6. 在中**端口绑定属性**对话框中，选择您的主机，如 BizTalkServerApplication，，然后单击**确定**。  

7. 在 BizTalk 浏览器中右键单击**RepairSWIFTRejectedMessage.Orchestration_1**，然后单击**启动**。  

8. 在中**快速启动**对话框中，单击**确定**。  

9. 单击 **“启动”**，再单击 **“运行”**。 输入**services.msc**，然后单击**确定**。 右键单击**BizTalk 服务**，然后单击**重新启动**。
