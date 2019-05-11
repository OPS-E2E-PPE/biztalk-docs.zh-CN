---
title: 创建或编辑本组织 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- home organizations, about home organizations
- home organizations, modifying
- creating, home organizations
- modifying, home organizations
- home organizations
- home organizations, creating
ms.assetid: b54afb84-2f16-4516-8701-b03301476362
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3d35008b2dcb579ff412af4a6d067da3c9b3959
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284308"
---
# <a name="creating-or-editing-a-home-organization"></a>创建或编辑本组织
本主题介绍如何创建或编辑本组织。 本组织配置描述和分类组织，设置不可否认性，原始时间段，并提供联系人信息。  
  
 本组织配置不包括签名，并与合作伙伴配置执行解密证书。 在 microsoft BizTalk 组配置签名证书[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 在中配置的 BizTalk 主机 （BizTalkServerApplication 和 BizTalkIsolatedHost） 的解密证书[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
 您可以创建两个本组织中的单个公司或部署。 出现这种可能想要创建的消息的优先级处理的实例，在哪些消息绑定的一个组织时，会优先于绑定的另一个消息。 在创建多个本组织时，必须提供单独的邓氏编号，以唯一标识其每个本组织。 Duns 是定义 RosettaNet 连接的内容。  
  
 本组织说明中的设置是下表中，按选项卡中所示。有关如何创建和编辑本组织，请参阅表后面的过程的说明。  
  
|Tab|设置|用法|  
|---------|-------------|-----------|  
|**常规**|**名称**|本组织名称。<br /><br /> 必填的字段。<br /><br /> 最大长度：255|  
|**常规**|**GBI**|本组织全局业务标识符。 这必须是九个数字的长度，并且必须与邓氏号相对应。<br /><br /> 必填的字段。|  
|**常规**|**说明**|有助于确定本组织说明。|  
|**常规**|**本组织分类**|组织的性质。<br /><br /> 可以是**最终用户**，**最终用户政府**，**金融家**，**制造商**，**零售商**， **购物者**，**货物转发器**，或**Marketplace**。<br /><br /> 为本组织分类的服务头中的一条消息，可以输入其他值覆盖此属性，通过该协议的自定义属性选项卡中输入 HPCC 自定义属性。 有关详细信息，请参阅[创建或编辑协议](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)。|  
|**联系人属性**|**联系人姓名**|在本组织联系人的名称。<br /><br /> 必填的字段。|  
|**联系人属性**|**电子邮件地址**|在本组织联系人的电子邮件地址。<br /><br /> 必填的字段。|  
|**联系人属性**|**电话号码**|在本组织联系人的电话号码。<br /><br /> 必填的字段。|  
|**联系人属性**|**传真号码**|在本组织联系人的传真号码。<br /><br /> 必填的字段。|  
|**联系人属性**|**供应链代码**|本组织供应链代码。<br /><br /> 必填的字段。|  
  
### <a name="to-create-a-home-organization-definition"></a>若要创建本组织定义  
  
1. 单击**启动**，依次指向**所有程序**，指向**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，然后单击[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理控制台**.  
  
2. 在 BTARN 管理控制台中，展开[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]。  
  
3. 右键单击**本组织**，依次指向**新建**，然后单击**本组织**。  
  
4. 在新本组织属性对话框中，在**常规**并**联系人属性**选项卡上，为设置输入值。 有关这些设置的信息，请参阅上表。  
  
5. 单击“确定” 。  
  
### <a name="to-edit-a-home-organization"></a>若要编辑本组织  
  
1. 单击**启动**，依次指向**所有程序**，指向**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，然后单击[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理控制台**.  
  
2. 在 BTARN 管理控制台中，展开[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]。  
  
3. 单击**Home 组织**。  
  
4. 右键单击你想要编辑，然后单击本组织**属性**。  
  
5. 在中*\<本组织\>* 属性对话框中，在**常规**并**联系人属性**选项卡上，根据需要更改设置。 有关这些设置的信息，请参阅上表。  
  
6. 单击“确定” 。  
  
## <a name="see-also"></a>请参阅  
 [管理配置、 证书、 数据库和安全](manage-configuration-certificates-databases-security.md)   
 [管理 BTARN 配置](../../adapters-and-accelerators/accelerator-rosettanet/administering-the-btarn-configuration.md)