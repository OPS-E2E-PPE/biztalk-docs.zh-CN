---
title: "创建或编辑主组织 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- home organizations, about home organizations
- home organizations, modifying
- creating, home organizations
- modifying, home organizations
- home organizations
- home organizations, creating
ms.assetid: b54afb84-2f16-4516-8701-b03301476362
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bc8a298686772d354c934d76fbcb7dbbb8146f8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-or-editing-a-home-organization"></a>创建或编辑主组织
本主题讲述如何创建或编辑本组织。 本组织配置用于对组织进行描述和分类、设置原始时间段的不可否认性以及提供联系人信息。  
  
 与合作伙伴配置不同，本组织配置不包括签名证书和解密证书。 为 BizTalk 组中配置的签名证书[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 在 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 管理控制台中配置 BizTalk 主机 (BizTalkServerApplication 和 BizTalkIsolatedHost) 的解密证书。  
  
 您可以在一个公司或一次部署中创建两个本组织。 例如，您可能希望创建处理消息的优先级，根据该优先级，发往一个组织的消息可以优先于发往另一个组织的消息。 如果要创建多个本组织，则必须为每个本组织提供单独的邓氏 (DUNS) 编码，以标识其唯一身份。 邓氏 (DUNS) 编码是定义 RosettaNet 连接的编码。  
  
 本组织说明中的设置如下表所示，其排列顺序按选项卡进行。有关如何创建和编辑本组织的说明，请参阅表后面的步骤。  
  
|选项卡|设置|用法|  
|---------|-------------|-----------|  
|**常规**|**名称**|本组织的名称。<br /><br /> 必填字段。<br /><br /> 最大长度： 255|  
|**常规**|**GBI**|本组织的全局业务标识符。 该值的长度必须为 9 位，而且必须与邓氏 (DUNS) 编码相对应。<br /><br /> 必填字段。|  
|**常规**|**Description**|帮助确定本组织身份的说明。|  
|**常规**|**本组织分类**|组织的性质。<br /><br /> 可以是**最终用户**，**最终用户政府**，**金融家**，**制造商**，**零售商**， **购物者**，**运费转发器**，或**Marketplace**。<br /><br /> 可以在消息的服务头中为本组织分类输入其他值，覆盖此属性，方法是，在协议的“自定义属性”选项卡中输入 HPCC 自定义属性。 有关详细信息，请参阅[创建或编辑协议](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)。|  
|**联系人属性**|**联系人姓名**|本组织联系人的姓名。<br /><br /> 必填字段。|  
|**联系人属性**|**电子邮件地址**|本组织联系人的电子邮件地址。<br /><br /> 必填字段。|  
|**联系人属性**|**电话号码**|本组织联系人的电话号码。<br /><br /> 必填字段。|  
|**联系人属性**|**传真号码**|本组织联系人的传真号码。<br /><br /> 必填字段。|  
|**联系人属性**|**供应链代码**|本组织的供应链代码。<br /><br /> 必填字段。|  
  
### <a name="to-create-a-home-organization-definition"></a>创建本组织定义  
  
1.  单击**启动**，指向**所有程序**，指向**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，然后单击[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理控制台**.  
  
2.  在 BTARN 管理控制台中，展开 [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]。  
  
3.  右键单击**主页组织**，指向**新建**，然后单击**主页组织**。  
  
4.  在新主页组织属性对话框中，在**常规**和**联系人属性**选项卡上，输入设置的值。 有关这些设置的信息，请参阅上表。  
  
5.  单击 **“确定”**。  
  
### <a name="to-edit-a-home-organization"></a>编辑本组织  
  
1.  单击**启动**，指向**所有程序**，指向**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，然后单击[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理控制台**.  
  
2.  在 BTARN 管理控制台中，展开 [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]。  
  
3.  单击**主页组织**。  
  
4.  右键单击你想要编辑，然后单击该主组织**属性**。  
  
5.  在*\<主页组织 >*属性对话框中，在**常规**和**联系人属性**选项卡上，根据需要更改设置。 有关这些设置的信息，请参阅上表。  
  
6.  单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [管理配置、 证书、 数据库和安全](manage-configuration-certificates-databases-security.md)   
 [管理 BTARN 配置](../../adapters-and-accelerators/accelerator-rosettanet/administering-the-btarn-configuration.md)