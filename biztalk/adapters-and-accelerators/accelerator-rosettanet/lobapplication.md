---
title: LOBApplication | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- trading partners, submitting actions
- LOBs, submitting actions
- LOBApplication utility
- trading partners, response messages
- LOBs, LOBApplication utility
- LOBs, response messages
ms.assetid: ad5986af-4175-49cd-806b-04e1fde63f55
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3f65980015d689cd79f1d006441c1687d15be01
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283327"
---
# <a name="lobapplication"></a>LOBApplication
使用 LOBApplication 实用工具提交给贸易合作伙伴，模拟实际的业务线 (LOB) 桌面程序的操作或响应消息。  
  
 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]提供了示例消息中的\<*驱动器*\>\Program 文件 (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances 文件夹。  
  
## <a name="location-in-sdk"></a>在 SDK 中的位置  
 \<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBApplication  
  
## <a name="running-lobapplication"></a>运行 LOBApplication  
  
#### <a name="to-run-lobapplication"></a>若要运行 LOBApplication  
  
1.  在 Windows 资源管理器，转至\<*驱动器*\>\Program 文件 (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\\。  
  
2.  双击**LOBApplication.exe**，然后按 ENTER。  
  
     向导中的页面将提示你输入是运行该实用程序所必需的信息。  
  
## <a name="syntax-for-lobapplication"></a>LOBApplication 的语法  
 使用**LOB 应用程序代理**页后，可以指定与合作伙伴的名称、 合作伙伴接口流程 (PIP) 属性和 LOBApplication 实用工具发送的消息的消息属性。  
  
 下表介绍了如何使用每个字段**LOB 应用程序代理**页。  
  
|使用此选项|执行的操作|  
|--------------|----------------|  
|**本组织配置文件名称**|键入本组织 （源参与方） 的名称。|  
|**贸易合作伙伴名称**|键入贸易合作伙伴 （目标参与方） 的名称。|  
|**PIP 名称**|键入 PIP，例如，类型的显示代码**3A2**。 此值区分大小写。|  
|**PIP 版本**|键入 PIP 的版本，例如，类型**V02.00**。 此值区分大小写。|  
|**PIP 实例 ID** （可选）|键入的字母数字实例 ID 对于 PIP，例如，键入**STD_3A2_V02.02**。 不要使用特殊字符。 ID 应为每个合作伙伴和每个 PIP 代码唯一。 对于标记为操作消息，如果实例 ID 是空的消息，LOBApplication 实用工具用于生成的 HUID 值 PIP 实例 id。 **注意：** 当选择**响应**中**消息类别**，必须在此字段中键入 PIP 实例 ID。|  
|**文件名**|单击省略号按钮 （...），转到包含 PIP 实例文件的文件夹，然后单击 PIP 实例文件。|  
|**消息类别**|选择消息类型 (**操作**或**响应**)。|  
|**Attachments**|单击**外**，转到包含附件文件的文件夹，然后单击**打开**。|  
|**提交消息**|单击此项可将消息发送。|  
|**“状态”**|阅读此字段中的操作的状态。|  
  
## <a name="remarks"></a>备注  
 LOBApplication 实用工具创建具有指定的属性的消息，并将其发送给贸易合作伙伴。 此实用程序将消息中的服务内容数据写入到 BTARNDATA 数据库的 MessageFromLOB 表中。 此实用工具模拟发送操作消息。  
  
 中的 LOBApplication 文件夹下的 SampleInstances 文件夹中的示例消息[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]SDK 已预先配置为假定以下全局业务标识符 (Gbi):本组织和合作伙伴组织为 987654321 123456789。 必须更改文本编辑器中的示例消息，以使用其他 Gbi。  
  
 使用 LOBApplication 实用工具来模拟业务线桌面程序提交消息。 使用 LOBWebApplication 实用工具来模拟业务线 Web 应用程序提交一条消息。  
  
## <a name="see-also"></a>请参阅  
 [实用程序](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)   
 [LOBWebApplication](../../adapters-and-accelerators/accelerator-rosettanet/lobwebapplication.md)
