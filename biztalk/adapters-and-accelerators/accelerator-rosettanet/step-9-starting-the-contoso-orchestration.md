---
title: 步骤 9： 启动 Contoso 业务流程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, starting orchestrations
ms.assetid: df3ff90b-5a9f-4ae7-819a-11cb36d64ccd
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d58d7f2f9d725fca94eb6cf3d2412b3c376fe015
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209445"
---
# <a name="step-9-starting-the-contoso-orchestration"></a>步骤 9： 启动 Contoso 业务流程
在此步骤中，你将通过定义物理源位置和目标位置来完成端口配置流程。 将物理端口绑定到你在中创建的逻辑端口[步骤 7： 创建和配置端口](../../adapters-and-accelerators/accelerator-rosettanet/step-7-creating-and-configuring-ports.md)。 然后登记服务关联的物理环境的业务流程将运行中的业务流程中设计的业务流程。 最后，你启动业务流程，以便它可以参与与 Fabrikam 的业务事务。  
  
### <a name="to-bind-the-orchestration-ports"></a>绑定业务流程端口  
  
1.  打开**BizTalk 资源管理器**。  
  
2.  在 BizTalk 资源管理器中，展开**BizTalk 配置数据库**，展开**业务流程**，右键单击**ContosoPriceAndAvailability.PrivateResponderProcess**，然后单击**绑定**。  
  
3.  在端口绑定属性页中，选择**LOB_To_PrivateResponder**中**FromLOB**属性。  
  
4.  在**ContosoSQLReqResponsePort**框中，选择**3A2SQLReqResponseSendPort**。  
  
5.  在**ToLOB**属性中，展开**发送端口**和选择**PrivateResponder_To_LOB**。  
  
6.  在左窗格中的配置窗口中，选择**主机**。  
  
7.  在**主机**属性，请在**BizTalk 主机**类别中，选择**BizTalkServerApplication**从下拉列表，然后单击**确定**.  
  
### <a name="to-start-the-biztalk-runtime-process"></a>启动 BizTalk 运行时流程  
  
1.  单击**启动**，指向**所有程序**，指向**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] ，然后单击**BizTalk Server 管理**。  
  
2.  在 BizTalk 管理控制台中，在左窗格中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**平台设置**，，然后展开**主机实例**。  
  
3.  验证的状态**BizTalkServerApplication**服务是**运行**。  
  
### <a name="to-enlist-and-start-the-orchestration"></a>登记和启动业务流程  
  
1.  在 BizTalk 管理控制台的左窗格中，展开**应用程序**，展开**BizTalk 应用程序 1**，然后单击**业务流程**。  
  
2.  在右窗格中，右键单击**ContosoPriceAndAvailability.PrivateResponderProcess**业务流程，，然后单击**Enlist**。  
  
3.  右键单击**ContosoPriceAndAvailability.PrivateResponderProcess**业务流程，，然后单击**启动**启动业务流程。  
  
## <a name="see-also"></a>另请参阅  
 [创建 Fabrikam 解决方案](../../adapters-and-accelerators/accelerator-rosettanet/creating-the-fabrikam-solution.md)