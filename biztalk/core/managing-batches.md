---
title: 管理批处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82755840-4e00-4fed-80e0-1a22b248c0bf
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af801bd6ec61c883d81e7ea6fd15e92f2186b777
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021524"
---
# <a name="managing-batches"></a>管理批
如何手动控制版本的批处理交换，在顶部使用的控件**批配置**页的单向协议选项卡**协议属性**对话框 (在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台) X12 和 EDIFACT 编码的。 其中包括下列控件：  
  
- **启动批**。 激活批处理业务流程的实例。 选择后**启动**按钮时，批处理元素将收集实例在激活范围内时。  
  
- **重写批**。 创建使用现有元素一个批并立即发送它。 发送批之后，批处理业务流程将根据已建立的设置，继续进行批处理。  
  
- **停止批**。 停用批处理业务流程的激活的实例。 选择后**停止**按钮，该业务流程基于现有批元素创建批，将交换传送给 EDI 发送管道，并且将终止。  
  
  控件对单个批配置进行操作。  
  
  按下时，BizTalk 采取的操作**启动**取决于按钮**筛选器**条件**版本**条件，和**激活**上的范围设置**批配置**页。 筛选条件确定将对哪些消息进行批处理。 发布条件确定何时发布批。 “激活范围”属性确定批处理业务流程的激活实例是否将收集批处理元素。 有关这些设置的详细信息，请参阅[配置传出批](../core/configuring-an-outgoing-batch.md)。  

本主题演示如何启动、 停止、 重写，以及删除批。  

> [!NOTE]
>  有关如何配置批处理的说明，请参阅[配置 X12 批处理](../core/configuring-batching-x12.md)或[配置 EDIFACT 批处理](../core/configuring-batching-edifact.md)。 
  
## <a name="prerequisites"></a>必要條件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员可以启动、停止或重写批，但不能更改与批处理相关的任何配置设置。 必须是 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators 组的成员才能更改批配置。  
  
## <a name="start-stop-and-override-batches"></a>启动、 停止和重写批  
  
1. 打开**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理**、 BizTalk 组，然后选择**方**。  
  
2. 在中**参与方和业务配置文件**页面上，在**协议**部分中，右键单击你想要启动、 停止或重写其批配置的协议。  
  
3. 在单向协议选项卡中的**协议属性**，选择**批配置**页。  
  
4. 上**批配置**页上，选择你想要启动、 停止或重写批的选项卡。  
  
5. 验证筛选条件、发布条件和激活范围属性是否使用其应当使用的值。  
  
   > [!NOTE]
   >  如果您的成员[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]操作员组，但不是[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组，可以启动、 停止、 或重写批。 但是，不能更改批配置设置。 设置都可见，但是如果更改了设置，然后选择**确定**，出现权限错误。  
  
6. 如果尚未激活批处理业务流程的实例，请选择**启动**激活实例。  
  
   > [!NOTE]
   >  - 则可以确定是否批处理业务流程的实例未被激活**启动**启用按钮，并**激活批处理**下显示**开始**控件。  
   >  - 如果已单击**启动**按钮，并已激活批处理业务流程实例，但为批收集任何元素，然后验证中的日期时间**激活**文本框中已发生的情况。 如果没有，则**激活**日期必须设置为当前日期或更早版本。  
  
7. 当不满足发布条件时发送批处理的交换，请选择**重写**。  
  
   > [!NOTE]
   >  选择**重写**导致批处理的交换发送，但不会影响批处理业务流程实例、 激活条件或发布条件的激活状态。  
  
8. 若要停用批处理业务流程的实例，请选择**停止**。  
  
   > [!NOTE]
   >  选择**停止**导致批处理的交换发送，并正在终止批处理业务流程实例。  
  
9. 选择**确定**或**取消**以关闭**协议属性**。  

## <a name="delete-batches"></a>删除批  
  
1. 在中**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理**，选择**方**。  
  
2. 在中**参与方和业务配置文件**页面上，在**协议**部分中，右键单击你想要删除的批配置的协议。  
  
3. 在单向协议选项卡中的**协议属性**对话框中，选择**批配置**页。  
  
4. 上**批配置**页上，选择你想要删除的批的选项卡。  
  
5. 在右下角的选项卡页上选择**删除**。  
  
6. 选择**确定**以关闭**协议属性**。  

  
## <a name="see-also"></a>请参阅  
 [配置传出批](../core/configuring-an-outgoing-batch.md)  
 [管理 EDI 和 AS2 解决方案](../core/managing-edi-and-as2-solutions.md)