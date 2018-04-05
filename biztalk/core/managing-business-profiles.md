---
title: 管理业务配置文件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.admin.resultsobject.businessprofile
ms.assetid: cf98c5a4-71bb-440b-8172-717ed0eb8373
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 434979376e679f1098557dc5b55f50e599ed21cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="managing-business-profiles"></a>管理业务配置文件
业务配置文件代表组织的业务部门。 就像一个组织可以拥有各种部门，方可以具有各种[业务配置文件](http://msdn.microsoft.com/library/f8286130-57fe-40ed-9fd8-81da2c8baaaf)。 
  
一个业务配置文件代表组织中的一个业务部门。 就像一个组织可以有多个部门（会计、采购、发货等等）一样，一个参与方也可有许多业务配置文件，每个业务配置文件代表组织中一个业务部门。 业务配置文件属性包含下列信息：  
  
-   常规信息，例如业务配置文件名称  
  
-   可以与业务配置文件相关联的唯一标识  
  
-   编码设置 （对于 X12 和 EDIFACT 消息） 和[协议设置](../core/protocol-settings.md)(AS2)，它定义如何发送或接收来自另一方的消息的业务配置文件。  
  
本主题演示如何创建、 查看、 编辑或删除业务配置文件。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
## <a name="create-a-business-profile"></a>创建业务配置文件  
  
1.  在**BizTalk Server 管理**，展开 BizTalk 组中，然后选择**方**。 
2. 在**方和业务配置文件**窗格中，右击的当事方，选择**新建**，然后选择**业务配置文件**。  
  
3.  在**常规**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|输入业务配置文件名称。|  
    |**Description**|为该业务配置文件输入说明。|  
    |**其他属性 – 名称/值**|输入一个名称/值对以存储有关参与方的任何信息。 可以根据需要添加任意数量的名称/值对。 **注意：**名称-值对不用于 BizTalk server 任何处理; 此数据是仅供信息。|  
    |**删除**|选择要删除所选的名称-值对。|  
  
4.  如果需要，则为该业务配置文件添加业务标识。 在**标识**选项卡上，执行以下操作：  
  
    > [!NOTE]
    >  在此阶段中添加业务标识不是强制性的。 你可以更高版本，添加业务标识，作为商业版配置文件的协议的一部分。 如果你选择要添加业务标识现在，它们在就可创建此业务配置文件的协议。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|选择空单元格，并从下拉列表网格中，选择主体提供到组织的唯一业务标识为身份验证。 例如， **D-U-N-S （Bradstreet Dun)**。 两个业务合作伙伴可以选择一个双方商定的业务标识。 对于这种情况下，选择**双方约定**（对于 EDIFACT) 或**双方约定 (X12)** （对于 X12)。|  
    |**Qualifier**|显示基于为选定的值的预定义的值**名称**。|  
    |**值**|输入业务标识的值。 在提供业务标识的值时，您必须注意以下事项。<br /><br /> -对于给定的当事方，你可以使用的标识名称和标识值的相同组合的多个业务配置文件。 例如，对于使用方有两个业务配置文件**名称**作为**双方约定 (X12)**和**值**作为**THEM**。<br />-跨方，不能有两个业务配置文件使用的标识名称和标识值的相同组合。|  
    |**删除**|选择要删除选定的标识。|  
  
5.  如果需要，添加 X12 编码消息、 EDIFACT 编码消息或 AS2 传输的协议设置的协议设置。 请参阅[配置业务配置文件属性](../core/configuring-business-profile-properties.md)。  
  
6.  选择**应用**接受属性，或选择**确定**完成的配置设置。 以上任一操作验证的设置。  
  
## <a name="view-or-change-a-business-profile"></a>查看或更改业务配置文件  
  
1.  在**BizTalk Server 管理**，选择**方**。 

2. 在**方和业务配置文件**窗格中，展开一个方节点以查看其下的业务配置文件。 右键单击你想要编辑，，然后选择业务配置文件**属性**。  
  
3.  在**配置文件属性**对话框中，查看或编辑配置文件。 有关可以在不同的页指定的值的信息**配置文件属性**对话框中，请参阅[配置业务配置文件属性](../core/configuring-business-profile-properties.md)。  
  
4.  选择**应用**接受属性，或选择**确定**完成的配置设置。 以上任一操作验证的设置。  

## <a name="delete-a-business-profile"></a>删除业务配置文件  
  
1.  在**BizTalk Server 管理**，选择**方**。  
  
3.  在**方和业务配置文件**窗格中，展开一个方节点以查看其下的业务配置文件。  
  
4.  右键单击你想要删除，然后选择的业务配置文件**删除**。 
  
5.  在**确认删除业务配置文件**对话框中，选择**是**若要删除的业务配置文件。  


## <a name="see-also"></a>另请参阅  
 [管理 EDI 和 AS2 解决方案](../core/managing-edi-and-as2-solutions.md)