---
title: 创建或编辑合作伙伴 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, trading partners
- trading partners
- modifying, trading partners
- trading partners, creating
- trading partners, modifying
- trading partners, about trading partners
ms.assetid: 63809035-65a5-472d-b2e5-359c8e9d9d8c
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6e5f8c666de367860ad4243be444cecac6fa8bf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012662"
---
# <a name="creating-or-editing-a-partner"></a>创建或编辑合作伙伴
本主题介绍如何创建或编辑合作伙伴。 合作伙伴配置描述和合作伙伴将分为两类、 设置不可否认性，原始时间段、 配置证书对于合作伙伴，并提供联系信息。  

 当你首次创建合作伙伴，Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]创建两个发送端口以供该合作伙伴，一个异步和一个同步。 这些发送端口分别称为\<*合作伙伴名称*\>。异步发送端口并\<*合作伙伴名称*\>。同步的发送端口。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 自动登记并启动这些发送端口基于合作伙伴协议。 您可以在 BizTalk 管理控制台中查看这些端口。  

 合作伙伴设置是下表中，按选项卡中所示。有关如何创建和编辑合作伙伴，请参阅表后面的过程的说明。  


|                            选项卡                             |            设置            |                                                                                                                                                                                                                                                                                                                                                                                    用法                                                                                                                                                                                                                                                                                                                                                                                    |
|------------------------------------------------------------|-------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                        **常规**                         |           **名称**            |                                                                                                                                                                                                                                                                                                                                        贸易合作伙伴的名称。<br /><br /> 必填字段。<br /><br /> 最大长度： 255                                                                                                                                                                                                                                                                                                                                        |
|                        **常规**                         |            **GBI**            |                                                                                                                                                                                                                                                                                                             合作伙伴全局业务标识符。 这必须为 9 位长，并且必须对应于 duns。<br /><br /> 必填字段。                                                                                                                                                                                                                                                                                                              |
|                        **常规**                         |        **Description**        |                                                                                                                                                                                                                                                                                                                                                                 用于标识合作伙伴的说明。                                                                                                                                                                                                                                                                                                                                                                  |
|                        **常规**                         |        **保留到**         |                                                                                       在其上的日期[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]将消息提交到 MessagesFromLOB 表。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将不会传递此消息，直到**保留到**日期。 合作伙伴必须同意此日期后，根据接收方将准备好接收消息。 此设置可能会很有用，如果合作伙伴将不可用来处理消息，例如，在节假日期间。<br /><br /> 默认值是当前日期。                                                                                       |
|                        **常规**                         |  **合作伙伴分类**   |            合作伙伴组织的类型。<br /><br /> 可以是**承运人**（默认值），**分发服务器**，**最终用户**，**最终用户政府**，**金融家**，**制造商**，**零售商**，或**购物者**。<br /><br /> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将此字段的值包括在服务头中。<br /><br /> 为合作伙伴分类的服务头中的一条消息，可以输入其他值覆盖此属性，通过该协议的自定义属性选项卡中输入 PPCC 自定义属性。 有关详细信息，请参阅[创建或编辑协议](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)。            |
|                        **常规**                         | **不可否认性的源** | 天数[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]在 MessageStorageIn 或 MessageStorageOut 不可否认性 （以便合法地证明它已收到） 数据库中将保存消息的传输格式。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 每个传入或传出消息上标记此日期。<br /><br /> 默认值为 2485 天。<br /><br /> 但是，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]不会从这段时间到期后的数据库中删除一条消息。 如果你想要删除这些消息，开发的 SQL 脚本来删除旧基于此日期/时间戳的消息。 |
| **常规**<br /><br /> (**公钥证书**区域) |         **签名**         |                                                                                                                                                     公钥证书[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]将用于验证传入消息的合作伙伴的签名。 此证书必须存储在 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理控制台的证书（本地计算机）节点中的“其他人”证书存储区中。<br /><br /> 默认值是\<none\>。                                                                                                                                                     |
| **常规**<br /><br /> (**公钥证书**区域) |        **加密**         |                                                                                                                                                       公钥加密证书[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]将用于加密发送给合作伙伴的传出消息。 此证书必须存储在 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理控制台的证书（本地计算机）节点中的“其他人”证书存储区中。<br /><br /> 默认值是\<none\>。                                                                                                                                                       |
|                   **联系人属性**                   |       **联系人姓名**        |                                                                                                                                                                                                                                                                                                                                                     合作伙伴联系人的名称。<br /><br /> 必填字段。                                                                                                                                                                                                                                                                                                                                                     |
|                   **联系人属性**                   |      **电子邮件地址**       |                                                                                                                                                                                                                                                                                                                                                合作伙伴联系人电子邮件地址。<br /><br /> 必填字段。                                                                                                                                                                                                                                                                                                                                                |
|                   **联系人属性**                   |     **电话号码**      |                                                                                                                                                                                                                                                                                                                                              合作伙伴联系人的电话号码。<br /><br /> 必填字段。                                                                                                                                                                                                                                                                                                                                               |
|                   **联系人属性**                   |        **传真号码**         |                                                                                                                                                                                                                                                                                                                                                 合作伙伴联系人的传真号码。<br /><br /> 必填字段。                                                                                                                                                                                                                                                                                                                                                  |
|                   **联系人属性**                   |     **供应链代码**     |                                                                                                                                                                                                                                                                                                                    合作伙伴供应链代码。 例如，"信息技术"或者"电子组件"。<br /><br /> 必填字段。                                                                                                                                                                                                                                                                                                                     |

### <a name="to-create-a-partner"></a>创建合作伙伴  

1. 单击**启动**，依次指向**所有程序**，指向**Microsoft**[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，然后单击[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理控制台**.  

2. 在 BTARN 管理控制台中，展开 [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]。  

3. 右键单击**合作伙伴**，依次指向**新建**，然后单击**合作伙伴**。  

4. 在中**新合作伙伴属性**对话框中，在**常规**并**联系人属性**选项卡，设置的类型值。 有关这些设置的信息，请参阅上表。  

5. 单击“确定” 。  

### <a name="to-edit-a-partner"></a>若要编辑合作伙伴  

1. 单击**启动**，依次指向**所有程序**，指向**Microsoft**[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，然后单击[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理控制台**.  

2. 在 BTARN 管理控制台中，展开[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，然后单击**合作伙伴**。  

3. 右键单击你想要编辑，然后单击伙伴**属性**。  

4. 在中**\<**<em>合作伙伴</em>**\>** 属性对话框中，在**常规**和**联系人属性**选项卡上，根据需要更改设置。 有关这些设置的信息，请参阅上表。  

5. 单击“确定” 。  

## <a name="see-also"></a>请参阅  
 [管理配置、 证书、 数据库和安全](manage-configuration-certificates-databases-security.md)   
 [管理 BTARN 配置](../../adapters-and-accelerators/accelerator-rosettanet/administering-the-btarn-configuration.md)