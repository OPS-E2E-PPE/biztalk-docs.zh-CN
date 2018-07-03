---
title: 步骤 3： 配置并启动应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e4252470-805e-404f-80d5-df8d1ff3af63
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f932ca1f3570f080de239dd90c52d9a5f5db721
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988198"
---
# <a name="step-3-configure-and-start-the-application"></a>步骤 3： 配置并启动应用程序
![步骤 3，共 4 步](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")  
  
 **完成时间：** 10 分钟  
  
 **目标：** 在此步骤中，配置和启动 SampleApplication 应用程序。 在配置 SampleApplication 应用程序时，将关联中创建的逻辑项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]与其物理对应项。  
  
## <a name="prerequisites"></a>必要條件  
 你必须已完成[步骤 2： 配置的端口](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md)。  
  
### <a name="to-configure-and-start-the-application"></a>若要配置和启动应用程序  
  
1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2. 在左侧控制台树中，展开**BizTalk Server 管理**，右键单击**BizTalk 组**，然后单击**刷新**。  
  
3. 展开**BizTalk 组**，展开**应用程序**，右键单击**SampleApplication**，然后单击**配置**。  
  
4. 在中**配置应用程序**对话框中，在**EmployeeOrch**选项卡上，执行以下操作：  
  
   1.  有关**主机**下拉列表中，选择**BizTalkServerApplication**。  
  
   2.  双击跨单元格**ReceiveNotification** ，然后选择**NotifyReceivePort**从下拉列表。  
  
   3.  双击跨单元格**SQLOutboundPort** ，然后选择**SQLOutboundPort**从下拉列表。  
  
   4.  双击跨单元格**SaveResponsePort** ，然后选择**EmailResponse**从下拉列表。  
  
5. 下图显示了配置的应用程序。  
  
    ![配置应用程序](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-011-configure-app.gif "sql_adap_tut_011_configure_app")  
  
6. 在中**配置应用程序**对话框中，单击**确定**。  
  
7. 在控制台树中，右键单击**SampleApplication**，然后单击**启动**。  
  
8. 在控制台树中，单击**应用程序**。  
  
9. 在应用程序的详细信息窗格中，检查**状态**的**SampleApplication**是**已启动**。  
  
## <a name="what-did-i-just-do"></a>内容回顾  
 已配置并启动 SampleApplication 应用程序  
  
## <a name="next-steps"></a>后续步骤  
 插入新入职员工的测试应用程序**员工**表，如中所述[步骤 4： 测试应用程序](../../adapters-and-accelerators/adapter-sql/step-4-test-the-application.md)。  
  
## <a name="see-also"></a>请参阅  
 [步骤 2： 配置的端口](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md)   
 [步骤 4： 测试应用程序](../../adapters-and-accelerators/adapter-sql/step-4-test-the-application.md)   
 [第 5 课：部署解决方案](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)