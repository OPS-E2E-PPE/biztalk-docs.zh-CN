---
title: "管理批处理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82755840-4e00-4fed-80e0-1a22b248c0bf
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4903cf2722f1938ceb1df92c2a3ac2a88fe6d61e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="managing-batches"></a>管理批
如何手动控制版本的批处理的交换，在顶部使用的控件**批配置**的单向协议选项卡页**协议属性**对话框中 (在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台) 的 X12 和 EDIFACT 编码。 其中包括下列控件：  
  
-   **开始一批**。 激活批处理的业务流程的实例。 选择后**启动**按钮，批处理元素将收集实例激活范围内时。  
  
-   **重写一批**。 创建使用现有元素一批并立即将其发送。 发送批之后，批处理业务流程将根据已建立的设置，继续进行批处理。  
  
-   **停止一批**。 停用激活批处理的业务流程的实例。 选择后**停止**按钮，业务流程将创建一批从现有的批处理元素，将交换传递到 EDI 发送管道，并终止。  
  
 控件对单个批配置进行操作。  
  
 当你按下时，BizTalk 所执行的操作**启动**取决于按钮**筛选器**条件，**版本**条件，和**激活**上范围设置**批配置**页。 筛选条件确定将对哪些消息进行批处理。 发布条件确定何时发布批。 “激活范围”属性确定批处理业务流程的激活实例是否将收集批处理元素。 有关这些设置的详细信息，请参阅[配置传出批处理](../core/configuring-an-outgoing-batch.md)。  

本主题演示如何启动、 停止、 重写，并删除批次。  

> [!NOTE]
>  有关如何配置批说明，请参阅[配置 X12 批处理](../core/configuring-batching-x12.md)或[配置 EDIFACT 批处理](../core/configuring-batching-edifact.md)。 
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员可以启动、停止或重写批，但不能更改与批处理相关的任何配置设置。 必须是 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators 组的成员才能更改批配置。  
  
## <a name="start-stop-and-override-batches"></a>启动、 停止和重写批处理  
  
1.  打开**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理**，展开 BizTalk 组中，然后选择**方**。  
  
2.  在**方和业务配置文件**页上，在**协议**部分中，右键单击与你想要启动、 停止或重写的批处理配置的协议。  
  
3.  单向协议选项卡中**协议属性**，选择**批配置**页。  
  
4.  上**批配置**页上，选择你想要启动、 停止或重写的批处理的选项卡。  
  
5.  验证筛选条件、发布条件和激活范围属性是否使用其应当使用的值。  
  
    > [!NOTE]
    >  如果你是的成员[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Operators 组，但不是[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组，可以启动、 停止、 或替代批处理。 但是，你不能更改批处理配置设置。 设置是否可见，但如果你更改设置，然后选择**确定**，则会收到权限错误。  
  
6.  如果尚未激活批处理的业务流程的实例，则选择**启动**激活实例。  
  
    > [!NOTE]
    >  - 你可以判断，批处理的业务流程的实例尚未激活是否**启动**启用按钮，和**未激活批处理**下方只显示**启动**控件。  
    >  - 如果您在单击**启动**按钮，批处理的业务流程的实例已激活，但为批处理正在收集任何元素，然后验证中的 datetime**激活**文本框中已发生的情况。 如果没有，则**激活**日期必须设置为当前日期或更早版本。  
  
7.  若要释放条件未满足时，请发送批处理的交换，请选择**重写**。  
  
    > [!NOTE]
    >  选择**重写**导致批处理的交换发送，但不会影响的批处理的业务流程实例、 激活条件或释放条件的激活状态。  
  
8.  若要停用批处理的业务流程的实例，请选择**停止**。  
  
    > [!NOTE]
    >  选择**停止**会导致批处理的交换正在发送的数据和批处理的业务流程实例正在终止。  
  
9. 选择**确定**或**取消**关闭**协议属性**。  

## <a name="delete-batches"></a>删除批次  
  
1.  在**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理**，选择**方**。  
  
2.  在**方和业务配置文件**页上，在**协议**部分中，右键单击与你想要删除的批处理配置的协议。  
  
3.  单向协议选项卡中**协议属性**对话框中，选择**批配置**页。  
  
4.  上**批配置**页上，选择你想要删除的批处理的选项卡。  
  
5.  在选项卡页右上角，选择**删除**。  
  
6.  选择**确定**关闭**协议属性**。  

  
## <a name="see-also"></a>另请参阅  
 [配置传出批处理](../core/configuring-an-outgoing-batch.md)  
 [管理 EDI 和 AS2 解决方案](../core/managing-edi-and-as2-solutions.md)