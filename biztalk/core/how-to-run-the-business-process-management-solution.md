---
title: 如何运行业务流程管理解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, validating
- process management solution tutorial, submitting orders
- process management solution tutorial, stopping orders
- process management solution tutorial, updating orders
ms.assetid: cb77651e-e16c-49dc-9f8a-88584cd68a8b
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fc88a2999b9c38e95b70150e0686c8a353a1a32
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023339"
---
# <a name="how-to-run-the-business-process-management-solution"></a>如何运行业务流程管理解决方案
以下步骤介绍了如何在单台计算机上运行和验证业务流程管理解决方案。  
  
-   [启动业务流程管理解决方案](#step1)  
  
-   [运行并验证业务流程管理解决方案](#step3)  
  
## <a name="prerequisites"></a>必要條件  
 之前运行 BPM 解决方案，必须先执行中的步骤[如何安装业务流程管理解决方案](../core/how-to-install-the-business-process-management-solution.md)。  
  
##  <a name="step1"></a> 启动业务流程管理解决方案  
  
#### <a name="to-start-the-business-process-management-solution"></a>启动业务流程管理解决方案  
  
1. 单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在中**BizTalk Server 管理控制台**，展开**BizTalk 组**，展开**平台设置**，展开**主机实例**，右键单击**BizTalkServerApplication**，然后单击**启动**。  
  
3. 在中**BizTalk Server 管理控制台**，展开**BizTalk 组**，然后展开**应用程序**。  
  
   1.  右键单击 BTSScn.BPM.MessagingApp 中，单击**启动**，然后单击**启动**上**启动应用程序**对话框。  
  
   2.  右键单击 BTSScn.BPM.OrderBrokerApp，单击**启动**，然后单击**启动**上**启动应用程序**对话框。  
  
   3.  右键单击 BTSScn.BPM.CableOrderApp，单击**启动**，然后单击**启动**上**启动应用程序**对话框。  
  
   4.  右键单击 BTSScn.BPM.OrderBrokerApp.Test，然后单击**停止**。 在中**停止应用程序**对话框中，选择**完全停止-终止实例**，然后单击**停止**。  
  
   > [!NOTE]
   >  若要将信息插入历史记录数据库中。 OrderBroker 业务流程使用 HistoryPort 发送端口的这**送达通知**属性设置**传输**。 该发送端口绑定到 HistoryInsert-SPG 发送组，该组包括 HistoryInsert-SP 和 HistoryInsert-Test-SP 发送端口。 对于这两个发送端口，消息引擎将向 OrderBroker 业务流程发布两条确认消息。 这会使业务流程因未使用的消息而挂起。 若要避免这种情况，必须取消登记其中一个发送端口。 在此演练中，通过完全停止 BTSScn.BPM.OrderBrokerApp.Test 应用程序来取消登记 HistoryInsert-Test-SP 发送端口。 有关 OrderBroker 业务流程的详细信息，请参阅[在 OrderBroker 业务流程中处理](../core/processing-in-the-orderbroker-orchestration.md)。 有关详细信息**送达通知**属性，请参阅[使用确认](../core/using-acknowledgments.md)。  
  
4. 按以下步骤运行功能模拟程序：  
  
   1.  打开命令提示符，将目录更改为 %BTSSolutionsPath%\BPM\FacilitiesSimulator\bin\debug 文件夹。  
  
   2.  键入 `BTSScnBPMFacilities.exe`，然后按 Enter。 使 FacilitiesSimulator 保持运行状态。 此应用程序将模拟处理 Southridge Video 后端系统的功能。  
  
   3.  在 FacilitiesSimulator 中，键入以下接收和传输队列：  
  
       |“属性”|ReplTest1|  
       |----------|-----------|  
       |**接收队列**|`.\private$\ToFacilitiesQ`|  
       |**传输队列**|`.\private$\FromFacilitiesQ`|  
  
   4.  在 FacilitiesSimulator 中，单击**启动**。  
  
5. 按以下步骤运行运营服务器：  
  
   1.  打开新的命令提示符，将当前目录更改为 %BTSSolutionsPath%\BPM\OperationsServer\bin\debug 文件夹。  
  
   2.  类型`BTSScnBPMOperations.exe 8881`在命令提示符，然后按 ENTER。 使运营服务器保持运行状态。 运营服务器将监听 TCP 端口 8881 以接收来自 Ops 适配器的错误消息。 它将显示 Ops 适配器收到的错误消息。  
  
6. 按以下步骤运行宽带提供系统：  
  
   1.  打开新的命令提示符，将当前目录更改为 %BTSSolutionsPath%\BPM\CableProvisioningSystemServer\bin\debug 文件夹。  
  
   2.  键入 `BTSScnBPMProvisioning.exe 8880`，然后按 Enter。 然后，使宽带提供系统保持运行状态。 宽带提供系统侦听 TCP 端口 8880。 此应用程序模拟后端订单系统，并显示最终的订单。  
  
##  <a name="step3"></a> 运行并验证业务流程管理解决方案  
  
#### <a name="to-submit-a-new-order-and-validate-the-solution"></a>提交新订单并验证解决方案  
  
1.  在 Internet Explorer 中，在**地址**框中，键入客户服务 Web 应用程序的 URL 如下所示：  
  
    -   `http://localhost/CSRWebApp/CSRMainForm.aspx`  
  
2.  上**Southridge Video 客户服务申请单输入表单**页上，在以下表中，输入新的订单，然后单击**提交订单。**  
  
    |条目|ReplTest1|  
    |-----------|-----------|  
    |客户 ID|@shouldalert|  
    |Order ID|@shouldalert|  
    |序列号|@shouldalert|  
    |服务类型代码|新的标准服务|  
  
3.  上**Southridge Video 客户服务申请单输入表单**页上，结果消息，如下所示：  
  
     **客户 ID 1 订单 ID 1 序列号 1**  
  
4.  在运行宽带提供系统的命令提示符下验证已下订单。 该应用程序将显示已分析、激活并完成提交的订单的消息。  
  
5.  验证功能模拟程序中的消息总数增量为 1。  
  
#### <a name="to-submit-a-duplicate-while-the-biztalk-server-is-processing-the-original-order"></a>在 BizTalk Server 处理原始订单时提交重复订单  
  
1.  在 Internet Explorer 中，在**地址**框中，键入客户服务 Web 应用程序的 URL 如下所示：  
  
    -   `http://localhost/CSRWebApp/CSRMainForm.aspx`  
  
2.  在 FacilitiesSimulator 中，单击**停止**。 这样将不会进一步处理提交的订单。  
  
3.  上**Southridge Video 客户服务申请单输入表单**页上，在以下表中，输入新的订单，然后单击**提交订单**两次以模拟重复的订单。  
  
    |条目|ReplTest1|  
    |-----------|-----------|  
    |客户 ID|2|  
    |Order ID|@shouldalert|  
    |序列号|@shouldalert|  
    |服务类型代码|新的标准服务|  
  
4.  上**Southridge Video 客户服务申请单输入表单**页上，结果消息，如下所示：  
  
     **客户 ID 为 2 的订单 ID 1 序列号 1**  
  
5.  在 FacilitiesSimulator 中，单击**启动**。 将会恢复等待来自功能模拟程序的响应的业务流程。 在处理第一个订单时该程序将模拟提交一个重复的订单。  
  
6.  在运行宽带提供系统的命令提示符下检查已下订单。 该应用程序将显示有关仅分析、激活并完成了第一个订单的消息。  
  
7.  在运行运营服务器的命令提示符下检查重复订单的错误消息。  
  
#### <a name="to-update-an-order-while-the-biztalk-server-is-processing-the-order"></a>在 BizTalk Server 处理订单时更新订单  
  
1.  在 Internet Explorer 中，在**地址**框中，键入客户服务 Web 应用程序的 URL 如下所示：  
  
    -   `http://localhost/CSRWebApp/CSRMainForm.aspx`  
  
2.  在 FacilitiesSimulator 中，单击**停止**。  
  
3.  上**Southridge Video 客户服务申请单输入表单**页上，在以下表中，输入新的订单，然后单击**提交订单**。  
  
    |条目|ReplTest1|  
    |-----------|-----------|  
    |客户 ID|3|  
    |Order ID|@shouldalert|  
    |序列号|@shouldalert|  
    |服务类型代码|新的标准服务|  
  
4.  上**Southridge Video 客户服务申请单输入表单**页上，结果消息，如下所示：  
  
     **客户 ID 3 订单 ID 1 序列号 1**  
  
5.  上**Southridge Video 客户服务申请单输入表单**页上，输入下表中更新的订单，然后单击**提交订单**。  
  
    |条目|ReplTest1|  
    |-----------|-----------|  
    |客户 ID|3|  
    |Order ID|@shouldalert|  
    |序列号|2|  
    |服务类型代码|新的高级服务|  
  
6.  上**Southridge Video 客户服务申请单输入表单**页上，结果消息，如下所示：  
  
     **客户 ID 3 订单 ID 1 序列号 2**  
  
7.  在 FacilitiesSimulator 中，单击**开始**  
  
8.  检查结果消息**Southridge Video 客户服务申请单输入表单**页。  
  
9. 在运行宽带提供系统的命令提示符下检查已下订单。 该应用程序将显示已分析两个订单但仅激活和完成了更新的订单的消息。  
  
10. 单击**启动**，依次指向**所有程序**，指向**管理工具**，单击**事件查看器**，然后选中一个新的警告，原始订单已中断。  
  
11. 在运行运营服务器的命令提示符下检查路由故障错误消息。  
  
    > [!NOTE]
    >  事件日志和运营服务器中将出现错误。 来自功能系统的响应消息不再与业务流程实例相关，因为具有更高序列号的新订单所导致的中断已终止该消息。 因此，该响应消息是孤立消息并将路由到运营服务器。 有关订单更新的详细信息，请参阅[订单流通过进程管理器](../core/order-flow-through-the-process-manager.md)。  
  
12. 使用记事本打开 %SystemDrive%:\BPMTest\HistoryUpdate-SP 文件夹中的最新消息。 检查**CustName**， **OrderNum**， **OrderSeqNum**，以及**状态**域，以查看该消息是否已创建的新订单和**状态**字段是**COMPLETED**。  
  
#### <a name="to-terminate-an-order-while-the-biztalk-server-is-processing-the-order"></a>在 BizTalk Server 处理订单时终止订单  
  
1.  在 Internet Explorer 中，在**地址**框中，键入客户服务 Web 应用程序的 URL 如下所示：  
  
    -   `http://localhost/CSRWebApp/CSRMainForm.aspx`  
  
2.  在 FacilitiesSimulator 中，单击**停止**。  
  
3.  上**Southridge Video 客户服务申请单输入表单**页上，在以下表中，输入新的订单，然后单击**提交订单**。  
  
    |条目|ReplTest1|  
    |-----------|-----------|  
    |客户 ID|4|  
    |Order ID|@shouldalert|  
    |序列号|@shouldalert|  
    |服务类型代码|新的标准服务|  
  
4.  上**Southridge Video 客户服务申请单输入表单**页上，结果消息，如下所示：  
  
     **客户 ID 4 订单 ID 1 序列号 1**  
  
5.  上**Southridge Video 客户服务申请单输入表单**页上，单击**终止订单**。  
  
6.  上**Southridge Video 客户服务申请单输入表单**页上，结果消息，如下所示：  
  
     **客户 ID 4 订单 ID 1 序列号 1**  
  
7.  在 FacilitiesSimulator 中，单击**启动**。  
  
8.  在运行宽带提供系统的命令提示符下检查已下订单。 该应用程序将显示仅分析和激活该订单的消息。  
  
9. 单击**启动**，依次指向**所有程序**，指向**管理工具**，单击**事件查看器**，然后选中一个新的警告，用户已终止订单。  
  
    > [!NOTE]
    >  有关终止订单的详细信息，请参阅[订单流通过进程管理器](../core/order-flow-through-the-process-manager.md)。  
  
10. 在运行运营服务器的命令提示符下检查路由故障错误消息。  
  
## <a name="see-also"></a>请参阅  
 [安装业务流程管理解决方案之前](../core/before-installing-the-business-process-management-solution.md)   
 [业务流程管理解决方案的开发人员计算机设置](../core/developer-machine-setup-for-the-business-process-management-solution.md)