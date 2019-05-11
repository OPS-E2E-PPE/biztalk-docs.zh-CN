---
title: 管理业务配置文件 |Microsoft Docs
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
ms.openlocfilehash: 296f11ff5ed9d558ce086190129c18a0233d2152
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380243"
---
# <a name="managing-business-profiles"></a>管理业务配置文件
一个业务配置文件代表组织的内部的业务部门。 就像一个组织可以有不同的部门，一个参与方可以有各种[业务配置文件](http://msdn.microsoft.com/library/f8286130-57fe-40ed-9fd8-81da2c8baaaf)。 
  
业务配置文件表示的组织中一个业务部门。 就像一个组织可以有多个部门 （会计、 采购、 发货等），一个参与方可以有多个业务配置文件，每个资源表示一个业务部门的组织中。 业务配置文件属性包含下列信息：  
  
-   常规信息，如业务配置文件名称  
  
-   可以与业务配置文件相关联的唯一标识  
  
-   编码设置 （适用于 X12 和 EDIFACT 消息） 和[协议设置](../core/protocol-settings.md)(AS2)，它定义如何发送或接收来自另一方的消息的业务配置文件。  
  
本主题演示如何创建、 查看、 编辑或删除业务配置文件。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  
  
## <a name="create-a-business-profile"></a>创建业务配置文件  
  
1.  在中**BizTalk Server 管理**、 BizTalk 组，然后选择**方**。 
2. 在中**参与方和业务配置文件**窗格中，右击的参与方，选择**新建**，然后选择**业务配置文件**。  
  
3.  在中**常规**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|输入业务配置文件名称。|  
    |**说明**|输入业务配置文件的说明。|  
    |**其他属性 – 名称/值**|输入的名称-值对来存储有关参与方的任何信息。 您可以添加所需的任意多个名称 / 值对。 **注意：** 名称 / 值对不进行任何处理; 使用由 BizTalk Server此数据是为了仅提供信息。|  
    |**删除**|选择此项可删除所选的名称-值对。|  
  
4.  如果需要，添加业务标识的业务配置文件。 在中**标识**选项卡上，执行以下操作：  
  
    > [!NOTE]
    >  在此阶段中添加业务标识不是必需的。 作为业务配置文件的协议的一部分，可以更高版本，添加业务标识。 如果您选择添加业务标识现在，它们是可创建此业务配置文件的协议时。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|选择空单元格，并从下拉列表网格中，选择提供唯一业务标识到组织的认证机构。 例如， **D-U-N-S (Dun & Bradstreet)**。 两个业务合作伙伴可以选择相互议定的业务标识。 对于这种情况下，选择**双方**（适用于 EDIFACT) 或**双方 (X12)** （适用于 X12)。|  
    |**Qualifier**|显示基于为选定的值的预定义的值**名称**。|  
    |**ReplTest1**|输入业务标识的值。 提供的业务标识时，必须考虑以下注意事项。<br /><br /> -对于给定参与方，您可以使用相同的标识名称和标识值组合的多个业务配置文件。 例如，可以有两个业务配置文件与参与方**名称**作为**双方 (X12)** 并**值**作为**THEM**。<br />-多个参与方，不能具有使用相同的标识名称和标识值组合的两个业务配置文件。|  
    |**删除**|选择此项可删除所选的标识。|  
  
5.  如果需要，添加 X12 编码的消息、 EDIFACT 编码的消息或 AS2 传输协议设置的协议设置。 请参阅[配置业务配置文件属性](../core/configuring-business-profile-properties.md)。  
  
6.  选择**Apply**以接受这些属性，或选择**确定**即可完成配置设置。 以上任一操作会验证设置。  
  
## <a name="view-or-change-a-business-profile"></a>查看或更改业务配置文件  
  
1.  在中**BizTalk Server 管理**，选择**方**。 

2. 在中**参与方和业务配置文件**窗格中，展开一个参与方节点以查看其下的业务配置文件。 右键单击你想要编辑，然后选择一个业务配置文件**属性**。  
  
3.  在中**配置文件属性**对话框中，查看或编辑配置文件。 有关可以指定不同页面中的值的信息**配置文件属性**对话框中，请参阅[配置业务配置文件属性](../core/configuring-business-profile-properties.md)。  
  
4.  选择**Apply**以接受这些属性，或选择**确定**即可完成配置设置。 以上任一操作会验证设置。  

## <a name="delete-a-business-profile"></a>删除业务配置文件  
  
1.  在中**BizTalk Server 管理**，选择**方**。  
  
3.  在中**参与方和业务配置文件**窗格中，展开一个参与方节点以查看其下的业务配置文件。  
  
4.  右键单击你想要删除，然后选择的业务配置文件**删除**。 
  
5.  在中**确认删除业务配置文件**对话框中，选择**是**来删除业务配置文件。  


## <a name="see-also"></a>请参阅  
 [管理 EDI 和 AS2 解决方案](../core/managing-edi-and-as2-solutions.md)