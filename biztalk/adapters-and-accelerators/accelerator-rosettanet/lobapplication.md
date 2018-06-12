---
title: LOBApplication |Microsoft 文档
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
ms.openlocfilehash: 7bacce1a64f59d61b5175b10fc14cde1ca862635
ms.sourcegitcommit: 436ebffd959a9c4bdaafd4da9a5843c59a018eb7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2018
ms.locfileid: "34855528"
---
# <a name="lobapplication"></a>LOBApplication
使用 LOBApplication 实用工具可以将操作或响应消息提交给贸易合作伙伴，并模拟实际的业务线 (LOB) 桌面程序。  
  
 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]提供中的示例消息\<*驱动器*\>\Program Files (x86) \Microsoft BizTalk\<版本\>RosettaNet\SDK\LOBApplication\ 快捷键SampleInstances 文件夹。  
  
## <a name="location-in-sdk"></a>在 SDK 中的位置  
 \<*驱动器*\>\Program Files (x86) \Microsoft BizTalk\<版本\>RosettaNet\SDK\LOBApplication 快捷键  
  
## <a name="running-lobapplication"></a>运行 LOBApplication  
  
#### <a name="to-run-lobapplication"></a>若要运行 LOBApplication  
  
1.  在 Windows 资源管理器，移动到\<*驱动器*\>\Program Files (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\\。  
  
2.  双击**LOBApplication.exe**，然后按 ENTER。  
  
     之后显示的页将提示你输入运行该实用工具所需的信息。  
  
## <a name="syntax-for-lobapplication"></a>LOBApplication 的语法  
 使用**LOB 应用程序代理**页后，可以指定主页和合作伙伴名称、 合作伙伴接口过程 (PIP) 属性和 LOBApplication 实用程序发送的消息的消息属性。  
  
 下表介绍如何使用每个字段上**LOB 应用程序代理**页。  
  
|使用此选项|执行的操作|  
|--------------|----------------|  
|**主配置文件名称**|键入本组织的名称（源参与方）。|  
|**贸易合作伙伴名称**|键入贸易合作伙伴的名称（目标参与方）。|  
|**PIP 名称**|键入 PIP，例如，类型的显示代码**3A2**。 此值区分大小写。|  
|**PIP 版本**|键入的 PIP，例如，类型版本**V02.00**。 此值区分大小写。|  
|**PIP 实例 ID** （可选）|键入的字母数字的实例 ID PIP，例如，键入**STD_3A2_V02.02**。 不要使用特殊字符。 该 ID 对于每个合作伙伴和每个 PIP 代码应是唯一的。 对于标记为操作消息的消息，如果实例 ID 为空，则 LOBApplication 实用工具将使用生成的 HUID 值作为 PIP 实例 ID。 **注意：** 选中**响应**中**消息类别**，必须在此字段中键入 PIP 实例 ID。|  
|**文件名**|单击省略号按钮 (...)，转到包含 PIP 实例文件的文件夹，然后单击该 PIP 实例文件。|  
|**消息类别**|选择消息的类型 (**操作**或**响应**)。|  
|**Attachments**|单击**添加**，将移动到包含附件文件的文件夹，然后单击**打开**。|  
|**提交消息**|单击以发送消息。|  
|**“状态”**|在此字段中读取操作的状态。|  
  
## <a name="remarks"></a>Remarks  
 LOBApplication 实用工具创建具有指定属性的消息，并将其发送给贸易合作伙伴。 此实用工具将消息中的服务内容数据写入到 BTARNDATA 数据库的 MessageFromLOB 表中。 此实用工具模拟发送操作消息的过程。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK 的 LOBApplication 文件夹下的 SampleInstances 文件夹中提供了示例消息，这些消息根据以下假定进行了预配置：假定全局业务标识符 (GBI) 为 123456789（用于本组织）和 987654321（对于合作伙伴组织）。 若要使用其他 GBI，则必须在文本编辑器中更改示例消息。  
  
 使用 LOBApplication 实用工具可以模拟业务线桌面程序提交消息的过程。 使用 LOBWebApplication 实用工具还可以模拟业务线 Web 应用程序提交消息的过程。  
  
## <a name="see-also"></a>请参阅  
 [实用程序](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)   
 [LOBWebApplication](../../adapters-and-accelerators/accelerator-rosettanet/lobwebapplication.md)
